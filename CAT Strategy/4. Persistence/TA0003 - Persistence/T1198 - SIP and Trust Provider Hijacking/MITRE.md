<div class="container-fluid">
 <h1>
  SIP and Trust Provider Hijacking
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    In user mode, Windows Authenticode
    <span class="scite-citeref-number" data-reference="Microsoft Authenticode" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://msdn.microsoft.com/library/ms537359.aspx" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    digital signatures are used to verify a file's origin and integrity, variables that may be used to establish trust in signed code (ex: a driver with a valid Microsoft signature may be handled as safe). The signature validation process is handled via the WinVerifyTrust application programming interface (API) function,
    <span class="scite-citeref-number" data-reference="Microsoft WinVerifyTrust" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://msdn.microsoft.com/library/windows/desktop/aa388208.aspx" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    which accepts an inquiry and coordinates with the appropriate trust provider, which is responsible for validating parameters of a signature.
    <span class="scite-citeref-number" data-reference="SpectorOps Subverting Trust Sept 2017" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://specterops.io/assets/resources/SpecterOps_Subverting_Trust_in_Windows.pdf" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Because of the varying executable file types and corresponding signature formats, Microsoft created software components called Subject Interface Packages (SIPs)
    <span class="scite-citeref-number" data-reference="EduardosBlog SIPs July 2008" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://blogs.technet.microsoft.com/eduardonavarro/2008/07/11/sips-subject-interface-package-and-authenticode/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    to provide a layer of abstraction between API functions and files. SIPs are responsible for enabling API functions to create, retrieve, calculate, and verify signatures. Unique SIPs exist for most file formats (Executable, PowerShell, Installer, etc., with catalog signing providing a catch-all
    <span class="scite-citeref-number" data-reference="Microsoft Catalog Files and Signatures April 2017" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://docs.microsoft.com/windows-hardware/drivers/install/catalog-files" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    ) and are identified by globally unique identifiers (GUIDs).
    <span class="scite-citeref-number" data-reference="SpectorOps Subverting Trust Sept 2017" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://specterops.io/assets/resources/SpecterOps_Subverting_Trust_in_Windows.pdf" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Similar to
    <a href="https://attack.mitre.org/techniques/T1116">
     Code Signing
    </a>
    , adversaries may abuse this architecture to subvert trust controls and bypass security policies that allow only legitimately signed code to execute on a system. Adversaries may hijack SIP and trust provider components to mislead operating system and whitelisting tools to classify malicious (or any) code as signed by:
    <span class="scite-citeref-number" data-reference="SpectorOps Subverting Trust Sept 2017" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://specterops.io/assets/resources/SpecterOps_Subverting_Trust_in_Windows.pdf" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <ul>
    <li>
     Modifying the
     <code>
      Dll
     </code>
     and
     <code>
      FuncName
     </code>
     Registry values in
     <code>
      HKLM\SOFTWARE[\WOW6432Node]Microsoft\Cryptography\OID\EncodingType 0\CryptSIPDllGetSignedDataMsg{SIP_GUID}
     </code>
     that point to the dynamic link library (DLL) providing a SIP’s CryptSIPDllGetSignedDataMsg function, which retrieves an encoded digital certificate from a signed file. By pointing to a maliciously-crafted DLL with an exported function that always returns a known good signature value (ex: a Microsoft signature for Portable Executables) rather than the file’s real signature, an adversary can apply an acceptable signature value all files using that SIP
     <span class="scite-citeref-number" data-reference="GitHub SIP POC Sept 2017" id="scite-ref-6-a">
      <sup>
       <a aria-describedby="qtip-5" data-hasqtip="5" href="https://github.com/mattifestation/PoCSubjectInterfacePackage" target="_blank">
        [6]
       </a>
      </sup>
     </span>
     (although a hash mismatch will likely occur, invalidating the signature, since the hash returned by the function will not match the value computed from the file).
    </li>
    <li>
     Modifying the
     <code>
      Dll
     </code>
     and
     <code>
      FuncName
     </code>
     Registry values in
     <code>
      HKLM\SOFTWARE[WOW6432Node]Microsoft\Cryptography\OID\EncodingType 0\CryptSIPDllVerifyIndirectData{SIP_GUID}
     </code>
     that point to the DLL providing a SIP’s CryptSIPDllVerifyIndirectData function, which validates a file’s computed hash against the signed hash value. By pointing to a maliciously-crafted DLL with an exported function that always returns TRUE (indicating that the validation was successful), an adversary can successfully validate any file (with a legitimate signature) using that SIP
     <span class="scite-citeref-number" data-reference="GitHub SIP POC Sept 2017" id="scite-ref-6-a">
      <sup>
       <a aria-describedby="qtip-5" data-hasqtip="5" href="https://github.com/mattifestation/PoCSubjectInterfacePackage" target="_blank">
        [6]
       </a>
      </sup>
     </span>
     (with or without hijacking the previously mentioned CryptSIPDllGetSignedDataMsg function). This Registry value could also be redirected to a suitable exported function from an already present DLL, avoiding the requirement to drop and execute a new file on disk.
    </li>
    <li>
     Modifying the
     <code>
      DLL
     </code>
     and
     <code>
      Function
     </code>
     Registry values in
     <code>
      HKLM\SOFTWARE[WOW6432Node]Microsoft\Cryptography\Providers\Trust\FinalPolicy{trust provider GUID}
     </code>
     that point to the DLL providing a trust provider’s FinalPolicy function, which is where the decoded and parsed signature is checked and the majority of trust decisions are made. Similar to hijacking SIP’s CryptSIPDllVerifyIndirectData function, this value can be redirected to a suitable exported function from an already present DLL or a maliciously-crafted DLL (though the implementation of a trust provider is complex).
    </li>
    <li>
     <strong>
      Note:
     </strong>
     The above hijacks are also possible without modifying the Registry via
     <a href="https://attack.mitre.org/techniques/T1038">
      DLL Search Order Hijacking
     </a>
     .
    </li>
   </ul>
   <p>
    Hijacking SIP or trust provider components can also enable persistent code execution, since these malicious components may be invoked by any application that performs code signing or signature validation.
    <span class="scite-citeref-number" data-reference="SpectorOps Subverting Trust Sept 2017" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://specterops.io/assets/resources/SpecterOps_Subverting_Trust_in_Windows.pdf" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1198
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Tactic
      </span>
      : Defense Evasion, Persistence
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Platform:
      </span>
      Windows
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Permissions Required:
      </span>
      Administrator, SYSTEM
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      API monitoring, Application logs, DLL monitoring, Loaded DLLs, Process monitoring, Windows Registry, Windows event logs
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Defense Bypassed:
      </span>
      Application whitelisting, Autoruns Analysis, Digital Certificate Validation, Process whitelisting, User Mode Signature Validation
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Contributors:
      </span>
      Matt Graeber, @mattifestation, SpecterOps
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Version
      </span>
      : 1.0
     </div>
    </div>
   </div>
  </div>
 </div>
 <h2 class="pt-3" id="mitigation">
  Mitigation
 </h2>
 <p>
  Ensure proper permissions are set for Registry hives to prevent users from modifying keys related to SIP and trust provider components. Also ensure that these values contain their full path to prevent
  <a href="https://attack.mitre.org/techniques/T1038">
   DLL Search Order Hijacking
  </a>
  .
  <span class="scite-citeref-number" data-reference="SpectorOps Subverting Trust Sept 2017" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="https://specterops.io/assets/resources/SpecterOps_Subverting_Trust_in_Windows.pdf" target="_blank">
     [3]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Consider removing unnecessary and/or stale SIPs.
  <span class="scite-citeref-number" data-reference="SpectorOps Subverting Trust Sept 2017" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="https://specterops.io/assets/resources/SpecterOps_Subverting_Trust_in_Windows.pdf" target="_blank">
     [3]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Restrict storage and execution of SIP DLLs to protected directories, such as C:\Windows, rather than user directories.
 </p>
 <p>
  Enable whitelisting solutions such as AppLocker and/or Device Guard to block the loading of malicious SIP DLLs. Components may still be able to be hijacked to suitable functions already present on disk if malicious modifications to Registry keys are not prevented.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Periodically baseline registered SIPs and trust providers (Registry entries and files on disk), specifically looking for new, modified, or non-Microsoft entries.
  <span class="scite-citeref-number" data-reference="SpectorOps Subverting Trust Sept 2017" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="https://specterops.io/assets/resources/SpecterOps_Subverting_Trust_in_Windows.pdf" target="_blank">
     [3]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Enable CryptoAPI v2 (CAPI) event logging
  <span class="scite-citeref-number" data-reference="Entrust Enable CAPI2 Aug 2017" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="http://www.entrust.net/knowledge-base/technote.cfm?tn=8165" target="_blank">
     [7]
    </a>
   </sup>
  </span>
  to monitor and analyze error events related to failed trust validation (Event ID 81, though this event can be subverted by hijacked trust provider components) as well as any other provided information events (ex: successful validations). Code Integrity event logging may also provide valuable indicators of malicious SIP or trust provider loads, since protected processes that attempt to load a maliciously-crafted trust validation component will likely fail (Event ID 3033).
  <span class="scite-citeref-number" data-reference="SpectorOps Subverting Trust Sept 2017" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="https://specterops.io/assets/resources/SpecterOps_Subverting_Trust_in_Windows.pdf" target="_blank">
     [3]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Utilize Sysmon detection rules and/or enable the Registry (Global Object Access Auditing)
  <span class="scite-citeref-number" data-reference="Microsoft Registry Auditing Aug 2016" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn311461(v=ws.11)" target="_blank">
     [8]
    </a>
   </sup>
  </span>
  setting in the Advanced Security Audit policy to apply a global system access control list (SACL) and event auditing on modifications to Registry values (sub)keys related to SIPs and trust providers:
  <span class="scite-citeref-number" data-reference="Microsoft Audit Registry July 2012" id="scite-ref-9-a">
   <sup>
    <a aria-describedby="qtip-8" data-hasqtip="8" href="https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd941614(v=ws.10)" target="_blank">
     [9]
    </a>
   </sup>
  </span>
 </p>
 <ul>
  <li>
   HKLM\SOFTWARE\Microsoft\Cryptography\OID
  </li>
  <li>
   HKLM\SOFTWARE\WOW6432Node\Microsoft\Cryptography\OID
  </li>
  <li>
   HKLM\SOFTWARE\Microsoft\Cryptography\Providers\Trust
  </li>
  <li>
   HKLM\SOFTWARE\WOW6432Node\Microsoft\Cryptography\Providers\Trust
  </li>
 </ul>
 <p>
  <strong>
   Note:
  </strong>
  As part of this technique, adversaries may attempt to manually edit these Registry keys (ex: Regedit) or utilize the legitimate registration process using
  <a href="https://attack.mitre.org/techniques/T1117">
   Regsvr32
  </a>
  .
  <span class="scite-citeref-number" data-reference="SpectorOps Subverting Trust Sept 2017" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="https://specterops.io/assets/resources/SpecterOps_Subverting_Trust_in_Windows.pdf" target="_blank">
     [3]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Analyze Autoruns data for oddities and anomalies, specifically malicious files attempting persistent execution by hiding within auto-starting locations. Autoruns will hide entries signed by Microsoft or Windows by default, so ensure "Hide Microsoft Entries" and "Hide Windows Entries" are both deselected.
  <span class="scite-citeref-number" data-reference="SpectorOps Subverting Trust Sept 2017" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="https://specterops.io/assets/resources/SpecterOps_Subverting_Trust_in_Windows.pdf" target="_blank">
     [3]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="references">
  References
 </h2>
 <div class="row">
  <div class="col">
   <ol>
    <li>
     <span class="scite-citation" id="scite-1">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/ms537359.aspx" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Authenticode. Retrieved January 31, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/windows/desktop/aa388208.aspx" name="scite-2" rel="nofollow" target="_blank">
        Microsoft. (n.d.). WinVerifyTrust function. Retrieved January 31, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://specterops.io/assets/resources/SpecterOps_Subverting_Trust_in_Windows.pdf" name="scite-3" rel="nofollow" target="_blank">
        Graeber, M. (2017, September). Subverting Trust in Windows. Retrieved January 31, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://blogs.technet.microsoft.com/eduardonavarro/2008/07/11/sips-subject-interface-package-and-authenticode/" name="scite-4" rel="nofollow" target="_blank">
        Navarro, E. (2008, July 11). SIP’s (Subject Interface Package) and Authenticode. Retrieved January 31, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/windows-hardware/drivers/install/catalog-files" name="scite-5" rel="nofollow" target="_blank">
        Hudek, T. (2017, April 20). Catalog Files and Digital Signatures. Retrieved January 31, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="6.5">
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/mattifestation/PoCSubjectInterfacePackage" name="scite-6" rel="nofollow" target="_blank">
        Graeber, M. (2017, September 14). PoCSubjectInterfacePackage. Retrieved January 31, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.entrust.net/knowledge-base/technote.cfm?tn=8165" name="scite-7" rel="nofollow" target="_blank">
        Entrust Datacard. (2017, August 16). How do I enable CAPI 2.0 logging in Windows Vista, Windows 7 and Windows 2008 Server?. Retrieved January 31, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn311461(v=ws.11)" name="scite-8" rel="nofollow" target="_blank">
        Microsoft. (2016, August 31). Registry (Global Object Access Auditing). Retrieved January 31, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd941614(v=ws.10)" name="scite-9" rel="nofollow" target="_blank">
        Microsoft. (2012, July 2). Audit Registry. Retrieved January 31, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
