<div class="container-fluid">
 <h1>
  LSASS Driver
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    The Windows security subsystem is a set of components that manage and enforce the security policy for a computer or domain. The Local Security Authority (LSA) is the main component responsible for local security policy and user authentication. The LSA includes multiple dynamic link libraries (DLLs) associated with various other security functions, all of which run in the context of the LSA Subsystem Service (LSASS) lsass.exe process.
    <span class="scite-citeref-number" data-reference="Microsoft Security Subsystem" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://technet.microsoft.com/library/cc961760.aspx" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries may target lsass.exe drivers to obtain execution and/or persistence. By either replacing or adding illegitimate drivers (e.g.,
    <a href="https://attack.mitre.org/techniques/T1073">
     DLL Side-Loading
    </a>
    or
    <a href="https://attack.mitre.org/techniques/T1038">
     DLL Search Order Hijacking
    </a>
    ), an adversary can achieve arbitrary code execution triggered by continuous LSA operations.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1177
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
      : Execution, Persistence
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
      API monitoring, DLL monitoring, File monitoring, Kernel drivers, Loaded DLLs, Process monitoring
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Supports Remote:
      </span>
      No
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
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Contributors:
      </span>
      Vincent Le Toux
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
 <h2 class="pt-3" id="examples">
  Examples
 </h2>
 <table class="table table-bordered table-light mt-2">
  <thead>
   <tr>
    <th scope="col">
     Name
    </th>
    <th scope="col">
     Description
    </th>
   </tr>
  </thead>
  <tbody class="bg-white">
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0208">
      Pasam
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0208">
       Pasam
      </a>
      establishes by infecting the Security Accounts Manager (SAM) DLL to load a malicious DLL dropped to disk.
      <span class="scite-citeref-number" data-reference="Symantec Pasam May 2012" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-050412-4128-99" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0176">
      Wingbird
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0176">
       Wingbird
      </a>
      drops a malicious file (sspisrv.dll) alongside a copy of lsass.exe, which is used to register a service that loads sspisrv.dll as a driver. The payload of the malicious driver (located in its entry-point function) is executed when loaded by lsass.exe before the spoofed service becomes unstable and crashes.
      <span class="scite-citeref-number" data-reference="Microsoft SIR Vol 21" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="http://download.microsoft.com/download/E/B/0/EB0F50CC-989C-4B66-B7F6-68CD3DC90DE3/Microsoft_Security_Intelligence_Report_Volume_21_English.pdf" target="_blank">
         [3]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Microsoft Wingbird Nov 2017" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.microsoft.com/wdsi/threats/malware-encyclopedia-description?Name=Backdoor:Win32/Wingbird.A!dha" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
  </tbody>
 </table>
 <h2 class="pt-3" id="mitigation">
  Mitigation
 </h2>
 <p>
  On Windows 8.1 and Server 2012 R2, enable LSA Protection by setting the Registry key
  <code>
   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Lsa\RunAsPPL
  </code>
  to
  <code>
   dword:00000001
  </code>
  .
  <span class="scite-citeref-number" data-reference="Microsoft LSA Protection Mar 2014" id="scite-ref-5-a">
   <sup>
    <a aria-describedby="qtip-4" data-hasqtip="4" href="https://technet.microsoft.com/library/dn408187.aspx" target="_blank">
     [5]
    </a>
   </sup>
  </span>
  LSA Protection ensures that LSA plug-ins and drivers are only loaded if they are digitally signed with a Microsoft signature and adhere to the Microsoft Security Development Lifecycle (SDL) process guidance.
 </p>
 <p>
  On Windows 10 and Server 2016, enable Windows Defender Credential Guard
  <span class="scite-citeref-number" data-reference="Microsoft Enable Cred Guard April 2017" id="scite-ref-6-a">
   <sup>
    <a aria-describedby="qtip-5" data-hasqtip="5" href="https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard-manage" target="_blank">
     [6]
    </a>
   </sup>
  </span>
  to run lsass.exe in an isolated virtualized environment without any device drivers.
  <span class="scite-citeref-number" data-reference="Microsoft Credential Guard April 2017" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard-how-it-works" target="_blank">
     [7]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Ensure safe DLL search mode is enabled
  <code>
   HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Session Manager\SafeDllSearchMode
  </code>
  to mitigate risk that lsass.exe loads a malicious code library.
  <span class="scite-citeref-number" data-reference="Microsoft DLL Security" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="https://msdn.microsoft.com/library/windows/desktop/ff919712.aspx" target="_blank">
     [8]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  With LSA Protection enabled, monitor the event logs (Events 3033 and 3063) for failed attempts to load LSA plug-ins and drivers.
  <span class="scite-citeref-number" data-reference="Microsoft LSA Protection Mar 2014" id="scite-ref-5-a">
   <sup>
    <a aria-describedby="qtip-4" data-hasqtip="4" href="https://technet.microsoft.com/library/dn408187.aspx" target="_blank">
     [5]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Utilize the Sysinternals Autoruns/Autorunsc utility
  <span class="scite-citeref-number" data-reference="TechNet Autoruns" id="scite-ref-9-a">
   <sup>
    <a aria-describedby="qtip-8" data-hasqtip="8" href="https://technet.microsoft.com/en-us/sysinternals/bb963902" target="_blank">
     [9]
    </a>
   </sup>
  </span>
  to examine loaded drivers associated with the LSA.
 </p>
 <p>
  Utilize the Sysinternals Process Monitor utility to monitor DLL load operations in lsass.exe.
  <span class="scite-citeref-number" data-reference="Microsoft DLL Security" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="https://msdn.microsoft.com/library/windows/desktop/ff919712.aspx" target="_blank">
     [8]
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
       <a class="external text" href="https://technet.microsoft.com/library/cc961760.aspx" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Security Subsystem Architecture. Retrieved November 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-050412-4128-99" name="scite-2" rel="nofollow" target="_blank">
        Mullaney, C. &amp; Honda, H. (2012, May 4). Trojan.Pasam. Retrieved February 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="http://download.microsoft.com/download/E/B/0/EB0F50CC-989C-4B66-B7F6-68CD3DC90DE3/Microsoft_Security_Intelligence_Report_Volume_21_English.pdf" name="scite-3" rel="nofollow" target="_blank">
        Anthe, C. et al. (2016, December 14). Microsoft Security Intelligence Report Volume 21. Retrieved November 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.microsoft.com/wdsi/threats/malware-encyclopedia-description?Name=Backdoor:Win32/Wingbird.A!dha" name="scite-4" rel="nofollow" target="_blank">
        Microsoft. (2017, November 9). Backdoor:Win32/Wingbird.A!dha. Retrieved November 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/library/dn408187.aspx" name="scite-5" rel="nofollow" target="_blank">
        Microsoft. (2014, March 12). Configuring Additional LSA Protection. Retrieved November 27, 2017.
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
       <a class="external text" href="https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard-manage" name="scite-6" rel="nofollow" target="_blank">
        Lich, B., Tobin, J., Hall, J. (2017, April 5). Manage Windows Defender Credential Guard. Retrieved November 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard-how-it-works" name="scite-7" rel="nofollow" target="_blank">
        Lich, B., Tobin, J. (2017, April 5). How Windows Defender Credential Guard works. Retrieved November 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/windows/desktop/ff919712.aspx" name="scite-8" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Dynamic-Link Library Security. Retrieved November 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/sysinternals/bb963902" name="scite-9" rel="nofollow" target="_blank">
        Russinovich, M. (2016, January 4). Autoruns for Windows v13.51. Retrieved June 6, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
