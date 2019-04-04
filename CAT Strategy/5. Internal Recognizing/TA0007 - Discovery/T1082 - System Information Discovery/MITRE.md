<div class="container-fluid">
 <h1>
  System Information Discovery
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An adversary may attempt to get detailed information about the operating system and hardware, including version, patches, hotfixes, service packs, and architecture.
   </p>
   <h3>
    Windows
   </h3>
   <p>
    Example commands and utilities that obtain this information include
    <code>
     ver
    </code>
    ,
    <a href="https://attack.mitre.org/software/S0096">
     Systeminfo
    </a>
    , and
    <code>
     dir
    </code>
    within
    <a href="https://attack.mitre.org/software/S0106">
     cmd
    </a>
    for identifying information based on present files and directories.
   </p>
   <h3>
    Mac
   </h3>
   <p>
    On Mac, the
    <code>
     systemsetup
    </code>
    command gives a detailed breakdown of the system, but it requires administrative privileges. Additionally, the
    <code>
     system_profiler
    </code>
    gives a very detailed breakdown of configurations, firewall rules, mounted volumes, hardware, and many other things without needing elevated permissions.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1082
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
      Process monitoring, Process command-line parameters
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
      <a href="https://capec.mitre.org/data/definitions/311.html" target="_blank">
       CAPEC-311
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
     <a href="https://attack.mitre.org/software/S0065">
      4H RAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0065">
       4H RAT
      </a>
      sends an OS version identifier in its beacons.
      <span class="scite-citeref-number" data-reference="CrowdStrike Putter Panda" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="http://cdn0.vox-cdn.com/assets/4589853/crowdstrike-intelligence-report-putter-panda.original.pdf" target="_blank">
         [1]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
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
      actors used the following commands after exploiting a machine with
      <a href="https://attack.mitre.org/software/S0042">
       LOWBALL
      </a>
      malware to obtain information about the OS:
      <code>
       ver &gt;&gt; %temp%\download
      </code>
      <code>
       systeminfo &gt;&gt; %temp%\download
      </code>
      <span class="scite-citeref-number" data-reference="FireEye admin@338" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.fireeye.com/blog/threat-research/2015/11/china-based-threat.html" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0045">
      ADVSTORESHELL
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0045">
       ADVSTORESHELL
      </a>
      can run
      <a href="https://attack.mitre.org/software/S0096">
       Systeminfo
      </a>
      to gather information about the victim.
      <span class="scite-citeref-number" data-reference="ESET Sednit Part 2" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part-2.pdf" target="_blank">
         [3]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Bitdefender APT28 Dec 2015" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://download.bitdefender.com/resources/media/materials/white-papers/en/Bitdefender_In-depth_analysis_of_APT28%E2%80%93The_Political_Cyber-Espionage.pdf" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0073">
      APT19
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0073">
       APT19
      </a>
      collected system architecture information.
      <a href="https://attack.mitre.org/groups/G0073">
       APT19
      </a>
      used an HTTP malware variant and a Port 22 malware variant to gather the hostname and CPU information from the victim’s machine.
      <span class="scite-citeref-number" data-reference="FireEye APT19" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.fireeye.com/blog/threat-research/2017/06/phished-at-the-request-of-counsel.html" target="_blank">
         [5]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Unit 42 C0d0so0 Jan 2016" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://researchcenter.paloaltonetworks.com/2016/01/new-attacks-linked-to-c0d0s0-group/" target="_blank">
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
      has a tool that can obtain information about the local system.
      <span class="scite-citeref-number" data-reference="Symantec Buckeye" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="http://www.symantec.com/connect/blogs/buckeye-cyberespionage-group-shifts-gaze-us-hong-kong" target="_blank">
         [7]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="evolution of pirpi" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://recon.cx/2017/montreal/resources/slides/RECON-MTL-2017-evolution_of_pirpi.pdf" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0050">
      APT32
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0050">
       APT32
      </a>
      collects the OS version and computer name.
      <span class="scite-citeref-number" data-reference="ESET OceanLotus" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.welivesecurity.com/2018/03/13/oceanlotus-ships-new-backdoor/" target="_blank">
         [9]
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
      collects the computer name, the BIOS model, and execution path.
      <span class="scite-citeref-number" data-reference="Talos Group123" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://blog.talosintelligence.com/2018/01/korea-in-crosshairs.html" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0093">
      Backdoor.Oldrea
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0093">
       Backdoor.Oldrea
      </a>
      collects information about the OS and computer name.
      <span class="scite-citeref-number" data-reference="Symantec Dragonfly" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/Dragonfly_Threat_Against_Western_Energy_Suppliers.pdf" target="_blank">
         [11]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0031">
      BACKSPACE
     </a>
    </td>
    <td>
     <p>
      During its initial execution,
      <a href="https://attack.mitre.org/software/S0031">
       BACKSPACE
      </a>
      extracts operating system information from the infected host.
      <span class="scite-citeref-number" data-reference="FireEye APT30" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://www2.fireeye.com/rs/fireye/images/rpt-apt30.pdf" target="_blank">
         [12]
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
      collects the computer name and host name on the compromised system.
      <span class="scite-citeref-number" data-reference="US-CERT BADCALL" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-G.PDF" target="_blank">
         [13]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0239">
      Bankshot
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0239">
       Bankshot
      </a>
      gathers system information, network addresses, disk type, disk free space, and the operation system version.
      <span class="scite-citeref-number" data-reference="McAfee Bankshot" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://securingtomorrow.mcafee.com/mcafee-labs/hidden-cobra-targets-turkish-financial-sector-new-bankshot-implant/" target="_blank">
         [14]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT Bankshot Dec 2017" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-B_WHITE.PDF" target="_blank">
         [15]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0268">
      Bisonal
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0268">
       Bisonal
      </a>
      has a command to gather system information from the victim’s machine.
      <span class="scite-citeref-number" data-reference="Unit 42 Bisonal July 2018" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-bisonal-malware-used-attacks-russia-south-korea/" target="_blank">
         [16]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0089">
      BlackEnergy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0089">
       BlackEnergy
      </a>
      has used
      <a href="https://attack.mitre.org/software/S0096">
       Systeminfo
      </a>
      to gather the OS version, as well as information on the system configuration, BIOS, the motherboard, and the processor.
      <span class="scite-citeref-number" data-reference="F-Secure BlackEnergy 2014" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://www.f-secure.com/documents/996508/1030745/blackenergy_whitepaper.pdf" target="_blank">
         [17]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Securelist BlackEnergy Nov 2014" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="https://securelist.com/be2-custom-plugins-router-abuse-and-target-profiles/67353/" target="_blank">
         [18]
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
      collects hard drive content and system configuration information.
      <span class="scite-citeref-number" data-reference="McAfee Gold Dragon" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="https://securingtomorrow.mcafee.com/mcafee-labs/gold-dragon-widens-olympics-malware-attacks-gains-permanent-presence-on-victims-systems/" target="_blank">
         [19]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0043">
      BUBBLEWRAP
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0043">
       BUBBLEWRAP
      </a>
      collects system information, including the operating system version and hostname.
      <span class="scite-citeref-number" data-reference="FireEye admin@338" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.fireeye.com/blog/threat-research/2015/11/china-based-threat.html" target="_blank">
         [2]
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
      collects the victim hostname, window resolution, and Microsoft Windows version.
      <span class="scite-citeref-number" data-reference="Palo Alto menuPass Feb 2017" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="http://researchcenter.paloaltonetworks.com/2017/02/unit42-menupass-returns-new-malware-new-attacks-japanese-academics-organizations/" target="_blank">
         [20]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PWC Cloud Hopper Technical Annex April 2017" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" target="_blank">
         [21]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0106">
      cmd
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0106">
       cmd
      </a>
      can be used to find information about the operating system.
      <span class="scite-citeref-number" data-reference="TechNet Dir" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="https://technet.microsoft.com/en-us/library/cc755121.aspx" target="_blank">
         [22]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0244">
      Comnie
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0244">
       Comnie
      </a>
      collects the hostname of the victim machine.
      <span class="scite-citeref-number" data-reference="Palo Alto Comnie" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="https://researchcenter.paloaltonetworks.com/2018/01/unit42-comnie-continues-target-organizations-east-asia/" target="_blank">
         [23]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0137">
      CORESHELL
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0137">
       CORESHELL
      </a>
      collects hostname, volume serial number and OS version data from the victim and sends the information to its C2 server.
      <span class="scite-citeref-number" data-reference="FireEye APT28" id="scite-ref-24-a" onclick="scrollToRef('scite-24')">
       <sup>
        <a aria-describedby="qtip-23" data-hasqtip="23" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/rpt-apt28.pdf" target="_blank">
         [24]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0046">
      CozyCar
     </a>
    </td>
    <td>
     <p>
      A system info module in
      <a href="https://attack.mitre.org/software/S0046">
       CozyCar
      </a>
      gathers information on the victim host’s configuration.
      <span class="scite-citeref-number" data-reference="F-Secure CozyDuke" id="scite-ref-25-a" onclick="scrollToRef('scite-25')">
       <sup>
        <a aria-describedby="qtip-24" data-hasqtip="24" href="https://www.f-secure.com/documents/996508/1030745/CozyDuke" target="_blank">
         [25]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0115">
      Crimson
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0115">
       Crimson
      </a>
      contains a command to collect the victim PC name and operating system.
      <span class="scite-citeref-number" data-reference="Proofpoint Operation Transparent Tribe March 2016" id="scite-ref-26-a" onclick="scrollToRef('scite-26')">
       <sup>
        <a aria-describedby="qtip-25" data-hasqtip="25" href="https://www.proofpoint.com/sites/default/files/proofpoint-operation-transparent-tribe-threat-insight-en.pdf" target="_blank">
         [26]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0021">
      Derusbi
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0021">
       Derusbi
      </a>
      gathers the name of the local host, version of GNU Compiler Collection (GCC), and the system information about the CPU, machine, and operating system.
      <span class="scite-citeref-number" data-reference="Fidelis Turbo" id="scite-ref-27-a" onclick="scrollToRef('scite-27')">
       <sup>
        <a aria-describedby="qtip-26" data-hasqtip="26" href="https://www.fidelissecurity.com/sites/default/files/TA_Fidelis_Turbo_1602_0.pdf" target="_blank">
         [27]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0186">
      DownPaper
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0186">
       DownPaper
      </a>
      collects the victim host name and serial number, and then sends the information to the C2 server.
      <span class="scite-citeref-number" data-reference="ClearSky Charming Kitten Dec 2017" id="scite-ref-28-a" onclick="scrollToRef('scite-28')">
       <sup>
        <a aria-describedby="qtip-27" data-hasqtip="27" href="http://www.clearskysec.com/wp-content/uploads/2017/12/Charming_Kitten_2017.pdf" target="_blank">
         [28]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0062">
      DustySky
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0062">
       DustySky
      </a>
      extracts basic information about the operating system.
      <span class="scite-citeref-number" data-reference="DustySky" id="scite-ref-29-a" onclick="scrollToRef('scite-29')">
       <sup>
        <a aria-describedby="qtip-28" data-hasqtip="28" href="https://www.clearskysec.com/wp-content/uploads/2016/01/Operation%20DustySky_TLP_WHITE.pdf" target="_blank">
         [29]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0081">
      Elise
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0081">
       Elise
      </a>
      executes
      <code>
       systeminfo
      </code>
      after initial communication is made to the remote server.
      <span class="scite-citeref-number" data-reference="Lotus Blossom Jun 2015" id="scite-ref-30-a" onclick="scrollToRef('scite-30')">
       <sup>
        <a aria-describedby="qtip-29" data-hasqtip="29" href="https://www.paloaltonetworks.com/resources/research/unit42-operation-lotus-blossom.html" target="_blank">
         [30]
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
      has the capability to execute ver, systeminfo, and gpresult commands.
      <span class="scite-citeref-number" data-reference="Emissary Trojan Feb 2016" id="scite-ref-31-a" onclick="scrollToRef('scite-31')">
       <sup>
        <a aria-describedby="qtip-30" data-hasqtip="30" href="http://researchcenter.paloaltonetworks.com/2016/02/emissary-trojan-changelog-did-operation-lotus-blossom-cause-it-to-evolve/" target="_blank">
         [31]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0181">
      FALLCHILL
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0181">
       FALLCHILL
      </a>
      can collect operating system (OS) version information, processor information, system name, and information about installed disks from the victim.
      <span class="scite-citeref-number" data-reference="US-CERT FALLCHILL Nov 2017" id="scite-ref-32-a" onclick="scrollToRef('scite-32')">
       <sup>
        <a aria-describedby="qtip-31" data-hasqtip="31" href="https://www.us-cert.gov/ncas/alerts/TA17-318A" target="_blank">
         [32]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0171">
      Felismus
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0171">
       Felismus
      </a>
      collects the system information, including hostname and OS version, and sends it to the C2 server.
      <span class="scite-citeref-number" data-reference="Forcepoint Felismus Mar 2017" id="scite-ref-33-a" onclick="scrollToRef('scite-33')">
       <sup>
        <a aria-describedby="qtip-32" data-hasqtip="32" href="https://blogs.forcepoint.com/security-labs/playing-cat-mouse-introducing-felismus-malware" target="_blank">
         [33]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0267">
      FELIXROOT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0267">
       FELIXROOT
      </a>
      collects the victim’s computer name, processor architecture, OS version, and volume serial number.
      <span class="scite-citeref-number" data-reference="FireEye FELIXROOT July 2018" id="scite-ref-34-a" onclick="scrollToRef('scite-34')">
       <sup>
        <a aria-describedby="qtip-33" data-hasqtip="33" href="https://www.fireeye.com/blog/threat-research/2018/07/microsoft-office-vulnerabilities-used-to-distribute-felixroot-backdoor.html" target="_blank">
         [34]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0182">
      FinFisher
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0182">
       FinFisher
      </a>
      checks if the victim OS is 32 or 64-bit.
      <span class="scite-citeref-number" data-reference="FinFisher Citation" id="scite-ref-35-a" onclick="scrollToRef('scite-35')">
       <sup>
        <a aria-describedby="qtip-34" data-hasqtip="34" href="http://www.finfisher.com/FinFisher/index.html" target="_blank">
         [35]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Microsoft FinFisher March 2018" id="scite-ref-36-a" onclick="scrollToRef('scite-36')">
       <sup>
        <a aria-describedby="qtip-35" data-hasqtip="35" href="https://cloudblogs.microsoft.com/microsoftsecure/2018/03/01/finfisher-exposed-a-researchers-tale-of-defeating-traps-tricks-and-complex-virtual-machines/" target="_blank">
         [36]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0047">
      Gamaredon Group
     </a>
    </td>
    <td>
     <p>
      A
      <a href="https://attack.mitre.org/groups/G0047">
       Gamaredon Group
      </a>
      file stealer can gather the victim's computer name and drive serial numbers to send to a C2 server.
      <span class="scite-citeref-number" data-reference="Palo Alto Gamaredon Feb 2017" id="scite-ref-37-a" onclick="scrollToRef('scite-37')">
       <sup>
        <a aria-describedby="qtip-36" data-hasqtip="36" href="https://researchcenter.paloaltonetworks.com/2017/02/unit-42-title-gamaredon-group-toolset-evolution/" target="_blank">
         [37]
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
      collects endpoint information using the
      <code>
       systeminfo
      </code>
      command.
      <span class="scite-citeref-number" data-reference="McAfee Gold Dragon" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="https://securingtomorrow.mcafee.com/mcafee-labs/gold-dragon-widens-olympics-malware-attacks-gains-permanent-presence-on-victims-systems/" target="_blank">
         [19]
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
      collects the MAC address, computer name, and CPU information.
      <span class="scite-citeref-number" data-reference="Talos GravityRAT" id="scite-ref-38-a" onclick="scrollToRef('scite-38')">
       <sup>
        <a aria-describedby="qtip-37" data-hasqtip="37" href="https://blog.talosintelligence.com/2018/04/gravityrat-two-year-evolution-of-apt.html" target="_blank">
         [38]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0151">
      HALFBAKED
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0151">
       HALFBAKED
      </a>
      can obtain information about the OS, processor, and BIOS.
      <span class="scite-citeref-number" data-reference="FireEye FIN7 April 2017" id="scite-ref-39-a" onclick="scrollToRef('scite-39')">
       <sup>
        <a aria-describedby="qtip-38" data-hasqtip="38" href="https://www.fireeye.com/blog/threat-research/2017/04/fin7-phishing-lnk.html" target="_blank">
         [39]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0214">
      HAPPYWORK
     </a>
    </td>
    <td>
     <p>
      can collect system information, including computer name, system manufacturer, IsDebuggerPresent state, and execution path.
      <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-40-a" onclick="scrollToRef('scite-40')">
       <sup>
        <a aria-describedby="qtip-39" data-hasqtip="39" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
         [40]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
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
      gathers computer name and information using the
      <code>
       systeminfo
      </code>
      command.
      <span class="scite-citeref-number" data-reference="McAfee Honeybee" id="scite-ref-41-a" onclick="scrollToRef('scite-41')">
       <sup>
        <a aria-describedby="qtip-40" data-hasqtip="40" href="https://securingtomorrow.mcafee.com/mcafee-labs/mcafee-uncovers-operation-honeybee-malicious-document-campaign-targeting-humanitarian-aid-groups/" target="_blank">
         [41]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0203">
      Hydraq
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0203">
       Hydraq
      </a>
      creates a backdoor through which remote attackers can retrieve information such as computer name, OS version, processor speed, memory size, and CPU speed.
      <span class="scite-citeref-number" data-reference="Symantec Hydraq Jan 2010" id="scite-ref-42-a" onclick="scrollToRef('scite-42')">
       <sup>
        <a aria-describedby="qtip-41" data-hasqtip="41" href="https://www.symantec.com/security_response/writeup.jsp?docid=2010-011114-1830-99" target="_blank">
         [42]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0259">
      InnaputRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0259">
       InnaputRAT
      </a>
      gathers volume drive information and system information.
      <span class="scite-citeref-number" data-reference="ASERT InnaputRAT April 2018" id="scite-ref-43-a" onclick="scrollToRef('scite-43')">
       <sup>
        <a aria-describedby="qtip-42" data-hasqtip="42" href="https://asert.arbornetworks.com/innaput-actors-utilize-remote-access-trojan-since-2016-presumably-targeting-victim-files/" target="_blank">
         [43]
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
      can gather information on the mapped drives, OS version, computer name, and memory size.
      <span class="scite-citeref-number" data-reference="ESET InvisiMole June 2018" id="scite-ref-44-a" onclick="scrollToRef('scite-44')">
       <sup>
        <a aria-describedby="qtip-43" data-hasqtip="43" href="https://www.welivesecurity.com/2018/06/07/invisimole-equipped-spyware-undercover/" target="_blank">
         [44]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0044">
      JHUHUGIT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0044">
       JHUHUGIT
      </a>
      obtains a build identifier as well as victim hard drive information from Windows registry key
      <code>
       HKLM\SYSTEM\CurrentControlSet\Services\Disk\Enum
      </code>
      . Another
      <a href="https://attack.mitre.org/software/S0044">
       JHUHUGIT
      </a>
      variant gathers the victim storage volume serial number and the storage device name.
      <span class="scite-citeref-number" data-reference="ESET Sednit Part 1" id="scite-ref-45-a" onclick="scrollToRef('scite-45')">
       <sup>
        <a aria-describedby="qtip-44" data-hasqtip="44" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part1.pdf" target="_blank">
         [45]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Unit 42 Sofacy Feb 2018" id="scite-ref-46-a" onclick="scrollToRef('scite-46')">
       <sup>
        <a aria-describedby="qtip-45" data-hasqtip="45" href="https://researchcenter.paloaltonetworks.com/2018/02/unit42-sofacy-attacks-multiple-government-entities/" target="_blank">
         [46]
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
      can obtain system information such as OS version and disk space.
      <span class="scite-citeref-number" data-reference="Microsoft PLATINUM April 2016" id="scite-ref-47-a" onclick="scrollToRef('scite-47')">
       <sup>
        <a aria-describedby="qtip-46" data-hasqtip="46" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" target="_blank">
         [47]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0215">
      KARAE
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0215">
       KARAE
      </a>
      can collect system information.
      <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-40-a" onclick="scrollToRef('scite-40')">
       <sup>
        <a aria-describedby="qtip-39" data-hasqtip="39" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
         [40]
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
      has the ability to obtain a victim's system name and operating system version.
      <span class="scite-citeref-number" data-reference="Zscaler Kasidet" id="scite-ref-48-a" onclick="scrollToRef('scite-48')">
       <sup>
        <a aria-describedby="qtip-47" data-hasqtip="47" href="http://research.zscaler.com/2016/01/malicious-office-files-dropping-kasidet.html" target="_blank">
         [48]
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
      gathers information on the system and local drives.
      <span class="scite-citeref-number" data-reference="Unit 42 Kazuar May 2017" id="scite-ref-49-a" onclick="scrollToRef('scite-49')">
       <sup>
        <a aria-describedby="qtip-48" data-hasqtip="48" href="https://researchcenter.paloaltonetworks.com/2017/05/unit42-kazuar-multiplatform-espionage-backdoor-api-access/" target="_blank">
         [49]
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
      performs operating system information discovery using
      <code>
       systeminfo
      </code>
      .
      <span class="scite-citeref-number" data-reference="Villeneuve et al 2014" id="scite-ref-50-a" onclick="scrollToRef('scite-50')">
       <sup>
        <a aria-describedby="qtip-49" data-hasqtip="49" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/wp-operation-ke3chang.pdf" target="_blank">
         [50]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="NCC Group APT15 Alive and Strong" id="scite-ref-51-a" onclick="scrollToRef('scite-51')">
       <sup>
        <a aria-describedby="qtip-50" data-hasqtip="50" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/" target="_blank">
         [51]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0271">
      KEYMARBLE
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0271">
       KEYMARBLE
      </a>
      has the capability to collect the computer name, language settings, the OS version, CPU information, disk devices, and time elapsed since system start.
      <span class="scite-citeref-number" data-reference="US-CERT KEYMARBLE Aug 2018" id="scite-ref-52-a" onclick="scrollToRef('scite-52')">
       <sup>
        <a aria-describedby="qtip-51" data-hasqtip="51" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-221A" target="_blank">
         [52]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0156">
      KOMPROGO
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0156">
       KOMPROGO
      </a>
      is capable of retrieving information about the infected system.
      <span class="scite-citeref-number" data-reference="FireEye APT32 May 2017" id="scite-ref-53-a" onclick="scrollToRef('scite-53')">
       <sup>
        <a aria-describedby="qtip-52" data-hasqtip="52" href="https://www.fireeye.com/blog/threat-research/2017/05/cyber-espionage-apt32.html" target="_blank">
         [53]
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
      collects OS version information such as registered owner details, manufacturer details, processor type, available storage, installed patches, hostname, version info, system date, and other system information by using the commands
      <code>
       systeminfo
      </code>
      ,
      <code>
       net config workstation
      </code>
      ,
      <code>
       hostname
      </code>
      ,
      <code>
       ver
      </code>
      ,
      <code>
       set
      </code>
      , and
      <code>
       date /t
      </code>
      .
      <span class="scite-citeref-number" data-reference="Symantec Orangeworm April 2018" id="scite-ref-54-a" onclick="scrollToRef('scite-54')">
       <sup>
        <a aria-describedby="qtip-53" data-hasqtip="53" href="https://www.symantec.com/blogs/threat-intelligence/orangeworm-targets-healthcare-us-europe-asia" target="_blank">
         [54]
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
      Several
      <a href="https://attack.mitre.org/groups/G0032">
       Lazarus Group
      </a>
      malware families collect information on the type and version of the victim OS, as well as the victim computer name and CPU information. A Destover-like variant used by
      <a href="https://attack.mitre.org/groups/G0032">
       Lazarus Group
      </a>
      also collects disk space information and sends it to its C2 server.
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster" id="scite-ref-55-a" onclick="scrollToRef('scite-55')">
       <sup>
        <a aria-describedby="qtip-54" data-hasqtip="54" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" target="_blank">
         [55]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster Destructive Malware" id="scite-ref-56-a" onclick="scrollToRef('scite-56')">
       <sup>
        <a aria-describedby="qtip-55" data-hasqtip="55" href="https://operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Destructive-Malware-Report.pdf" target="_blank">
         [56]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster Loaders" id="scite-ref-57-a" onclick="scrollToRef('scite-57')">
       <sup>
        <a aria-describedby="qtip-56" data-hasqtip="56" href="https://operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Loaders-Installers-and-Uninstallers-Report.pdf" target="_blank">
         [57]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="McAfee Lazarus Resurfaces Feb 2018" id="scite-ref-58-a" onclick="scrollToRef('scite-58')">
       <sup>
        <a aria-describedby="qtip-57" data-hasqtip="57" href="https://securingtomorrow.mcafee.com/mcafee-labs/lazarus-resurfaces-targets-global-banks-bitcoin-users/" target="_blank">
         [58]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="McAfee GhostSecret" id="scite-ref-59-a" onclick="scrollToRef('scite-59')">
       <sup>
        <a aria-describedby="qtip-58" data-hasqtip="58" href="https://securingtomorrow.mcafee.com/mcafee-labs/analyzing-operation-ghostsecret-attack-seeks-to-steal-data-worldwide/" target="_blank">
         [59]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0211">
      Linfo
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0211">
       Linfo
      </a>
      creates a backdoor through which remote attackers can retrieve system information.
      <span class="scite-citeref-number" data-reference="Symantec Linfo May 2012" id="scite-ref-60-a" onclick="scrollToRef('scite-60')">
       <sup>
        <a aria-describedby="qtip-59" data-hasqtip="59" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051605-2535-99" target="_blank">
         [60]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0059">
      Magic Hound
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0059">
       Magic Hound
      </a>
      malware has used a PowerShell command to check the victim system architecture to determine if it is an x64 machine. Other malware has obtained the OS version, UUID, and computer/host name to send to the C2 server.
      <span class="scite-citeref-number" data-reference="Unit 42 Magic Hound Feb 2017" id="scite-ref-61-a" onclick="scrollToRef('scite-61')">
       <sup>
        <a aria-describedby="qtip-60" data-hasqtip="60" href="https://researchcenter.paloaltonetworks.com/2017/02/unit42-magic-hound-campaign-attacks-saudi-targets/" target="_blank">
         [61]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0280">
      MirageFox
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0280">
       MirageFox
      </a>
      can collect CPU and architecture information from the victim’s machine.
      <span class="scite-citeref-number" data-reference="APT15 Intezer June 2018" id="scite-ref-62-a" onclick="scrollToRef('scite-62')">
       <sup>
        <a aria-describedby="qtip-61" data-hasqtip="61" href="https://www.intezer.com/miragefox-apt15-resurfaces-with-new-tools-based-on-old-ones/" target="_blank">
         [62]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0084">
      Mis-Type
     </a>
    </td>
    <td>
     <p>
      The initial beacon packet for
      <a href="https://attack.mitre.org/software/S0084">
       Mis-Type
      </a>
      contains the operating system version and file system of the victim.
      <span class="scite-citeref-number" data-reference="Cylance Dust Storm" id="scite-ref-63-a" onclick="scrollToRef('scite-63')">
       <sup>
        <a aria-describedby="qtip-62" data-hasqtip="62" href="https://www.cylance.com/content/dam/cylance/pdfs/reports/Op_Dust_Storm_Report.pdf" target="_blank">
         [63]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0083">
      Misdat
     </a>
    </td>
    <td>
     <p>
      The initial beacon packet for
      <a href="https://attack.mitre.org/software/S0083">
       Misdat
      </a>
      contains the operating system version of the victim.
      <span class="scite-citeref-number" data-reference="Cylance Dust Storm" id="scite-ref-63-a" onclick="scrollToRef('scite-63')">
       <sup>
        <a aria-describedby="qtip-62" data-hasqtip="62" href="https://www.cylance.com/content/dam/cylance/pdfs/reports/Op_Dust_Storm_Report.pdf" target="_blank">
         [63]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0079">
      MobileOrder
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0079">
       MobileOrder
      </a>
      has a command to upload to its C2 server victim mobile device information, including IMEI, IMSI, SIM card serial number, phone number, Android version, and other information.
      <span class="scite-citeref-number" data-reference="Scarlet Mimic Jan 2016" id="scite-ref-64-a" onclick="scrollToRef('scite-64')">
       <sup>
        <a aria-describedby="qtip-63" data-hasqtip="63" href="http://researchcenter.paloaltonetworks.com/2016/01/scarlet-mimic-years-long-espionage-targets-minority-activists/" target="_blank">
         [64]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0149">
      MoonWind
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0149">
       MoonWind
      </a>
      can obtain the victim hostname, Windows version, RAM amount, number of drives, and screen resolution.
      <span class="scite-citeref-number" data-reference="Palo Alto MoonWind March 2017" id="scite-ref-65-a" onclick="scrollToRef('scite-65')">
       <sup>
        <a aria-describedby="qtip-64" data-hasqtip="64" href="http://researchcenter.paloaltonetworks.com/2017/03/unit42-trochilus-rat-new-moonwind-rat-used-attack-thai-utility-organizations/" target="_blank">
         [65]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0284">
      More_eggs
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0284">
       More_eggs
      </a>
      has the capability to gather the OS version and computer name.
      <span class="scite-citeref-number" data-reference="Talos Cobalt Group July 2018" id="scite-ref-66-a" onclick="scrollToRef('scite-66')">
       <sup>
        <a aria-describedby="qtip-65" data-hasqtip="65" href="https://blog.talosintelligence.com/2018/07/multiple-cobalt-personality-disorder.html" target="_blank">
         [66]
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
      has the capability to retrieve information about the OS.
      <span class="scite-citeref-number" data-reference="FireEye Periscope March 2018" id="scite-ref-67-a" onclick="scrollToRef('scite-67')">
       <sup>
        <a aria-describedby="qtip-66" data-hasqtip="66" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" target="_blank">
         [67]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0205">
      Naid
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0205">
       Naid
      </a>
      collects a unique identifier (UID) from a compromised host.
      <span class="scite-citeref-number" data-reference="Symantec Naid June 2012" id="scite-ref-68-a" onclick="scrollToRef('scite-68')">
       <sup>
        <a aria-describedby="qtip-67" data-hasqtip="67" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-061518-4639-99" target="_blank">
         [68]
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
      can gather the victim computer name and serial number.
      <span class="scite-citeref-number" data-reference="Proofpoint Leviathan Oct 2017" id="scite-ref-69-a" onclick="scrollToRef('scite-69')">
       <sup>
        <a aria-describedby="qtip-68" data-hasqtip="68" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" target="_blank">
         [69]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0247">
      NavRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0247">
       NavRAT
      </a>
      uses
      <code>
       systeminfo
      </code>
      on a victim’s machine.
      <span class="scite-citeref-number" data-reference="Talos NavRAT May 2018" id="scite-ref-70-a" onclick="scrollToRef('scite-70')">
       <sup>
        <a aria-describedby="qtip-69" data-hasqtip="69" href="https://blog.talosintelligence.com/2018/05/navrat.html" target="_blank">
         [70]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0272">
      NDiskMonitor
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0272">
       NDiskMonitor
      </a>
      obtains the victim computer name and encrypts the information to send over its C2 channel.
      <span class="scite-citeref-number" data-reference="TrendMicro Patchwork Dec 2017" id="scite-ref-71-a" onclick="scrollToRef('scite-71')">
       <sup>
        <a aria-describedby="qtip-70" data-hasqtip="70" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" target="_blank">
         [71]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0198">
      NETWIRE
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0198">
       NETWIRE
      </a>
      can discover and collect victim system information.
      <span class="scite-citeref-number" data-reference="McAfee Netwire Mar 2015" id="scite-ref-72-a" onclick="scrollToRef('scite-72')">
       <sup>
        <a aria-describedby="qtip-71" data-hasqtip="71" href="https://securingtomorrow.mcafee.com/mcafee-labs/netwire-rat-behind-recent-targeted-attacks/" target="_blank">
         [72]
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
      has run
      <code>
       hostname
      </code>
      and
      <code>
       systeminfo
      </code>
      on a victim.
      <span class="scite-citeref-number" data-reference="Palo Alto OilRig May 2016" id="scite-ref-73-a" onclick="scrollToRef('scite-73')">
       <sup>
        <a aria-describedby="qtip-72" data-hasqtip="72" href="http://researchcenter.paloaltonetworks.com/2016/05/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/" target="_blank">
         [73]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Palo Alto OilRig Oct 2016" id="scite-ref-74-a" onclick="scrollToRef('scite-74')">
       <sup>
        <a aria-describedby="qtip-73" data-hasqtip="73" href="http://researchcenter.paloaltonetworks.com/2016/10/unit42-oilrig-malware-campaign-updates-toolset-and-expands-targets/" target="_blank">
         [74]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0264">
      OopsIE
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0264">
       OopsIE
      </a>
      checks for information on the CPU fan, temperature, mouse, hard disk, and motherboard as part of its anti-VM checks.
      <span class="scite-citeref-number" data-reference="Unit 42 OilRig Sept 2018" id="scite-ref-75-a" onclick="scrollToRef('scite-75')">
       <sup>
        <a aria-describedby="qtip-74" data-hasqtip="74" href="https://researchcenter.paloaltonetworks.com/2018/09/unit42-oilrig-targets-middle-eastern-government-adds-evasion-techniques-oopsie/" target="_blank">
         [75]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0229">
      Orz
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0229">
       Orz
      </a>
      can gather the victim OS version and whether it is 64 or 32 bit.
      <span class="scite-citeref-number" data-reference="Proofpoint Leviathan Oct 2017" id="scite-ref-69-a" onclick="scrollToRef('scite-69')">
       <sup>
        <a aria-describedby="qtip-68" data-hasqtip="68" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" target="_blank">
         [69]
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
      discovers information about the infected machine.
      <span class="scite-citeref-number" data-reference="Symantec Buckeye" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="http://www.symantec.com/connect/blogs/buckeye-cyberespionage-group-shifts-gaze-us-hong-kong" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0208">
      Pasam
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0208">
       Pasam
      </a>
      creates a backdoor through which remote attackers can retrieve information such as hostname and free disk space.
      <span class="scite-citeref-number" data-reference="Symantec Pasam May 2012" id="scite-ref-76-a" onclick="scrollToRef('scite-76')">
       <sup>
        <a aria-describedby="qtip-75" data-hasqtip="75" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-050412-4128-99" target="_blank">
         [76]
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
      collected the victim computer name, OS version, and architecture type and sent the information to its C2 server.
      <a href="https://attack.mitre.org/groups/G0040">
       Patchwork
      </a>
      also enumerated all available drives on the victim's machine.
      <span class="scite-citeref-number" data-reference="Cymmetria Patchwork" id="scite-ref-77-a" onclick="scrollToRef('scite-77')">
       <sup>
        <a aria-describedby="qtip-76" data-hasqtip="76" href="https://s3-us-west-2.amazonaws.com/cymmetria-blog/public/Unveiling_Patchwork.pdf" target="_blank">
         [77]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="TrendMicro Patchwork Dec 2017" id="scite-ref-71-a" onclick="scrollToRef('scite-71')">
       <sup>
        <a aria-describedby="qtip-70" data-hasqtip="70" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" target="_blank">
         [71]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0048">
      PinchDuke
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0048">
       PinchDuke
      </a>
      gathers system configuration information.
      <span class="scite-citeref-number" data-reference="F-Secure The Dukes" id="scite-ref-78-a" onclick="scrollToRef('scite-78')">
       <sup>
        <a aria-describedby="qtip-77" data-hasqtip="77" href="https://www.f-secure.com/documents/996508/1030745/dukes_whitepaper.pdf" target="_blank">
         [78]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0124">
      Pisloader
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0124">
       Pisloader
      </a>
      has a command to collect victim system information, including the system name and OS version.
      <span class="scite-citeref-number" data-reference="Palo Alto DNS Requests" id="scite-ref-79-a" onclick="scrollToRef('scite-79')">
       <sup>
        <a aria-describedby="qtip-78" data-hasqtip="78" href="http://researchcenter.paloaltonetworks.com/2016/05/unit42-new-wekby-attacks-use-dns-requests-as-command-and-control-mechanism/" target="_blank">
         [79]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0254">
      PLAINTEE
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0254">
       PLAINTEE
      </a>
      collects general system enumeration data about the infected machine and checks the OS version.
      <span class="scite-citeref-number" data-reference="Rancor Unit42 June 2018" id="scite-ref-80-a" onclick="scrollToRef('scite-80')">
       <sup>
        <a aria-describedby="qtip-79" data-hasqtip="79" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-rancor-targeted-attacks-south-east-asia-using-plaintee-ddkong-malware-families/" target="_blank">
         [80]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0216">
      POORAIM
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0216">
       POORAIM
      </a>
      can identify system information, including battery status.
      <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-40-a" onclick="scrollToRef('scite-40')">
       <sup>
        <a aria-describedby="qtip-39" data-hasqtip="39" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
         [40]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0139">
      PowerDuke
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0139">
       PowerDuke
      </a>
      has commands to get information about the victim's name, build, version, serial number, and memory usage.
      <span class="scite-citeref-number" data-reference="Volexity PowerDuke November 2016" id="scite-ref-81-a" onclick="scrollToRef('scite-81')">
       <sup>
        <a aria-describedby="qtip-80" data-hasqtip="80" href="https://www.volexity.com/blog/2016/11/09/powerduke-post-election-spear-phishing-campaigns-targeting-think-tanks-and-ngos/" target="_blank">
         [81]
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
      can retrieve OS name/architecture and computer/domain name information from compromised hosts.
      <span class="scite-citeref-number" data-reference="FireEye MuddyWater Mar 2018" id="scite-ref-82-a" onclick="scrollToRef('scite-82')">
       <sup>
        <a aria-describedby="qtip-81" data-hasqtip="81" href="https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html" target="_blank">
         [82]
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
      may collect information about the system by running
      <code>
       hostname
      </code>
      and
      <code>
       systeminfo
      </code>
      on a victim.
      <span class="scite-citeref-number" data-reference="FireEye APT34 Dec 2017" id="scite-ref-83-a" onclick="scrollToRef('scite-83')">
       <sup>
        <a aria-describedby="qtip-82" data-hasqtip="82" href="https://www.fireeye.com/blog/threat-research/2017/12/targeted-attack-in-middle-east-by-apt34.html" target="_blank">
         [83]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0113">
      Prikormka
     </a>
    </td>
    <td>
     <p>
      A module in
      <a href="https://attack.mitre.org/software/S0113">
       Prikormka
      </a>
      collects information from the victim about Windows OS version, computer name, battery info, and physical memory.
      <span class="scite-citeref-number" data-reference="ESET Operation Groundbait" id="scite-ref-84-a" onclick="scrollToRef('scite-84')">
       <sup>
        <a aria-describedby="qtip-83" data-hasqtip="83" href="http://www.welivesecurity.com/wp-content/uploads/2016/05/Operation-Groundbait.pdf" target="_blank">
         [84]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0238">
      Proxysvc
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0238">
       Proxysvc
      </a>
      collects the OS version, country name, MAC address, computer name, physical memory statistics, and volume information for all drives on the system.
      <span class="scite-citeref-number" data-reference="McAfee GhostSecret" id="scite-ref-59-a" onclick="scrollToRef('scite-59')">
       <sup>
        <a aria-describedby="qtip-58" data-hasqtip="58" href="https://securingtomorrow.mcafee.com/mcafee-labs/analyzing-operation-ghostsecret-attack-seeks-to-steal-data-worldwide/" target="_blank">
         [59]
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
      can grab a system’s information including the OS version, architecture, etc.
      <span class="scite-citeref-number" data-reference="GitHub Pupy" id="scite-ref-85-a" onclick="scrollToRef('scite-85')">
       <sup>
        <a aria-describedby="qtip-84" data-hasqtip="84" href="https://github.com/n1nj4sec/pupy" target="_blank">
         [85]
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
      has a command to gather system information from the victim’s machine.
      <span class="scite-citeref-number" data-reference="GitHub QuasarRAT" id="scite-ref-86-a" onclick="scrollToRef('scite-86')">
       <sup>
        <a aria-describedby="qtip-85" data-hasqtip="85" href="https://github.com/quasar/QuasarRAT" target="_blank">
         [86]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0241">
      RATANKBA
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0241">
       RATANKBA
      </a>
      gathers information about the OS architecture, OS name, and OS version/Service pack.
      <span class="scite-citeref-number" data-reference="Lazarus RATANKBA" id="scite-ref-87-a" onclick="scrollToRef('scite-87')">
       <sup>
        <a aria-describedby="qtip-86" data-hasqtip="86" href="https://blog.trendmicro.com/trendlabs-security-intelligence/lazarus-campaign-targeting-cryptocurrencies-reveals-remote-controller-tool-evolved-ratankba/" target="_blank">
         [87]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="RATANKBA" id="scite-ref-88-a" onclick="scrollToRef('scite-88')">
       <sup>
        <a aria-describedby="qtip-87" data-hasqtip="87" href="https://blog.trendmicro.com/trendlabs-security-intelligence/ratankba-watering-holes-against-enterprises/" target="_blank">
         [88]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0172">
      Reaver
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0172">
       Reaver
      </a>
      collects system information from the victim, including CPU speed, computer name, volume serial number, ANSI code page, OEM code page identifier for the OS, Microsoft Windows version, and memory information.
      <span class="scite-citeref-number" data-reference="Palo Alto Reaver Nov 2017" id="scite-ref-89-a" onclick="scrollToRef('scite-89')">
       <sup>
        <a aria-describedby="qtip-88" data-hasqtip="88" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-new-malware-with-ties-to-sunorcal-discovered/" target="_blank">
         [89]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0153">
      RedLeaves
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0153">
       RedLeaves
      </a>
      can gather extended system information including the hostname, OS version number, platform, memory information, time elapsed since system startup, and CPU information.
      <span class="scite-citeref-number" data-reference="PWC Cloud Hopper Technical Annex April 2017" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" target="_blank">
         [21]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Accenture Hogfish April 2018" id="scite-ref-90-a" onclick="scrollToRef('scite-90')">
       <sup>
        <a aria-describedby="qtip-89" data-hasqtip="89" href="https://www.accenture.com/t20180423T055005Z_w_/se-en/_acnmedia/PDF-76/Accenture-Hogfish-Threat-Analysis.pdf" target="_blank">
         [90]
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
      can obtain the OS version information, computer name, processor architecture, machine role, and OS edition.
      <span class="scite-citeref-number" data-reference="Kaspersky ProjectSauron Technical Analysis" id="scite-ref-91-a" onclick="scrollToRef('scite-91')">
       <sup>
        <a aria-describedby="qtip-90" data-hasqtip="90" href="https://securelist.com/files/2016/07/The-ProjectSauron-APT_Technical_Analysis_KL.pdf" target="_blank">
         [91]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0270">
      RogueRobin
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0270">
       RogueRobin
      </a>
      gathers BIOS versions and manufacturers, the number of CPU cores, the total physical memory, and the computer name.
      <span class="scite-citeref-number" data-reference="Unit 42 DarkHydrus July 2018" id="scite-ref-92-a" onclick="scrollToRef('scite-92')">
       <sup>
        <a aria-describedby="qtip-91" data-hasqtip="91" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-new-threat-actor-group-darkhydrus-targets-middle-east-government/" target="_blank">
         [92]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0240">
      ROKRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0240">
       ROKRAT
      </a>
      gathers the computer name and checks the OS version to ensure it doesn’t run on a Windows XP or Windows Server 2003 systems.
      <span class="scite-citeref-number" data-reference="Talos ROKRAT" id="scite-ref-93-a" onclick="scrollToRef('scite-93')">
       <sup>
        <a aria-describedby="qtip-92" data-hasqtip="92" href="https://blog.talosintelligence.com/2017/04/introducing-rokrat.html" target="_blank">
         [93]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Talos ROKRAT 2" id="scite-ref-94-a" onclick="scrollToRef('scite-94')">
       <sup>
        <a aria-describedby="qtip-93" data-hasqtip="93" href="https://blog.talosintelligence.com/2017/11/ROKRAT-Reloaded.html" target="_blank">
         [94]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0148">
      RTM
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0148">
       RTM
      </a>
      can obtain the computer name, OS version, and default language identifier.
      <span class="scite-citeref-number" data-reference="ESET RTM Feb 2017" id="scite-ref-95-a" onclick="scrollToRef('scite-95')">
       <sup>
        <a aria-describedby="qtip-94" data-hasqtip="94" href="https://www.welivesecurity.com/wp-content/uploads/2017/02/Read-The-Manual.pdf" target="_blank">
         [95]
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
      gathers the OS version, logical drives information, processor information, and volume information.
      <span class="scite-citeref-number" data-reference="McAfee Gold Dragon" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="https://securingtomorrow.mcafee.com/mcafee-labs/gold-dragon-widens-olympics-malware-attacks-gains-permanent-presence-on-victims-systems/" target="_blank">
         [19]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0085">
      S-Type
     </a>
    </td>
    <td>
     <p>
      The initial beacon packet for
      <a href="https://attack.mitre.org/software/S0085">
       S-Type
      </a>
      contains the operating system version and file system of the victim.
      <span class="scite-citeref-number" data-reference="Cylance Dust Storm" id="scite-ref-63-a" onclick="scrollToRef('scite-63')">
       <sup>
        <a aria-describedby="qtip-62" data-hasqtip="62" href="https://www.cylance.com/content/dam/cylance/pdfs/reports/Op_Dust_Storm_Report.pdf" target="_blank">
         [63]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0140">
      Shamoon
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0140">
       Shamoon
      </a>
      obtains the victim's operating system version and keyboard layout and sends the information to the C2 server.
      <span class="scite-citeref-number" data-reference="Palo Alto Shamoon Nov 2016" id="scite-ref-96-a" onclick="scrollToRef('scite-96')">
       <sup>
        <a aria-describedby="qtip-95" data-hasqtip="95" href="http://researchcenter.paloaltonetworks.com/2016/11/unit42-shamoon-2-return-disttrack-wiper/" target="_blank">
         [96]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0217">
      SHUTTERSPEED
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0217">
       SHUTTERSPEED
      </a>
      can collect system information.
      <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-40-a" onclick="scrollToRef('scite-40')">
       <sup>
        <a aria-describedby="qtip-39" data-hasqtip="39" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
         [40]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0218">
      SLOWDRIFT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0218">
       SLOWDRIFT
      </a>
      collects and sends system information to its C2.
      <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-40-a" onclick="scrollToRef('scite-40')">
       <sup>
        <a aria-describedby="qtip-39" data-hasqtip="39" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
         [40]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0157">
      SOUNDBITE
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0157">
       SOUNDBITE
      </a>
      is capable of gathering system information.
      <span class="scite-citeref-number" data-reference="FireEye APT32 May 2017" id="scite-ref-53-a" onclick="scrollToRef('scite-53')">
       <sup>
        <a aria-describedby="qtip-52" data-hasqtip="52" href="https://www.fireeye.com/blog/threat-research/2017/05/cyber-espionage-apt32.html" target="_blank">
         [53]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0054">
      Sowbug
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0054">
       Sowbug
      </a>
      obtained OS version and hardware configuration from a victim.
      <span class="scite-citeref-number" data-reference="Symantec Sowbug Nov 2017" id="scite-ref-97-a" onclick="scrollToRef('scite-97')">
       <sup>
        <a aria-describedby="qtip-96" data-hasqtip="96" href="https://www.symantec.com/connect/blogs/sowbug-cyber-espionage-group-targets-south-american-and-southeast-asian-governments" target="_blank">
         [97]
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
      sends information to its hard-coded C2, including OS version, service pack information, processor speed, system name, and OS install date.
      <span class="scite-citeref-number" data-reference="Baumgartner Naikon 2015" id="scite-ref-98-a" onclick="scrollToRef('scite-98')">
       <sup>
        <a aria-describedby="qtip-97" data-hasqtip="97" href="https://securelist.com/files/2015/05/TheNaikonAPT-MsnMM1.pdf" target="_blank">
         [98]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0038">
      Stealth Falcon
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0038">
       Stealth Falcon
      </a>
      malware gathers system information via WMI, including the system directory, build number, serial number, version, manufacturer, model, and total physical memory.
      <span class="scite-citeref-number" data-reference="Citizen Lab Stealth Falcon May 2016" id="scite-ref-99-a" onclick="scrollToRef('scite-99')">
       <sup>
        <a aria-describedby="qtip-98" data-hasqtip="98" href="https://citizenlab.org/2016/05/stealth-falcon/" target="_blank">
         [99]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0142">
      StreamEx
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0142">
       StreamEx
      </a>
      has the ability to enumerate system information.
      <span class="scite-citeref-number" data-reference="Cylance Shell Crew Feb 2017" id="scite-ref-100-a" onclick="scrollToRef('scite-100')">
       <sup>
        <a aria-describedby="qtip-99" data-hasqtip="99" href="https://www.cylance.com/shell-crew-variants-continue-to-fly-under-big-avs-radar" target="_blank">
         [100]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0242">
      SynAck
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0242">
       SynAck
      </a>
      gathers computer names, OS version info, and also checks installed keyboard layouts to estimate if it has been launched from a certain list of countries.
      <span class="scite-citeref-number" data-reference="SecureList SynAck Doppelgänging May 2018" id="scite-ref-101-a" onclick="scrollToRef('scite-101')">
       <sup>
        <a aria-describedby="qtip-100" data-hasqtip="100" href="https://securelist.com/synack-targeted-ransomware-uses-the-doppelganging-technique/85431/" target="_blank">
         [101]
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
      collects the computer name, OS versioning information, and OS install date and sends the information to the C2.
      <span class="scite-citeref-number" data-reference="Baumgartner Naikon 2015" id="scite-ref-98-a" onclick="scrollToRef('scite-98')">
       <sup>
        <a aria-describedby="qtip-97" data-hasqtip="97" href="https://securelist.com/files/2015/05/TheNaikonAPT-MsnMM1.pdf" target="_blank">
         [98]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0096">
      Systeminfo
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0096">
       Systeminfo
      </a>
      can be used to gather information about the operating system.
      <span class="scite-citeref-number" data-reference="TechNet Systeminfo" id="scite-ref-102-a" onclick="scrollToRef('scite-102')">
       <sup>
        <a aria-describedby="qtip-101" data-hasqtip="101" href="https://technet.microsoft.com/en-us/library/bb491007.aspx" target="_blank">
         [102]
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
      <a href="https://attack.mitre.org/software/S0098">
       T9000
      </a>
      gathers and beacons the operating system build number and CPU Architecture (32-bit/64-bit) during installation.
      <span class="scite-citeref-number" data-reference="Palo Alto T9000 Feb 2016" id="scite-ref-103-a" onclick="scrollToRef('scite-103')">
       <sup>
        <a aria-describedby="qtip-102" data-hasqtip="102" href="http://researchcenter.paloaltonetworks.com/2016/02/t9000-advanced-modular-backdoor-uses-complex-anti-analysis-techniques/" target="_blank">
         [103]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0266">
      TrickBot
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0266">
       TrickBot
      </a>
      gathers the OS version, CPU type, amount of RAM available from the victim’s machine.
      <span class="scite-citeref-number" data-reference="S2 Grupo TrickBot June 2017" id="scite-ref-104-a" onclick="scrollToRef('scite-104')">
       <sup>
        <a aria-describedby="qtip-103" data-hasqtip="103" href="https://www.securityartwork.es/wp-content/uploads/2017/07/Trickbot-report-S2-Grupo.pdf" target="_blank">
         [104]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Fidelis TrickBot Oct 2016" id="scite-ref-105-a" onclick="scrollToRef('scite-105')">
       <sup>
        <a aria-describedby="qtip-104" data-hasqtip="104" href="https://www.fidelissecurity.com/threatgeek/2016/10/trickbot-we-missed-you-dyre" target="_blank">
         [105]
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
      surveys a system upon check-in to discover operating system configuration details using the
      <code>
       systeminfo
      </code>
      and
      <code>
       set
      </code>
      commands.
      <span class="scite-citeref-number" data-reference="Kaspersky Turla" id="scite-ref-106-a" onclick="scrollToRef('scite-106')">
       <sup>
        <a aria-describedby="qtip-105" data-hasqtip="105" href="https://securelist.com/the-epic-turla-operation/65545/" target="_blank">
         [106]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0199">
      TURNEDUP
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0199">
       TURNEDUP
      </a>
      is capable of gathering system information.
      <span class="scite-citeref-number" data-reference="FireEye APT33 Sept 2017" id="scite-ref-107-a" onclick="scrollToRef('scite-107')">
       <sup>
        <a aria-describedby="qtip-106" data-hasqtip="106" href="https://www.fireeye.com/blog/threat-research/2017/09/apt33-insights-into-iranian-cyber-espionage.html" target="_blank">
         [107]
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
      can gather the disk volume information.
      <span class="scite-citeref-number" data-reference="US-CERT TYPEFRAME June 2018" id="scite-ref-108-a" onclick="scrollToRef('scite-108')">
       <sup>
        <a aria-describedby="qtip-107" data-hasqtip="107" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-165A" target="_blank">
         [108]
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
      can obtain information about the victim computer name, physical memory, country, and date.
      <span class="scite-citeref-number" data-reference="Forcepoint Monsoon" id="scite-ref-109-a" onclick="scrollToRef('scite-109')">
       <sup>
        <a aria-describedby="qtip-108" data-hasqtip="108" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" target="_blank">
         [109]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0275">
      UPPERCUT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0275">
       UPPERCUT
      </a>
      has the capability to gather the system’s hostname and OS version.
      <span class="scite-citeref-number" data-reference="FireEye APT10 Sept 2018" id="scite-ref-110-a" onclick="scrollToRef('scite-110')">
       <sup>
        <a aria-describedby="qtip-109" data-hasqtip="109" href="https://www.fireeye.com/blog/threat-research/2018/09/apt10-targeting-japanese-corporations-using-updated-ttps.html" target="_blank">
         [110]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0257">
      VERMIN
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0257">
       VERMIN
      </a>
      collects the OS name, machine name, and architecture information.
      <span class="scite-citeref-number" data-reference="Unit 42 VERMIN Jan 2018" id="scite-ref-111-a" onclick="scrollToRef('scite-111')">
       <sup>
        <a aria-describedby="qtip-110" data-hasqtip="110" href="https://researchcenter.paloaltonetworks.com/2018/01/unit42-vermin-quasar-rat-custom-malware-used-ukraine/" target="_blank">
         [111]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0180">
      Volgmer
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0180">
       Volgmer
      </a>
      can gather system information, the computer name, OS version, drive and serial information from the victim's machine.
      <span class="scite-citeref-number" data-reference="US-CERT Volgmer Nov 2017" id="scite-ref-112-a" onclick="scrollToRef('scite-112')">
       <sup>
        <a aria-describedby="qtip-111" data-hasqtip="111" href="https://www.us-cert.gov/ncas/alerts/TA17-318B" target="_blank">
         [112]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT Volgmer 2 Nov 2017" id="scite-ref-113-a" onclick="scrollToRef('scite-113')">
       <sup>
        <a aria-describedby="qtip-112" data-hasqtip="112" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-D_WHITE_S508C.PDF" target="_blank">
         [113]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Symantec Volgmer Aug 2014" id="scite-ref-114-a" onclick="scrollToRef('scite-114')">
       <sup>
        <a aria-describedby="qtip-113" data-hasqtip="113" href="https://www.symantec.com/security-center/writeup/2014-081811-3237-99?tabid=2" target="_blank">
         [114]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0155">
      WINDSHIELD
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0155">
       WINDSHIELD
      </a>
      can gather the victim computer name.
      <span class="scite-citeref-number" data-reference="FireEye APT32 May 2017" id="scite-ref-53-a" onclick="scrollToRef('scite-53')">
       <sup>
        <a aria-describedby="qtip-52" data-hasqtip="52" href="https://www.fireeye.com/blog/threat-research/2017/05/cyber-espionage-apt32.html" target="_blank">
         [53]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0219">
      WINERACK
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0219">
       WINERACK
      </a>
      can gather information about the host.
      <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-40-a" onclick="scrollToRef('scite-40')">
       <sup>
        <a aria-describedby="qtip-39" data-hasqtip="39" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
         [40]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0176">
      Wingbird
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0176">
       Wingbird
      </a>
      checks the victim OS version after executing to determine where to drop files based on whether the victim is 32-bit or 64-bit.
      <span class="scite-citeref-number" data-reference="Microsoft SIR Vol 21" id="scite-ref-115-a" onclick="scrollToRef('scite-115')">
       <sup>
        <a aria-describedby="qtip-114" data-hasqtip="114" href="http://download.microsoft.com/download/E/B/0/EB0F50CC-989C-4B66-B7F6-68CD3DC90DE3/Microsoft_Security_Intelligence_Report_Volume_21_English.pdf" target="_blank">
         [115]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0059">
      WinMM
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0059">
       WinMM
      </a>
      collects the system name, OS version including service pack, and system install date and sends the information to the C2 server.
      <span class="scite-citeref-number" data-reference="Baumgartner Naikon 2015" id="scite-ref-98-a" onclick="scrollToRef('scite-98')">
       <sup>
        <a aria-describedby="qtip-97" data-hasqtip="97" href="https://securelist.com/files/2015/05/TheNaikonAPT-MsnMM1.pdf" target="_blank">
         [98]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0161">
      XAgentOSX
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0161">
       XAgentOSX
      </a>
      contains the getInstalledAPP function to run
      <code>
       ls -la /Applications
      </code>
      to gather what applications are installed.
      <span class="scite-citeref-number" data-reference="XAgentOSX" id="scite-ref-116-a" onclick="scrollToRef('scite-116')">
       <sup>
        <a aria-describedby="qtip-115" data-hasqtip="115" href="https://researchcenter.paloaltonetworks.com/2017/02/unit42-xagentosx-sofacys-xagent-macos-tool/" target="_blank">
         [116]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0248">
      yty
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0248">
       yty
      </a>
      gathers the computer name, the serial number of the main disk volume, CPU information, Microsoft Windows version, and runs the command
      <code>
       systeminfo
      </code>
      .
      <span class="scite-citeref-number" data-reference="ASERT Donot March 2018" id="scite-ref-117-a" onclick="scrollToRef('scite-117')">
       <sup>
        <a aria-describedby="qtip-116" data-hasqtip="116" href="https://www.arbornetworks.com/blog/asert/donot-team-leverages-new-modular-malware-framework-south-asia/" target="_blank">
         [117]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0251">
      Zebrocy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0251">
       Zebrocy
      </a>
      collects the computer name and serial number for the storage volume C:.
      <span class="scite-citeref-number" data-reference="Palo Alto Sofacy 06-2018" id="scite-ref-118-a" onclick="scrollToRef('scite-118')">
       <sup>
        <a aria-describedby="qtip-117" data-hasqtip="117" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-sofacy-groups-parallel-attacks/" target="_blank">
         [118]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0230">
      ZeroT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0230">
       ZeroT
      </a>
      gathers the victim's computer name, Windows version, and system language, and then sends it to its C2 server.
      <span class="scite-citeref-number" data-reference="Proofpoint ZeroT Feb 2017" id="scite-ref-119-a" onclick="scrollToRef('scite-119')">
       <sup>
        <a aria-describedby="qtip-118" data-hasqtip="118" href="https://www.proofpoint.com/us/threat-insight/post/APT-targets-russia-belarus-zerot-plugx" target="_blank">
         [119]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0086">
      ZLib
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0086">
       ZLib
      </a>
      has the ability to enumerate system information.
      <span class="scite-citeref-number" data-reference="Cylance Dust Storm" id="scite-ref-63-a" onclick="scrollToRef('scite-63')">
       <sup>
        <a aria-describedby="qtip-62" data-hasqtip="62" href="https://www.cylance.com/content/dam/cylance/pdfs/reports/Op_Dust_Storm_Report.pdf" target="_blank">
         [63]
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
  Identify unnecessary system utilities or potentially malicious software that may be used to acquire information about the operating system and underlying hardware, and audit and/or block them by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-120-a">
   <sup>
    <a aria-describedby="qtip-119" data-hasqtip="119" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [120]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-121-a">
   <sup>
    <a aria-describedby="qtip-120" data-hasqtip="120" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [121]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-122-a">
   <sup>
    <a aria-describedby="qtip-121" data-hasqtip="121" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [122]
    </a>
   </sup>
  </span>
  or Software Restriction Policies
  <span class="scite-citeref-number" data-reference="Corio 2008" id="scite-ref-123-a">
   <sup>
    <a aria-describedby="qtip-122" data-hasqtip="122" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" target="_blank">
     [123]
    </a>
   </sup>
  </span>
  where appropriate.
  <span class="scite-citeref-number" data-reference="TechNet Applocker vs SRP" id="scite-ref-124-a">
   <sup>
    <a aria-describedby="qtip-123" data-hasqtip="123" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" target="_blank">
     [124]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  System and network discovery techniques normally occur throughout an operation as an adversary learns the environment. Data and events should not be viewed in isolation, but as part of a chain of behavior that could lead to other activities based on the information obtained.
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
       <a class="external text" href="http://cdn0.vox-cdn.com/assets/4589853/crowdstrike-intelligence-report-putter-panda.original.pdf" name="scite-1" rel="nofollow" target="_blank">
        Crowdstrike Global Intelligence Team. (2014, June 9). CrowdStrike Intelligence Report: Putter Panda. Retrieved January 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2015/11/china-based-threat.html" name="scite-2" rel="nofollow" target="_blank">
        FireEye Threat Intelligence. (2015, December 1). China-based Cyber Threat Group Uses Dropbox for Malware Communications and Targets Hong Kong Media Outlets. Retrieved December 4, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part-2.pdf" name="scite-3" rel="nofollow" target="_blank">
        ESET. (2016, October). En Route with Sednit - Part 2: Observing the Comings and Goings. Retrieved November 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://download.bitdefender.com/resources/media/materials/white-papers/en/Bitdefender_In-depth_analysis_of_APT28%E2%80%93The_Political_Cyber-Espionage.pdf" name="scite-4" rel="nofollow" target="_blank">
        Bitdefender. (2015, December). APT28 Under the Scope. Retrieved February 23, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/06/phished-at-the-request-of-counsel.html" name="scite-5" rel="nofollow" target="_blank">
        Ahl, I. (2017, June 06). Privileges and Credentials: Phished at the Request of Counsel. Retrieved May 17, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2016/01/new-attacks-linked-to-c0d0s0-group/" name="scite-6" rel="nofollow" target="_blank">
        Grunzweig, J., Lee, B. (2016, January 22). New Attacks Linked to C0d0so0 Group. Retrieved August 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/connect/blogs/buckeye-cyberespionage-group-shifts-gaze-us-hong-kong" name="scite-7" rel="nofollow" target="_blank">
        Symantec Security Response. (2016, September 6). Buckeye cyberespionage group shifts gaze from US to Hong Kong. Retrieved September 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://recon.cx/2017/montreal/resources/slides/RECON-MTL-2017-evolution_of_pirpi.pdf" name="scite-8" rel="nofollow" target="_blank">
        Yates, M. (2017, June 18). APT3 Uncovered: The code evolution of Pirpi. Retrieved September 28, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2018/03/13/oceanlotus-ships-new-backdoor/" name="scite-9" rel="nofollow" target="_blank">
        Foltýn, T. (2018, March 13). OceanLotus ships new backdoor using old tricks. Retrieved May 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/01/korea-in-crosshairs.html" name="scite-10" rel="nofollow" target="_blank">
        Mercer, W., Rascagneres, P. (2018, January 16). Korea In The Crosshairs. Retrieved May 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/Dragonfly_Threat_Against_Western_Energy_Suppliers.pdf" name="scite-11" rel="nofollow" target="_blank">
        Symantec Security Response. (2014, July 7). Dragonfly: Cyberespionage Attacks Against Energy Suppliers. Retrieved April 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/fireye/images/rpt-apt30.pdf" name="scite-12" rel="nofollow" target="_blank">
        FireEye Labs. (2015, April). APT30 AND THE MECHANICS OF A LONG-RUNNING CYBER ESPIONAGE OPERATION. Retrieved May 1, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-G.PDF" name="scite-13" rel="nofollow" target="_blank">
        US-CERT. (2018, February 06). Malware Analysis Report (MAR) - 10135536-G. Retrieved June 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/hidden-cobra-targets-turkish-financial-sector-new-bankshot-implant/" name="scite-14" rel="nofollow" target="_blank">
        Sherstobitoff, R. (2018, March 08). Hidden Cobra Targets Turkish Financial Sector With New Bankshot Implant. Retrieved May 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-B_WHITE.PDF" name="scite-15" rel="nofollow" target="_blank">
        US-CERT. (2017, December 13). Malware Analysis Report (MAR) - 10135536-B. Retrieved July 17, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-bisonal-malware-used-attacks-russia-south-korea/" name="scite-16" rel="nofollow" target="_blank">
        Hayashi, K., Ray, V. (2018, July 31). Bisonal Malware Used in Attacks Against Russia and South Korea. Retrieved August 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.f-secure.com/documents/996508/1030745/blackenergy_whitepaper.pdf" name="scite-17" rel="nofollow" target="_blank">
        F-Secure Labs. (2014). BlackEnergy &amp; Quedagh: The convergence of crimeware and APT attacks. Retrieved March 24, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/be2-custom-plugins-router-abuse-and-target-profiles/67353/" name="scite-18" rel="nofollow" target="_blank">
        Baumgartner, K. and Garnaeva, M.. (2014, November 3). BE2 custom plugins, router abuse, and target profiles. Retrieved March 24, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/gold-dragon-widens-olympics-malware-attacks-gains-permanent-presence-on-victims-systems/" name="scite-19" rel="nofollow" target="_blank">
        Sherstobitoff, R., Saavedra-Morales, J. (2018, February 02). Gold Dragon Widens Olympics Malware Attacks, Gains Permanent Presence on Victims’ Systems. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2017/02/unit42-menupass-returns-new-malware-new-attacks-japanese-academics-organizations/" name="scite-20" rel="nofollow" target="_blank">
        Miller-Osborn, J. and Grunzweig, J.. (2017, February 16). menuPass Returns with New Malware and New Attacks Against Japanese Academics and Organizations. Retrieved March 1, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" name="scite-21" rel="nofollow" target="_blank">
        PwC and BAE Systems. (2017, April). Operation Cloud Hopper: Technical Annex. Retrieved April 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/cc755121.aspx" name="scite-22" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Dir. Retrieved April 18, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-23">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/01/unit42-comnie-continues-target-organizations-east-asia/" name="scite-23" rel="nofollow" target="_blank">
        Grunzweig, J. (2018, January 31). Comnie Continues to Target Organizations in East Asia. Retrieved June 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-24">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/rpt-apt28.pdf" name="scite-24" rel="nofollow" target="_blank">
        FireEye. (2015). APT28: A WINDOW INTO RUSSIA’S CYBER ESPIONAGE OPERATIONS?. Retrieved August 19, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-25">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.f-secure.com/documents/996508/1030745/CozyDuke" name="scite-25" rel="nofollow" target="_blank">
        F-Secure Labs. (2015, April 22). CozyDuke: Malware Analysis. Retrieved December 10, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-26">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/sites/default/files/proofpoint-operation-transparent-tribe-threat-insight-en.pdf" name="scite-26" rel="nofollow" target="_blank">
        Huss, D.. (2016, March 1). Operation Transparent Tribe. Retrieved June 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-27">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fidelissecurity.com/sites/default/files/TA_Fidelis_Turbo_1602_0.pdf" name="scite-27" rel="nofollow" target="_blank">
        Fidelis Cybersecurity. (2016, February 29). The Turbo Campaign, Featuring Derusbi for 64-bit Linux. Retrieved March 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-28">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.clearskysec.com/wp-content/uploads/2017/12/Charming_Kitten_2017.pdf" name="scite-28" rel="nofollow" target="_blank">
        ClearSky Cyber Security. (2017, December). Charming Kitten. Retrieved December 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-29">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.clearskysec.com/wp-content/uploads/2016/01/Operation%20DustySky_TLP_WHITE.pdf" name="scite-29" rel="nofollow" target="_blank">
        ClearSky. (2016, January 7). Operation DustySky. Retrieved January 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-30">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.paloaltonetworks.com/resources/research/unit42-operation-lotus-blossom.html" name="scite-30" rel="nofollow" target="_blank">
        Falcone, R., et al.. (2015, June 16). Operation Lotus Blossom. Retrieved February 15, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-31">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/02/emissary-trojan-changelog-did-operation-lotus-blossom-cause-it-to-evolve/" name="scite-31" rel="nofollow" target="_blank">
        Falcone, R. and Miller-Osborn, J.. (2016, February 3). Emissary Trojan Changelog: Did Operation Lotus Blossom Cause It to Evolve?. Retrieved February 15, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-32">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA17-318A" name="scite-32" rel="nofollow" target="_blank">
        US-CERT. (2017, November 22). Alert (TA17-318A): HIDDEN COBRA – North Korean Remote Administration Tool: FALLCHILL. Retrieved December 7, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-33">
      <span class="scite-citation-text">
       <a class="external text" href="https://blogs.forcepoint.com/security-labs/playing-cat-mouse-introducing-felismus-malware" name="scite-33" rel="nofollow" target="_blank">
        Somerville, L. and Toro, A. (2017, March 30). Playing Cat &amp; Mouse: Introducing the Felismus Malware. Retrieved November 16, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-34">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/07/microsoft-office-vulnerabilities-used-to-distribute-felixroot-backdoor.html" name="scite-34" rel="nofollow" target="_blank">
        Patil, S. (2018, June 26). Microsoft Office Vulnerabilities Used to Distribute FELIXROOT Backdoor in Recent Campaign. Retrieved July 31, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-35">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.finfisher.com/FinFisher/index.html" name="scite-35" rel="nofollow" target="_blank">
        FinFisher. (n.d.). Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-36">
      <span class="scite-citation-text">
       <a class="external text" href="https://cloudblogs.microsoft.com/microsoftsecure/2018/03/01/finfisher-exposed-a-researchers-tale-of-defeating-traps-tricks-and-complex-virtual-machines/" name="scite-36" rel="nofollow" target="_blank">
        Allievi, A.,Flori, E. (2018, March 01). FinFisher exposed: A researcher’s tale of defeating traps, tricks, and complex virtual machines. Retrieved July 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-37">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/02/unit-42-title-gamaredon-group-toolset-evolution/" name="scite-37" rel="nofollow" target="_blank">
        Kasza, A. and Reichel, D.. (2017, February 27). The Gamaredon Group Toolset Evolution. Retrieved March 1, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-38">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/04/gravityrat-two-year-evolution-of-apt.html" name="scite-38" rel="nofollow" target="_blank">
        Mercer, W., Rascagneres, P. (2018, April 26). GravityRAT - The Two-Year Evolution Of An APT Targeting India. Retrieved May 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-39">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/04/fin7-phishing-lnk.html" name="scite-39" rel="nofollow" target="_blank">
        Carr, N., et al. (2017, April 24). FIN7 Evolution and the Phishing LNK. Retrieved April 24, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-40">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" name="scite-40" rel="nofollow" target="_blank">
        FireEye. (2018, February 20). APT37 (Reaper): The Overlooked North Korean Actor. Retrieved March 1, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-41">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/mcafee-uncovers-operation-honeybee-malicious-document-campaign-targeting-humanitarian-aid-groups/" name="scite-41" rel="nofollow" target="_blank">
        Sherstobitoff, R. (2018, March 02). McAfee Uncovers Operation Honeybee, a Malicious Document Campaign Targeting Humanitarian Aid Groups. Retrieved May 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-42">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2010-011114-1830-99" name="scite-42" rel="nofollow" target="_blank">
        Lelli, A. (2010, January 11). Trojan.Hydraq. Retrieved February 20, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-43">
      <span class="scite-citation-text">
       <a class="external text" href="https://asert.arbornetworks.com/innaput-actors-utilize-remote-access-trojan-since-2016-presumably-targeting-victim-files/" name="scite-43" rel="nofollow" target="_blank">
        ASERT Team. (2018, April 04). Innaput Actors Utilize Remote Access Trojan Since 2016, Presumably Targeting Victim Files. Retrieved July 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-44">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2018/06/07/invisimole-equipped-spyware-undercover/" name="scite-44" rel="nofollow" target="_blank">
        Hromcová, Z. (2018, June 07). InvisiMole: Surprisingly equipped spyware, undercover since 2013. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-45">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part1.pdf" name="scite-45" rel="nofollow" target="_blank">
        ESET. (2016, October). En Route with Sednit - Part 1: Approaching the Target. Retrieved November 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-46">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/02/unit42-sofacy-attacks-multiple-government-entities/" name="scite-46" rel="nofollow" target="_blank">
        Lee, B, et al. (2018, February 28). Sofacy Attacks Multiple Government Entities. Retrieved March 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-47">
      <span class="scite-citation-text">
       <a class="external text" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" name="scite-47" rel="nofollow" target="_blank">
        Windows Defender Advanced Threat Hunting Team. (2016, April 29). PLATINUM: Targeted attacks in South and Southeast Asia. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-48">
      <span class="scite-citation-text">
       <a class="external text" href="http://research.zscaler.com/2016/01/malicious-office-files-dropping-kasidet.html" name="scite-48" rel="nofollow" target="_blank">
        Yadav, A., et al. (2016, January 29). Malicious Office files dropping Kasidet and Dridex. Retrieved March 24, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-49">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/05/unit42-kazuar-multiplatform-espionage-backdoor-api-access/" name="scite-49" rel="nofollow" target="_blank">
        Levene, B, et al. (2017, May 03). Kazuar: Multiplatform Espionage Backdoor with API Access. Retrieved July 17, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-50">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/wp-operation-ke3chang.pdf" name="scite-50" rel="nofollow" target="_blank">
        Villeneuve, N., Bennett, J. T., Moran, N., Haq, T., Scott, M., &amp; Geers, K. (2014). OPERATION “KE3CHANG”: Targeted Attacks Against Ministries of Foreign Affairs. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-51">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/" name="scite-51" rel="nofollow" target="_blank">
        Smallridge, R. (2018, March 10). APT15 is alive and strong: An analysis of RoyalCli and RoyalDNS. Retrieved April 4, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-52">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-221A" name="scite-52" rel="nofollow" target="_blank">
        US-CERT. (2018, August 09). MAR-10135536-17 – North Korean Trojan: KEYMARBLE. Retrieved August 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-53">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/05/cyber-espionage-apt32.html" name="scite-53" rel="nofollow" target="_blank">
        Carr, N.. (2017, May 14). Cyber Espionage is Alive and Well: APT32 and the Threat to Global Corporations. Retrieved June 18, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-54">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/orangeworm-targets-healthcare-us-europe-asia" name="scite-54" rel="nofollow" target="_blank">
        Symantec Security Response Attack Investigation Team. (2018, April 23). New Orangeworm attack group targets the healthcare sector in the U.S., Europe, and Asia. Retrieved May 8, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-55">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" name="scite-55" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Unraveling the Long Thread of the Sony Attack. Retrieved February 25, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-56">
      <span class="scite-citation-text">
       <a class="external text" href="https://operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Destructive-Malware-Report.pdf" name="scite-56" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Destructive Malware Report. Retrieved March 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-57">
      <span class="scite-citation-text">
       <a class="external text" href="https://operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Loaders-Installers-and-Uninstallers-Report.pdf" name="scite-57" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Loaders, Installers and Uninstallers Report. Retrieved March 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-58">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/lazarus-resurfaces-targets-global-banks-bitcoin-users/" name="scite-58" rel="nofollow" target="_blank">
        Sherstobitoff, R. (2018, February 12). Lazarus Resurfaces, Targets Global Banks and Bitcoin Users. Retrieved February 19, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-59">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/analyzing-operation-ghostsecret-attack-seeks-to-steal-data-worldwide/" name="scite-59" rel="nofollow" target="_blank">
        Sherstobitoff, R., Malhotra, A. (2018, April 24). Analyzing Operation GhostSecret: Attack Seeks to Steal Data Worldwide. Retrieved May 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-60">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051605-2535-99" name="scite-60" rel="nofollow" target="_blank">
        Zhou, R. (2012, May 15). Backdoor.Linfo. Retrieved February 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-61">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/02/unit42-magic-hound-campaign-attacks-saudi-targets/" name="scite-61" rel="nofollow" target="_blank">
        Lee, B. and Falcone, R. (2017, February 15). Magic Hound Campaign Attacks Saudi Targets. Retrieved December 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-62">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.intezer.com/miragefox-apt15-resurfaces-with-new-tools-based-on-old-ones/" name="scite-62" rel="nofollow" target="_blank">
        Rosenberg, J. (2018, June 14). MirageFox: APT15 Resurfaces With New Tools Based On Old Ones. Retrieved September 21, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="63.0">
    <li>
     <span class="scite-citation" id="scite-63">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cylance.com/content/dam/cylance/pdfs/reports/Op_Dust_Storm_Report.pdf" name="scite-63" rel="nofollow" target="_blank">
        Gross, J. (2016, February 23). Operation Dust Storm. Retrieved September 19, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-64">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/01/scarlet-mimic-years-long-espionage-targets-minority-activists/" name="scite-64" rel="nofollow" target="_blank">
        Falcone, R. and Miller-Osborn, J.. (2016, January 24). Scarlet Mimic: Years-Long Espionage Campaign Targets Minority Activists. Retrieved February 10, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-65">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2017/03/unit42-trochilus-rat-new-moonwind-rat-used-attack-thai-utility-organizations/" name="scite-65" rel="nofollow" target="_blank">
        Miller-Osborn, J. and Grunzweig, J.. (2017, March 30). Trochilus and New MoonWind RATs Used In Attack Against Thai Organizations. Retrieved March 30, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-66">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/07/multiple-cobalt-personality-disorder.html" name="scite-66" rel="nofollow" target="_blank">
        Svajcer, V. (2018, July 31). Multiple Cobalt Personality Disorder. Retrieved September 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-67">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" name="scite-67" rel="nofollow" target="_blank">
        FireEye. (2018, March 16). Suspected Chinese Cyber Espionage Group (TEMP.Periscope) Targeting U.S. Engineering and Maritime Industries. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-68">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-061518-4639-99" name="scite-68" rel="nofollow" target="_blank">
        Neville, A. (2012, June 15). Trojan.Naid. Retrieved February 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-69">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" name="scite-69" rel="nofollow" target="_blank">
        Axel F, Pierre T. (2017, October 16). Leviathan: Espionage actor spearphishes maritime and defense targets. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-70">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/05/navrat.html" name="scite-70" rel="nofollow" target="_blank">
        Mercer, W., Rascagneres, P. (2018, May 31). NavRAT Uses US-North Korea Summit As Decoy For Attacks In South Korea. Retrieved June 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-71">
      <span class="scite-citation-text">
       <a class="external text" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" name="scite-71" rel="nofollow" target="_blank">
        Lunghi, D., et al. (2017, December). Untangling the Patchwork Cyberespionage Group. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-72">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/netwire-rat-behind-recent-targeted-attacks/" name="scite-72" rel="nofollow" target="_blank">
        McAfee. (2015, March 2). Netwire RAT Behind Recent Targeted Attacks. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-73">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/05/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/" name="scite-73" rel="nofollow" target="_blank">
        Falcone, R. and Lee, B.. (2016, May 26). The OilRig Campaign: Attacks on Saudi Arabian Organizations Deliver Helminth Backdoor. Retrieved May 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-74">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/10/unit42-oilrig-malware-campaign-updates-toolset-and-expands-targets/" name="scite-74" rel="nofollow" target="_blank">
        Grunzweig, J. and Falcone, R.. (2016, October 4). OilRig Malware Campaign Updates Toolset and Expands Targets. Retrieved May 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-75">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/09/unit42-oilrig-targets-middle-eastern-government-adds-evasion-techniques-oopsie/" name="scite-75" rel="nofollow" target="_blank">
        Falcone, R., et al. (2018, September 04). OilRig Targets a Middle Eastern Government and Adds Evasion Techniques to OopsIE. Retrieved September 24, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-76">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-050412-4128-99" name="scite-76" rel="nofollow" target="_blank">
        Mullaney, C. &amp; Honda, H. (2012, May 4). Trojan.Pasam. Retrieved February 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-77">
      <span class="scite-citation-text">
       <a class="external text" href="https://s3-us-west-2.amazonaws.com/cymmetria-blog/public/Unveiling_Patchwork.pdf" name="scite-77" rel="nofollow" target="_blank">
        Cymmetria. (2016). Unveiling Patchwork - The Copy-Paste APT. Retrieved August 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-78">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.f-secure.com/documents/996508/1030745/dukes_whitepaper.pdf" name="scite-78" rel="nofollow" target="_blank">
        F-Secure Labs. (2015, September 17). The Dukes: 7 years of Russian cyberespionage. Retrieved December 10, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-79">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/05/unit42-new-wekby-attacks-use-dns-requests-as-command-and-control-mechanism/" name="scite-79" rel="nofollow" target="_blank">
        Grunzweig, J., et al. (2016, May 24). New Wekby Attacks Use DNS Requests As Command and Control Mechanism. Retrieved August 17, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-80">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-rancor-targeted-attacks-south-east-asia-using-plaintee-ddkong-malware-families/" name="scite-80" rel="nofollow" target="_blank">
        Ash, B., et al. (2018, June 26). RANCOR: Targeted Attacks in South East Asia Using PLAINTEE and DDKONG Malware Families. Retrieved July 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-81">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.volexity.com/blog/2016/11/09/powerduke-post-election-spear-phishing-campaigns-targeting-think-tanks-and-ngos/" name="scite-81" rel="nofollow" target="_blank">
        Adair, S.. (2016, November 9). PowerDuke: Widespread Post-Election Spear Phishing Campaigns Targeting Think Tanks and NGOs. Retrieved January 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-82">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html" name="scite-82" rel="nofollow" target="_blank">
        Singh, S. et al.. (2018, March 13). Iranian Threat Group Updates Tactics, Techniques and Procedures in Spear Phishing Campaign. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-83">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/12/targeted-attack-in-middle-east-by-apt34.html" name="scite-83" rel="nofollow" target="_blank">
        Sardiwal, M, et al. (2017, December 7). New Targeted Attack in the Middle East by APT34, a Suspected Iranian Threat Group, Using CVE-2017-11882 Exploit. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-84">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.welivesecurity.com/wp-content/uploads/2016/05/Operation-Groundbait.pdf" name="scite-84" rel="nofollow" target="_blank">
        Cherepanov, A.. (2016, May 17). Operation Groundbait: Analysis of a surveillance toolkit. Retrieved May 18, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-85">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/n1nj4sec/pupy" name="scite-85" rel="nofollow" target="_blank">
        Nicolas Verdier. (n.d.). Retrieved January 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-86">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/quasar/QuasarRAT" name="scite-86" rel="nofollow" target="_blank">
        MaxXor. (n.d.). QuasarRAT. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-87">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/lazarus-campaign-targeting-cryptocurrencies-reveals-remote-controller-tool-evolved-ratankba/" name="scite-87" rel="nofollow" target="_blank">
        Lei, C., et al. (2018, January 24). Lazarus Campaign Targeting Cryptocurrencies Reveals Remote Controller Tool, an Evolved RATANKBA, and More. Retrieved May 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-88">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/ratankba-watering-holes-against-enterprises/" name="scite-88" rel="nofollow" target="_blank">
        Trend Micro. (2017, February 27). RATANKBA: Delving into Large-scale Watering Holes against Enterprises. Retrieved May 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-89">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-new-malware-with-ties-to-sunorcal-discovered/" name="scite-89" rel="nofollow" target="_blank">
        Grunzweig, J. and Miller-Osborn, J. (2017, November 10). New Malware with Ties to SunOrcal Discovered. Retrieved November 16, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-90">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.accenture.com/t20180423T055005Z_w_/se-en/_acnmedia/PDF-76/Accenture-Hogfish-Threat-Analysis.pdf" name="scite-90" rel="nofollow" target="_blank">
        Accenture Security. (2018, April 23). Hogfish Redleaves Campaign. Retrieved July 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-91">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/files/2016/07/The-ProjectSauron-APT_Technical_Analysis_KL.pdf" name="scite-91" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research &amp; Analysis Team. (2016, August 9). The ProjectSauron APT. Technical Analysis. Retrieved August 17, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-92">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-new-threat-actor-group-darkhydrus-targets-middle-east-government/" name="scite-92" rel="nofollow" target="_blank">
        Falcone, R., et al. (2018, July 27). New Threat Actor Group DarkHydrus Targets Middle East Government. Retrieved August 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-93">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2017/04/introducing-rokrat.html" name="scite-93" rel="nofollow" target="_blank">
        Mercer, W., Rascagneres, P. (2017, April 03). Introducing ROKRAT. Retrieved May 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-94">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2017/11/ROKRAT-Reloaded.html" name="scite-94" rel="nofollow" target="_blank">
        Mercer, W., Rascagneres, P. (2017, November 28). ROKRAT Reloaded. Retrieved May 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-95">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2017/02/Read-The-Manual.pdf" name="scite-95" rel="nofollow" target="_blank">
        Faou, M. and Boutin, J.. (2017, February). Read The Manual: A Guide to the RTM Banking Trojan. Retrieved March 9, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-96">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/11/unit42-shamoon-2-return-disttrack-wiper/" name="scite-96" rel="nofollow" target="_blank">
        Falcone, R.. (2016, November 30). Shamoon 2: Return of the Disttrack Wiper. Retrieved January 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-97">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/connect/blogs/sowbug-cyber-espionage-group-targets-south-american-and-southeast-asian-governments" name="scite-97" rel="nofollow" target="_blank">
        Symantec Security Response. (2017, November 7). Sowbug: Cyber espionage group targets South American and Southeast Asian governments. Retrieved November 16, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-98">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/files/2015/05/TheNaikonAPT-MsnMM1.pdf" name="scite-98" rel="nofollow" target="_blank">
        Baumgartner, K., Golovkin, M.. (2015, May). The MsnMM Campaigns: The Earliest Naikon APT Campaigns. Retrieved December 17, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-99">
      <span class="scite-citation-text">
       <a class="external text" href="https://citizenlab.org/2016/05/stealth-falcon/" name="scite-99" rel="nofollow" target="_blank">
        Marczak, B. and Scott-Railton, J.. (2016, May 29). Keep Calm and (Don’t) Enable Macros: A New Threat Actor Targets UAE Dissidents. Retrieved June 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-100">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cylance.com/shell-crew-variants-continue-to-fly-under-big-avs-radar" name="scite-100" rel="nofollow" target="_blank">
        Cylance SPEAR Team. (2017, February 9). Shell Crew Variants Continue to Fly Under Big AV’s Radar. Retrieved February 15, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-101">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/synack-targeted-ransomware-uses-the-doppelganging-technique/85431/" name="scite-101" rel="nofollow" target="_blank">
        Ivanov, A. et al.. (2018, May 7). SynAck targeted ransomware uses the Doppelgänging technique. Retrieved May 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-102">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/bb491007.aspx" name="scite-102" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Systeminfo. Retrieved April 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-103">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/02/t9000-advanced-modular-backdoor-uses-complex-anti-analysis-techniques/" name="scite-103" rel="nofollow" target="_blank">
        Grunzweig, J. and Miller-Osborn, J.. (2016, February 4). T9000: Advanced Modular Backdoor Uses Complex Anti-Analysis Techniques. Retrieved April 15, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-104">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.securityartwork.es/wp-content/uploads/2017/07/Trickbot-report-S2-Grupo.pdf" name="scite-104" rel="nofollow" target="_blank">
        Salinas, M., Holguin, J. (2017, June). Evolution of Trickbot. Retrieved July 31, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-105">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fidelissecurity.com/threatgeek/2016/10/trickbot-we-missed-you-dyre" name="scite-105" rel="nofollow" target="_blank">
        Reaves, J. (2016, October 15). TrickBot: We Missed you, Dyre. Retrieved August 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-106">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/the-epic-turla-operation/65545/" name="scite-106" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2014, August 7). The Epic Turla Operation: Solving some of the mysteries of Snake/Uroburos. Retrieved December 11, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-107">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/09/apt33-insights-into-iranian-cyber-espionage.html" name="scite-107" rel="nofollow" target="_blank">
        O'Leary, J., et al. (2017, September 20). Insights into Iranian Cyber Espionage: APT33 Targets Aerospace and Energy Sectors and has Ties to Destructive Malware. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-108">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-165A" name="scite-108" rel="nofollow" target="_blank">
        US-CERT. (2018, June 14). MAR-10135536-12 – North Korean Trojan: TYPEFRAME. Retrieved July 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-109">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" name="scite-109" rel="nofollow" target="_blank">
        Settle, A., et al. (2016, August 8). MONSOON - Analysis Of An APT Campaign. Retrieved September 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-110">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/09/apt10-targeting-japanese-corporations-using-updated-ttps.html" name="scite-110" rel="nofollow" target="_blank">
        Matsuda, A., Muhammad I. (2018, September 13). APT10 Targeting Japanese Corporations Using Updated TTPs. Retrieved September 17, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-111">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/01/unit42-vermin-quasar-rat-custom-malware-used-ukraine/" name="scite-111" rel="nofollow" target="_blank">
        Lancaster, T., Cortes, J. (2018, January 29). VERMIN: Quasar RAT and Custom Malware Used In Ukraine. Retrieved July 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-112">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA17-318B" name="scite-112" rel="nofollow" target="_blank">
        US-CERT. (2017, November 22). Alert (TA17-318B): HIDDEN COBRA – North Korean Trojan: Volgmer. Retrieved December 7, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-113">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-D_WHITE_S508C.PDF" name="scite-113" rel="nofollow" target="_blank">
        US-CERT. (2017, November 01). Malware Analysis Report (MAR) - 10135536-D. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-114">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security-center/writeup/2014-081811-3237-99?tabid=2" name="scite-114" rel="nofollow" target="_blank">
        Yagi, J. (2014, August 24). Trojan.Volgmer. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-115">
      <span class="scite-citation-text">
       <a class="external text" href="http://download.microsoft.com/download/E/B/0/EB0F50CC-989C-4B66-B7F6-68CD3DC90DE3/Microsoft_Security_Intelligence_Report_Volume_21_English.pdf" name="scite-115" rel="nofollow" target="_blank">
        Anthe, C. et al. (2016, December 14). Microsoft Security Intelligence Report Volume 21. Retrieved November 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-116">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/02/unit42-xagentosx-sofacys-xagent-macos-tool/" name="scite-116" rel="nofollow" target="_blank">
        Robert Falcone. (2017, February 14). XAgentOSX: Sofacy's Xagent macOS Tool. Retrieved July 12, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-117">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.arbornetworks.com/blog/asert/donot-team-leverages-new-modular-malware-framework-south-asia/" name="scite-117" rel="nofollow" target="_blank">
        Schwarz, D., Sopko J. (2018, March 08). Donot Team Leverages New Modular Malware Framework in South Asia. Retrieved June 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-118">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-sofacy-groups-parallel-attacks/" name="scite-118" rel="nofollow" target="_blank">
        Lee, B., Falcone, R. (2018, June 06). Sofacy Group’s Parallel Attacks. Retrieved June 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-119">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/us/threat-insight/post/APT-targets-russia-belarus-zerot-plugx" name="scite-119" rel="nofollow" target="_blank">
        Huss, D., et al. (2017, February 2). Oops, they did it again: APT Targets Russia and Belarus with ZeroT and PlugX. Retrieved April 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-120">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-120" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-121">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-121" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-122">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-122" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-123">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" name="scite-123" rel="nofollow" target="_blank">
        Corio, C., &amp; Sayana, D. P. (2008, June). Application Lockdown with Software Restriction Policies. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-124">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" name="scite-124" rel="nofollow" target="_blank">
        Microsoft. (2012, June 27). Using Software Restriction Policies and AppLocker Policies. Retrieved April 7, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
