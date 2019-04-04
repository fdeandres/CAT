<div class="container-fluid">
 <h1>
  Winlogon Helper DLL
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Winlogon.exe is a Windows component responsible for actions at logon/logoff as well as the secure attention sequence (SAS) triggered by Ctrl-Alt-Delete. Registry entries in
    <code>
     HKLM\Software[Wow6432Node]Microsoft\Windows NT\CurrentVersion\Winlogon\
    </code>
    and
    <code>
     HKCU\Software\Microsoft\Windows NT\CurrentVersion\Winlogon\
    </code>
    are used to manage additional helper programs and functionalities that support Winlogon.
    <span class="scite-citeref-number" data-reference="Cylance Reg Persistence Sept 2013" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://blog.cylance.com/windows-registry-persistence-part-2-the-run-keys-and-search-order" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Malicious modifications to these Registry keys may cause Winlogon to load and execute malicious DLLs and/or executables. Specifically, the following subkeys have been known to be possibly vulnerable to abuse:
    <span class="scite-citeref-number" data-reference="Cylance Reg Persistence Sept 2013" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://blog.cylance.com/windows-registry-persistence-part-2-the-run-keys-and-search-order" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <ul>
    <li>
     Winlogon\Notify - points to notification package DLLs that handle Winlogon events
    </li>
    <li>
     Winlogon\Userinit - points to userinit.exe, the user initialization program executed when a user logs on
    </li>
    <li>
     Winlogon\Shell - points to explorer.exe, the system shell executed when a user logs on
    </li>
   </ul>
   <p>
    Adversaries may take advantage of these features to repeatedly execute malicious code and establish Persistence.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1004
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
      : Persistence
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
      Windows Registry, File monitoring, Process monitoring
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
       CAPEC ID:
      </span>
      <a href="https://capec.mitre.org/data/definitions/579.html" target="_blank">
       CAPEC-579
      </a>
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Contributors:
      </span>
      Praetorian
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
     <a href="https://attack.mitre.org/software/S0200">
      Dipsind
     </a>
    </td>
    <td>
     <p>
      A
      <a href="https://attack.mitre.org/software/S0200">
       Dipsind
      </a>
      variant registers as a Winlogon Event Notify DLL to establish persistence.
      <span class="scite-citeref-number" data-reference="Microsoft PLATINUM April 2016" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0168">
      Gazer
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0168">
       Gazer
      </a>
      can establish persistence by setting the value "Shell" with "explorer.exe, %malware_pathfile%" under the Registry key
      <code>
       HKCU\Software\Microsoft\Windows NT\CurrentVersion\Winlogon
      </code>
      .
      <span class="scite-citeref-number" data-reference="ESET Gazer Aug 2017" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0010">
      Turla
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0010">
       Turla
      </a>
      established persistence by adding a Shell value under the Registry key
      <code>
       HKCU\Software\Microsoft\Windows NT\CurrentVersion]Winlogon
      </code>
      .
      <span class="scite-citeref-number" data-reference="ESET Turla Mosquito Jan 2018" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.welivesecurity.com/wp-content/uploads/2018/01/ESET_Turla_Mosquito.pdf" target="_blank">
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
  Limit the privileges of user accounts so that only authorized administrators can perform Winlogon helper changes.
 </p>
 <p>
  Identify and block potentially malicious software that may be executed through the Winlogon helper process by using whitelisting
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
  that are capable of auditing and/or blocking unknown DLLs.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor for changes to Registry entries associated with Winlogon that do not correlate with known software, patch cycles, etc. Tools such as Sysinternals Autoruns may also be used to detect system changes that could be attempts at persistence, including listing current Winlogon helper values.
  <span class="scite-citeref-number" data-reference="TechNet Autoruns" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="https://technet.microsoft.com/en-us/sysinternals/bb963902" target="_blank">
     [8]
    </a>
   </sup>
  </span>
  New DLLs written to System32 that do not correlate with known good software or patching may also be suspicious.
 </p>
 <p>
  Look for abnormal process behavior that may be due to a process loading a malicious DLL. Data and events should not be viewed in isolation, but as part of a chain of behavior that could lead to other activities, such as network connections made for Command and Control, learning details about the environment through Discovery, and Lateral Movement.
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
       <a class="external text" href="https://blog.cylance.com/windows-registry-persistence-part-2-the-run-keys-and-search-order" name="scite-1" rel="nofollow" target="_blank">
        Langendorf, S. (2013, September 24). Windows Registry Persistence, Part 2: The Run Keys and Search-Order. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" name="scite-2" rel="nofollow" target="_blank">
        Windows Defender Advanced Threat Hunting Team. (2016, April 29). PLATINUM: Targeted attacks in South and Southeast Asia. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf" name="scite-3" rel="nofollow" target="_blank">
        ESET. (2017, August). Gazing at Gazer: Turla’s new second stage backdoor. Retrieved September 14, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2018/01/ESET_Turla_Mosquito.pdf" name="scite-4" rel="nofollow" target="_blank">
        ESET, et al. (2018, January). Diplomats in Eastern Europe bitten by a Turla mosquito. Retrieved July 3, 2018.
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
       <a class="external text" href="https://technet.microsoft.com/en-us/sysinternals/bb963902" name="scite-8" rel="nofollow" target="_blank">
        Russinovich, M. (2016, January 4). Autoruns for Windows v13.51. Retrieved June 6, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
