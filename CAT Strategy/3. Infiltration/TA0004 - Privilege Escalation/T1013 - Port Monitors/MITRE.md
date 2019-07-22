<div class="container-fluid">
 <h1>
  Port Monitors
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    A port monitor can be set through the
    <span class="scite-citeref-number" data-reference="AddMonitor" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://msdn.microsoft.com/en-us/library/dd183341" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    API call to set a DLL to be loaded at startup.
    <span class="scite-citeref-number" data-reference="AddMonitor" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://msdn.microsoft.com/en-us/library/dd183341" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    This DLL can be located in
    <code>
     C:\Windows\System32
    </code>
    and will be loaded by the print spooler service, spoolsv.exe, on boot. The spoolsv.exe process also runs under SYSTEM level permissions.
    <span class="scite-citeref-number" data-reference="Bloxham" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.defcon.org/images/defcon-22/dc-22-presentations/Bloxham/DEFCON-22-Brady-Bloxham-Windows-API-Abuse-UPDATED.pdf" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    Alternatively, an arbitrary DLL can be loaded if permissions allow writing a fully-qualified pathname for that DLL to
    <code>
     HKLM\SYSTEM\CurrentControlSet\Control\Print\Monitors
    </code>
    .
   </p>
   <p>
    The Registry key contains entries for the following:
   </p>
   <ul>
    <li>
     Local Port
    </li>
    <li>
     Standard TCP/IP Port
    </li>
    <li>
     USB Monitor
    </li>
    <li>
     WSD Port
    </li>
   </ul>
   <p>
    Adversaries can use this technique to load malicious code at startup that will persist on system reboot and execute as SYSTEM.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1013
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
      : Persistence, Privilege Escalation
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
       Effective Permissions:
      </span>
      SYSTEM
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      File monitoring, API monitoring, DLL monitoring, Windows Registry, Process monitoring
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
      Stefan Kanthak; Travis Smith, Tripwire
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
     <a href="https://attack.mitre.org/groups/G0082">
      APT38
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0082">
       APT38
      </a>
      installed a port monitoring tool, MAPMAKER, to print the active TCP connections on the local system.
      <span class="scite-citeref-number" data-reference="FireEye APT38 Oct 2018" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://content.fireeye.com/apt/rpt-apt38" target="_blank">
         [3]
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
  Identify and block potentially malicious software that may persist in this manner by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [4]
    </a>
   </sup>
  </span>
  tools capable of monitoring DLL loads by processes running under SYSTEM permissions.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <ul>
  <li>
   Monitor process API calls to
   <span class="scite-citeref-number" data-reference="AddMonitor" id="scite-ref-1-a">
    <sup>
     <a aria-describedby="qtip-0" data-hasqtip="0" href="http://msdn.microsoft.com/en-us/library/dd183341" target="_blank">
      [1]
     </a>
    </sup>
   </span>
   .
  </li>
  <li>
   Monitor DLLs that are loaded by spoolsv.exe for DLLs that are abnormal.
  </li>
  <li>
   New DLLs written to the System32 directory that do not correlate with known good software or patching may be suspicious.
  </li>
  <li>
   Monitor Registry writes to
   <code>
    HKLM\SYSTEM\CurrentControlSet\Control\Print\Monitors
   </code>
   .
  </li>
  <li>
   Run the Autoruns utility, which checks for this Registry key as a persistence mechanism
   <span class="scite-citeref-number" data-reference="TechNet Autoruns" id="scite-ref-5-a">
    <sup>
     <a aria-describedby="qtip-4" data-hasqtip="4" href="https://technet.microsoft.com/en-us/sysinternals/bb963902" target="_blank">
      [5]
     </a>
    </sup>
   </span>
  </li>
 </ul>
 <h2 class="pt-3" id="references">
  References
 </h2>
 <div class="row">
  <div class="col">
   <ol>
    <li>
     <span class="scite-citation" id="scite-1">
      <span class="scite-citation-text">
       <a class="external text" href="http://msdn.microsoft.com/en-us/library/dd183341" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (n.d.). AddMonitor function. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.defcon.org/images/defcon-22/dc-22-presentations/Bloxham/DEFCON-22-Brady-Bloxham-Windows-API-Abuse-UPDATED.pdf" name="scite-2" rel="nofollow" target="_blank">
        Bloxham, B. (n.d.). Getting Windows to Play with Itself [PowerPoint slides]. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://content.fireeye.com/apt/rpt-apt38" name="scite-3" rel="nofollow" target="_blank">
        FireEye. (2018, October 03). APT38: Un-usual Suspects. Retrieved November 6, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="4.5">
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-4" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/sysinternals/bb963902" name="scite-5" rel="nofollow" target="_blank">
        Russinovich, M. (2016, January 4). Autoruns for Windows v13.51. Retrieved June 6, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
