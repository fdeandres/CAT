<div class="container-fluid">
 <h1>
  Control Panel Items
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Windows Control Panel items are utilities that allow users to view and adjust computer settings. Control Panel items are registered executable (.exe) or Control Panel (.cpl) files, the latter are actually renamed dynamic-link library (.dll) files that export a CPlApplet function.
    <span class="scite-citeref-number" data-reference="Microsoft Implementing CPL" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://msdn.microsoft.com/library/windows/desktop/cc144185.aspx" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="TrendMicro CPL Malware Jan 2014" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.trendmicro.de/cloud-content/us/pdfs/security-intelligence/white-papers/wp-cpl-malware.pdf" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    Control Panel items can be executed directly from the command line, programmatically via an application programming interface (API) call, or by simply double-clicking the file.
    <span class="scite-citeref-number" data-reference="Microsoft Implementing CPL" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://msdn.microsoft.com/library/windows/desktop/cc144185.aspx" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="TrendMicro CPL Malware Jan 2014" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.trendmicro.de/cloud-content/us/pdfs/security-intelligence/white-papers/wp-cpl-malware.pdf" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="TrendMicro CPL Malware Dec 2013" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://blog.trendmicro.com/trendlabs-security-intelligence/control-panel-files-used-as-malicious-attachments/" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    For ease of use, Control Panel items typically include graphical menus available to users after being registered and loaded into the Control Panel.
    <span class="scite-citeref-number" data-reference="Microsoft Implementing CPL" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://msdn.microsoft.com/library/windows/desktop/cc144185.aspx" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries can use Control Panel items as execution payloads to execute arbitrary commands. Malicious Control Panel items can be delivered via
    <a href="https://attack.mitre.org/techniques/T1193">
     Spearphishing Attachment
    </a>
    campaigns
    <span class="scite-citeref-number" data-reference="TrendMicro CPL Malware Jan 2014" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.trendmicro.de/cloud-content/us/pdfs/security-intelligence/white-papers/wp-cpl-malware.pdf" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="TrendMicro CPL Malware Dec 2013" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://blog.trendmicro.com/trendlabs-security-intelligence/control-panel-files-used-as-malicious-attachments/" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    or executed as part of multi-stage malware.
    <span class="scite-citeref-number" data-reference="Palo Alto Reaver Nov 2017" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-new-malware-with-ties-to-sunorcal-discovered/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    Control Panel items, specifically CPL files, may also bypass application and/or file extension whitelisting.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1196
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
      : Defense Evasion, Execution
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
      User, Administrator, SYSTEM
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
      API monitoring, Binary file metadata, DLL monitoring, Windows Registry, Windows event logs, Process command-line parameters, Process monitoring
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
       Defense Bypassed:
      </span>
      Application whitelisting, Process whitelisting
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
     <a href="https://attack.mitre.org/software/S0172">
      Reaver
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0172">
       Reaver
      </a>
      drops and executes a malicious CPL file as its payload.
      <span class="scite-citeref-number" data-reference="Palo Alto Reaver Nov 2017" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-new-malware-with-ties-to-sunorcal-discovered/" target="_blank">
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
  This type of attack technique cannot be easily mitigated with preventive controls since it is based on the abuse of operating system design features. For example, mitigating specific Windows API calls and/or execution of particular file extensions will likely have unintended side effects, such as preventing legitimate software (i.e., drivers and configuration tools) from operating properly. Efforts should be focused on preventing adversary tools from running earlier in the chain of activity and on identification of subsequent malicious behavior.
 </p>
 <p>
  Restrict storage and execution of Control Panel items to protected directories, such as
  <code>
   C:\Windows
  </code>
  , rather than user directories.
 </p>
 <p>
  Index known safe Control Panel items and block potentially malicious software using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-5-a">
   <sup>
    <a aria-describedby="qtip-4" data-hasqtip="4" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [5]
    </a>
   </sup>
  </span>
  tools like AppLocker
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-6-a">
   <sup>
    <a aria-describedby="qtip-5" data-hasqtip="5" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [6]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [7]
    </a>
   </sup>
  </span>
  that are capable of auditing and/or blocking unknown executable files.
 </p>
 <p>
  Consider fully enabling User Account Control (UAC) to impede system-wide changes from illegitimate administrators.
  <span class="scite-citeref-number" data-reference="Microsoft UAC" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="https://msdn.microsoft.com/library/windows/desktop/dn742497.aspx" target="_blank">
     [8]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor and analyze activity related to items associated with CPL files, such as the Windows Control Panel process binary (control.exe) and the Control_RunDLL and ControlRunDLLAsUser API functions in shell32.dll. When executed from the command line or clicked, control.exe will execute the CPL file (ex:
  <code>
   control.exe file.cpl
  </code>
  ) before
  <a href="https://attack.mitre.org/techniques/T1085">
   Rundll32
  </a>
  is used to call the CPL's API functions (ex:
  <code>
   rundll32.exe shell32.dll,Control_RunDLL file.cpl
  </code>
  ). CPL files can be executed directly via the CPL API function with just the latter
  <a href="https://attack.mitre.org/techniques/T1085">
   Rundll32
  </a>
  command, which may bypass detections and/or execution filters for control.exe.
  <span class="scite-citeref-number" data-reference="TrendMicro CPL Malware Jan 2014" id="scite-ref-2-a">
   <sup>
    <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.trendmicro.de/cloud-content/us/pdfs/security-intelligence/white-papers/wp-cpl-malware.pdf" target="_blank">
     [2]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Inventory Control Panel items to locate unregistered and potentially malicious files present on systems:
 </p>
 <ul>
  <li>
   Executable format registered Control Panel items will have a globally unique identifier (GUID) and registration Registry entries in
   <code>
    HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\ControlPanel\NameSpace
   </code>
   and
   <code>
    HKEY_CLASSES_ROOT\CLSID{GUID}
   </code>
   . These entries may contain information about the Control Panel item such as its display name, path to the local file, and the command executed when opened in the Control Panel.
   <span class="scite-citeref-number" data-reference="Microsoft Implementing CPL" id="scite-ref-1-a">
    <sup>
     <a aria-describedby="qtip-0" data-hasqtip="0" href="https://msdn.microsoft.com/library/windows/desktop/cc144185.aspx" target="_blank">
      [1]
     </a>
    </sup>
   </span>
  </li>
  <li>
   CPL format registered Control Panel items stored in the System32 directory are automatically shown in the Control Panel. Other Control Panel items will have registration entries in the
   <code>
    Cpls
   </code>
   and
   <code>
    Extended Properties
   </code>
   Registry keys of
   <code>
    HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Control Panel
   </code>
   . These entries may include information such as a GUID, path to the local file, and a canonical name used to launch the file programmatically (
   <code>
    WinExec("c:\windows\system32\control.exe {Canonical_Name}", SW_NORMAL);
   </code>
   ) or from a command line (
   <code>
    control.exe /name {Canonical_Name}
   </code>
   ).
   <span class="scite-citeref-number" data-reference="Microsoft Implementing CPL" id="scite-ref-1-a">
    <sup>
     <a aria-describedby="qtip-0" data-hasqtip="0" href="https://msdn.microsoft.com/library/windows/desktop/cc144185.aspx" target="_blank">
      [1]
     </a>
    </sup>
   </span>
  </li>
  <li>
   Some Control Panel items are extensible via Shell extensions registered in
   <code>
    HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Controls Folder{name}\Shellex\PropertySheetHandlers
   </code>
   where {name} is the predefined name of the system item.
   <span class="scite-citeref-number" data-reference="Microsoft Implementing CPL" id="scite-ref-1-a">
    <sup>
     <a aria-describedby="qtip-0" data-hasqtip="0" href="https://msdn.microsoft.com/library/windows/desktop/cc144185.aspx" target="_blank">
      [1]
     </a>
    </sup>
   </span>
  </li>
 </ul>
 <p>
  Analyze new Control Panel items as well as those present on disk for malicious content. Both executable and CPL formats are compliant Portable Executable (PE) images and can be examined using traditional tools and methods, pending anti-reverse-engineering techniques.
  <span class="scite-citeref-number" data-reference="TrendMicro CPL Malware Jan 2014" id="scite-ref-2-a">
   <sup>
    <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.trendmicro.de/cloud-content/us/pdfs/security-intelligence/white-papers/wp-cpl-malware.pdf" target="_blank">
     [2]
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
       <a class="external text" href="https://msdn.microsoft.com/library/windows/desktop/cc144185.aspx" name="scite-1" rel="nofollow" target="_blank">
        M. (n.d.). Implementing Control Panel Items. Retrieved January 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.trendmicro.de/cloud-content/us/pdfs/security-intelligence/white-papers/wp-cpl-malware.pdf" name="scite-2" rel="nofollow" target="_blank">
        Mercês, F. (2014, January 27). CPL Malware - Malicious Control Panel Items. Retrieved January 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/control-panel-files-used-as-malicious-attachments/" name="scite-3" rel="nofollow" target="_blank">
        Bernardino, J. (2013, December 17). Control Panel Files Used As Malicious Attachments. Retrieved January 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-new-malware-with-ties-to-sunorcal-discovered/" name="scite-4" rel="nofollow" target="_blank">
        Grunzweig, J. and Miller-Osborn, J. (2017, November 10). New Malware with Ties to SunOrcal Discovered. Retrieved November 16, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="5.0">
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-5" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-6" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-7" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/windows/desktop/dn742497.aspx" name="scite-8" rel="nofollow" target="_blank">
        Microsoft. (n.d.). User Account Control. Retrieved January 18, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
