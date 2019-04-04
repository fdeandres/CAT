<div class="container-fluid">
 <h1>
  BITS Jobs
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Windows Background Intelligent Transfer Service (BITS) is a low-bandwidth, asynchronous file transfer mechanism exposed through Component Object Model (COM).
    <span class="scite-citeref-number" data-reference="Microsoft COM" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://msdn.microsoft.com/library/windows/desktop/ms680573.aspx" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Microsoft BITS" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://msdn.microsoft.com/library/windows/desktop/bb968799.aspx" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    BITS is commonly used by updaters, messengers, and other applications preferred to operate in the background (using available idle bandwidth) without interrupting other networked applications. File transfer tasks are implemented as BITS jobs, which contain a queue of one or more file operations.
   </p>
   <p>
    The interface to create and manage BITS jobs is accessible through
    <a href="https://attack.mitre.org/techniques/T1086">
     PowerShell
    </a>
    <span class="scite-citeref-number" data-reference="Microsoft BITS" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://msdn.microsoft.com/library/windows/desktop/bb968799.aspx" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    and the
    <a href="https://attack.mitre.org/software/S0190">
     BITSAdmin
    </a>
    tool.
    <span class="scite-citeref-number" data-reference="Microsoft BITSAdmin" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://msdn.microsoft.com/library/aa362813.aspx" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries may abuse BITS to download, execute, and even clean up after running malicious code. BITS tasks are self-contained in the BITS job database, without new files or registry modifications, and often permitted by host firewalls.
    <span class="scite-citeref-number" data-reference="CTU BITS Malware June 2016" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.secureworks.com/blog/malware-lingers-with-bits" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Mondok Windows PiggyBack BITS May 2007" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://arstechnica.com/information-technology/2007/05/malware-piggybacks-on-windows-background-intelligent-transfer-service/" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Symantec BITS May 2007" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.symantec.com/connect/blogs/malware-update-windows-update" target="_blank">
       [6]
      </a>
     </sup>
    </span>
    BITS enabled execution may also allow Persistence by creating long-standing jobs (the default maximum lifetime is 90 days and extendable) or invoking an arbitrary program when a job completes or errors (including after system reboots).
    <span class="scite-citeref-number" data-reference="PaloAlto UBoatRAT Nov 2017" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-uboatrat-navigates-east-asia/" target="_blank">
       [7]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="CTU BITS Malware June 2016" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.secureworks.com/blog/malware-lingers-with-bits" target="_blank">
       [4]
      </a>
     </sup>
    </span>
   </p>
   <p>
    BITS upload functionalities can also be used to perform
    <a href="https://attack.mitre.org/techniques/T1048">
     Exfiltration Over Alternative Protocol
    </a>
    .
    <span class="scite-citeref-number" data-reference="CTU BITS Malware June 2016" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.secureworks.com/blog/malware-lingers-with-bits" target="_blank">
       [4]
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
      : T1197
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
      API monitoring, Packet capture, Windows event logs
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
      Firewall, Host forensic analysis
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
       Contributors:
      </span>
      Ricardo Dias; Red Canary
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
     <a href="https://attack.mitre.org/software/S0154">
      Cobalt Strike
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0154">
       Cobalt Strike
      </a>
      can download a hosted "beacon" payload using
      <a href="https://attack.mitre.org/software/S0190">
       BITSAdmin
      </a>
      .
      <span class="scite-citeref-number" data-reference="CobaltStrike Scripted Web Delivery" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.cobaltstrike.com/help-scripted-web-delivery" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0201">
      JPIN
     </a>
    </td>
    <td>
     <p>
      A
      <a href="https://attack.mitre.org/software/S0201">
       JPIN
      </a>
      variant downloads the backdoor payload via the BITS service.
      <span class="scite-citeref-number" data-reference="Microsoft PLATINUM April 2016" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" target="_blank">
         [9]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0065">
      Leviathan
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0065">
       Leviathan
      </a>
      has used bitsadmin.exe to download additional tools.
      <span class="scite-citeref-number" data-reference="FireEye Periscope March 2018" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" target="_blank">
         [10]
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
  This type of attack technique cannot be easily mitigated with preventive controls since it is based on the abuse of operating system design features. For example, disabling all BITS functionality will likely have unintended side effects, such as preventing legitimate software patching and updating. Efforts should be focused on preventing adversary tools from running earlier in the chain of activity and on identification of subsequent malicious behavior.
  <span class="scite-citeref-number" data-reference="Mondok Windows PiggyBack BITS May 2007" id="scite-ref-5-a">
   <sup>
    <a aria-describedby="qtip-4" data-hasqtip="4" href="https://arstechnica.com/information-technology/2007/05/malware-piggybacks-on-windows-background-intelligent-transfer-service/" target="_blank">
     [5]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Modify network and/or host firewall rules, as well as other network controls, to only allow legitimate BITS traffic.
 </p>
 <p>
  Consider limiting access to the BITS interface to specific users or groups.
  <span class="scite-citeref-number" data-reference="Symantec BITS May 2007" id="scite-ref-6-a">
   <sup>
    <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.symantec.com/connect/blogs/malware-update-windows-update" target="_blank">
     [6]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Consider reducing the default BITS job lifetime in Group Policy or by editing the
  <code>
   JobInactivityTimeout
  </code>
  and
  <code>
   MaxDownloadTime
  </code>
  Registry values in
  <code>
   HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\BITS
  </code>
  .
  <span class="scite-citeref-number" data-reference="Microsoft BITS" id="scite-ref-2-a">
   <sup>
    <a aria-describedby="qtip-1" data-hasqtip="1" href="https://msdn.microsoft.com/library/windows/desktop/bb968799.aspx" target="_blank">
     [2]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  BITS runs as a service and its status can be checked with the Sc query utility (
  <code>
   sc query bits
  </code>
  ).
  <span class="scite-citeref-number" data-reference="Microsoft Issues with BITS July 2011" id="scite-ref-11-a">
   <sup>
    <a aria-describedby="qtip-10" data-hasqtip="10" href="https://technet.microsoft.com/library/dd939934.aspx" target="_blank">
     [11]
    </a>
   </sup>
  </span>
  Active BITS tasks can be enumerated using the
  <a href="https://attack.mitre.org/software/S0190">
   BITSAdmin
  </a>
  tool (
  <code>
   bitsadmin /list /allusers /verbose
  </code>
  ).
  <span class="scite-citeref-number" data-reference="Microsoft BITS" id="scite-ref-2-a">
   <sup>
    <a aria-describedby="qtip-1" data-hasqtip="1" href="https://msdn.microsoft.com/library/windows/desktop/bb968799.aspx" target="_blank">
     [2]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Monitor usage of the
  <a href="https://attack.mitre.org/software/S0190">
   BITSAdmin
  </a>
  tool (especially the ‘Transfer’, 'Create', 'AddFile', 'SetNotifyFlags', 'SetNotifyCmdLine', 'SetMinRetryDelay', 'SetCustomHeaders', and 'Resume' command options)
  <span class="scite-citeref-number" data-reference="Microsoft BITS" id="scite-ref-2-a">
   <sup>
    <a aria-describedby="qtip-1" data-hasqtip="1" href="https://msdn.microsoft.com/library/windows/desktop/bb968799.aspx" target="_blank">
     [2]
    </a>
   </sup>
  </span>
  Admin and the Windows Event log for BITS activity. Also consider investigating more detailed information about jobs by parsing the BITS job database.
  <span class="scite-citeref-number" data-reference="CTU BITS Malware June 2016" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.secureworks.com/blog/malware-lingers-with-bits" target="_blank">
     [4]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Monitor and analyze network activity generated by BITS. BITS jobs use HTTP(S) and SMB for remote connections and are tethered to the creating user and will only function when that user is logged on (this rule applies even if a user attaches the job to a service account).
  <span class="scite-citeref-number" data-reference="Microsoft BITS" id="scite-ref-2-a">
   <sup>
    <a aria-describedby="qtip-1" data-hasqtip="1" href="https://msdn.microsoft.com/library/windows/desktop/bb968799.aspx" target="_blank">
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
       <a class="external text" href="https://msdn.microsoft.com/library/windows/desktop/ms680573.aspx" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Component Object Model (COM). Retrieved November 22, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/windows/desktop/bb968799.aspx" name="scite-2" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Background Intelligent Transfer Service. Retrieved January 12, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/aa362813.aspx" name="scite-3" rel="nofollow" target="_blank">
        Microsoft. (n.d.). BITSAdmin Tool. Retrieved January 12, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/blog/malware-lingers-with-bits" name="scite-4" rel="nofollow" target="_blank">
        Counter Threat Unit Research Team. (2016, June 6). Malware Lingers with BITS. Retrieved January 12, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://arstechnica.com/information-technology/2007/05/malware-piggybacks-on-windows-background-intelligent-transfer-service/" name="scite-5" rel="nofollow" target="_blank">
        Mondok, M. (2007, May 11). Malware piggybacks on Windows’ Background Intelligent Transfer Service. Retrieved January 12, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/connect/blogs/malware-update-windows-update" name="scite-6" rel="nofollow" target="_blank">
        Florio, E. (2007, May 9). Malware Update with Windows Update. Retrieved January 12, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="7.5">
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-uboatrat-navigates-east-asia/" name="scite-7" rel="nofollow" target="_blank">
        Hayashi, K. (2017, November 28). UBoatRAT Navigates East Asia. Retrieved January 12, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cobaltstrike.com/help-scripted-web-delivery" name="scite-8" rel="nofollow" target="_blank">
        Strategic Cyber, LLC. (n.d.). Scripted Web Delivery. Retrieved January 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" name="scite-9" rel="nofollow" target="_blank">
        Windows Defender Advanced Threat Hunting Team. (2016, April 29). PLATINUM: Targeted attacks in South and Southeast Asia. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" name="scite-10" rel="nofollow" target="_blank">
        FireEye. (2018, March 16). Suspected Chinese Cyber Espionage Group (TEMP.Periscope) Targeting U.S. Engineering and Maritime Industries. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/library/dd939934.aspx" name="scite-11" rel="nofollow" target="_blank">
        Microsoft. (2011, July 19). Issues with BITS. Retrieved January 12, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
