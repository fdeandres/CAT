<div class="container-fluid">
 <h1>
  Permission Groups Discovery
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries may attempt to find local system or domain-level groups and permissions settings.
   </p>
   <h3>
    Windows
   </h3>
   <p>
    Examples of commands that can list groups are
    <code>
     net group /domain
    </code>
    and
    <code>
     net localgroup
    </code>
    using the
    <a href="https://attack.mitre.org/software/S0039">
     Net
    </a>
    utility.
   </p>
   <h3>
    Mac
   </h3>
   <p>
    On Mac, this same thing can be accomplished with the
    <code>
     dscacheutil -q group
    </code>
    for the domain, or
    <code>
     dscl . -list /Groups
    </code>
    for local groups.
   </p>
   <h3>
    Linux
   </h3>
   <p>
    On Linux, local groups can be enumerated with the
    <code>
     groups
    </code>
    command and domain groups via the
    <code>
     ldapsearch
    </code>
    command.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1069
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
      : Discovery
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
      API monitoring, Process monitoring, Process command-line parameters
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
      <a href="https://capec.mitre.org/data/definitions/576.html" target="_blank">
       CAPEC-576
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
     <a href="https://attack.mitre.org/groups/G0018">
      admin@338
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0018">
       admin@338
      </a>
      actors used the following command following exploitation of a machine with
      <a href="https://attack.mitre.org/software/S0042">
       LOWBALL
      </a>
      malware to list local groups:
      <code>
       net localgroup administrator &gt;&gt; %temp%\download
      </code>
      <span class="scite-citeref-number" data-reference="FireEye admin@338" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.fireeye.com/blog/threat-research/2015/11/china-based-threat.html" target="_blank">
         [1]
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
      has a tool that can enumerate the permissions associated with Windows groups.
      <span class="scite-citeref-number" data-reference="Symantec Buckeye" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="http://www.symantec.com/connect/blogs/buckeye-cyberespionage-group-shifts-gaze-us-hong-kong" target="_blank">
         [2]
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
      used batch scripts to enumerate administrators in the environment.
      <span class="scite-citeref-number" data-reference="US-CERT TA18-074A" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0105">
      dsquery
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0105">
       dsquery
      </a>
      can be used to gather information on permission groups within a domain.
      <span class="scite-citeref-number" data-reference="TechNet Dsquery" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://technet.microsoft.com/en-us/library/cc732952.aspx" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0082">
      Emissary
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0082">
       Emissary
      </a>
      has the capability to execute the command
      <code>
       net localgroup administrators
      </code>
      .
      <span class="scite-citeref-number" data-reference="Emissary Trojan Feb 2016" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="http://researchcenter.paloaltonetworks.com/2016/02/emissary-trojan-changelog-did-operation-lotus-blossom-cause-it-to-evolve/" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0170">
      Helminth
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0170">
       Helminth
      </a>
      has checked for the local admin group domain admin group and Exchange Trusted Subsystem groups using the commands
      <code>
       net group Exchange Trusted Subsystem /domain
      </code>
      and
      <code>
       net group domain admins /domain
      </code>
      .
      <span class="scite-citeref-number" data-reference="Unit 42 Playbook Dec 2017" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://pan-unit42.github.io/playbook_viewer/" target="_blank">
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
      can obtain the victim user name.
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
     <a href="https://attack.mitre.org/software/S0265">
      Kazuar
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0265">
       Kazuar
      </a>
      gathers information about local groups and members.
      <span class="scite-citeref-number" data-reference="Unit 42 Kazuar May 2017" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://researchcenter.paloaltonetworks.com/2017/05/unit42-kazuar-multiplatform-espionage-backdoor-api-access/" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0004">
      Ke3chang
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0004">
       Ke3chang
      </a>
      performs discovery of permission groups
      <code>
       net group /domain
      </code>
      .
      <span class="scite-citeref-number" data-reference="Villeneuve et al 2014" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/wp-operation-ke3chang.pdf" target="_blank">
         [9]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0236">
      Kwampirs
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0236">
       Kwampirs
      </a>
      collects lists of local accounts with administrative access, local group user accounts, and domain local groups with the commands
      <code>
       net localgroup administrators
      </code>
      ,
      <code>
       net localgroup users
      </code>
      , and
      <code>
       net localgroup /domain
      </code>
      .
      <span class="scite-citeref-number" data-reference="Symantec Orangeworm April 2018" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www.symantec.com/blogs/threat-intelligence/orangeworm-targets-healthcare-us-europe-asia" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0233">
      MURKYTOP
     </a>
    </td>
    <td>
     <p>
      has the capability to retrieve information about groups.
      <span class="scite-citeref-number" data-reference="FireEye Periscope March 2018" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" target="_blank">
         [11]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0039">
      Net
     </a>
    </td>
    <td>
     <p>
      Commands such as
      <code>
       net group
      </code>
      and
      <code>
       net localgroup
      </code>
      can be used in
      <a href="https://attack.mitre.org/software/S0039">
       Net
      </a>
      to gather information about and manipulate groups.
      <span class="scite-citeref-number" data-reference="Savill 1999" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="http://windowsitpro.com/windows/netexe-reference" target="_blank">
         [12]
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
      has used
      <code>
       net group /domain
      </code>
      ,
      <code>
       net localgroup administrators
      </code>
      ,
      <code>
       net group "domain admins" /domain
      </code>
      , and
      <code>
       net group "Exchange Trusted Subsystem" /domain
      </code>
      to find group permission settings on a victim.
      <span class="scite-citeref-number" data-reference="Palo Alto OilRig May 2016" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="http://researchcenter.paloaltonetworks.com/2016/05/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/" target="_blank">
         [13]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0165">
      OSInfo
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0165">
       OSInfo
      </a>
      specifically looks for Domain Admins, Power Users, and the Administrators groups within the domain and locally
      <span class="scite-citeref-number" data-reference="Symantec Buckeye" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="http://www.symantec.com/connect/blogs/buckeye-cyberespionage-group-shifts-gaze-us-hong-kong" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0184">
      POWRUNER
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0184">
       POWRUNER
      </a>
      may collect permission group information by running
      <code>
       net group /domain
      </code>
      or a series of other commands on a victim.
      <span class="scite-citeref-number" data-reference="FireEye APT34 Dec 2017" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://www.fireeye.com/blog/threat-research/2017/12/targeted-attack-in-middle-east-by-apt34.html" target="_blank">
         [14]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0060">
      Sys10
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0060">
       Sys10
      </a>
      collects the group name of the logged-in user and sends it to the C2.
      <span class="scite-citeref-number" data-reference="Baumgartner Naikon 2015" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://securelist.com/files/2015/05/TheNaikonAPT-MsnMM1.pdf" target="_blank">
         [15]
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
  Identify unnecessary system utilities or potentially malicious software that may be used to acquire information about groups and permissions, and audit and/or block them by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-16-a">
   <sup>
    <a aria-describedby="qtip-15" data-hasqtip="15" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [16]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-17-a">
   <sup>
    <a aria-describedby="qtip-16" data-hasqtip="16" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [17]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-18-a">
   <sup>
    <a aria-describedby="qtip-17" data-hasqtip="17" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [18]
    </a>
   </sup>
  </span>
  or Software Restriction Policies
  <span class="scite-citeref-number" data-reference="Corio 2008" id="scite-ref-19-a">
   <sup>
    <a aria-describedby="qtip-18" data-hasqtip="18" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" target="_blank">
     [19]
    </a>
   </sup>
  </span>
  where appropriate.
  <span class="scite-citeref-number" data-reference="TechNet Applocker vs SRP" id="scite-ref-20-a">
   <sup>
    <a aria-describedby="qtip-19" data-hasqtip="19" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" target="_blank">
     [20]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  System and network discovery techniques normally occur throughout an operation as an adversary learns the environment. Data and events should not be viewed in isolation, but as part of a chain of behavior that could lead to other activities, such as Lateral Movement, based on the information obtained.
 </p>
 <p>
  Monitor processes and command-line arguments for actions that could be taken to gather system and network information. Remote access tools with built-in features may interact directly with the Windows API to gather information. Information may also be acquired through Windows system management tools such as
  <a href="https://attack.mitre.org/techniques/T1047">
   Windows Management Instrumentation
  </a>
  and
  <a href="https://attack.mitre.org/techniques/T1086">
   PowerShell
  </a>
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
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2015/11/china-based-threat.html" name="scite-1" rel="nofollow" target="_blank">
        FireEye Threat Intelligence. (2015, December 1). China-based Cyber Threat Group Uses Dropbox for Malware Communications and Targets Hong Kong Media Outlets. Retrieved December 4, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/connect/blogs/buckeye-cyberespionage-group-shifts-gaze-us-hong-kong" name="scite-2" rel="nofollow" target="_blank">
        Symantec Security Response. (2016, September 6). Buckeye cyberespionage group shifts gaze from US to Hong Kong. Retrieved September 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" name="scite-3" rel="nofollow" target="_blank">
        US-CERT. (2018, March 16). Alert (TA18-074A): Russian Government Cyber Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/cc732952.aspx" name="scite-4" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Dsquery. Retrieved April 18, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/02/emissary-trojan-changelog-did-operation-lotus-blossom-cause-it-to-evolve/" name="scite-5" rel="nofollow" target="_blank">
        Falcone, R. and Miller-Osborn, J.. (2016, February 3). Emissary Trojan Changelog: Did Operation Lotus Blossom Cause It to Evolve?. Retrieved February 15, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://pan-unit42.github.io/playbook_viewer/" name="scite-6" rel="nofollow" target="_blank">
        Unit 42. (2017, December 15). Unit 42 Playbook Viewer. Retrieved December 20, 2017.
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
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/05/unit42-kazuar-multiplatform-espionage-backdoor-api-access/" name="scite-8" rel="nofollow" target="_blank">
        Levene, B, et al. (2017, May 03). Kazuar: Multiplatform Espionage Backdoor with API Access. Retrieved July 17, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/wp-operation-ke3chang.pdf" name="scite-9" rel="nofollow" target="_blank">
        Villeneuve, N., Bennett, J. T., Moran, N., Haq, T., Scott, M., &amp; Geers, K. (2014). OPERATION “KE3CHANG”: Targeted Attacks Against Ministries of Foreign Affairs. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/orangeworm-targets-healthcare-us-europe-asia" name="scite-10" rel="nofollow" target="_blank">
        Symantec Security Response Attack Investigation Team. (2018, April 23). New Orangeworm attack group targets the healthcare sector in the U.S., Europe, and Asia. Retrieved May 8, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="11.0">
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" name="scite-11" rel="nofollow" target="_blank">
        FireEye. (2018, March 16). Suspected Chinese Cyber Espionage Group (TEMP.Periscope) Targeting U.S. Engineering and Maritime Industries. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="http://windowsitpro.com/windows/netexe-reference" name="scite-12" rel="nofollow" target="_blank">
        Savill, J. (1999, March 4). Net.exe reference. Retrieved September 22, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/05/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/" name="scite-13" rel="nofollow" target="_blank">
        Falcone, R. and Lee, B.. (2016, May 26). The OilRig Campaign: Attacks on Saudi Arabian Organizations Deliver Helminth Backdoor. Retrieved May 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/12/targeted-attack-in-middle-east-by-apt34.html" name="scite-14" rel="nofollow" target="_blank">
        Sardiwal, M, et al. (2017, December 7). New Targeted Attack in the Middle East by APT34, a Suspected Iranian Threat Group, Using CVE-2017-11882 Exploit. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/files/2015/05/TheNaikonAPT-MsnMM1.pdf" name="scite-15" rel="nofollow" target="_blank">
        Baumgartner, K., Golovkin, M.. (2015, May). The MsnMM Campaigns: The Earliest Naikon APT Campaigns. Retrieved December 17, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-16" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-17" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-18" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" name="scite-19" rel="nofollow" target="_blank">
        Corio, C., &amp; Sayana, D. P. (2008, June). Application Lockdown with Software Restriction Policies. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" name="scite-20" rel="nofollow" target="_blank">
        Microsoft. (2012, June 27). Using Software Restriction Policies and AppLocker Policies. Retrieved April 7, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
