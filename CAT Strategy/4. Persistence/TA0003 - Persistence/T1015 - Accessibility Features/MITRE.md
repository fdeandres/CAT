<div class="container-fluid">
 <h1>
  Accessibility Features
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Windows contains accessibility features that may be launched with a key combination before a user has logged in (for example, when the user is on the Windows logon screen). An adversary can modify the way these programs are launched to get a command prompt or backdoor without logging in to the system.
   </p>
   <p>
    Two common accessibility programs are
    <code>
     C:\Windows\System32\sethc.exe
    </code>
    , launched when the shift key is pressed five times and
    <code>
     C:\Windows\System32\utilman.exe
    </code>
    , launched when the Windows + U key combination is pressed. The sethc.exe program is often referred to as "sticky keys", and has been used by adversaries for unauthenticated access through a remote desktop login screen.
    <span class="scite-citeref-number" data-reference="FireEye Hikit Rootkit" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.fireeye.com/blog/threat-research/2012/08/hikit-rootkit-advanced-persistent-attack-techniques-part-1.html" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Depending on the version of Windows, an adversary may take advantage of these features in different ways because of code integrity enhancements. In newer versions of Windows, the replaced binary needs to be digitally signed for x64 systems, the binary must reside in
    <code>
     %systemdir%\
    </code>
    , and it must be protected by Windows File or Resource Protection (WFP/WRP).
    <span class="scite-citeref-number" data-reference="DEFCON2016 Sticky Keys" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.slideshare.net/DennisMaldonado5/sticky-keys-to-the-kingdom" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    The debugger method was likely discovered as a potential workaround because it does not require the corresponding accessibility feature binary to be replaced. Examples for both methods:
   </p>
   <p>
    For simple binary replacement on Windows XP and later as well as and Windows Server 2003/R2 and later, for example, the program (e.g.,
    <code>
     C:\Windows\System32\utilman.exe
    </code>
    ) may be replaced with "cmd.exe" (or another program that provides backdoor access). Subsequently, pressing the appropriate key combination at the login screen while sitting at the keyboard or when connected over
    <a href="https://attack.mitre.org/techniques/T1076">
     Remote Desktop Protocol
    </a>
    will cause the replaced file to be executed with SYSTEM privileges.
    <span class="scite-citeref-number" data-reference="Tilbury 2014" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="http://blog.crowdstrike.com/registry-analysis-with-crowdresponse/" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    For the debugger method on Windows Vista and later as well as Windows Server 2008 and later, for example, a Registry key may be modified that configures "cmd.exe," or another program that provides backdoor access, as a "debugger" for the accessibility program (e.g., "utilman.exe"). After the Registry is modified, pressing the appropriate key combination at the login screen while at the keyboard or when connected with RDP will cause the "debugger" program to be executed with SYSTEM privileges.
    <span class="scite-citeref-number" data-reference="Tilbury 2014" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="http://blog.crowdstrike.com/registry-analysis-with-crowdresponse/" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Other accessibility features exist that may also be leveraged in a similar fashion:
    <span class="scite-citeref-number" data-reference="DEFCON2016 Sticky Keys" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.slideshare.net/DennisMaldonado5/sticky-keys-to-the-kingdom" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <ul>
    <li>
     On-Screen Keyboard:
     <code>
      C:\Windows\System32\osk.exe
     </code>
    </li>
    <li>
     Magnifier:
     <code>
      C:\Windows\System32\Magnify.exe
     </code>
    </li>
    <li>
     Narrator:
     <code>
      C:\Windows\System32\Narrator.exe
     </code>
    </li>
    <li>
     Display Switcher:
     <code>
      C:\Windows\System32\DisplaySwitch.exe
     </code>
    </li>
    <li>
     App Switcher:
     <code>
      C:\Windows\System32\AtBroker.exe
     </code>
    </li>
   </ul>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1015
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
      Administrator
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
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       CAPEC ID:
      </span>
      <a href="https://capec.mitre.org/data/definitions/558.html" target="_blank">
       CAPEC-558
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
      Paul Speulstra, AECOM Global Security Operations Center
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
     <a href="https://attack.mitre.org/groups/G0016">
      APT29
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0016">
       APT29
      </a>
      used sticky-keys to obtain unauthenticated, privileged console access.
      <span class="scite-citeref-number" data-reference="Mandiant No Easy Breach" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="http://www.slideshare.net/MatthewDunwoody1/no-easy-breach-derby-con-2016" target="_blank">
         [4]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye APT29 Domain Fronting" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.fireeye.com/blog/threat-research/2017/03/apt29_domain_frontin.html" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0022">
      APT3
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0022">
       APT3
      </a>
      replaces the Sticky Keys binary
      <code>
       C:\Windows\System32\sethc.exe
      </code>
      for persistence.
      <span class="scite-citeref-number" data-reference="aptsim" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="http://carnal0wnage.attackresearch.com/2012/09/more-on-aptsim.html" target="_blank">
         [6]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0001">
      Axiom
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0001">
       Axiom
      </a>
      actors have been known to use the Sticky Keys replacement within RDP sessions to obtain persistence.
      <span class="scite-citeref-number" data-reference="Novetta-Axiom" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="http://www.novetta.com/wp-content/uploads/2014/11/Executive_Summary-Final_1.pdf" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0009">
      Deep Panda
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0009">
       Deep Panda
      </a>
      has used the sticky-keys technique to bypass the RDP login screen on remote systems during intrusions.
      <span class="scite-citeref-number" data-reference="RSA Shell Crew" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.emc.com/collateral/white-papers/h12756-wp-shell-crew.pdf" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0363">
      Empire
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0363">
       Empire
      </a>
      can leverage WMI debugging to remotely replace binaries like sethc.exe, Utilman.exe, and Magnify.exe with cmd.exe.
      <span class="scite-citeref-number" data-reference="Github PowerShell Empire" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://github.com/PowerShellEmpire/Empire" target="_blank">
         [9]
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
  To use this technique remotely, an adversary must use it in conjunction with RDP. Ensure that Network Level Authentication is enabled to force the remote desktop session to authenticate before the session is created and the login screen displayed. It is enabled by default on Windows Vista and later.
  <span class="scite-citeref-number" data-reference="TechNet RDP NLA" id="scite-ref-10-a">
   <sup>
    <a aria-describedby="qtip-9" data-hasqtip="9" href="https://technet.microsoft.com/en-us/library/cc732713.aspx" target="_blank">
     [10]
    </a>
   </sup>
  </span>
 </p>
 <p>
  If possible, use a Remote Desktop Gateway to manage connections and security configuration of RDP within a network.
  <span class="scite-citeref-number" data-reference="TechNet RDP Gateway" id="scite-ref-11-a">
   <sup>
    <a aria-describedby="qtip-10" data-hasqtip="10" href="https://technet.microsoft.com/en-us/library/cc731150.aspx" target="_blank">
     [11]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Identify and block potentially malicious software that may be executed by an adversary with this technique by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-12-a">
   <sup>
    <a aria-describedby="qtip-11" data-hasqtip="11" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [12]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-13-a">
   <sup>
    <a aria-describedby="qtip-12" data-hasqtip="12" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [13]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-14-a">
   <sup>
    <a aria-describedby="qtip-13" data-hasqtip="13" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [14]
    </a>
   </sup>
  </span>
  or Software Restriction Policies
  <span class="scite-citeref-number" data-reference="Corio 2008" id="scite-ref-15-a">
   <sup>
    <a aria-describedby="qtip-14" data-hasqtip="14" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" target="_blank">
     [15]
    </a>
   </sup>
  </span>
  where appropriate.
  <span class="scite-citeref-number" data-reference="TechNet Applocker vs SRP" id="scite-ref-16-a">
   <sup>
    <a aria-describedby="qtip-15" data-hasqtip="15" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" target="_blank">
     [16]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Changes to accessibility utility binaries or binary paths that do not correlate with known software, patch cycles, etc., are suspicious. Command line invocation of tools capable of modifying the Registry for associated keys are also suspicious. Utility arguments and the binaries themselves should be monitored for changes. Monitor Registry keys within
  <code>
   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options
  </code>
  .
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
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2012/08/hikit-rootkit-advanced-persistent-attack-techniques-part-1.html" name="scite-1" rel="nofollow" target="_blank">
        Glyer, C., Kazanciyan, R. (2012, August 20). THE “HIKIT” ROOTKIT: ADVANCED AND PERSISTENT ATTACK TECHNIQUES (PART 1). Retrieved June 6, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.slideshare.net/DennisMaldonado5/sticky-keys-to-the-kingdom" name="scite-2" rel="nofollow" target="_blank">
        Maldonado, D., McGuffin, T. (2016, August 6). Sticky Keys to the Kingdom. Retrieved July 5, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.crowdstrike.com/registry-analysis-with-crowdresponse/" name="scite-3" rel="nofollow" target="_blank">
        Tilbury, C. (2014, August 28). Registry Analysis with CrowdResponse. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.slideshare.net/MatthewDunwoody1/no-easy-breach-derby-con-2016" name="scite-4" rel="nofollow" target="_blank">
        Dunwoody, M. and Carr, N.. (2016, September 27). No Easy Breach DerbyCon 2016. Retrieved October 4, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/03/apt29_domain_frontin.html" name="scite-5" rel="nofollow" target="_blank">
        Dunwoody, M. (2017, March 27). APT29 Domain Fronting With TOR. Retrieved March 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="http://carnal0wnage.attackresearch.com/2012/09/more-on-aptsim.html" name="scite-6" rel="nofollow" target="_blank">
        valsmith. (2012, September 21). More on APTSim. Retrieved September 28, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.novetta.com/wp-content/uploads/2014/11/Executive_Summary-Final_1.pdf" name="scite-7" rel="nofollow" target="_blank">
        Novetta. (n.d.). Operation SMN: Axiom Threat Actor Group Report. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.emc.com/collateral/white-papers/h12756-wp-shell-crew.pdf" name="scite-8" rel="nofollow" target="_blank">
        RSA Incident Response. (2014, January). RSA Incident Response Emerging Threat Profile: Shell Crew. Retrieved January 14, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="9.0">
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellEmpire/Empire" name="scite-9" rel="nofollow" target="_blank">
        Schroeder, W., Warner, J., Nelson, M. (n.d.). Github PowerShellEmpire. Retrieved April 28, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/cc732713.aspx" name="scite-10" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Configure Network Level Authentication for Remote Desktop Services Connections. Retrieved June 6, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/cc731150.aspx" name="scite-11" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Overview of Remote Desktop Gateway. Retrieved June 6, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-12" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-13" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-14" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" name="scite-15" rel="nofollow" target="_blank">
        Corio, C., &amp; Sayana, D. P. (2008, June). Application Lockdown with Software Restriction Policies. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" name="scite-16" rel="nofollow" target="_blank">
        Microsoft. (2012, June 27). Using Software Restriction Policies and AppLocker Policies. Retrieved April 7, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
