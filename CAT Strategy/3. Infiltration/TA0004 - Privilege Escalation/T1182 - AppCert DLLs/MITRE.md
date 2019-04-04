<div class="container-fluid">
 <h1>
  AppCert DLLs
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Dynamic-link libraries (DLLs) that are specified in the AppCertDLLs value in the Registry key
    <code>
     HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Session Manager
    </code>
    are loaded into every process that calls the ubiquitously used application programming interface (API) functions:
    <span class="scite-citeref-number" data-reference="Endgame Process Injection July 2017" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <ul>
    <li>
     CreateProcess
    </li>
    <li>
     CreateProcessAsUser
    </li>
    <li>
     CreateProcessWithLoginW
    </li>
    <li>
     CreateProcessWithTokenW
    </li>
    <li>
     WinExec
    </li>
   </ul>
   <p>
    Similar to
    <a href="https://attack.mitre.org/techniques/T1055">
     Process Injection
    </a>
    , this value can be abused to obtain persistence and privilege escalation by causing a malicious DLL to be loaded and run in the context of separate processes on the computer.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1182
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
      Administrator, SYSTEM
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      Loaded DLLs, Process monitoring, Windows Registry
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
     <a href="https://attack.mitre.org/groups/G0072">
      Honeybee
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0072">
       Honeybee
      </a>
      's service-based DLL implant can execute a downloaded file with parameters specified using
      <code>
       CreateProcessAsUser
      </code>
      .
      <span class="scite-citeref-number" data-reference="McAfee Honeybee" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://securingtomorrow.mcafee.com/mcafee-labs/mcafee-uncovers-operation-honeybee-malicious-document-campaign-targeting-humanitarian-aid-groups/" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0196">
      PUNCHBUGGY
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0196">
       PUNCHBUGGY
      </a>
      can establish using a AppCertDLLs Registry key.
      <span class="scite-citeref-number" data-reference="FireEye Know Your Enemy FIN8 Aug 2016" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" target="_blank">
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
  Identify and block potentially malicious software that may be executed through AppCert DLLs by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [4]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-5-a">
   <sup>
    <a aria-describedby="qtip-4" data-hasqtip="4" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [5]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-6-a">
   <sup>
    <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [6]
    </a>
   </sup>
  </span>
  that are capable of auditing and/or blocking unknown DLLs.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor DLL loads by processes, specifically looking for DLLs that are not recognized or not normally loaded into a process. Monitor the AppCertDLLs Registry value for modifications that do not correlate with known software, patch cycles, etc. Monitor and analyze application programming interface (API) calls that are indicative of Registry edits such as RegCreateKeyEx and RegSetValueEx.
  <span class="scite-citeref-number" data-reference="Endgame Process Injection July 2017" id="scite-ref-1-a">
   <sup>
    <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process" target="_blank">
     [1]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Tools such as Sysinternals Autoruns may overlook AppCert DLLs as an auto-starting location.
  <span class="scite-citeref-number" data-reference="TechNet Autoruns" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://technet.microsoft.com/en-us/sysinternals/bb963902" target="_blank">
     [7]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Sysinternals AppCertDlls Oct 2007" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="https://forum.sysinternals.com/appcertdlls_topic12546.html" target="_blank">
     [8]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Look for abnormal process behavior that may be due to a process loading a malicious DLL. Data and events should not be viewed in isolation, but as part of a chain of behavior that could lead to other activities, such as making network connections for Command and Control, learning details about the environment through Discovery, and conducting Lateral Movement.
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
       <a class="external text" href="https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process" name="scite-1" rel="nofollow" target="_blank">
        Hosseini, A. (2017, July 18). Ten Process Injection Techniques: A Technical Survey Of Common And Trending Process Injection Techniques. Retrieved December 7, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/mcafee-uncovers-operation-honeybee-malicious-document-campaign-targeting-humanitarian-aid-groups/" name="scite-2" rel="nofollow" target="_blank">
        Sherstobitoff, R. (2018, March 02). McAfee Uncovers Operation Honeybee, a Malicious Document Campaign Targeting Humanitarian Aid Groups. Retrieved May 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" name="scite-3" rel="nofollow" target="_blank">
        Elovitz, S. &amp; Ahl, I. (2016, August 18). Know Your Enemy:  New Financially-Motivated &amp; Spear-Phishing Group. Retrieved February 26, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-4" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
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
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-5" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-6" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/sysinternals/bb963902" name="scite-7" rel="nofollow" target="_blank">
        Russinovich, M. (2016, January 4). Autoruns for Windows v13.51. Retrieved June 6, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://forum.sysinternals.com/appcertdlls_topic12546.html" name="scite-8" rel="nofollow" target="_blank">
        Microsoft. (2007, October 24). Windows Sysinternals - AppCertDlls. Retrieved December 18, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
