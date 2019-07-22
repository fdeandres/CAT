<div class="container-fluid">
 <h1>
  File Permissions Modification
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    File permissions are commonly managed by discretionary access control lists (DACLs) specified by the file owner. File DACL implementation may vary by platform, but generally explicitly designate which users/groups can perform which actions (ex: read, write, execute, etc.).
    <span class="scite-citeref-number" data-reference="Microsoft DACL May 2018" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://docs.microsoft.com/windows/desktop/secauthz/dacls-and-aces" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Microsoft File Rights May 2018" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://docs.microsoft.com/windows/desktop/fileio/file-security-and-access-rights" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Unix File Permissions" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.tutorialspoint.com/unix/unix-file-permission.htm" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries may modify file permissions/attributes to evade intended DACLs.
    <span class="scite-citeref-number" data-reference="Hybrid Analysis Icacls1 June 2018" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.hybrid-analysis.com/sample/ef0d2628823e8e0a0de3b08b8eacaf41cf284c086a948bdfd67f4e4373c14e4d?environmentId=100" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Hybrid Analysis Icacls2 May 2018" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.hybrid-analysis.com/sample/22dab012c3e20e3d9291bce14a2bfc448036d3b966c6e78167f4626f5f9e38d6?environmentId=110" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    Modifications may include changing specific access rights, which may require taking ownership of a file and/or elevated permissions such as Administrator/root depending on the file's existing permissions to enable malicious activity such as modifying, replacing, or deleting specific files. Specific file modifications may be a required step for many techniques, such as establishing Persistence via
    <a href="https://attack.mitre.org/techniques/T1015">
     Accessibility Features
    </a>
    ,
    <a href="https://attack.mitre.org/techniques/T1037">
     Logon Scripts
    </a>
    , or tainting/hijacking other instrumental binary/configuration files.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1222
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
      Linux, Windows, macOS
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
      User, Administrator, SYSTEM, root
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
      File monitoring, Process monitoring, Process command-line parameters, Windows event logs
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
      File system access controls
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
      Jan Miller, CrowdStrike
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
     <a href="https://attack.mitre.org/groups/G0050">
      APT32
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0050">
       APT32
      </a>
      's macOS backdoor changes the permission of the file it wants to execute to 755.
      <span class="scite-citeref-number" data-reference="ESET OceanLotus macOS April 2019" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.welivesecurity.com/2019/04/09/oceanlotus-macos-malware-update/" target="_blank">
         [6]
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
      <a href="https://attack.mitre.org/software/S0201">
       JPIN
      </a>
      can use the command-line utility cacls.exe to change file permissions.
      <span class="scite-citeref-number" data-reference="Microsoft PLATINUM April 2016" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0366">
      WannaCry
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0366">
       WannaCry
      </a>
      uses
      <code>
       attrib +h
      </code>
      and
      <code>
       icacls . /grant Everyone:F /T /C /Q
      </code>
      to make some of its files hidden and grant all users full access controls.
      <span class="scite-citeref-number" data-reference="LogRhythm WannaCry" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://logrhythm.com/blog/a-technical-analysis-of-wannacry-ransomware/" target="_blank">
         [8]
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
  This type of technique cannot be easily mitigated with preventive controls since it is based on the abuse of operating system design features. Efforts should be focused on preventing adversary tools from running earlier in the chain of activity and on identification of subsequent malicious behavior.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor and investigate attempts to modify DACLs and file ownership, such as use of icacls
  <span class="scite-citeref-number" data-reference="Microsoft icacls OCT 2017" id="scite-ref-9-a">
   <sup>
    <a aria-describedby="qtip-8" data-hasqtip="8" href="https://docs.microsoft.com/windows-server/administration/windows-commands/icacls" target="_blank">
     [9]
    </a>
   </sup>
  </span>
  , takeown
  <span class="scite-citeref-number" data-reference="Microsoft takeown OCT 2017" id="scite-ref-10-a">
   <sup>
    <a aria-describedby="qtip-9" data-hasqtip="9" href="https://docs.microsoft.com/windows-server/administration/windows-commands/takeown" target="_blank">
     [10]
    </a>
   </sup>
  </span>
  , attrib
  <span class="scite-citeref-number" data-reference="Microsoft attrib OCT 2017" id="scite-ref-11-a">
   <sup>
    <a aria-describedby="qtip-10" data-hasqtip="10" href="https://docs.microsoft.com/windows-server/administration/windows-commands/attrib" target="_blank">
     [11]
    </a>
   </sup>
  </span>
  , and
  <a href="https://attack.mitre.org/techniques/T1086">
   PowerShell
  </a>
  Set-Acl
  <span class="scite-citeref-number" data-reference="Microsoft SetAcl" id="scite-ref-12-a">
   <sup>
    <a aria-describedby="qtip-11" data-hasqtip="11" href="https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-acl" target="_blank">
     [12]
    </a>
   </sup>
  </span>
  in Windows and chmod
  <span class="scite-citeref-number" data-reference="Linux chmod" id="scite-ref-13-a">
   <sup>
    <a aria-describedby="qtip-12" data-hasqtip="12" href="https://linux.die.net/man/1/chmod" target="_blank">
     [13]
    </a>
   </sup>
  </span>
  /chown
  <span class="scite-citeref-number" data-reference="Linux chown" id="scite-ref-14-a">
   <sup>
    <a aria-describedby="qtip-13" data-hasqtip="13" href="https://linux.die.net/man/1/chown" target="_blank">
     [14]
    </a>
   </sup>
  </span>
  in macOS/Linux. Many of these are built-in system utilities and may generate high false positive alerts, so compare against baseline knowledge for how systems are typically used and correlate modification events with other indications of malicious activity where possible.
 </p>
 <p>
  Consider enabling file permission change auditing on folders containing key binary/configuration files. Windows Security Log events (Event ID 4670) are used when DACLs are modified.
  <span class="scite-citeref-number" data-reference="EventTracker File Permissions Feb 2014" id="scite-ref-15-a">
   <sup>
    <a aria-describedby="qtip-14" data-hasqtip="14" href="https://www.eventtracker.com/tech-articles/monitoring-file-permission-changes-windows-security-log/" target="_blank">
     [15]
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
       <a class="external text" href="https://docs.microsoft.com/windows/desktop/secauthz/dacls-and-aces" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (2018, May 30). DACLs and ACEs. Retrieved August 19, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/windows/desktop/fileio/file-security-and-access-rights" name="scite-2" rel="nofollow" target="_blank">
        Microsoft. (2018, May 30). File Security and Access Rights. Retrieved August 19, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.tutorialspoint.com/unix/unix-file-permission.htm" name="scite-3" rel="nofollow" target="_blank">
        Tutorials Point. (n.d.). Unix / Linux - File Permission / Access Modes. Retrieved August 19, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.hybrid-analysis.com/sample/ef0d2628823e8e0a0de3b08b8eacaf41cf284c086a948bdfd67f4e4373c14e4d?environmentId=100" name="scite-4" rel="nofollow" target="_blank">
        Hybrid Analysis. (2018, June 12). c9b65b764985dfd7a11d3faf599c56b8.exe. Retrieved August 19, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.hybrid-analysis.com/sample/22dab012c3e20e3d9291bce14a2bfc448036d3b966c6e78167f4626f5f9e38d6?environmentId=110" name="scite-5" rel="nofollow" target="_blank">
        Hybrid Analysis. (2018, May 30). 2a8efbfadd798f6111340f7c1c956bee.dll. Retrieved August 19, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2019/04/09/oceanlotus-macos-malware-update/" name="scite-6" rel="nofollow" target="_blank">
        Dumont, R.. (2019, April 9). OceanLotus: macOS malware update. Retrieved April 15, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" name="scite-7" rel="nofollow" target="_blank">
        Windows Defender Advanced Threat Hunting Team. (2016, April 29). PLATINUM: Targeted attacks in South and Southeast Asia. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://logrhythm.com/blog/a-technical-analysis-of-wannacry-ransomware/" name="scite-8" rel="nofollow" target="_blank">
        Noerenberg, E., Costis, A., and Quist, N. (2017, May 16). A Technical Analysis of WannaCry Ransomware. Retrieved March 25, 2019.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="9.5">
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/windows-server/administration/windows-commands/icacls" name="scite-9" rel="nofollow" target="_blank">
        Plett, C. et al.. (2017, October 17). icacls. Retrieved August 19, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/windows-server/administration/windows-commands/takeown" name="scite-10" rel="nofollow" target="_blank">
        Plett, C. et al.. (2017, October 15). takeown. Retrieved August 19, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/windows-server/administration/windows-commands/attrib" name="scite-11" rel="nofollow" target="_blank">
        Plett, C. et al.. (2017, October 15). attrib. Retrieved August 19, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-acl" name="scite-12" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Set-Acl. Retrieved August 19, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://linux.die.net/man/1/chmod" name="scite-13" rel="nofollow" target="_blank">
        MacKenzie, D. &amp; Meyering, J. (n.d.). chmod(1) - Linux man page. Retrieved August 19, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://linux.die.net/man/1/chown" name="scite-14" rel="nofollow" target="_blank">
        MacKenzie, D. &amp; Meyering, J. (n.d.). chown(1) - Linux man page. Retrieved August 19, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.eventtracker.com/tech-articles/monitoring-file-permission-changes-windows-security-log/" name="scite-15" rel="nofollow" target="_blank">
        Netsurion. (2014, February 19). Monitoring File Permission Changes with the Windows Security Log. Retrieved August 19, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
