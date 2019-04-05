<div class="container-fluid">
 <h1>
  Disabling Security Tools
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries may disable security tools to avoid possible detection of their tools and activities. This can take the form of killing security software or event logging processes, deleting Registry keys so that tools do not start at run time, or other methods to interfere with security scanning or event reporting.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1089
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
      Linux, macOS, Windows
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
       Data Sources:
      </span>
      API monitoring, File monitoring, Services, Windows Registry, Process command-line parameters, Anti-virus
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
      File monitoring, Host intrusion prevention systems, Signature-based detection, Log analysis, Anti-virus
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       CAPEC ID:
      </span>
      <a href="https://capec.mitre.org/data/definitions/578.html" target="_blank">
       CAPEC-578
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
     <a href="https://attack.mitre.org/software/S0031">
      BACKSPACE
     </a>
    </td>
    <td>
     <p>
      The "ZR" variant of
      <a href="https://attack.mitre.org/software/S0031">
       BACKSPACE
      </a>
      will check to see if known host-based firewalls are installed on the infected systems.
      <a href="https://attack.mitre.org/software/S0031">
       BACKSPACE
      </a>
      will attempt to establish a C2 channel, then will examine open windows to identify a pop-up from the firewall software and will simulate a mouse-click to allow the connection to proceed.
      <span class="scite-citeref-number" data-reference="FireEye APT30" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www2.fireeye.com/rs/fireye/images/rpt-apt30.pdf" target="_blank">
         [1]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0245">
      BADCALL
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0245">
       BADCALL
      </a>
      disables the Windows firewall before binding to a port.
      <span class="scite-citeref-number" data-reference="US-CERT BADCALL" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-G.PDF" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0252">
      Brave Prince
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0252">
       Brave Prince
      </a>
      terminates antimalware processes.
      <span class="scite-citeref-number" data-reference="McAfee Gold Dragon" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://securingtomorrow.mcafee.com/mcafee-labs/gold-dragon-widens-olympics-malware-attacks-gains-permanent-presence-on-victims-systems/" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0008">
      Carbanak
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0008">
       Carbanak
      </a>
      may use
      <a href="https://attack.mitre.org/software/S0108">
       netsh
      </a>
      to add local firewall rule exceptions.
      <span class="scite-citeref-number" data-reference="Group-IB Anunak" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="http://www.group-ib.com/files/Anunak_APT_against_financial_institutions.pdf" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0144">
      ChChes
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0144">
       ChChes
      </a>
      can alter the victim's proxy configuration.
      <span class="scite-citeref-number" data-reference="PWC Cloud Hopper Technical Annex April 2017" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" target="_blank">
         [5]
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
      has disabled host-based firewalls. The group has also globally opened port 3389.
      <span class="scite-citeref-number" data-reference="US-CERT TA18-074A" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" target="_blank">
         [6]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT APT Energy Oct 2017" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0249">
      Gold Dragon
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0249">
       Gold Dragon
      </a>
      terminates anti-malware processes if they’re found running on the system.
      <span class="scite-citeref-number" data-reference="McAfee Gold Dragon" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://securingtomorrow.mcafee.com/mcafee-labs/gold-dragon-widens-olympics-malware-attacks-gains-permanent-presence-on-victims-systems/" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0078">
      Gorgon Group
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0078">
       Gorgon Group
      </a>
      malware can attempt to disable security features in Microsoft Office and Windows Defender using the
      <code>
       taskkill
      </code>
      command.
      <span class="scite-citeref-number" data-reference="Unit 42 Gorgon Group Aug 2018" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://researchcenter.paloaltonetworks.com/2018/08/unit42-gorgon-group-slithering-nation-state-cybercrime/" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0132">
      H1N1
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0132">
       H1N1
      </a>
      kills and disables services for Windows Firewall, Windows Security Center, and Windows Defender.
      <span class="scite-citeref-number" data-reference="Cisco H1N1 Part 2" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="http://blogs.cisco.com/security/h1n1-technical-analysis-reveals-new-capabilities-part-2" target="_blank">
         [9]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0246">
      HARDRAIN
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0246">
       HARDRAIN
      </a>
      opens the Windows Firewall to modify incoming connections.
      <span class="scite-citeref-number" data-reference="US-CERT HARDRAIN March 2018" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-F.pdf" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0061">
      HDoor
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0061">
       HDoor
      </a>
      kills anti-virus found on the victim.
      <span class="scite-citeref-number" data-reference="Baumgartner Naikon 2015" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://securelist.com/files/2015/05/TheNaikonAPT-MsnMM1.pdf" target="_blank">
         [11]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0260">
      InvisiMole
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0260">
       InvisiMole
      </a>
      has a command to disable routing and the Firewall on the victim’s machine.
      <span class="scite-citeref-number" data-reference="ESET InvisiMole June 2018" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://www.welivesecurity.com/2018/06/07/invisimole-equipped-spyware-undercover/" target="_blank">
         [12]
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
      lower disable security settings by changing Registry keys.
      <span class="scite-citeref-number" data-reference="Microsoft PLATINUM April 2016" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" target="_blank">
         [13]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0088">
      Kasidet
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0088">
       Kasidet
      </a>
      has the ability to change firewall settings to allow a plug-in to be downloaded.
      <span class="scite-citeref-number" data-reference="Zscaler Kasidet" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="http://research.zscaler.com/2016/01/malicious-office-files-dropping-kasidet.html" target="_blank">
         [14]
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
      Various
      <a href="https://attack.mitre.org/groups/G0032">
       Lazarus Group
      </a>
      malware modifies the Windows firewall to allow incoming connections or disable it entirely using
      <a href="https://attack.mitre.org/software/S0108">
       netsh
      </a>
      .
      <a href="https://attack.mitre.org/groups/G0032">
       Lazarus Group
      </a>
      malware TangoDelta attempts to terminate various processes associated with McAfee. Additionally,
      <a href="https://attack.mitre.org/groups/G0032">
       Lazarus Group
      </a>
      malware SHARPKNOT disables the Microsoft Windows System Event Notification and Alerter services.
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" target="_blank">
         [15]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster Loaders" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="https://operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Loaders-Installers-and-Uninstallers-Report.pdf" target="_blank">
         [16]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster Tools" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Tools-Report.pdf" target="_blank">
         [17]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT SHARPKNOT June 2018" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536.11.WHITE.pdf" target="_blank">
         [18]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0228">
      NanHaiShu
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0228">
       NanHaiShu
      </a>
      can change Internet Explorer settings to reduce warnings about malware activity.
      <span class="scite-citeref-number" data-reference="Proofpoint Leviathan Oct 2017" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" target="_blank">
         [19]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0108">
      netsh
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0108">
       netsh
      </a>
      can be used to disable local firewall settings.
      <span class="scite-citeref-number" data-reference="TechNet Netsh" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://technet.microsoft.com/library/bb490939.aspx" target="_blank">
         [20]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="TechNet Netsh Firewall" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="https://technet.microsoft.com/en-us/library/cc771046(v=ws.10).aspx" target="_blank">
         [21]
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
      can disable Microsoft Office Protected View by changing Registry keys.
      <span class="scite-citeref-number" data-reference="FireEye MuddyWater Mar 2018" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html" target="_blank">
         [22]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0279">
      Proton
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0279">
       Proton
      </a>
      kills security tools like Wireshark that are running.
      <span class="scite-citeref-number" data-reference="objsee mac malware 2017" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="https://objective-see.com/blog/blog_0x25.html" target="_blank">
         [23]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0024">
      Putter Panda
     </a>
    </td>
    <td>
     <p>
      Malware used by
      <a href="https://attack.mitre.org/groups/G0024">
       Putter Panda
      </a>
      attempts to terminate processes corresponding to two components of Sophos Anti-Virus (SAVAdminService.exe and SavService.exe).
      <span class="scite-citeref-number" data-reference="CrowdStrike Putter Panda" id="scite-ref-24-a" onclick="scrollToRef('scite-24')">
       <sup>
        <a aria-describedby="qtip-23" data-hasqtip="23" href="http://cdn0.vox-cdn.com/assets/4589853/crowdstrike-intelligence-report-putter-panda.original.pdf" target="_blank">
         [24]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0125">
      Remsec
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0125">
       Remsec
      </a>
      can add or remove applications or ports on the Windows firewall or disable it entirely.
      <span class="scite-citeref-number" data-reference="Kaspersky ProjectSauron Technical Analysis" id="scite-ref-25-a" onclick="scrollToRef('scite-25')">
       <sup>
        <a aria-describedby="qtip-24" data-hasqtip="24" href="https://securelist.com/files/2016/07/The-ProjectSauron-APT_Technical_Analysis_KL.pdf" target="_blank">
         [25]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0253">
      RunningRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0253">
       RunningRAT
      </a>
      kills antimalware running process.
      <span class="scite-citeref-number" data-reference="McAfee Gold Dragon" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://securingtomorrow.mcafee.com/mcafee-labs/gold-dragon-widens-olympics-malware-attacks-gains-permanent-presence-on-victims-systems/" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0058">
      SslMM
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0058">
       SslMM
      </a>
      identifies and kills anti-malware processes.
      <span class="scite-citeref-number" data-reference="Baumgartner Naikon 2015" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://securelist.com/files/2015/05/TheNaikonAPT-MsnMM1.pdf" target="_blank">
         [11]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0027">
      Threat Group-3390
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0027">
       Threat Group-3390
      </a>
      has used appcmd.exe to disable logging on a victim server.
      <span class="scite-citeref-number" data-reference="SecureWorks BRONZE UNION June 2017" id="scite-ref-26-a" onclick="scrollToRef('scite-26')">
       <sup>
        <a aria-describedby="qtip-25" data-hasqtip="25" href="https://www.secureworks.com/research/bronze-union" target="_blank">
         [26]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0004">
      TinyZBot
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0004">
       TinyZBot
      </a>
      can disable Avira anti-virus.
      <span class="scite-citeref-number" data-reference="Cylance Cleaver" id="scite-ref-27-a" onclick="scrollToRef('scite-27')">
       <sup>
        <a aria-describedby="qtip-26" data-hasqtip="26" href="https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf" target="_blank">
         [27]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0263">
      TYPEFRAME
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0263">
       TYPEFRAME
      </a>
      can open the Windows Firewall on the victim’s machine to allow incoming connections.
      <span class="scite-citeref-number" data-reference="US-CERT TYPEFRAME June 2018" id="scite-ref-28-a" onclick="scrollToRef('scite-28')">
       <sup>
        <a aria-describedby="qtip-27" data-hasqtip="27" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-165A" target="_blank">
         [28]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0130">
      Unknown Logger
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0130">
       Unknown Logger
      </a>
      has functionality to disable security tools, including Kaspersky, BitDefender, and MalwareBytes.
      <span class="scite-citeref-number" data-reference="Forcepoint Monsoon" id="scite-ref-29-a" onclick="scrollToRef('scite-29')">
       <sup>
        <a aria-describedby="qtip-28" data-hasqtip="28" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" target="_blank">
         [29]
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
  Ensure proper process, registry, and file permissions are in place to prevent adversaries from disabling or interfering with security services.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor processes and command-line arguments to see if security tools are killed or stop running. Monitor Registry edits for modifications to services and startup programs that correspond to security tools. Lack of log or event file reporting may be suspicious.
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
       <a class="external text" href="https://www2.fireeye.com/rs/fireye/images/rpt-apt30.pdf" name="scite-1" rel="nofollow" target="_blank">
        FireEye Labs. (2015, April). APT30 AND THE MECHANICS OF A LONG-RUNNING CYBER ESPIONAGE OPERATION. Retrieved May 1, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-G.PDF" name="scite-2" rel="nofollow" target="_blank">
        US-CERT. (2018, February 06). Malware Analysis Report (MAR) - 10135536-G. Retrieved June 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/gold-dragon-widens-olympics-malware-attacks-gains-permanent-presence-on-victims-systems/" name="scite-3" rel="nofollow" target="_blank">
        Sherstobitoff, R., Saavedra-Morales, J. (2018, February 02). Gold Dragon Widens Olympics Malware Attacks, Gains Permanent Presence on Victims’ Systems. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.group-ib.com/files/Anunak_APT_against_financial_institutions.pdf" name="scite-4" rel="nofollow" target="_blank">
        Group-IB and Fox-IT. (2014, December). Anunak: APT against financial institutions. Retrieved April 20, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" name="scite-5" rel="nofollow" target="_blank">
        PwC and BAE Systems. (2017, April). Operation Cloud Hopper: Technical Annex. Retrieved April 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" name="scite-6" rel="nofollow" target="_blank">
        US-CERT. (2018, March 16). Alert (TA18-074A): Russian Government Cyber Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" name="scite-7" rel="nofollow" target="_blank">
        US-CERT. (2017, October 20). Alert (TA17-293A): Advanced Persistent Threat Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved November 2, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/08/unit42-gorgon-group-slithering-nation-state-cybercrime/" name="scite-8" rel="nofollow" target="_blank">
        Falcone, R., et al. (2018, August 02). The Gorgon Group: Slithering Between Nation State and Cybercrime. Retrieved August 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="http://blogs.cisco.com/security/h1n1-technical-analysis-reveals-new-capabilities-part-2" name="scite-9" rel="nofollow" target="_blank">
        Reynolds, J.. (2016, September 14). H1N1: Technical analysis reveals new capabilities – part 2. Retrieved September 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-F.pdf" name="scite-10" rel="nofollow" target="_blank">
        US-CERT. (2018, February 05). Malware Analysis Report (MAR) - 10135536-F. Retrieved June 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/files/2015/05/TheNaikonAPT-MsnMM1.pdf" name="scite-11" rel="nofollow" target="_blank">
        Baumgartner, K., Golovkin, M.. (2015, May). The MsnMM Campaigns: The Earliest Naikon APT Campaigns. Retrieved December 17, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2018/06/07/invisimole-equipped-spyware-undercover/" name="scite-12" rel="nofollow" target="_blank">
        Hromcová, Z. (2018, June 07). InvisiMole: Surprisingly equipped spyware, undercover since 2013. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" name="scite-13" rel="nofollow" target="_blank">
        Windows Defender Advanced Threat Hunting Team. (2016, April 29). PLATINUM: Targeted attacks in South and Southeast Asia. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="http://research.zscaler.com/2016/01/malicious-office-files-dropping-kasidet.html" name="scite-14" rel="nofollow" target="_blank">
        Yadav, A., et al. (2016, January 29). Malicious Office files dropping Kasidet and Dridex. Retrieved March 24, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" name="scite-15" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Unraveling the Long Thread of the Sony Attack. Retrieved February 25, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="16.5">
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Loaders-Installers-and-Uninstallers-Report.pdf" name="scite-16" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Loaders, Installers and Uninstallers Report. Retrieved March 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Tools-Report.pdf" name="scite-17" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Tools Report. Retrieved March 10, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536.11.WHITE.pdf" name="scite-18" rel="nofollow" target="_blank">
        US-CERT. (2018, March 09). Malware Analysis Report (MAR) - 10135536.11.WHITE. Retrieved June 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" name="scite-19" rel="nofollow" target="_blank">
        Axel F, Pierre T. (2017, October 16). Leviathan: Espionage actor spearphishes maritime and defense targets. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/library/bb490939.aspx" name="scite-20" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Using Netsh. Retrieved February 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/cc771046(v=ws.10).aspx" name="scite-21" rel="nofollow" target="_blank">
        Microsoft. (2009, June 3). Netsh Commands for Windows Firewall. Retrieved April 20, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html" name="scite-22" rel="nofollow" target="_blank">
        Singh, S. et al.. (2018, March 13). Iranian Threat Group Updates Tactics, Techniques and Procedures in Spear Phishing Campaign. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-23">
      <span class="scite-citation-text">
       <a class="external text" href="https://objective-see.com/blog/blog_0x25.html" name="scite-23" rel="nofollow" target="_blank">
        Patrick Wardle. (n.d.). Mac Malware of 2017. Retrieved September 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-24">
      <span class="scite-citation-text">
       <a class="external text" href="http://cdn0.vox-cdn.com/assets/4589853/crowdstrike-intelligence-report-putter-panda.original.pdf" name="scite-24" rel="nofollow" target="_blank">
        Crowdstrike Global Intelligence Team. (2014, June 9). CrowdStrike Intelligence Report: Putter Panda. Retrieved January 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-25">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/files/2016/07/The-ProjectSauron-APT_Technical_Analysis_KL.pdf" name="scite-25" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research &amp; Analysis Team. (2016, August 9). The ProjectSauron APT. Technical Analysis. Retrieved August 17, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-26">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/bronze-union" name="scite-26" rel="nofollow" target="_blank">
        Counter Threat Unit Research Team. (2017, June 27). BRONZE UNION Cyberespionage Persists Despite Disclosures. Retrieved July 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-27">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf" name="scite-27" rel="nofollow" target="_blank">
        Cylance. (2014, December). Operation Cleaver. Retrieved September 14, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-28">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-165A" name="scite-28" rel="nofollow" target="_blank">
        US-CERT. (2018, June 14). MAR-10135536-12 – North Korean Trojan: TYPEFRAME. Retrieved July 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-29">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" name="scite-29" rel="nofollow" target="_blank">
        Settle, A., et al. (2016, August 8). MONSOON - Analysis Of An APT Campaign. Retrieved September 22, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
