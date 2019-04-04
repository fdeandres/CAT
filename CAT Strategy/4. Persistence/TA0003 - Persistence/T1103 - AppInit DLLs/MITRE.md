<div class="container-fluid">
 <h1>
  AppInit DLLs
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Dynamic-link libraries (DLLs) that are specified in the AppInit_DLLs value in the Registry keys
    <code>
     HKEY_LOCAL_MACHINE\Software\Microsoft\Windows NT\CurrentVersion\Windows
    </code>
    or
    <code>
     HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Windows NT\CurrentVersion\Windows
    </code>
    are loaded by user32.dll into every process that loads user32.dll. In practice this is nearly every program, since user32.dll is a very common library.
    <span class="scite-citeref-number" data-reference="Endgame Process Injection July 2017" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    Similar to
    <a href="https://attack.mitre.org/techniques/T1055">
     Process Injection
    </a>
    , these values can be abused to obtain persistence and privilege escalation by causing a malicious DLL to be loaded and run in the context of separate processes on the computer.
    <span class="scite-citeref-number" data-reference="AppInit Registry" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://support.microsoft.com/en-us/kb/197571" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    The AppInit DLL functionality is disabled in Windows 8 and later versions when secure boot is enabled.
    <span class="scite-citeref-number" data-reference="AppInit Secure Boot" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://msdn.microsoft.com/en-us/library/dn280412" target="_blank">
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
      : T1103
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
      Administrator
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
     <a href="https://attack.mitre.org/software/S0107">
      Cherry Picker
     </a>
    </td>
    <td>
     <p>
      Some variants of
      <a href="https://attack.mitre.org/software/S0107">
       Cherry Picker
      </a>
      use AppInit_DLLs to achieve persistence by creating the following Registry key:
      <code>
       HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Windows "AppInit_DLLs"="pserver32.dll"
      </code>
      <span class="scite-citeref-number" data-reference="Trustwave Cherry Picker" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.trustwave.com/Resources/SpiderLabs-Blog/Shining-the-Spotlight-on-Cherry-Picker-PoS-Malware/" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0098">
      T9000
     </a>
    </td>
    <td>
     <p>
      If a victim meets certain criteria,
      <a href="https://attack.mitre.org/software/S0098">
       T9000
      </a>
      uses the AppInit_DLL functionality to achieve persistence by ensuring that every user mode process that is spawned will load its malicious DLL, ResN32.dll. It does this by creating the following Registry keys:
      <code>
       HKLM\Software\Microsoft\Windows NT\CurrentVersion\Windows\AppInit_DLLs – %APPDATA%\Intel\ResN32.dll
      </code>
      and
      <code>
       HKLM\Software\Microsoft\Windows NT\CurrentVersion\Windows\LoadAppInit_DLLs – 0x1
      </code>
      .
      <span class="scite-citeref-number" data-reference="Palo Alto T9000 Feb 2016" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="http://researchcenter.paloaltonetworks.com/2016/02/t9000-advanced-modular-backdoor-uses-complex-anti-analysis-techniques/" target="_blank">
         [5]
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
  Upgrade to Windows 8 or later and enable secure boot.
 </p>
 <p>
  Identify and block potentially malicious software that may be executed through AppInit DLLs by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-6-a">
   <sup>
    <a aria-describedby="qtip-5" data-hasqtip="5" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [6]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [7]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [8]
    </a>
   </sup>
  </span>
  that are capable of auditing and/or blocking unknown DLLs.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor DLL loads by processes that load user32.dll and look for DLLs that are not recognized or not normally loaded into a process. Monitor the AppInit_DLLs Registry values for modifications that do not correlate with known software, patch cycles, etc. Monitor and analyze application programming interface (API) calls that are indicative of Registry edits such as RegCreateKeyEx and RegSetValueEx.
  <span class="scite-citeref-number" data-reference="Endgame Process Injection July 2017" id="scite-ref-1-a">
   <sup>
    <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process" target="_blank">
     [1]
    </a>
   </sup>
  </span>
  Tools such as Sysinternals Autoruns may also be used to detect system changes that could be attempts at persistence, including listing current AppInit DLLs.
  <span class="scite-citeref-number" data-reference="TechNet Autoruns" id="scite-ref-9-a">
   <sup>
    <a aria-describedby="qtip-8" data-hasqtip="8" href="https://technet.microsoft.com/en-us/sysinternals/bb963902" target="_blank">
     [9]
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
       <a class="external text" href="https://support.microsoft.com/en-us/kb/197571" name="scite-2" rel="nofollow" target="_blank">
        Microsoft. (2006, October). Working with the AppInit_DLLs registry value. Retrieved July 15, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/en-us/library/dn280412" name="scite-3" rel="nofollow" target="_blank">
        Microsoft. (n.d.). AppInit DLLs and Secure Boot. Retrieved July 15, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.trustwave.com/Resources/SpiderLabs-Blog/Shining-the-Spotlight-on-Cherry-Picker-PoS-Malware/" name="scite-4" rel="nofollow" target="_blank">
        Merritt, E.. (2015, November 16). Shining the Spotlight on Cherry Picker PoS Malware. Retrieved April 20, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/02/t9000-advanced-modular-backdoor-uses-complex-anti-analysis-techniques/" name="scite-5" rel="nofollow" target="_blank">
        Grunzweig, J. and Miller-Osborn, J.. (2016, February 4). T9000: Advanced Modular Backdoor Uses Complex Anti-Analysis Techniques. Retrieved April 15, 2016.
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
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-6" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-7" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-8" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
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
