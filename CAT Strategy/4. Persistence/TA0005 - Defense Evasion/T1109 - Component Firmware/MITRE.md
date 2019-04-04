<div class="container-fluid">
 <h1>
  Component Firmware
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Some adversaries may employ sophisticated means to compromise computer components and install malicious firmware that will execute adversary code outside of the operating system and main system firmware or BIOS. This technique may be similar to
    <a href="https://attack.mitre.org/techniques/T1019">
     System Firmware
    </a>
    but conducted upon other system components that may not have the same capability or level of integrity checking. Malicious device firmware could provide both a persistent level of access to systems despite potential typical failures to maintain access and hard disk re-images, as well as a way to evade host software-based defenses and integrity checks.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1109
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
      SYSTEM
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
      Disk forensics, API monitoring, Process monitoring, Component firmware
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
      File monitoring, Host intrusion prevention systems, Anti-virus
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
     <a href="https://attack.mitre.org/groups/G0020">
      Equation
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0020">
       Equation
      </a>
      is known to have the capability to overwrite the firmware on hard drives from some manufacturers.
      <span class="scite-citeref-number" data-reference="Kaspersky Equation QA" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08064459/Equation_group_questions_and_answers.pdf" target="_blank">
         [1]
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
  Prevent adversary access to privileged accounts or access necessary to perform this technique.
 </p>
 <p>
  Consider removing and replacing system components suspected of being compromised.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Data and telemetry from use of device drivers (i.e. processes and API calls) and/or provided by SMART (Self-Monitoring, Analysis and Reporting Technology)
  <span class="scite-citeref-number" data-reference="SanDisk SMART" id="scite-ref-2-a">
   <sup>
    [2]
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="SmartMontools" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.smartmontools.org/" target="_blank">
     [3]
    </a>
   </sup>
  </span>
  disk monitoring may reveal malicious manipulations of components. Otherwise, this technique may be difficult to detect since malicious activity is taking place on system components possibly outside the purview of OS security and integrity mechanisms.
 </p>
 <p>
  Disk check and forensic utilities
  <span class="scite-citeref-number" data-reference="ITWorld Hard Disk Health Dec 2014" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.itworld.com/article/2853992/3-tools-to-check-your-hard-drives-health-and-make-sure-its-not-already-dying-on-you.html" target="_blank">
     [4]
    </a>
   </sup>
  </span>
  may reveal indicators of malicious firmware such as strings, unexpected disk partition table entries, or blocks of otherwise unusual memory that warrant deeper investigation. Also consider comparing components, including hashes of component firmware and behavior, against known good images.
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
       <a class="external text" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08064459/Equation_group_questions_and_answers.pdf" name="scite-1" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2015, February). Equation Group: Questions and Answers. Retrieved December 21, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       SanDisk. (n.d.). Self-Monitoring, Analysis and Reporting Technology (S.M.A.R.T.). Retrieved October 2, 2018.
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="3.0">
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.smartmontools.org/" name="scite-3" rel="nofollow" target="_blank">
        smartmontools. (n.d.). smartmontools. Retrieved October 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.itworld.com/article/2853992/3-tools-to-check-your-hard-drives-health-and-make-sure-its-not-already-dying-on-you.html" name="scite-4" rel="nofollow" target="_blank">
        Pinola, M. (2014, December 14). 3 tools to check your hard drive's health and make sure it's not already dying on you. Retrieved October 2, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
