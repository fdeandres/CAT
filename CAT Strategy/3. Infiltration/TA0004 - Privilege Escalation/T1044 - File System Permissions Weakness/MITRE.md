<div class="container-fluid">
 <h1>
  File System Permissions Weakness
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Processes may automatically execute specific binaries as part of their functionality or to perform other actions. If the permissions on the file system directory containing a target binary, or permissions on the binary itself, are improperly set, then the target binary may be overwritten with another binary using user-level permissions and executed by the original process. If the original process and thread are running under a higher permissions level, then the replaced binary will also execute under higher-level permissions, which could include SYSTEM.
   </p>
   <p>
    Adversaries may use this technique to replace legitimate binaries with malicious ones as a means of executing code at a higher permissions level. If the executing process is set to run at a specific time or during a certain event (e.g., system bootup) then this technique can also be used for persistence.
   </p>
   <h3>
    Services
   </h3>
   <p>
    Manipulation of Windows service binaries is one variation of this technique. Adversaries may replace a legitimate service executable with their own executable to gain persistence and/or privilege escalation to the account context the service is set to execute under (local/domain account, SYSTEM, LocalService, or NetworkService). Once the service is started, either directly by the user (if appropriate access is available) or through some other means, such as a system restart if the service starts on bootup, the replaced executable will run instead of the original service executable.
   </p>
   <h3>
    Executable Installers
   </h3>
   <p>
    Another variation of this technique can be performed by taking advantage of a weakness that is common in executable, self-extracting installers. During the installation process, it is common for installers to use a subdirectory within the
    <code>
     %TEMP%
    </code>
    directory to unpack binaries such as DLLs, EXEs, or other payloads. When installers create subdirectories and files they often do not set appropriate permissions to restrict write access, which allows for execution of untrusted code placed in the subdirectories or overwriting of binaries used in the installation process. This behavior is related to and may take advantage of
    <a href="https://attack.mitre.org/techniques/T1038">
     DLL Search Order Hijacking
    </a>
    . Some installers may also require elevated privileges that will result in privilege escalation when executing adversary controlled code. This behavior is related to
    <a href="https://attack.mitre.org/techniques/T1088">
     Bypass User Account Control
    </a>
    . Several examples of this weakness in existing common installers have been reported to software vendors.
    <span class="scite-citeref-number" data-reference="Mozilla Firefox Installer DLL Hijack" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.mozilla.org/en-US/security/advisories/mfsa2012-98/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Seclists Kanthak 7zip Installer" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="http://seclists.org/fulldisclosure/2015/Dec/34" target="_blank">
       [2]
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
      : T1044
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
      Administrator, User
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Effective Permissions:
      </span>
      SYSTEM, User, Administrator
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      File monitoring, Services, Process command-line parameters
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
      <a href="https://capec.mitre.org/data/definitions/17.html" target="_blank">
       CAPEC-17
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
     <a href="https://attack.mitre.org/software/S0089">
      BlackEnergy
     </a>
    </td>
    <td>
     <p>
      One variant of
      <a href="https://attack.mitre.org/software/S0089">
       BlackEnergy
      </a>
      locates existing driver services that have been disabled and drops its driver component into one of those service's paths, replacing the legitimate executable. The malware then sets the hijacked service to start automatically to establish persistence.
      <span class="scite-citeref-number" data-reference="F-Secure BlackEnergy 2014" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.f-secure.com/documents/996508/1030745/blackenergy_whitepaper.pdf" target="_blank">
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
  Use auditing tools capable of detecting file system permissions abuse opportunities on systems within an enterprise and correct them. Limit privileges of user accounts and groups so that only authorized administrators can interact with service changes and service binary target path locations. Toolkits like the PowerSploit framework contain PowerUp modules that can be used to explore systems for service file system permissions weaknesses.
  <span class="scite-citeref-number" data-reference="Powersploit" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="https://github.com/mattifestation/PowerSploit" target="_blank">
     [4]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Identify and block potentially malicious software that may be executed through abuse of file, directory, and service permissions by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-5-a">
   <sup>
    <a aria-describedby="qtip-4" data-hasqtip="4" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [5]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
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
  that are capable of auditing and/or blocking unknown programs. Deny execution from user directories such as file download directories and temp directories where able.
  <span class="scite-citeref-number" data-reference="Seclists Kanthak 7zip Installer" id="scite-ref-2-a">
   <sup>
    <a aria-describedby="qtip-1" data-hasqtip="1" href="http://seclists.org/fulldisclosure/2015/Dec/34" target="_blank">
     [2]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Turn off UAC's privilege elevation for standard users
  <code>
   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System]
  </code>
  to automatically deny elevation requests, add:
  <code>
   "ConsentPromptBehaviorUser"=dword:00000000
  </code>
  <span class="scite-citeref-number" data-reference="Seclists Kanthak 7zip Installer" id="scite-ref-2-a">
   <sup>
    <a aria-describedby="qtip-1" data-hasqtip="1" href="http://seclists.org/fulldisclosure/2015/Dec/34" target="_blank">
     [2]
    </a>
   </sup>
  </span>
  . Consider enabling installer detection for all users by adding:
  <code>
   "EnableInstallerDetection"=dword:00000001
  </code>
  . This will prompt for a password for installation and also log the attempt. To disable installer detection, instead add:
  <code>
   "EnableInstallerDetection"=dword:00000000
  </code>
  . This may prevent potential elevation of privileges through exploitation during the process of UAC detecting the installer, but will allow the installation process to continue without being logged.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Look for changes to binaries and service executables that may normally occur during software updates. If an executable is written, renamed, and/or moved to match an existing service executable, it could be detected and correlated with other suspicious behavior. Hashing of binaries and service executables could be used to detect replacement against historical data.
 </p>
 <p>
  Look for abnormal process call trees from typical processes and services and for execution of other commands that could relate to Discovery or other adversary techniques.
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
       <a class="external text" href="https://www.mozilla.org/en-US/security/advisories/mfsa2012-98/" name="scite-1" rel="nofollow" target="_blank">
        Kugler, R. (2012, November 20). Mozilla Foundation Security Advisory 2012-98. Retrieved March 10, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://seclists.org/fulldisclosure/2015/Dec/34" name="scite-2" rel="nofollow" target="_blank">
        Kanthak, S. (2015, December 8). Executable installers are vulnerable^WEVIL (case 7): 7z*.exe allows remote code execution with escalation of privilege. Retrieved March 10, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.f-secure.com/documents/996508/1030745/blackenergy_whitepaper.pdf" name="scite-3" rel="nofollow" target="_blank">
        F-Secure Labs. (2014). BlackEnergy &amp; Quedagh: The convergence of crimeware and APT attacks. Retrieved March 24, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/mattifestation/PowerSploit" name="scite-4" rel="nofollow" target="_blank">
        PowerSploit. (n.d.). Retrieved December 4, 2014.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="5.5">
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
   </ol>
  </div>
 </div>
</div>
