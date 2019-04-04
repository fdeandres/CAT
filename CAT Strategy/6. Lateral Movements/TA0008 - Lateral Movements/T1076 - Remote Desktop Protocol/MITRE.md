<div class="container-fluid">
 <h1>
  Remote Desktop Protocol
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Remote desktop is a common feature in operating systems. It allows a user to log into an interactive session with a system desktop graphical user interface on a remote system. Microsoft refers to its implementation of the Remote Desktop Protocol (RDP) as Remote Desktop Services (RDS).
    <span class="scite-citeref-number" data-reference="TechNet Remote Desktop Services" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://technet.microsoft.com/en-us/windowsserver/ee236407.aspx" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    There are other implementations and third-party tools that provide graphical access
    <a href="https://attack.mitre.org/techniques/T1021">
     Remote Services
    </a>
    similar to RDS.
   </p>
   <p>
    Adversaries may connect to a remote system over RDP/RDS to expand access if the service is enabled and allows access to accounts with known credentials. Adversaries will likely use Credential Access techniques to acquire credentials to use with RDP. Adversaries may also use RDP in conjunction with the
    <a href="https://attack.mitre.org/techniques/T1015">
     Accessibility Features
    </a>
    technique for Persistence.
    <span class="scite-citeref-number" data-reference="Alperovitch Malware" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="http://blog.crowdstrike.com/adversary-tricks-crowdstrike-treats/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries may also perform RDP session hijacking which involves stealing a legitimate user's remote session. Typically, a user is notified when someone else is trying to steal their session and prompted with a question. With System permissions and using Terminal Services Console,
    <code>
     c:\windows\system32\tscon.exe [session number to be stolen]
    </code>
    , an adversary can hijack a session without the need for credentials or prompts to the user.
    <span class="scite-citeref-number" data-reference="RDP Hijacking Korznikov" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="http://www.korznikov.com/2017/03/0-day-or-feature-privilege-escalation.html" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    This can be done remotely or locally and with active or disconnected sessions.
    <span class="scite-citeref-number" data-reference="RDP Hijacking Medium" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://medium.com/@networksecurity/rdp-hijacking-how-to-hijack-rds-and-remoteapp-sessions-transparently-to-move-through-an-da2a1e73a5f6" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    It can also lead to
    <a href="https://attack.mitre.org/techniques/T1018">
     Remote System Discovery
    </a>
    and Privilege Escalation by stealing a Domain Admin or higher privileged account session. All of this can be done by using native Windows commands, but it has also been added as a feature in RedSnarf.
    <span class="scite-citeref-number" data-reference="Kali Redsnarf" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://github.com/nccgroup/redsnarf" target="_blank">
       [5]
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
      : T1076
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
      : Lateral Movement
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
      Remote Desktop Users, User
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
      Authentication logs, Netflow/Enclave netflow, Process monitoring
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
      <a href="https://capec.mitre.org/data/definitions/555.html" target="_blank">
       CAPEC-555
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
     <a href="https://attack.mitre.org/groups/G0006">
      APT1
     </a>
    </td>
    <td>
     <p>
      The
      <a href="https://attack.mitre.org/groups/G0006">
       APT1
      </a>
      group is known to have used RDP during operations.
      <span class="scite-citeref-number" data-reference="FireEye PLA" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.fireeye.com/blog/threat-research/2014/05/the-pla-and-the-800am-500pm-work-day-fireeye-confirms-dojs-findings-on-apt1-intrusion-activity.html" target="_blank">
         [6]
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
      enables the Remote Desktop Protocol for persistence.
      <span class="scite-citeref-number" data-reference="aptsim" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="http://carnal0wnage.attackresearch.com/2012/09/more-on-aptsim.html" target="_blank">
         [7]
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
      The
      <a href="https://attack.mitre.org/groups/G0001">
       Axiom
      </a>
      group is known to have used RDP during operations.
      <span class="scite-citeref-number" data-reference="Novetta-Axiom" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="http://www.novetta.com/wp-content/uploads/2014/11/Executive_Summary-Final_1.pdf" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0030">
      Carbanak
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0030">
       Carbanak
      </a>
      enables concurrent Remote Desktop Protocol (RDP).
      <span class="scite-citeref-number" data-reference="FireEye CARBANAK June 2017" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.fireeye.com/blog/threat-research/2017/06/behind-the-carbanak-backdoor.html" target="_blank">
         [9]
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
      has used Remote Desktop Protocol to conduct lateral movement.
      <span class="scite-citeref-number" data-reference="Group IB Cobalt Aug 2017" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www.group-ib.com/blog/cobalt" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0154">
      Cobalt Strike
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0154">
       Cobalt Strike
      </a>
      can start a VNC-based remote desktop server and tunnel the connection through the already established C2 channel.
      <span class="scite-citeref-number" data-reference="cobaltstrike manual" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://cobaltstrike.com/downloads/csmanual38.pdf" target="_blank">
         [11]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0074">
      Dragonfly 2.0
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0074">
       Dragonfly 2.0
      </a>
      moved laterally via RDP.
      <span class="scite-citeref-number" data-reference="US-CERT TA18-074A" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" target="_blank">
         [12]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT APT Energy Oct 2017" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" target="_blank">
         [13]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0051">
      FIN10
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0051">
       FIN10
      </a>
      has used RDP to move laterally to systems in the victim environment.
      <span class="scite-citeref-number" data-reference="FireEye FIN10 June 2017" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin10.pdf" target="_blank">
         [14]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0037">
      FIN6
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0037">
       FIN6
      </a>
      used RDP to move laterally in victim networks.
      <span class="scite-citeref-number" data-reference="FireEye FIN6 April 2016" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin6.pdf" target="_blank">
         [15]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0061">
      FIN8
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0061">
       FIN8
      </a>
      has used RDP for.
      <span class="scite-citeref-number" data-reference="FireEye Know Your Enemy FIN8 Aug 2016" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" target="_blank">
         [16]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0250">
      Koadic
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0250">
       Koadic
      </a>
      can enable remote desktop on the victim's machine.
      <span class="scite-citeref-number" data-reference="Github Koadic" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://github.com/zerosum0x0/koadic" target="_blank">
         [17]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0032">
      Lazarus Group
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0032">
       Lazarus Group
      </a>
      malware SierraCharlie uses RDP for propagation.
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" target="_blank">
         [18]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster RATs" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-RAT-and-Staging-Report.pdf" target="_blank">
         [19]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0045">
      menuPass
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0045">
       menuPass
      </a>
      has used RDP connections to move across the victim network.
      <span class="scite-citeref-number" data-reference="PWC Cloud Hopper April 2017" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-report-final-v4.pdf" target="_blank">
         [20]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0049">
      OilRig
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0049">
       OilRig
      </a>
      has used Remote Desktop Protocol for lateral movement. The group has also used tunneling tools to tunnel RDP into the environment.
      <span class="scite-citeref-number" data-reference="Unit 42 Playbook Dec 2017" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="https://pan-unit42.github.io/playbook_viewer/" target="_blank">
         [21]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye APT34 Webinar Dec 2017" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="https://www.brighttalk.com/webcast/10703/296317/apt34-new-targeted-attack-in-the-middle-east" target="_blank">
         [22]
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
      attempted to use RDP to move laterally.
      <span class="scite-citeref-number" data-reference="Cymmetria Patchwork" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="https://s3-us-west-2.amazonaws.com/cymmetria-blog/public/Unveiling_Patchwork.pdf" target="_blank">
         [23]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0192">
      Pupy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0192">
       Pupy
      </a>
      can enable/disable RDP connection and can start a remote desktop session using a browser web socket client.
      <span class="scite-citeref-number" data-reference="GitHub Pupy" id="scite-ref-24-a" onclick="scrollToRef('scite-24')">
       <sup>
        <a aria-describedby="qtip-23" data-hasqtip="23" href="https://github.com/n1nj4sec/pupy" target="_blank">
         [24]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0262">
      QuasarRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0262">
       QuasarRAT
      </a>
      has a module for performing remote desktop access.
      <span class="scite-citeref-number" data-reference="GitHub QuasarRAT" id="scite-ref-25-a" onclick="scrollToRef('scite-25')">
       <sup>
        <a aria-describedby="qtip-24" data-hasqtip="24" href="https://github.com/quasar/QuasarRAT" target="_blank">
         [25]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Volexity Patchwork June 2018" id="scite-ref-26-a" onclick="scrollToRef('scite-26')">
       <sup>
        <a aria-describedby="qtip-25" data-hasqtip="25" href="https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/" target="_blank">
         [26]
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
  Disable the RDP service if it is unnecessary, remove unnecessary accounts and groups from Remote Desktop Users groups, and enable firewall rules to block RDP traffic between network security zones. Audit the Remote Desktop Users group membership regularly. Remove the local Administrators group from the list of groups allowed to log in through RDP. Limit remote user permissions if remote access is necessary. Use remote desktop gateways and multifactor authentication for remote logins.
  <span class="scite-citeref-number" data-reference="Berkley Secure" id="scite-ref-27-a">
   <sup>
    <a aria-describedby="qtip-26" data-hasqtip="26" href="https://security.berkeley.edu/node/94" target="_blank">
     [27]
    </a>
   </sup>
  </span>
  Do not leave RDP accessible from the internet. Change GPOs to define shorter timeouts sessions and maximum amount of time any single session can be active. Change GPOs to specify the maximum amount of time that a disconnected session stays active on the RD session host server.
  <span class="scite-citeref-number" data-reference="Windows RDP Sessions" id="scite-ref-28-a">
   <sup>
    <a aria-describedby="qtip-27" data-hasqtip="27" href="https://technet.microsoft.com/en-us/library/cc754272(v=ws.11).aspx" target="_blank">
     [28]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Use of RDP may be legitimate, depending on the network environment and how it is used. Other factors, such as access patterns and activity that occurs after a remote login, may indicate suspicious or malicious behavior with RDP. Monitor for user accounts logged into systems they would not normally access or access patterns to multiple systems over a relatively short period of time.
 </p>
 <p>
  Also, set up process monitoring for
  <code>
   tscon.exe
  </code>
  usage and monitor service creation that uses
  <code>
   cmd.exe /k
  </code>
  or
  <code>
   cmd.exe /c
  </code>
  in its arguments to prevent RDP session hijacking.
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
       <a class="external text" href="https://technet.microsoft.com/en-us/windowsserver/ee236407.aspx" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Remote Desktop Services. Retrieved June 1, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.crowdstrike.com/adversary-tricks-crowdstrike-treats/" name="scite-2" rel="nofollow" target="_blank">
        Alperovitch, D. (2014, October 31). Malware-Free Intrusions. Retrieved November 4, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.korznikov.com/2017/03/0-day-or-feature-privilege-escalation.html" name="scite-3" rel="nofollow" target="_blank">
        Korznikov, A. (2017, March 17). Passwordless RDP Session Hijacking Feature All Windows versions. Retrieved December 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://medium.com/@networksecurity/rdp-hijacking-how-to-hijack-rds-and-remoteapp-sessions-transparently-to-move-through-an-da2a1e73a5f6" name="scite-4" rel="nofollow" target="_blank">
        Beaumont, K. (2017, March 19). RDP hijacking — how to hijack RDS and RemoteApp sessions transparently to move through an organisation. Retrieved December 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/nccgroup/redsnarf" name="scite-5" rel="nofollow" target="_blank">
        NCC Group PLC. (2016, November 1). Kali Redsnarf. Retrieved December 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2014/05/the-pla-and-the-800am-500pm-work-day-fireeye-confirms-dojs-findings-on-apt1-intrusion-activity.html" name="scite-6" rel="nofollow" target="_blank">
        FireEye Labs. (2014, May 20). The PLA and the 8:00am-5:00pm Work Day: FireEye Confirms DOJ’s Findings on APT1 Intrusion Activity. Retrieved November 4, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="http://carnal0wnage.attackresearch.com/2012/09/more-on-aptsim.html" name="scite-7" rel="nofollow" target="_blank">
        valsmith. (2012, September 21). More on APTSim. Retrieved September 28, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.novetta.com/wp-content/uploads/2014/11/Executive_Summary-Final_1.pdf" name="scite-8" rel="nofollow" target="_blank">
        Novetta. (n.d.). Operation SMN: Axiom Threat Actor Group Report. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/06/behind-the-carbanak-backdoor.html" name="scite-9" rel="nofollow" target="_blank">
        Bennett, J., Vengerik, B. (2017, June 12). Behind the CARBANAK Backdoor. Retrieved June 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.group-ib.com/blog/cobalt" name="scite-10" rel="nofollow" target="_blank">
        Matveeva, V. (2017, August 15). Secrets of Cobalt. Retrieved October 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://cobaltstrike.com/downloads/csmanual38.pdf" name="scite-11" rel="nofollow" target="_blank">
        Strategic Cyber LLC. (2017, March 14). Cobalt Strike Manual. Retrieved May 24, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" name="scite-12" rel="nofollow" target="_blank">
        US-CERT. (2018, March 16). Alert (TA18-074A): Russian Government Cyber Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" name="scite-13" rel="nofollow" target="_blank">
        US-CERT. (2017, October 20). Alert (TA17-293A): Advanced Persistent Threat Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved November 2, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin10.pdf" name="scite-14" rel="nofollow" target="_blank">
        FireEye iSIGHT Intelligence. (2017, June 16). FIN10: Anatomy of a Cyber Extortion Operation. Retrieved June 25, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="15.0">
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin6.pdf" name="scite-15" rel="nofollow" target="_blank">
        FireEye Threat Intelligence. (2016, April). Follow the Money: Dissecting the Operations of the Cyber Crime Group FIN6. Retrieved June 1, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" name="scite-16" rel="nofollow" target="_blank">
        Elovitz, S. &amp; Ahl, I. (2016, August 18). Know Your Enemy:  New Financially-Motivated &amp; Spear-Phishing Group. Retrieved February 26, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/zerosum0x0/koadic" name="scite-17" rel="nofollow" target="_blank">
        Magius, J., et al. (2017, July 19). Koadic. Retrieved June 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" name="scite-18" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Unraveling the Long Thread of the Sony Attack. Retrieved February 25, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-RAT-and-Staging-Report.pdf" name="scite-19" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Remote Administration Tools &amp; Content Staging Malware Report. Retrieved March 16, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-report-final-v4.pdf" name="scite-20" rel="nofollow" target="_blank">
        PwC and BAE Systems. (2017, April). Operation Cloud Hopper. Retrieved April 5, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://pan-unit42.github.io/playbook_viewer/" name="scite-21" rel="nofollow" target="_blank">
        Unit 42. (2017, December 15). Unit 42 Playbook Viewer. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.brighttalk.com/webcast/10703/296317/apt34-new-targeted-attack-in-the-middle-east" name="scite-22" rel="nofollow" target="_blank">
        Davis, S. and Caban, D. (2017, December 19). APT34 - New Targeted Attack in the Middle East. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-23">
      <span class="scite-citation-text">
       <a class="external text" href="https://s3-us-west-2.amazonaws.com/cymmetria-blog/public/Unveiling_Patchwork.pdf" name="scite-23" rel="nofollow" target="_blank">
        Cymmetria. (2016). Unveiling Patchwork - The Copy-Paste APT. Retrieved August 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-24">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/n1nj4sec/pupy" name="scite-24" rel="nofollow" target="_blank">
        Nicolas Verdier. (n.d.). Retrieved January 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-25">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/quasar/QuasarRAT" name="scite-25" rel="nofollow" target="_blank">
        MaxXor. (n.d.). QuasarRAT. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-26">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/" name="scite-26" rel="nofollow" target="_blank">
        Meltzer, M, et al. (2018, June 07). Patchwork APT Group Targets US Think Tanks. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-27">
      <span class="scite-citation-text">
       <a class="external text" href="https://security.berkeley.edu/node/94" name="scite-27" rel="nofollow" target="_blank">
        Berkeley Security, University of California. (n.d.). Securing Remote Desktop for System Administrators. Retrieved November 4, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-28">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/cc754272(v=ws.11).aspx" name="scite-28" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Configure Timeout and Reconnection Settings for Remote Desktop Services Sessions. Retrieved December 11, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
