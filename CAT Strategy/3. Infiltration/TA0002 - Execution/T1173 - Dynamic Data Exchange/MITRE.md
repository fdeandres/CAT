<div class="container-fluid">
 <h1>
  Dynamic Data Exchange
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Windows Dynamic Data Exchange (DDE) is a client-server protocol for one-time and/or continuous inter-process communication (IPC) between applications. Once a link is established, applications can autonomously exchange transactions consisting of strings, warm data links (notifications when a data item changes), hot data links (duplications of changes to a data item), and requests for command execution.
   </p>
   <p>
    Object Linking and Embedding (OLE), or the ability to link data between documents, was originally implemented through DDE. Despite being superseded by COM, DDE may be enabled in Windows 10 and most of Microsoft Office 2016 via Registry keys.
    <span class="scite-citeref-number" data-reference="BleepingComputer DDE Disabled in Word Dec 2017" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.bleepingcomputer.com/news/microsoft/microsoft-disables-dde-feature-in-word-to-prevent-further-malware-attacks/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Microsoft ADV170021 Dec 2017" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://portal.msrc.microsoft.com/security-guidance/advisory/ADV170021" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Microsoft DDE Advisory Nov 2017" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://technet.microsoft.com/library/security/4053440" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries may use DDE to execute arbitrary commands. Microsoft Office documents can be poisoned with DDE commands
    <span class="scite-citeref-number" data-reference="SensePost PS DDE May 2016" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://sensepost.com/blog/2016/powershell-c-sharp-and-dde-the-power-within/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Kettle CSV DDE Aug 2014" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.contextis.com/blog/comma-separated-vulnerabilities" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    , directly or through embedded files
    <span class="scite-citeref-number" data-reference="Enigma Reviving DDE Jan 2018" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://posts.specterops.io/reviving-dde-using-onenote-and-excel-for-code-execution-d7226864caee" target="_blank">
       [6]
      </a>
     </sup>
    </span>
    , and used to deliver execution via phishing campaigns or hosted Web content, avoiding the use of Visual Basic for Applications (VBA) macros.
    <span class="scite-citeref-number" data-reference="SensePost MacroLess DDE Oct 2017" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="https://sensepost.com/blog/2017/macro-less-code-exec-in-msword/" target="_blank">
       [7]
      </a>
     </sup>
    </span>
    DDE could also be leveraged by an adversary operating on a compromised machine who does not have direct access to command line execution.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1173
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
      : Execution
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
      API monitoring, DLL monitoring, Process monitoring, Windows Registry, Windows event logs
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
      : 1.1
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
     <a href="https://attack.mitre.org/groups/G0007">
      APT28
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0007">
       APT28
      </a>
      has delivered
      <a href="https://attack.mitre.org/software/S0044">
       JHUHUGIT
      </a>
      and
      <a href="https://attack.mitre.org/software/S0250">
       Koadic
      </a>
      by executing PowerShell commands through DDE in Word documents.
      <span class="scite-citeref-number" data-reference="McAfee APT28 DDE1 Nov 2017" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://securingtomorrow.mcafee.com/mcafee-labs/apt28-threat-group-adopts-dde-technique-nyc-attack-theme-in-latest-campaign/" target="_blank">
         [8]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="McAfee APT28 DDE2 Nov 2017" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="http://securityaffairs.co/wordpress/65318/hacking/dde-attack-apt28.html" target="_blank">
         [9]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Palo Alto Sofacy 06-2018" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-sofacy-groups-parallel-attacks/" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0067">
      APT37
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0067">
       APT37
      </a>
      has used Windows DDE for execution of commands and a malicious VBS.
      <span class="scite-citeref-number" data-reference="Securelist ScarCruft Jun 2016" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://securelist.com/operation-daybreak/75100/" target="_blank">
         [11]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0080">
      Cobalt Group
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0080">
       Cobalt Group
      </a>
      has sent malicious Word OLE compound documents to victims.
      <span class="scite-citeref-number" data-reference="Talos Cobalt Group July 2018" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://blog.talosintelligence.com/2018/07/multiple-cobalt-personality-disorder.html" target="_blank">
         [12]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0046">
      FIN7
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0046">
       FIN7
      </a>
      spear phishing campaigns have included malicious Word documents with DDE execution.
      <span class="scite-citeref-number" data-reference="CyberScoop FIN7 Oct 2017" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://www.cyberscoop.com/fin7-dde-morphisec-fileless-malware/" target="_blank">
         [13]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0084">
      Gallmaker
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0084">
       Gallmaker
      </a>
      attempted to exploit Microsoft’s DDE protocol in order to gain access to victim machines and for execution.
      <span class="scite-citeref-number" data-reference="Symantec Gallmaker Oct 2018" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://www.symantec.com/blogs/threat-intelligence/gallmaker-attack-group" target="_blank">
         [14]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0237">
      GravityRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0237">
       GravityRAT
      </a>
      has been delivered via Word documents using DDE for execution.
      <span class="scite-citeref-number" data-reference="Talos GravityRAT" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://blog.talosintelligence.com/2018/04/gravityrat-two-year-evolution-of-apt.html" target="_blank">
         [15]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0069">
      MuddyWater
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0069">
       MuddyWater
      </a>
      has used malware that can execute PowerShell scripts via DDE.
      <span class="scite-citeref-number" data-reference="Securelist MuddyWater Oct 2018" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="https://securelist.com/muddywater/88059/" target="_blank">
         [16]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0040">
      Patchwork
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0040">
       Patchwork
      </a>
      leveraged the DDE protocol to deliver their malware.
      <span class="scite-citeref-number" data-reference="TrendMicro Patchwork Dec 2017" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" target="_blank">
         [17]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0223">
      POWERSTATS
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0223">
       POWERSTATS
      </a>
      can use DDE to execute additional payloads on compromised hosts.
      <span class="scite-citeref-number" data-reference="FireEye MuddyWater Mar 2018" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html" target="_blank">
         [18]
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
  Registry keys specific to Microsoft Office feature control security can be set to disable automatic DDE/OLE execution.
  <span class="scite-citeref-number" data-reference="Microsoft DDE Advisory Nov 2017" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="https://technet.microsoft.com/library/security/4053440" target="_blank">
     [3]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="BleepingComputer DDE Disabled in Word Dec 2017" id="scite-ref-1-a">
   <sup>
    <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.bleepingcomputer.com/news/microsoft/microsoft-disables-dde-feature-in-word-to-prevent-further-malware-attacks/" target="_blank">
     [1]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="GitHub Disable DDEAUTO Oct 2017" id="scite-ref-19-a">
   <sup>
    <a aria-describedby="qtip-18" data-hasqtip="18" href="https://gist.github.com/wdormann/732bb88d9b5dd5a66c9f1e1498f31a1b" target="_blank">
     [19]
    </a>
   </sup>
  </span>
  Microsoft also created, and enabled by default, Registry keys to completely disable DDE execution in Word and Excel.
  <span class="scite-citeref-number" data-reference="Microsoft ADV170021 Dec 2017" id="scite-ref-2-a">
   <sup>
    <a aria-describedby="qtip-1" data-hasqtip="1" href="https://portal.msrc.microsoft.com/security-guidance/advisory/ADV170021" target="_blank">
     [2]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Ensure Protected View is enabled
  <span class="scite-citeref-number" data-reference="Microsoft Protected View" id="scite-ref-20-a">
   <sup>
    <a aria-describedby="qtip-19" data-hasqtip="19" href="https://support.office.com/en-us/article/What-is-Protected-View-d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653" target="_blank">
     [20]
    </a>
   </sup>
  </span>
  and consider disabling embedded files in Office programs, such as OneNote, not enrolled in Protected View.
  <span class="scite-citeref-number" data-reference="Enigma Reviving DDE Jan 2018" id="scite-ref-6-a">
   <sup>
    <a aria-describedby="qtip-5" data-hasqtip="5" href="https://posts.specterops.io/reviving-dde-using-onenote-and-excel-for-code-execution-d7226864caee" target="_blank">
     [6]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="GitHub Disable DDEAUTO Oct 2017" id="scite-ref-19-a">
   <sup>
    <a aria-describedby="qtip-18" data-hasqtip="18" href="https://gist.github.com/wdormann/732bb88d9b5dd5a66c9f1e1498f31a1b" target="_blank">
     [19]
    </a>
   </sup>
  </span>
 </p>
 <p>
  On Windows 10, enable Attack Surface Reduction (ASR) rules to prevent DDE attacks and spawning of child processes from Office programs.
  <span class="scite-citeref-number" data-reference="Microsoft ASR Nov 2017" id="scite-ref-21-a">
   <sup>
    <a aria-describedby="qtip-20" data-hasqtip="20" href="https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/enable-attack-surface-reduction" target="_blank">
     [21]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Enigma Reviving DDE Jan 2018" id="scite-ref-6-a">
   <sup>
    <a aria-describedby="qtip-5" data-hasqtip="5" href="https://posts.specterops.io/reviving-dde-using-onenote-and-excel-for-code-execution-d7226864caee" target="_blank">
     [6]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  OLE and Office Open XML files can be scanned for ‘DDEAUTO', ‘DDE’, and other strings indicative of DDE execution.
  <span class="scite-citeref-number" data-reference="NVisio Labs DDE Detection Oct 2017" id="scite-ref-22-a">
   <sup>
    <a aria-describedby="qtip-21" data-hasqtip="21" href="https://blog.nviso.be/2017/10/11/detecting-dde-in-ms-office-documents/" target="_blank">
     [22]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Monitor for Microsoft Office applications loading DLLs and other modules not typically associated with the application.
 </p>
 <p>
  Monitor for spawning of unusual processes (such as cmd.exe) from Microsoft Office applications.
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
       <a class="external text" href="https://www.bleepingcomputer.com/news/microsoft/microsoft-disables-dde-feature-in-word-to-prevent-further-malware-attacks/" name="scite-1" rel="nofollow" target="_blank">
        Cimpanu, C. (2017, December 15). Microsoft Disables DDE Feature in Word to Prevent Further Malware Attacks. Retrieved December 19, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://portal.msrc.microsoft.com/security-guidance/advisory/ADV170021" name="scite-2" rel="nofollow" target="_blank">
        Microsoft. (2017, December 12). ADV170021 - Microsoft Office Defense in Depth Update. Retrieved February 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/library/security/4053440" name="scite-3" rel="nofollow" target="_blank">
        Microsoft. (2017, November 8). Microsoft Security Advisory 4053440 - Securely opening Microsoft Office documents that contain Dynamic Data Exchange (DDE) fields. Retrieved November 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://sensepost.com/blog/2016/powershell-c-sharp-and-dde-the-power-within/" name="scite-4" rel="nofollow" target="_blank">
        El-Sherei, S. (2016, May 20). PowerShell, C-Sharp and DDE The Power Within. Retrieved November 22, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.contextis.com/blog/comma-separated-vulnerabilities" name="scite-5" rel="nofollow" target="_blank">
        Kettle, J. (2014, August 29). Comma Separated Vulnerabilities. Retrieved November 22, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://posts.specterops.io/reviving-dde-using-onenote-and-excel-for-code-execution-d7226864caee" name="scite-6" rel="nofollow" target="_blank">
        Nelson, M. (2018, January 29). Reviving DDE: Using OneNote and Excel for Code Execution. Retrieved February 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://sensepost.com/blog/2017/macro-less-code-exec-in-msword/" name="scite-7" rel="nofollow" target="_blank">
        Stalmans, E., El-Sherei, S. (2017, October 9). Macro-less Code Exec in MSWord. Retrieved November 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/apt28-threat-group-adopts-dde-technique-nyc-attack-theme-in-latest-campaign/" name="scite-8" rel="nofollow" target="_blank">
        Sherstobitoff, R., Rea, M. (2017, November 7). Threat Group APT28 Slips Office Malware into Doc Citing NYC Terror Attack. Retrieved November 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="http://securityaffairs.co/wordpress/65318/hacking/dde-attack-apt28.html" name="scite-9" rel="nofollow" target="_blank">
        Paganini, P. (2017, November 9). Russia-Linked APT28 group observed using DDE attack to deliver malware. Retrieved November 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-sofacy-groups-parallel-attacks/" name="scite-10" rel="nofollow" target="_blank">
        Lee, B., Falcone, R. (2018, June 06). Sofacy Group’s Parallel Attacks. Retrieved June 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/operation-daybreak/75100/" name="scite-11" rel="nofollow" target="_blank">
        Raiu, C., and Ivanov, A. (2016, June 17). Operation Daybreak. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="12.0">
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/07/multiple-cobalt-personality-disorder.html" name="scite-12" rel="nofollow" target="_blank">
        Svajcer, V. (2018, July 31). Multiple Cobalt Personality Disorder. Retrieved September 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cyberscoop.com/fin7-dde-morphisec-fileless-malware/" name="scite-13" rel="nofollow" target="_blank">
        Waterman, S. (2017, October 16). Fin7 weaponization of DDE is just their latest slick move, say researchers. Retrieved November 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/gallmaker-attack-group" name="scite-14" rel="nofollow" target="_blank">
        Symantec Security Response. (2018, October 10). Gallmaker: New Attack Group Eschews Malware to Live off the Land. Retrieved November 27, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/04/gravityrat-two-year-evolution-of-apt.html" name="scite-15" rel="nofollow" target="_blank">
        Mercer, W., Rascagneres, P. (2018, April 26). GravityRAT - The Two-Year Evolution Of An APT Targeting India. Retrieved May 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/muddywater/88059/" name="scite-16" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research &amp; Analysis Team. (2018, October 10). MuddyWater expands operations. Retrieved November 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" name="scite-17" rel="nofollow" target="_blank">
        Lunghi, D., et al. (2017, December). Untangling the Patchwork Cyberespionage Group. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html" name="scite-18" rel="nofollow" target="_blank">
        Singh, S. et al.. (2018, March 13). Iranian Threat Group Updates Tactics, Techniques and Procedures in Spear Phishing Campaign. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://gist.github.com/wdormann/732bb88d9b5dd5a66c9f1e1498f31a1b" name="scite-19" rel="nofollow" target="_blank">
        Dormann, W. (2017, October 20). Disable DDEAUTO for Outlook, Word, OneNote, and Excel versions 2010, 2013, 2016. Retrieved February 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://support.office.com/en-us/article/What-is-Protected-View-d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653" name="scite-20" rel="nofollow" target="_blank">
        Microsoft. (n.d.). What is Protected View?. Retrieved November 22, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/enable-attack-surface-reduction" name="scite-21" rel="nofollow" target="_blank">
        Brower, N. &amp; D'Souza-Wiltshire, I. (2017, November 9). Enable Attack surface reduction. Retrieved February 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.nviso.be/2017/10/11/detecting-dde-in-ms-office-documents/" name="scite-22" rel="nofollow" target="_blank">
        NVISO Labs. (2017, October 11). Detecting DDE in MS Office documents. Retrieved November 21, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
