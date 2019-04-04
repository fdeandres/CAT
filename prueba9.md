<div class="container-fluid">
 <h1>
  Valid Accounts
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries may steal the credentials of a specific user or service account using Credential Access techniques or capture credentials earlier in their reconnaissance process through social engineering for means of gaining Initial Access.
   </p>
   <p>
    Compromised credentials may be used to bypass access controls placed on various resources on systems within the network and may even be used for persistent access to remote systems and externally available services, such as VPNs, Outlook Web Access and remote desktop. Compromised credentials may also grant an adversary increased privilege to specific systems or access to restricted areas of the network. Adversaries may choose not to use malware or tools in conjunction with the legitimate access those credentials provide to make it harder to detect their presence.
   </p>
   <p>
    Adversaries may also create accounts, sometimes using pre-defined account names and passwords, as a means for persistence through backup access in case other means are unsuccessful.
   </p>
   <p>
    The overlap of credentials and permissions across a network of systems is of concern because the adversary may be able to pivot across accounts and systems to reach a high level of access (i.e., domain or enterprise administrator) to bypass access controls set within the enterprise.
    <span class="scite-citeref-number" data-reference="TechNet Credential Theft" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://technet.microsoft.com/en-us/library/dn535501.aspx" target="_blank">
       [1]
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
      : T1078
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
      : Defense Evasion, Persistence, Privilege Escalation, Initial Access
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Platform:
      </span>
      Linux, macOS, Windows
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Permissions Required:
      </span>
      User, Administrator
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Effective Permissions:
      </span>
      User, Administrator
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      Authentication logs, Process monitoring
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
      Firewall, Host intrusion prevention systems, Network intrusion detection system, Process whitelisting, System access controls, Anti-virus
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       CAPEC ID:
      </span>
      <a href="https://capec.mitre.org/data/definitions/560.html" target="_blank">
       CAPEC-560
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
     <a href="/groups/G0026">
      APT18
     </a>
    </td>
    <td>
     <p>
      <a href="/groups/G0026">
       APT18
      </a>
      actors leverage legitimate credentials to log into external remote services.
      <span class="scite-citeref-number" data-reference="RSA2017 Detect and Respond Adair" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.rsaconference.com/writable/presentations/file_upload/hta-f02-detecting-and-responding-to-advanced-threats-within-exchange-environments.pdf" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/groups/G0007">
      APT28
     </a>
    </td>
    <td>
     <p>
      <a href="/groups/G0007">
       APT28
      </a>
      has used legitimate credentials to maintain access to a victim network and exfiltrate data. The group also used credentials stolen through a spearphishing email to login to the DCCC network.
      <span class="scite-citeref-number" data-reference="Trend Micro Pawn Storm April 2017" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://documents.trendmicro.com/assets/wp/wp-two-years-of-pawn-storm.pdf" target="_blank">
         [3]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="DOJ GRU Indictment Jul 2018" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.justice.gov/file/1080281/download" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/groups/G0022">
      APT3
     </a>
    </td>
    <td>
     <p>
      <a href="/groups/G0022">
       APT3
      </a>
      leverages valid accounts after gaining credentials for use within the victim domain.
      <span class="scite-citeref-number" data-reference="Symantec Buckeye" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="http://www.symantec.com/connect/blogs/buckeye-cyberespionage-group-shifts-gaze-us-hong-kong" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/groups/G0050">
      APT32
     </a>
    </td>
    <td>
     <p>
      <a href="/groups/G0050">
       APT32
      </a>
      has used legitimate local admin account credentials.
      <span class="scite-citeref-number" data-reference="FireEye APT32 May 2017" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.fireeye.com/blog/threat-research/2017/05/cyber-espionage-apt32.html" target="_blank">
         [6]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/groups/G0064">
      APT33
     </a>
    </td>
    <td>
     <p>
      <a href="/groups/G0064">
       APT33
      </a>
      has used valid accounts for privilege escalation.
      <span class="scite-citeref-number" data-reference="FireEye APT33 Webinar Sept 2017" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.brighttalk.com/webcast/10703/275683" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/groups/G0008">
      Carbanak
     </a>
    </td>
    <td>
     <p>
      <a href="/groups/G0008">
       Carbanak
      </a>
      actors used legitimate credentials of banking employees to perform operations that sent them millions of dollars.
      <span class="scite-citeref-number" data-reference="Kaspersky Carbanak" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08064518/Carbanak_APT_eng.pdf" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/software/S0154">
      Cobalt Strike
     </a>
    </td>
    <td>
     <p>
      <a href="/software/S0154">
       Cobalt Strike
      </a>
      can use known credentials to run commands and spawn processes as another user.
      <span class="scite-citeref-number" data-reference="cobaltstrike manual" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://cobaltstrike.com/downloads/csmanual38.pdf" target="_blank">
         [9]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/groups/G0074">
      Dragonfly 2.0
     </a>
    </td>
    <td>
     <p>
      <a href="/groups/G0074">
       Dragonfly 2.0
      </a>
      compromised user credentials and used valid accounts for operations.
      <span class="scite-citeref-number" data-reference="US-CERT TA18-074A" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/software/S0038">
      Duqu
     </a>
    </td>
    <td>
     <p>
      Adversaries can instruct
      <a href="/software/S0038">
       Duqu
      </a>
      to spread laterally by copying itself to shares it has enumerated and for which it has obtained legitimate credentials (via keylogging or other means). The remote host is then infected by using the compromised credentials to schedule a task on remote machines that executes the malware.
      <span class="scite-citeref-number" data-reference="Symantec W32.Duqu" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/w32_duqu_the_precursor_to_the_next_stuxnet.pdf" target="_blank">
         [11]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/groups/G0051">
      FIN10
     </a>
    </td>
    <td>
     <p>
      <a href="/groups/G0051">
       FIN10
      </a>
      has used stolen credentials to connect remotely to victim networks using VPNs protected with only a single factor. The group has also moved laterally using the Local Administrator account.
      <span class="scite-citeref-number" data-reference="FireEye FIN10 June 2017" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin10.pdf" target="_blank">
         [12]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/groups/G0053">
      FIN5
     </a>
    </td>
    <td>
     <p>
      <a href="/groups/G0053">
       FIN5
      </a>
      has used legitimate VPN, RDP, Citrix, or VNC credentials to maintain access to a victim environment.
      <span class="scite-citeref-number" data-reference="FireEye Respond Webinar July 2017" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://www2.fireeye.com/WBNR-Are-you-ready-to-respond.html" target="_blank">
         [13]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="DarkReading FireEye FIN5 Oct 2015" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://www.darkreading.com/analytics/prolific-cybercrime-gang-favors-legit-login-credentials/d/d-id/1322645?" target="_blank">
         [14]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Mandiant FIN5 GrrCON Oct 2016" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://www.youtube.com/watch?v=fevGZs0EQu8" target="_blank">
         [15]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/groups/G0037">
      FIN6
     </a>
    </td>
    <td>
     <p>
      To move laterally on a victim network,
      <a href="/groups/G0037">
       FIN6
      </a>
      has used credentials stolen from various systems on which it gathered usernames and password hashes.
      <span class="scite-citeref-number" data-reference="FireEye FIN6 April 2016" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin6.pdf" target="_blank">
         [16]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/groups/G0061">
      FIN8
     </a>
    </td>
    <td>
     <p>
      <a href="/groups/G0061">
       FIN8
      </a>
      has utilized
      <a href="/techniques/T1078">
       Valid Accounts
      </a>
      during and.
      <span class="scite-citeref-number" data-reference="FireEye Know Your Enemy FIN8 Aug 2016" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" target="_blank">
         [17]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/groups/G0065">
      Leviathan
     </a>
    </td>
    <td>
     <p>
      <a href="/groups/G0065">
       Leviathan
      </a>
      has used valid, compromised email accounts for defense evasion, including to send malicious emails to other victim organizations.
      <span class="scite-citeref-number" data-reference="Proofpoint Leviathan Oct 2017" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" target="_blank">
         [18]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/groups/G0045">
      menuPass
     </a>
    </td>
    <td>
     <p>
      <a href="/groups/G0045">
       menuPass
      </a>
      has used valid accounts shared between Managed Service Providers and clients to move between the two environments.
      <span class="scite-citeref-number" data-reference="PWC Cloud Hopper April 2017" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-report-final-v4.pdf" target="_blank">
         [19]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/groups/G0049">
      OilRig
     </a>
    </td>
    <td>
     <p>
      <a href="/groups/G0049">
       OilRig
      </a>
      has used compromised credentials to access other systems on a victim network.
      <span class="scite-citeref-number" data-reference="Unit 42 Playbook Dec 2017" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://pan-unit42.github.io/playbook_viewer/" target="_blank">
         [20]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye APT34 Webinar Dec 2017" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="https://www.brighttalk.com/webcast/10703/296317/apt34-new-targeted-attack-in-the-middle-east" target="_blank">
         [21]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/groups/G0011">
      PittyTiger
     </a>
    </td>
    <td>
     <p>
      <a href="/groups/G0011">
       PittyTiger
      </a>
      attempts to obtain legitimate credentials during operations.
      <span class="scite-citeref-number" data-reference="Bizeul 2014" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="http://blog.cassidiancybersecurity.com/post/2014/07/The-Eye-of-the-Tiger2" target="_blank">
         [22]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/software/S0053">
      SeaDuke
     </a>
    </td>
    <td>
     <p>
      Some
      <a href="/software/S0053">
       SeaDuke
      </a>
      samples have a module to extract email from Microsoft Exchange servers using compromised credentials.
      <span class="scite-citeref-number" data-reference="Symantec Seaduke 2015" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="http://www.symantec.com/connect/blogs/forkmeiamfamous-seaduke-latest-weapon-duke-armory" target="_blank">
         [23]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/software/S0140">
      Shamoon
     </a>
    </td>
    <td>
     <p>
      If
      <a href="/software/S0140">
       Shamoon
      </a>
      cannot access shares using current privileges, it attempts access using hard coded, domain-specific credentials gathered earlier in the intrusion.
      <span class="scite-citeref-number" data-reference="FireEye Shamoon Nov 2016" id="scite-ref-24-a" onclick="scrollToRef('scite-24')">
       <sup>
        <a aria-describedby="qtip-23" data-hasqtip="23" href="https://www.fireeye.com/blog/threat-research/2016/11/fireeye_respondsto.html" target="_blank">
         [24]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/groups/G0039">
      Suckfly
     </a>
    </td>
    <td>
     <p>
      <a href="/groups/G0039">
       Suckfly
      </a>
      used legitimate account credentials that they dumped to navigate the internal victim network as though they were the legitimate account owner.
      <span class="scite-citeref-number" data-reference="Symantec Suckfly May 2016" id="scite-ref-25-a" onclick="scrollToRef('scite-25')">
       <sup>
        <a aria-describedby="qtip-24" data-hasqtip="24" href="http://www.symantec.com/connect/blogs/indian-organizations-targeted-suckfly-attacks" target="_blank">
         [25]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/groups/G0028">
      Threat Group-1314
     </a>
    </td>
    <td>
     <p>
      <a href="/groups/G0028">
       Threat Group-1314
      </a>
      actors used compromised credentials for the victim's endpoint management platform, Altiris, to move laterally.
      <span class="scite-citeref-number" data-reference="Dell TG-1314" id="scite-ref-26-a" onclick="scrollToRef('scite-26')">
       <sup>
        <a aria-describedby="qtip-25" data-hasqtip="25" href="http://www.secureworks.com/resources/blog/living-off-the-land/" target="_blank">
         [26]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/groups/G0027">
      Threat Group-3390
     </a>
    </td>
    <td>
     <p>
      <a href="/groups/G0027">
       Threat Group-3390
      </a>
      actors obtain legitimate credentials using a variety of methods and use them to further lateral movement on victim networks.
      <span class="scite-citeref-number" data-reference="Dell TG-3390" id="scite-ref-27-a" onclick="scrollToRef('scite-27')">
       <sup>
        <a aria-describedby="qtip-26" data-hasqtip="26" href="https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage" target="_blank">
         [27]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="/software/S0221">
      Umbreon
     </a>
    </td>
    <td>
     <p>
      <a href="/software/S0221">
       Umbreon
      </a>
      creates valid users to provide access to the system.
      <span class="scite-citeref-number" data-reference="Umbreon Trend Micro" id="scite-ref-28-a" onclick="scrollToRef('scite-28')">
       <sup>
        <a aria-describedby="qtip-27" data-hasqtip="27" href="https://blog.trendmicro.com/trendlabs-security-intelligence/pokemon-themed-umbreon-linux-rootkit-hits-x86-arm-systems/?_ga=2.180041126.367598458.1505420282-1759340220.1502477046" target="_blank">
         [28]
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
  Take measures to detect or prevent techniques such as
  <a href="/techniques/T1003">
   Credential Dumping
  </a>
  or installation of keyloggers to acquire credentials through
  <a href="/techniques/T1056">
   Input Capture
  </a>
  . Limit credential overlap across systems to prevent access if account credentials are obtained. Ensure that local administrator accounts have complex, unique passwords across all systems on the network. Do not put user or admin domain accounts in the local administrator groups across systems unless they are tightly controlled and use of accounts is segmented, as this is often equivalent to having a local administrator account with the same password on all systems. Follow best practices for design and administration of an enterprise network to limit privileged account use across administrative tiers.
  <span class="scite-citeref-number" data-reference="Microsoft Securing Privileged Access" id="scite-ref-29-a">
   <sup>
    <a aria-describedby="qtip-28" data-hasqtip="28" href="https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access-reference-material#a-nameesaebmaesae-administrative-forest-design-approach" target="_blank">
     [29]
    </a>
   </sup>
  </span>
  . Audit domain and local accounts as well as their permission levels routinely to look for situations that could allow an adversary to gain wide access by obtaining credentials of a privileged account.
  <span class="scite-citeref-number" data-reference="TechNet Credential Theft" id="scite-ref-1-a">
   <sup>
    <a aria-describedby="qtip-0" data-hasqtip="0" href="https://technet.microsoft.com/en-us/library/dn535501.aspx" target="_blank">
     [1]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="TechNet Least Privilege" id="scite-ref-30-a">
   <sup>
    <a aria-describedby="qtip-29" data-hasqtip="29" href="https://technet.microsoft.com/en-us/library/dn487450.aspx" target="_blank">
     [30]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Configure robust, consistent account activity audit policies across the enterprise and with externally accessible services.
  <span class="scite-citeref-number" data-reference="TechNet Audit Policy" id="scite-ref-31-a">
   <sup>
    <a aria-describedby="qtip-30" data-hasqtip="30" href="https://technet.microsoft.com/en-us/library/dn487457.aspx" target="_blank">
     [31]
    </a>
   </sup>
  </span>
  Look for suspicious account behavior across systems that share accounts, either user, admin, or service accounts. Examples: one account logged into multiple systems simultaneously; multiple accounts logged into the same machine simultaneously; accounts logged in at odd times or outside of business hours. Activity may be from interactive login sessions or process ownership from accounts being used to execute binaries on a remote system as a particular account. Correlate other security systems with login information (e.g., a user has an active login session but has not entered the building or does not have VPN access).
 </p>
 <p>
  Perform regular audits of domain and local system accounts to detect accounts that may have been created by an adversary for persistence.
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
       <a class="external text" href="https://technet.microsoft.com/en-us/library/dn535501.aspx" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (2016, April 15). Attractive Accounts for Credential Theft. Retrieved June 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.rsaconference.com/writable/presentations/file_upload/hta-f02-detecting-and-responding-to-advanced-threats-within-exchange-environments.pdf" name="scite-2" rel="nofollow" target="_blank">
        Adair, S. (2017, February 17). Detecting and Responding to Advanced Threats within Exchange Environments. Retrieved March 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://documents.trendmicro.com/assets/wp/wp-two-years-of-pawn-storm.pdf" name="scite-3" rel="nofollow" target="_blank">
        Hacquebord, F.. (2017, April 25). Two Years of Pawn Storm: Examining an Increasingly Relevant Threat. Retrieved May 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.justice.gov/file/1080281/download" name="scite-4" rel="nofollow" target="_blank">
        Mueller, R. (2018, July 13). Indictment - United States of America vs. VIKTOR BORISOVICH NETYKSHO, et al. Retrieved September 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/connect/blogs/buckeye-cyberespionage-group-shifts-gaze-us-hong-kong" name="scite-5" rel="nofollow" target="_blank">
        Symantec Security Response. (2016, September 6). Buckeye cyberespionage group shifts gaze from US to Hong Kong. Retrieved September 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/05/cyber-espionage-apt32.html" name="scite-6" rel="nofollow" target="_blank">
        Carr, N.. (2017, May 14). Cyber Espionage is Alive and Well: APT32 and the Threat to Global Corporations. Retrieved June 18, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.brighttalk.com/webcast/10703/275683" name="scite-7" rel="nofollow" target="_blank">
        Davis, S. and Carr, N. (2017, September 21). APT33: New Insights into Iranian Cyber Espionage Group. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08064518/Carbanak_APT_eng.pdf" name="scite-8" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2015, February). CARBANAK APT THE GREAT BANK ROBBERY. Retrieved August 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://cobaltstrike.com/downloads/csmanual38.pdf" name="scite-9" rel="nofollow" target="_blank">
        Strategic Cyber LLC. (2017, March 14). Cobalt Strike Manual. Retrieved May 24, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" name="scite-10" rel="nofollow" target="_blank">
        US-CERT. (2018, March 16). Alert (TA18-074A): Russian Government Cyber Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/w32_duqu_the_precursor_to_the_next_stuxnet.pdf" name="scite-11" rel="nofollow" target="_blank">
        Symantec Security Response. (2011, November). W32.Duqu: The precursor to the next Stuxnet. Retrieved September 17, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin10.pdf" name="scite-12" rel="nofollow" target="_blank">
        FireEye iSIGHT Intelligence. (2017, June 16). FIN10: Anatomy of a Cyber Extortion Operation. Retrieved June 25, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/WBNR-Are-you-ready-to-respond.html" name="scite-13" rel="nofollow" target="_blank">
        Scavella, T. and Rifki, A. (2017, July 20). Are you Ready to Respond? (Webinar). Retrieved October 4, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.darkreading.com/analytics/prolific-cybercrime-gang-favors-legit-login-credentials/d/d-id/1322645?" name="scite-14" rel="nofollow" target="_blank">
        Higgins, K. (2015, October 13). Prolific Cybercrime Gang Favors Legit Login Credentials. Retrieved October 4, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.youtube.com/watch?v=fevGZs0EQu8" name="scite-15" rel="nofollow" target="_blank">
        Bromiley, M. and Lewis, P. (2016, October 7). Attacking the Hospitality and Gaming Industries: Tracking an Attacker Around the World in 7 Years. Retrieved October 6, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin6.pdf" name="scite-16" rel="nofollow" target="_blank">
        FireEye Threat Intelligence. (2016, April). Follow the Money: Dissecting the Operations of the Cyber Crime Group FIN6. Retrieved June 1, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="17.5">
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" name="scite-17" rel="nofollow" target="_blank">
        Elovitz, S. &amp; Ahl, I. (2016, August 18). Know Your Enemy:  New Financially-Motivated &amp; Spear-Phishing Group. Retrieved February 26, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" name="scite-18" rel="nofollow" target="_blank">
        Axel F, Pierre T. (2017, October 16). Leviathan: Espionage actor spearphishes maritime and defense targets. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-report-final-v4.pdf" name="scite-19" rel="nofollow" target="_blank">
        PwC and BAE Systems. (2017, April). Operation Cloud Hopper. Retrieved April 5, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://pan-unit42.github.io/playbook_viewer/" name="scite-20" rel="nofollow" target="_blank">
        Unit 42. (2017, December 15). Unit 42 Playbook Viewer. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.brighttalk.com/webcast/10703/296317/apt34-new-targeted-attack-in-the-middle-east" name="scite-21" rel="nofollow" target="_blank">
        Davis, S. and Caban, D. (2017, December 19). APT34 - New Targeted Attack in the Middle East. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.cassidiancybersecurity.com/post/2014/07/The-Eye-of-the-Tiger2" name="scite-22" rel="nofollow" target="_blank">
        Bizeul, D., Fontarensky, I., Mouchoux, R., Perigaud, F., Pernet, C. (2014, July 11). Eye of the Tiger. Retrieved September 29, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-23">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/connect/blogs/forkmeiamfamous-seaduke-latest-weapon-duke-armory" name="scite-23" rel="nofollow" target="_blank">
        Symantec Security Response. (2015, July 13). “Forkmeiamfamous”: Seaduke, latest weapon in the Duke armory. Retrieved July 22, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-24">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2016/11/fireeye_respondsto.html" name="scite-24" rel="nofollow" target="_blank">
        FireEye. (2016, November 30). FireEye Responds to Wave of Destructive Cyber Attacks in Gulf Region. Retrieved January 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-25">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/connect/blogs/indian-organizations-targeted-suckfly-attacks" name="scite-25" rel="nofollow" target="_blank">
        DiMaggio, J.. (2016, May 17). Indian organizations targeted in Suckfly attacks. Retrieved August 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-26">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.secureworks.com/resources/blog/living-off-the-land/" name="scite-26" rel="nofollow" target="_blank">
        Dell SecureWorks Counter Threat Unit Special Operations Team. (2015, May 28). Living off the Land. Retrieved January 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-27">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage" name="scite-27" rel="nofollow" target="_blank">
        Dell SecureWorks Counter Threat Unit Threat Intelligence. (2015, August 5). Threat Group-3390 Targets Organizations for Cyberespionage. Retrieved August 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-28">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/pokemon-themed-umbreon-linux-rootkit-hits-x86-arm-systems/?_ga=2.180041126.367598458.1505420282-1759340220.1502477046" name="scite-28" rel="nofollow" target="_blank">
        Fernando Mercês. (2016, September 5). Pokémon-themed Umbreon Linux Rootkit Hits x86, ARM Systems. Retrieved March 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-29">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access-reference-material#a-nameesaebmaesae-administrative-forest-design-approach" name="scite-29" rel="nofollow" target="_blank">
        Plett, C., Poggemeyer, L. (12, October 26). Securing Privileged Access Reference Material. Retrieved April 25, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-30">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/dn487450.aspx" name="scite-30" rel="nofollow" target="_blank">
        Microsoft. (2016, April 16). Implementing Least-Privilege Administrative Models. Retrieved June 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-31">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/dn487457.aspx" name="scite-31" rel="nofollow" target="_blank">
        Microsoft. (2016, April 15). Audit Policy Recommendations. Retrieved June 3, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
