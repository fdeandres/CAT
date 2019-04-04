<div class="container-fluid">
 <h1>
  Indirect Command Execution
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Various Windows utilities may be used to execute commands, possibly without invoking
    <a href="https://attack.mitre.org/software/S0106">
     cmd
    </a>
    . For example,
    <a href="https://attack.mitre.org/software/S0193">
     Forfiles
    </a>
    , the Program Compatibility Assistant (pcalua.exe), components of the Windows Subsystem for Linux (WSL), as well as other utilities may invoke the execution of programs and commands from a
    <a href="https://attack.mitre.org/techniques/T1059">
     Command-Line Interface
    </a>
    , Run window, or via scripts.
    <span class="scite-citeref-number" data-reference="VectorSec ForFiles Aug 2017" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://twitter.com/vector_sec/status/896049052642533376" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Evi1cg Forfiles Nov 2017" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://twitter.com/Evi1cg/status/935027922397573120" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries may abuse these utilities for Defense Evasion, specifically to perform arbitrary execution while subverting detections and/or mitigation controls (such as Group Policy) that limit/prevent the usage of
    <a href="https://attack.mitre.org/software/S0106">
     cmd
    </a>
    .
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1202
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
      : Defense Evasion
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
      User
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
      Process monitoring, Process command-line parameters, Windows event logs
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
      Application whitelisting, Process whitelisting, Whitelisting by file name or path
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
      Matthew Demaske, Adaptforward
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
     <a href="https://attack.mitre.org/software/S0193">
      Forfiles
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0193">
       Forfiles
      </a>
      can be used to subvert controls and possibly conceal command execution by not directly invoking
      <a href="https://attack.mitre.org/software/S0106">
       cmd
      </a>
      .
      <span class="scite-citeref-number" data-reference="VectorSec ForFiles Aug 2017" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://twitter.com/vector_sec/status/896049052642533376" target="_blank">
         [1]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Evi1cg Forfiles Nov 2017" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://twitter.com/Evi1cg/status/935027922397573120" target="_blank">
         [2]
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
  Identify or block potentially malicious software that may contain abusive functionality by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [3]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [4]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-5-a">
   <sup>
    <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [5]
    </a>
   </sup>
  </span>
  or Software Restriction Policies
  <span class="scite-citeref-number" data-reference="Corio 2008" id="scite-ref-6-a">
   <sup>
    <a aria-describedby="qtip-5" data-hasqtip="5" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" target="_blank">
     [6]
    </a>
   </sup>
  </span>
  where appropriate.
  <span class="scite-citeref-number" data-reference="TechNet Applocker vs SRP" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" target="_blank">
     [7]
    </a>
   </sup>
  </span>
  . These mechanisms can also be used to disable and/or limit user access to Windows utilities used to invoke execution.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor and analyze logs from host-based detection mechanisms, such as Sysmon, for events such as process creations that include or are resulting from parameters associated with invoking programs/commands and/or spawning child processes.
  <span class="scite-citeref-number" data-reference="RSA Forfiles Aug 2017" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="https://community.rsa.com/community/products/netwitness/blog/2017/08/14/are-you-looking-out-for-forfilesexe-if-you-are-watching-for-cmdexe" target="_blank">
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
       <a class="external text" href="https://twitter.com/vector_sec/status/896049052642533376" name="scite-1" rel="nofollow" target="_blank">
        vector_sec. (2017, August 11). Defenders watching launches of cmd? What about forfiles?. Retrieved January 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://twitter.com/Evi1cg/status/935027922397573120" name="scite-2" rel="nofollow" target="_blank">
        Evi1cg. (2017, November 26). block cmd.exe ? try this :. Retrieved January 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-3" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-4" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
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
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-5" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" name="scite-6" rel="nofollow" target="_blank">
        Corio, C., &amp; Sayana, D. P. (2008, June). Application Lockdown with Software Restriction Policies. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" name="scite-7" rel="nofollow" target="_blank">
        Microsoft. (2012, June 27). Using Software Restriction Policies and AppLocker Policies. Retrieved April 7, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://community.rsa.com/community/products/netwitness/blog/2017/08/14/are-you-looking-out-for-forfilesexe-if-you-are-watching-for-cmdexe" name="scite-8" rel="nofollow" target="_blank">
        Partington, E. (2017, August 14). Are you looking out for forfiles.exe (if you are watching for cmd.exe). Retrieved January 22, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
