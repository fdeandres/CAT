<div class="container-fluid">
 <h1>
  PowerShell
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    PowerShell is a powerful interactive command-line interface and scripting environment included in the Windows operating system.
    <span class="scite-citeref-number" data-reference="TechNet PowerShell" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://technet.microsoft.com/en-us/scriptcenter/dd742419.aspx" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    Adversaries can use PowerShell to perform a number of actions, including discovery of information and execution of code. Examples include the Start-Process cmdlet which can be used to run an executable and the Invoke-Command cmdlet which runs a command locally or on a remote computer.
   </p>
   <p>
    PowerShell may also be used to download and run executables from the Internet, which can be executed from disk or in memory without touching disk.
   </p>
   <p>
    Administrator permissions are required to use PowerShell to connect to remote systems.
   </p>
   <p>
    A number of PowerShell-based offensive testing tools are available, including Empire,
    <span class="scite-citeref-number" data-reference="Github PowerShell Empire" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://github.com/PowerShellEmpire/Empire" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    PowerSploit,
    <span class="scite-citeref-number" data-reference="Powersploit" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://github.com/mattifestation/PowerSploit" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    and PSAttack.
    <span class="scite-citeref-number" data-reference="Github PSAttack" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://github.com/jaredhaight/PSAttack" target="_blank">
       [4]
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
      : T1086
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
      : Execution
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
      User, Administrator
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
      Windows Registry, File monitoring, Process monitoring, Process command-line parameters
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Supports Remote:
      </span>
      Yes
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
     <a href="https://attack.mitre.org/groups/G0073">
      APT19
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0073">
       APT19
      </a>
      used PowerShell commands to execute payloads.
      <span class="scite-citeref-number" data-reference="FireEye APT19" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.fireeye.com/blog/threat-research/2017/06/phished-at-the-request-of-counsel.html" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0007">
      APT28
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0007">
       APT28
      </a>
      downloads and executes PowerShell scripts.
      <span class="scite-citeref-number" data-reference="Palo Alto Sofacy 06-2018" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-sofacy-groups-parallel-attacks/" target="_blank">
         [6]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
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
      has used encoded PowerShell scripts uploaded to
      <a href="https://attack.mitre.org/software/S0046">
       CozyCar
      </a>
      installations to download and install
      <a href="https://attack.mitre.org/software/S0053">
       SeaDuke
      </a>
      .
      <a href="https://attack.mitre.org/groups/G0016">
       APT29
      </a>
      also used PowerShell scripts to evade defenses.
      <span class="scite-citeref-number" data-reference="Symantec Seaduke 2015" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="http://www.symantec.com/connect/blogs/forkmeiamfamous-seaduke-latest-weapon-duke-armory" target="_blank">
         [7]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Mandiant No Easy Breach" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="http://www.slideshare.net/MatthewDunwoody1/no-easy-breach-derby-con-2016" target="_blank">
         [8]
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
      has used PowerShell on victim systems to download and run payloads after exploitation.
      <span class="scite-citeref-number" data-reference="FireEye Operation Double Tap" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.fireeye.com/blog/threat-research/2014/11/operation_doubletap.html" target="_blank">
         [9]
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
      has used PowerShell-based tools and shellcode loaders for execution.
      <span class="scite-citeref-number" data-reference="FireEye APT32 May 2017" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www.fireeye.com/blog/threat-research/2017/05/cyber-espionage-apt32.html" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0129">
      AutoIt backdoor
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0129">
       AutoIt backdoor
      </a>
      downloads a PowerShell script that decodes to a typical shellcode loader.
      <span class="scite-citeref-number" data-reference="Forcepoint Monsoon" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" target="_blank">
         [11]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0060">
      BRONZE BUTLER
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0060">
       BRONZE BUTLER
      </a>
      has used PowerShell for execution.
      <span class="scite-citeref-number" data-reference="Secureworks BRONZE BUTLER Oct 2017" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://www.secureworks.com/research/bronze-butler-targets-japanese-businesses" target="_blank">
         [12]
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
      has used powershell.exe to download and execute scripts.
      <span class="scite-citeref-number" data-reference="Talos Cobalt Group July 2018" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://blog.talosintelligence.com/2018/07/multiple-cobalt-personality-disorder.html" target="_blank">
         [13]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PTSecurity Cobalt Group Aug 2017" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://www.ptsecurity.com/upload/corporate/ww-en/analytics/Cobalt-2017-eng.pdf" target="_blank">
         [14]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PTSecurity Cobalt Dec 2016" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://www.ptsecurity.com/upload/corporate/ww-en/analytics/Cobalt-Snatch-eng.pdf" target="_blank">
         [15]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Group IB Cobalt Aug 2017" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="https://www.group-ib.com/blog/cobalt" target="_blank">
         [16]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="RiskIQ Cobalt Jan 2018" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://www.riskiq.com/blog/labs/cobalt-group-spear-phishing-russian-banks/" target="_blank">
         [17]
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
      can execute a payload on a remote host with PowerShell. This technique does write any data to disk.
      <span class="scite-citeref-number" data-reference="cobaltstrike manual" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="https://cobaltstrike.com/downloads/csmanual38.pdf" target="_blank">
         [18]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0052">
      CopyKittens
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0052">
       CopyKittens
      </a>
      has used PowerShell Empire.
      <span class="scite-citeref-number" data-reference="ClearSky Wilted Tulip July 2017" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="http://www.clearskysec.com/wp-content/uploads/2017/07/Operation_Wilted_Tulip.pdf" target="_blank">
         [19]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0079">
      DarkHydrus
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0079">
       DarkHydrus
      </a>
      leveraged PowerShell to download and execute additional scripts for execution.
      <span class="scite-citeref-number" data-reference="Unit 42 DarkHydrus July 2018" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-new-threat-actor-group-darkhydrus-targets-middle-east-government/" target="_blank">
         [20]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Unit 42 Playbook Dec 2017" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="https://pan-unit42.github.io/playbook_viewer/" target="_blank">
         [21]
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
      has used PowerShell scripts to download and execute programs in memory, without writing to disk.
      <span class="scite-citeref-number" data-reference="Alperovitch 2014" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="https://blog.crowdstrike.com/deep-thought-chinese-targeting-national-security-think-tanks/" target="_blank">
         [22]
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
      uses PowerShell for execution.
      <span class="scite-citeref-number" data-reference="ClearSky Charming Kitten Dec 2017" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="http://www.clearskysec.com/wp-content/uploads/2017/12/Charming_Kitten_2017.pdf" target="_blank">
         [23]
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
      used PowerShell scripts for execution.
      <span class="scite-citeref-number" data-reference="US-CERT TA18-074A" id="scite-ref-24-a" onclick="scrollToRef('scite-24')">
       <sup>
        <a aria-describedby="qtip-23" data-hasqtip="23" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" target="_blank">
         [24]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Symantec Dragonfly Sept 2017" id="scite-ref-25-a" onclick="scrollToRef('scite-25')">
       <sup>
        <a aria-describedby="qtip-24" data-hasqtip="24" href="https://www.symantec.com/connect/blogs/dragonfly-western-energy-sector-targeted-sophisticated-attack-group" target="_blank">
         [25]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT APT Energy Oct 2017" id="scite-ref-26-a" onclick="scrollToRef('scite-26')">
       <sup>
        <a aria-describedby="qtip-25" data-hasqtip="25" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" target="_blank">
         [26]
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
      uses PowerShell for execution as well as PowerShell Empire to establish persistence.
      <span class="scite-citeref-number" data-reference="FireEye FIN10 June 2017" id="scite-ref-27-a" onclick="scrollToRef('scite-27')">
       <sup>
        <a aria-describedby="qtip-26" data-hasqtip="26" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin10.pdf" target="_blank">
         [27]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Github PowerShell Empire" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://github.com/PowerShellEmpire/Empire" target="_blank">
         [2]
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
      has used a Metasploit PowerShell module to download and execute shellcode and to set up a local listener.
      <span class="scite-citeref-number" data-reference="FireEye FIN6 April 2016" id="scite-ref-28-a" onclick="scrollToRef('scite-28')">
       <sup>
        <a aria-describedby="qtip-27" data-hasqtip="27" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin6.pdf" target="_blank">
         [28]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0046">
      FIN7
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0046">
       FIN7
      </a>
      uses a PowerShell script to launch shellcode that retrieves an additional payload.
      <span class="scite-citeref-number" data-reference="FireEye FIN7 April 2017" id="scite-ref-29-a" onclick="scrollToRef('scite-29')">
       <sup>
        <a aria-describedby="qtip-28" data-hasqtip="28" href="https://www.fireeye.com/blog/threat-research/2017/04/fin7-phishing-lnk.html" target="_blank">
         [29]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Morphisec FIN7 June 2017" id="scite-ref-30-a" onclick="scrollToRef('scite-30')">
       <sup>
        <a aria-describedby="qtip-29" data-hasqtip="29" href="http://blog.morphisec.com/fin7-attacks-restaurant-industry" target="_blank">
         [30]
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
      's malicious spearphishing payloads are executed as
      <a href="https://attack.mitre.org/techniques/T1086">
       PowerShell
      </a>
      .
      <a href="https://attack.mitre.org/groups/G0061">
       FIN8
      </a>
      has also used
      <a href="https://attack.mitre.org/techniques/T1086">
       PowerShell
      </a>
      during and.
      <span class="scite-citeref-number" data-reference="FireEye Obfuscation June 2017" id="scite-ref-31-a" onclick="scrollToRef('scite-31')">
       <sup>
        <a aria-describedby="qtip-30" data-hasqtip="30" href="https://www.fireeye.com/blog/threat-research/2017/06/obfuscation-in-the-wild.html" target="_blank">
         [31]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye Know Your Enemy FIN8 Aug 2016" id="scite-ref-32-a" onclick="scrollToRef('scite-32')">
       <sup>
        <a aria-describedby="qtip-31" data-hasqtip="31" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" target="_blank">
         [32]
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
      malware can use PowerShell commands to download and execute a payload and open a decoy document on the victim’s machine.
      <span class="scite-citeref-number" data-reference="Unit 42 Gorgon Group Aug 2018" id="scite-ref-33-a" onclick="scrollToRef('scite-33')">
       <sup>
        <a aria-describedby="qtip-32" data-hasqtip="32" href="https://researchcenter.paloaltonetworks.com/2018/08/unit42-gorgon-group-slithering-nation-state-cybercrime/" target="_blank">
         [33]
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
      can execute PowerShell scripts.
      <span class="scite-citeref-number" data-reference="FireEye FIN7 April 2017" id="scite-ref-29-a" onclick="scrollToRef('scite-29')">
       <sup>
        <a aria-describedby="qtip-28" data-hasqtip="28" href="https://www.fireeye.com/blog/threat-research/2017/04/fin7-phishing-lnk.html" target="_blank">
         [29]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0037">
      HAMMERTOSS
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0037">
       HAMMERTOSS
      </a>
      is known to use PowerShell.
      <span class="scite-citeref-number" data-reference="FireEye APT29" id="scite-ref-34-a" onclick="scrollToRef('scite-34')">
       <sup>
        <a aria-describedby="qtip-33" data-hasqtip="33" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-apt29-hammertoss.pdf" target="_blank">
         [34]
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
      One version of
      <a href="https://attack.mitre.org/software/S0170">
       Helminth
      </a>
      uses a PowerShell script.
      <span class="scite-citeref-number" data-reference="Palo Alto OilRig May 2016" id="scite-ref-35-a" onclick="scrollToRef('scite-35')">
       <sup>
        <a aria-describedby="qtip-34" data-hasqtip="34" href="http://researchcenter.paloaltonetworks.com/2016/05/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/" target="_blank">
         [35]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0065">
      Leviathan
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0065">
       Leviathan
      </a>
      has used PowerShell for execution.
      <span class="scite-citeref-number" data-reference="Proofpoint Leviathan Oct 2017" id="scite-ref-36-a" onclick="scrollToRef('scite-36')">
       <sup>
        <a aria-describedby="qtip-35" data-hasqtip="35" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" target="_blank">
         [36]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye Periscope March 2018" id="scite-ref-37-a" onclick="scrollToRef('scite-37')">
       <sup>
        <a aria-describedby="qtip-36" data-hasqtip="36" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" target="_blank">
         [37]
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
      has used PowerShell for execution and privilege escalation.
      <span class="scite-citeref-number" data-reference="Unit 42 Magic Hound Feb 2017" id="scite-ref-38-a" onclick="scrollToRef('scite-38')">
       <sup>
        <a aria-describedby="qtip-37" data-hasqtip="37" href="https://researchcenter.paloaltonetworks.com/2017/02/unit42-magic-hound-campaign-attacks-saudi-targets/" target="_blank">
         [38]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye APT35 2018" id="scite-ref-39-a" onclick="scrollToRef('scite-39')">
       <sup>
        <a aria-describedby="qtip-38" data-hasqtip="38" href="https://www.fireeye.com/content/dam/collateral/en/mtrends-2018.pdf" target="_blank">
         [39]
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
      uses
      <a href="https://attack.mitre.org/software/S0194">
       PowerSploit
      </a>
      to inject shellcode into PowerShell.
      <span class="scite-citeref-number" data-reference="PWC Cloud Hopper Technical Annex April 2017" id="scite-ref-40-a" onclick="scrollToRef('scite-40')">
       <sup>
        <a aria-describedby="qtip-39" data-hasqtip="39" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" target="_blank">
         [40]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0256">
      Mosquito
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0256">
       Mosquito
      </a>
      can launch PowerShell Scripts.
      <span class="scite-citeref-number" data-reference="ESET Turla Mosquito Jan 2018" id="scite-ref-41-a" onclick="scrollToRef('scite-41')">
       <sup>
        <a aria-describedby="qtip-40" data-hasqtip="40" href="https://www.welivesecurity.com/wp-content/uploads/2018/01/ESET_Turla_Mosquito.pdf" target="_blank">
         [41]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0069">
      MuddyWater
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0069">
       MuddyWater
      </a>
      has used PowerShell for execution.
      <span class="scite-citeref-number" data-reference="FireEye MuddyWater Mar 2018" id="scite-ref-42-a" onclick="scrollToRef('scite-42')">
       <sup>
        <a aria-describedby="qtip-41" data-hasqtip="41" href="https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html" target="_blank">
         [42]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="MuddyWater TrendMicro June 2018" id="scite-ref-43-a" onclick="scrollToRef('scite-43')">
       <sup>
        <a aria-describedby="qtip-42" data-hasqtip="42" href="https://blog.trendmicro.com/trendlabs-security-intelligence/another-potential-muddywater-campaign-uses-powershell-based-prb-backdoor/" target="_blank">
         [43]
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
      has used PowerShell scripts for execution, including use of a macro to run a PowerShell command to decode file contents.
      <span class="scite-citeref-number" data-reference="FireEye APT34 Dec 2017" id="scite-ref-44-a" onclick="scrollToRef('scite-44')">
       <sup>
        <a aria-describedby="qtip-43" data-hasqtip="43" href="https://www.fireeye.com/blog/threat-research/2017/12/targeted-attack-in-middle-east-by-apt34.html" target="_blank">
         [44]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="OilRig New Delivery Oct 2017" id="scite-ref-45-a" onclick="scrollToRef('scite-45')">
       <sup>
        <a aria-describedby="qtip-44" data-hasqtip="44" href="https://researchcenter.paloaltonetworks.com/2017/10/unit42-oilrig-group-steps-attacks-new-delivery-documents-new-injector-trojan/" target="_blank">
         [45]
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
      used
      <a href="https://attack.mitre.org/software/S0194">
       PowerSploit
      </a>
      to download payloads, run a reverse shell, and execute malware on the victim's machine.
      <span class="scite-citeref-number" data-reference="Cymmetria Patchwork" id="scite-ref-46-a" onclick="scrollToRef('scite-46')">
       <sup>
        <a aria-describedby="qtip-45" data-hasqtip="45" href="https://s3-us-west-2.amazonaws.com/cymmetria-blog/public/Unveiling_Patchwork.pdf" target="_blank">
         [46]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="TrendMicro Patchwork Dec 2017" id="scite-ref-47-a" onclick="scrollToRef('scite-47')">
       <sup>
        <a aria-describedby="qtip-46" data-hasqtip="46" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" target="_blank">
         [47]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0033">
      Poseidon Group
     </a>
    </td>
    <td>
     <p>
      The
      <a href="https://attack.mitre.org/groups/G0033">
       Poseidon Group
      </a>
      's Information Gathering Tool (IGT) includes PowerShell components.
      <span class="scite-citeref-number" data-reference="Kaspersky Poseidon Group" id="scite-ref-48-a" onclick="scrollToRef('scite-48')">
       <sup>
        <a aria-describedby="qtip-47" data-hasqtip="47" href="https://securelist.com/poseidon-group-a-targeted-attack-boutique-specializing-in-global-cyber-espionage/73673/" target="_blank">
         [48]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0150">
      POSHSPY
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0150">
       POSHSPY
      </a>
      uses PowerShell to execute various commands, one to execute its payload.
      <span class="scite-citeref-number" data-reference="FireEye POSHSPY April 2017" id="scite-ref-49-a" onclick="scrollToRef('scite-49')">
       <sup>
        <a aria-describedby="qtip-48" data-hasqtip="48" href="https://www.fireeye.com/blog/threat-research/2017/03/dissecting_one_ofap.html" target="_blank">
         [49]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0145">
      POWERSOURCE
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0145">
       POWERSOURCE
      </a>
      is a PowerShell backdoor.
      <span class="scite-citeref-number" data-reference="FireEye FIN7 March 2017" id="scite-ref-50-a" onclick="scrollToRef('scite-50')">
       <sup>
        <a aria-describedby="qtip-49" data-hasqtip="49" href="https://www.fireeye.com/blog/threat-research/2017/03/fin7_spear_phishing.html" target="_blank">
         [50]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Cisco DNSMessenger March 2017" id="scite-ref-51-a" onclick="scrollToRef('scite-51')">
       <sup>
        <a aria-describedby="qtip-50" data-hasqtip="50" href="http://blog.talosintelligence.com/2017/03/dnsmessenger.html" target="_blank">
         [51]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0194">
      PowerSploit
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0194">
       PowerSploit
      </a>
      modules are written in and executed via
      <a href="https://attack.mitre.org/techniques/T1086">
       PowerShell
      </a>
      .
      <span class="scite-citeref-number" data-reference="GitHub PowerSploit May 2012" id="scite-ref-52-a" onclick="scrollToRef('scite-52')">
       <sup>
        <a aria-describedby="qtip-51" data-hasqtip="51" href="https://github.com/PowerShellMafia/PowerSploit" target="_blank">
         [52]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PowerSploit Documentation" id="scite-ref-53-a" onclick="scrollToRef('scite-53')">
       <sup>
        <a aria-describedby="qtip-52" data-hasqtip="52" href="http://powersploit.readthedocs.io" target="_blank">
         [53]
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
      uses PowerShell.
      <span class="scite-citeref-number" data-reference="Unit 42 MuddyWater Nov 2017" id="scite-ref-54-a" onclick="scrollToRef('scite-54')">
       <sup>
        <a aria-describedby="qtip-53" data-hasqtip="53" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-muddying-the-water-targeted-attacks-in-the-middle-east/" target="_blank">
         [54]
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
      is written in PowerShell.
      <span class="scite-citeref-number" data-reference="FireEye APT34 Dec 2017" id="scite-ref-44-a" onclick="scrollToRef('scite-44')">
       <sup>
        <a aria-describedby="qtip-43" data-hasqtip="43" href="https://www.fireeye.com/blog/threat-research/2017/12/targeted-attack-in-middle-east-by-apt34.html" target="_blank">
         [44]
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
      has a module for loading and executing PowerShell scripts.
      <span class="scite-citeref-number" data-reference="GitHub Pupy" id="scite-ref-55-a" onclick="scrollToRef('scite-55')">
       <sup>
        <a aria-describedby="qtip-54" data-hasqtip="54" href="https://github.com/n1nj4sec/pupy" target="_blank">
         [55]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0269">
      QUADAGENT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0269">
       QUADAGENT
      </a>
      uses PowerShell scripts for execution.
      <span class="scite-citeref-number" data-reference="Unit 42 QUADAGENT July 2018" id="scite-ref-56-a" onclick="scrollToRef('scite-56')">
       <sup>
        <a aria-describedby="qtip-55" data-hasqtip="55" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-oilrig-targets-technology-service-provider-government-agency-quadagent/" target="_blank">
         [56]
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
      There is a variant of
      <a href="https://attack.mitre.org/software/S0241">
       RATANKBA
      </a>
      that uses a PowerShell script instead of the traditional PE form.
      <span class="scite-citeref-number" data-reference="Lazarus RATANKBA" id="scite-ref-57-a" onclick="scrollToRef('scite-57')">
       <sup>
        <a aria-describedby="qtip-56" data-hasqtip="56" href="https://blog.trendmicro.com/trendlabs-security-intelligence/lazarus-campaign-targeting-cryptocurrencies-reveals-remote-controller-tool-evolved-ratankba/" target="_blank">
         [57]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="RATANKBA" id="scite-ref-58-a" onclick="scrollToRef('scite-58')">
       <sup>
        <a aria-describedby="qtip-57" data-hasqtip="57" href="https://blog.trendmicro.com/trendlabs-security-intelligence/ratankba-watering-holes-against-enterprises/" target="_blank">
         [58]
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
      uses PowerShell for execution.
      <span class="scite-citeref-number" data-reference="Unit 42 DarkHydrus July 2018" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-new-threat-actor-group-darkhydrus-targets-middle-east-government/" target="_blank">
         [20]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0053">
      SeaDuke
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0053">
       SeaDuke
      </a>
      uses a module to execute Mimikatz with PowerShell to perform
      <a href="https://attack.mitre.org/techniques/T1097">
       Pass the Ticket
      </a>
      .
      <span class="scite-citeref-number" data-reference="Symantec Seaduke 2015" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="http://www.symantec.com/connect/blogs/forkmeiamfamous-seaduke-latest-weapon-duke-armory" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0273">
      Socksbot
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0273">
       Socksbot
      </a>
      can write and execute PowerShell scripts.
      <span class="scite-citeref-number" data-reference="TrendMicro Patchwork Dec 2017" id="scite-ref-47-a" onclick="scrollToRef('scite-47')">
       <sup>
        <a aria-describedby="qtip-46" data-hasqtip="46" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" target="_blank">
         [47]
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
      malware uses PowerShell commands to perform various functions, including gathering system information via WMI and executing commands from its C2 server.
      <span class="scite-citeref-number" data-reference="Citizen Lab Stealth Falcon May 2016" id="scite-ref-59-a" onclick="scrollToRef('scite-59')">
       <sup>
        <a aria-describedby="qtip-58" data-hasqtip="58" href="https://citizenlab.org/2016/05/stealth-falcon/" target="_blank">
         [59]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0062">
      TA459
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0062">
       TA459
      </a>
      has used PowerShell for execution of a payload.
      <span class="scite-citeref-number" data-reference="Proofpoint TA459 April 2017" id="scite-ref-60-a" onclick="scrollToRef('scite-60')">
       <sup>
        <a aria-describedby="qtip-59" data-hasqtip="59" href="https://www.proofpoint.com/us/threat-insight/post/apt-targets-financial-analysts" target="_blank">
         [60]
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
      has used PowerShell for execution.
      <span class="scite-citeref-number" data-reference="SecureWorks BRONZE UNION June 2017" id="scite-ref-61-a" onclick="scrollToRef('scite-61')">
       <sup>
        <a aria-describedby="qtip-60" data-hasqtip="60" href="https://www.secureworks.com/research/bronze-union" target="_blank">
         [61]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0076">
      Thrip
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0076">
       Thrip
      </a>
      leveraged PowerShell to run commands to download payloads, traverse the compromised networks, and carry out reconnaissance.
      <span class="scite-citeref-number" data-reference="Symantec Thrip June 2018" id="scite-ref-62-a" onclick="scrollToRef('scite-62')">
       <sup>
        <a aria-describedby="qtip-61" data-hasqtip="61" href="https://www.symantec.com/blogs/threat-intelligence/thrip-hits-satellite-telecoms-defense-targets" target="_blank">
         [62]
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
      has used a custom executable to execute PowerShell scripts.
      <span class="scite-citeref-number" data-reference="ESET Turla Mosquito May 2018" id="scite-ref-63-a" onclick="scrollToRef('scite-63')">
       <sup>
        <a aria-describedby="qtip-62" data-hasqtip="62" href="https://www.welivesecurity.com/2018/05/22/turla-mosquito-shift-towards-generic-tools/" target="_blank">
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
  It may be possible to remove PowerShell from systems when not needed, but a review should be performed to assess the impact to an environment, since it could be in use for many legitimate purposes and administrative functions. When PowerShell is necessary, restrict PowerShell execution policy to administrators and to only execute signed scripts. Be aware that there are methods of bypassing the PowerShell execution policy, depending on environment configuration.
  <span class="scite-citeref-number" data-reference="Netspi PowerShell Execution Policy Bypass" id="scite-ref-64-a">
   <sup>
    <a aria-describedby="qtip-63" data-hasqtip="63" href="https://blog.netspi.com/15-ways-to-bypass-the-powershell-execution-policy/" target="_blank">
     [64]
    </a>
   </sup>
  </span>
  Disable/restrict the WinRM Service to help prevent uses of PowerShell for remote execution.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  If proper execution policy is set, adversaries will likely be able to define their own execution policy if they obtain administrator or system access, either through the Registry or at the command line. This change in policy on a system may be a way to detect malicious use of PowerShell. If PowerShell is not used in an environment, then simply looking for PowerShell execution may detect malicious activity.
 </p>
 <p>
  It is also beneficial to turn on PowerShell logging to gain increased fidelity in what occurs during execution.
  <span class="scite-citeref-number" data-reference="Malware Archaeology PowerShell Cheat Sheet" id="scite-ref-65-a">
   <sup>
    <a aria-describedby="qtip-64" data-hasqtip="64" href="http://www.malwarearchaeology.com/s/Windows-PowerShell-Logging-Cheat-Sheet-ver-June-2016-v2.pdf" target="_blank">
     [65]
    </a>
   </sup>
  </span>
  PowerShell 5.0 introduced enhanced logging capabilities, and some of those features have since been added to PowerShell 4.0. Earlier versions of PowerShell do not have many logging features.
  <span class="scite-citeref-number" data-reference="FireEye PowerShell Logging 2016" id="scite-ref-66-a">
   <sup>
    <a aria-describedby="qtip-65" data-hasqtip="65" href="https://www.fireeye.com/blog/threat-research/2016/02/greater_visibilityt.html" target="_blank">
     [66]
    </a>
   </sup>
  </span>
  An organization can gather PowerShell execution details in a data analytic platform to supplement it with other data.
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
       <a class="external text" href="https://technet.microsoft.com/en-us/scriptcenter/dd742419.aspx" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Windows PowerShell Scripting. Retrieved April 28, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellEmpire/Empire" name="scite-2" rel="nofollow" target="_blank">
        Schroeder, W., Warner, J., Nelson, M. (n.d.). Github PowerShellEmpire. Retrieved April 28, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/mattifestation/PowerSploit" name="scite-3" rel="nofollow" target="_blank">
        PowerSploit. (n.d.). Retrieved December 4, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/jaredhaight/PSAttack" name="scite-4" rel="nofollow" target="_blank">
        Haight, J. (2016, April 21). PS&gt;Attack. Retrieved June 1, 2016.
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
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-sofacy-groups-parallel-attacks/" name="scite-6" rel="nofollow" target="_blank">
        Lee, B., Falcone, R. (2018, June 06). Sofacy Group’s Parallel Attacks. Retrieved June 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/connect/blogs/forkmeiamfamous-seaduke-latest-weapon-duke-armory" name="scite-7" rel="nofollow" target="_blank">
        Symantec Security Response. (2015, July 13). “Forkmeiamfamous”: Seaduke, latest weapon in the Duke armory. Retrieved July 22, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.slideshare.net/MatthewDunwoody1/no-easy-breach-derby-con-2016" name="scite-8" rel="nofollow" target="_blank">
        Dunwoody, M. and Carr, N.. (2016, September 27). No Easy Breach DerbyCon 2016. Retrieved October 4, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2014/11/operation_doubletap.html" name="scite-9" rel="nofollow" target="_blank">
        Moran, N., et al. (2014, November 21). Operation Double Tap. Retrieved January 14, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/05/cyber-espionage-apt32.html" name="scite-10" rel="nofollow" target="_blank">
        Carr, N.. (2017, May 14). Cyber Espionage is Alive and Well: APT32 and the Threat to Global Corporations. Retrieved June 18, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" name="scite-11" rel="nofollow" target="_blank">
        Settle, A., et al. (2016, August 8). MONSOON - Analysis Of An APT Campaign. Retrieved September 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/bronze-butler-targets-japanese-businesses" name="scite-12" rel="nofollow" target="_blank">
        Counter Threat Unit Research Team. (2017, October 12). BRONZE BUTLER Targets Japanese Enterprises. Retrieved January 4, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/07/multiple-cobalt-personality-disorder.html" name="scite-13" rel="nofollow" target="_blank">
        Svajcer, V. (2018, July 31). Multiple Cobalt Personality Disorder. Retrieved September 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.ptsecurity.com/upload/corporate/ww-en/analytics/Cobalt-2017-eng.pdf" name="scite-14" rel="nofollow" target="_blank">
        Positive Technologies. (2017, August 16). Cobalt Strikes Back: An Evolving Multinational Threat to Finance. Retrieved September 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.ptsecurity.com/upload/corporate/ww-en/analytics/Cobalt-Snatch-eng.pdf" name="scite-15" rel="nofollow" target="_blank">
        Positive Technologies. (2016, December 16). Cobalt Snatch. Retrieved October 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.group-ib.com/blog/cobalt" name="scite-16" rel="nofollow" target="_blank">
        Matveeva, V. (2017, August 15). Secrets of Cobalt. Retrieved October 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.riskiq.com/blog/labs/cobalt-group-spear-phishing-russian-banks/" name="scite-17" rel="nofollow" target="_blank">
        Klijnsma, Y.. (2018, January 16). First Activities of Cobalt Group in 2018: Spear Phishing Russian Banks. Retrieved October 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://cobaltstrike.com/downloads/csmanual38.pdf" name="scite-18" rel="nofollow" target="_blank">
        Strategic Cyber LLC. (2017, March 14). Cobalt Strike Manual. Retrieved May 24, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.clearskysec.com/wp-content/uploads/2017/07/Operation_Wilted_Tulip.pdf" name="scite-19" rel="nofollow" target="_blank">
        ClearSky Cyber Security and Trend Micro. (2017, July). Operation Wilted Tulip: Exposing a cyber espionage apparatus. Retrieved August 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-new-threat-actor-group-darkhydrus-targets-middle-east-government/" name="scite-20" rel="nofollow" target="_blank">
        Falcone, R., et al. (2018, July 27). New Threat Actor Group DarkHydrus Targets Middle East Government. Retrieved August 2, 2018.
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
       <a class="external text" href="https://blog.crowdstrike.com/deep-thought-chinese-targeting-national-security-think-tanks/" name="scite-22" rel="nofollow" target="_blank">
        Alperovitch, D. (2014, July 7). Deep in Thought: Chinese Targeting of National Security Think Tanks. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-23">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.clearskysec.com/wp-content/uploads/2017/12/Charming_Kitten_2017.pdf" name="scite-23" rel="nofollow" target="_blank">
        ClearSky Cyber Security. (2017, December). Charming Kitten. Retrieved December 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-24">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" name="scite-24" rel="nofollow" target="_blank">
        US-CERT. (2018, March 16). Alert (TA18-074A): Russian Government Cyber Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-25">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/connect/blogs/dragonfly-western-energy-sector-targeted-sophisticated-attack-group" name="scite-25" rel="nofollow" target="_blank">
        Symantec Security Response. (2017, September 6). Dragonfly: Western energy sector targeted by sophisticated attack group. Retrieved September 9, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-26">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" name="scite-26" rel="nofollow" target="_blank">
        US-CERT. (2017, October 20). Alert (TA17-293A): Advanced Persistent Threat Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved November 2, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-27">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin10.pdf" name="scite-27" rel="nofollow" target="_blank">
        FireEye iSIGHT Intelligence. (2017, June 16). FIN10: Anatomy of a Cyber Extortion Operation. Retrieved June 25, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-28">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin6.pdf" name="scite-28" rel="nofollow" target="_blank">
        FireEye Threat Intelligence. (2016, April). Follow the Money: Dissecting the Operations of the Cyber Crime Group FIN6. Retrieved June 1, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-29">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/04/fin7-phishing-lnk.html" name="scite-29" rel="nofollow" target="_blank">
        Carr, N., et al. (2017, April 24). FIN7 Evolution and the Phishing LNK. Retrieved April 24, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-30">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.morphisec.com/fin7-attacks-restaurant-industry" name="scite-30" rel="nofollow" target="_blank">
        Gorelik, M.. (2017, June 9). FIN7 Takes Another Bite at the Restaurant Industry. Retrieved July 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-31">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/06/obfuscation-in-the-wild.html" name="scite-31" rel="nofollow" target="_blank">
        Bohannon, D. &amp; Carr N. (2017, June 30). Obfuscation in the Wild: Targeted Attackers Lead the Way in Evasion Techniques. Retrieved February 12, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-32">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" name="scite-32" rel="nofollow" target="_blank">
        Elovitz, S. &amp; Ahl, I. (2016, August 18). Know Your Enemy:  New Financially-Motivated &amp; Spear-Phishing Group. Retrieved February 26, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-33">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/08/unit42-gorgon-group-slithering-nation-state-cybercrime/" name="scite-33" rel="nofollow" target="_blank">
        Falcone, R., et al. (2018, August 02). The Gorgon Group: Slithering Between Nation State and Cybercrime. Retrieved August 7, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="34.0">
    <li>
     <span class="scite-citation" id="scite-34">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-apt29-hammertoss.pdf" name="scite-34" rel="nofollow" target="_blank">
        FireEye Labs. (2015, July). HAMMERTOSS: Stealthy Tactics Define a Russian Cyber Threat Group. Retrieved September 17, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-35">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/05/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/" name="scite-35" rel="nofollow" target="_blank">
        Falcone, R. and Lee, B.. (2016, May 26). The OilRig Campaign: Attacks on Saudi Arabian Organizations Deliver Helminth Backdoor. Retrieved May 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-36">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" name="scite-36" rel="nofollow" target="_blank">
        Axel F, Pierre T. (2017, October 16). Leviathan: Espionage actor spearphishes maritime and defense targets. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-37">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" name="scite-37" rel="nofollow" target="_blank">
        FireEye. (2018, March 16). Suspected Chinese Cyber Espionage Group (TEMP.Periscope) Targeting U.S. Engineering and Maritime Industries. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-38">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/02/unit42-magic-hound-campaign-attacks-saudi-targets/" name="scite-38" rel="nofollow" target="_blank">
        Lee, B. and Falcone, R. (2017, February 15). Magic Hound Campaign Attacks Saudi Targets. Retrieved December 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-39">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/content/dam/collateral/en/mtrends-2018.pdf" name="scite-39" rel="nofollow" target="_blank">
        Mandiant. (2018). Mandiant M-Trends 2018. Retrieved July 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-40">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" name="scite-40" rel="nofollow" target="_blank">
        PwC and BAE Systems. (2017, April). Operation Cloud Hopper: Technical Annex. Retrieved April 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-41">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2018/01/ESET_Turla_Mosquito.pdf" name="scite-41" rel="nofollow" target="_blank">
        ESET, et al. (2018, January). Diplomats in Eastern Europe bitten by a Turla mosquito. Retrieved July 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-42">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html" name="scite-42" rel="nofollow" target="_blank">
        Singh, S. et al.. (2018, March 13). Iranian Threat Group Updates Tactics, Techniques and Procedures in Spear Phishing Campaign. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-43">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/another-potential-muddywater-campaign-uses-powershell-based-prb-backdoor/" name="scite-43" rel="nofollow" target="_blank">
        Villanueva, M., Co, M. (2018, June 14). Another Potential MuddyWater Campaign uses Powershell-based PRB-Backdoor. Retrieved July 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-44">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/12/targeted-attack-in-middle-east-by-apt34.html" name="scite-44" rel="nofollow" target="_blank">
        Sardiwal, M, et al. (2017, December 7). New Targeted Attack in the Middle East by APT34, a Suspected Iranian Threat Group, Using CVE-2017-11882 Exploit. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-45">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/10/unit42-oilrig-group-steps-attacks-new-delivery-documents-new-injector-trojan/" name="scite-45" rel="nofollow" target="_blank">
        Falcone, R. and Lee, B. (2017, October 9). OilRig Group Steps Up Attacks with New Delivery Documents and New Injector Trojan. Retrieved January 8, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-46">
      <span class="scite-citation-text">
       <a class="external text" href="https://s3-us-west-2.amazonaws.com/cymmetria-blog/public/Unveiling_Patchwork.pdf" name="scite-46" rel="nofollow" target="_blank">
        Cymmetria. (2016). Unveiling Patchwork - The Copy-Paste APT. Retrieved August 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-47">
      <span class="scite-citation-text">
       <a class="external text" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" name="scite-47" rel="nofollow" target="_blank">
        Lunghi, D., et al. (2017, December). Untangling the Patchwork Cyberespionage Group. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-48">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/poseidon-group-a-targeted-attack-boutique-specializing-in-global-cyber-espionage/73673/" name="scite-48" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2016, February 9). Poseidon Group: a Targeted Attack Boutique specializing in global cyber-espionage. Retrieved March 16, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-49">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/03/dissecting_one_ofap.html" name="scite-49" rel="nofollow" target="_blank">
        Dunwoody, M.. (2017, April 3). Dissecting One of APT29’s Fileless WMI and PowerShell Backdoors (POSHSPY). Retrieved April 5, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-50">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/03/fin7_spear_phishing.html" name="scite-50" rel="nofollow" target="_blank">
        Miller, S., et al. (2017, March 7). FIN7 Spear Phishing Campaign Targets Personnel Involved in SEC Filings. Retrieved March 8, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-51">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.talosintelligence.com/2017/03/dnsmessenger.html" name="scite-51" rel="nofollow" target="_blank">
        Brumaghin, E. and Grady, C.. (2017, March 2). Covert Channels and Poor Decisions: The Tale of DNSMessenger. Retrieved March 8, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-52">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellMafia/PowerSploit" name="scite-52" rel="nofollow" target="_blank">
        PowerShellMafia. (2012, May 26). PowerSploit - A PowerShell Post-Exploitation Framework. Retrieved February 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-53">
      <span class="scite-citation-text">
       <a class="external text" href="http://powersploit.readthedocs.io" name="scite-53" rel="nofollow" target="_blank">
        PowerSploit. (n.d.). PowerSploit. Retrieved February 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-54">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-muddying-the-water-targeted-attacks-in-the-middle-east/" name="scite-54" rel="nofollow" target="_blank">
        Lancaster, T.. (2017, November 14). Muddying the Water: Targeted Attacks in the Middle East. Retrieved March 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-55">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/n1nj4sec/pupy" name="scite-55" rel="nofollow" target="_blank">
        Nicolas Verdier. (n.d.). Retrieved January 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-56">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-oilrig-targets-technology-service-provider-government-agency-quadagent/" name="scite-56" rel="nofollow" target="_blank">
        Lee, B., Falcone, R. (2018, July 25). OilRig Targets Technology Service Provider and Government Agency with QUADAGENT. Retrieved August 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-57">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/lazarus-campaign-targeting-cryptocurrencies-reveals-remote-controller-tool-evolved-ratankba/" name="scite-57" rel="nofollow" target="_blank">
        Lei, C., et al. (2018, January 24). Lazarus Campaign Targeting Cryptocurrencies Reveals Remote Controller Tool, an Evolved RATANKBA, and More. Retrieved May 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-58">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/ratankba-watering-holes-against-enterprises/" name="scite-58" rel="nofollow" target="_blank">
        Trend Micro. (2017, February 27). RATANKBA: Delving into Large-scale Watering Holes against Enterprises. Retrieved May 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-59">
      <span class="scite-citation-text">
       <a class="external text" href="https://citizenlab.org/2016/05/stealth-falcon/" name="scite-59" rel="nofollow" target="_blank">
        Marczak, B. and Scott-Railton, J.. (2016, May 29). Keep Calm and (Don’t) Enable Macros: A New Threat Actor Targets UAE Dissidents. Retrieved June 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-60">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/us/threat-insight/post/apt-targets-financial-analysts" name="scite-60" rel="nofollow" target="_blank">
        Axel F. (2017, April 27). APT Targets Financial Analysts with CVE-2017-0199. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-61">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/bronze-union" name="scite-61" rel="nofollow" target="_blank">
        Counter Threat Unit Research Team. (2017, June 27). BRONZE UNION Cyberespionage Persists Despite Disclosures. Retrieved July 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-62">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/thrip-hits-satellite-telecoms-defense-targets" name="scite-62" rel="nofollow" target="_blank">
        Security Response Attack Investigation Team. (2018, June 19). Thrip: Espionage Group Hits Satellite, Telecoms, and Defense Companies. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-63">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2018/05/22/turla-mosquito-shift-towards-generic-tools/" name="scite-63" rel="nofollow" target="_blank">
        ESET Research. (2018, May 22). Turla Mosquito: A shift towards more generic tools. Retrieved July 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-64">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.netspi.com/15-ways-to-bypass-the-powershell-execution-policy/" name="scite-64" rel="nofollow" target="_blank">
        Sutherland, S. (2014, September 9). 15 Ways to Bypass the PowerShell Execution Policy. Retrieved July 23, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-65">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.malwarearchaeology.com/s/Windows-PowerShell-Logging-Cheat-Sheet-ver-June-2016-v2.pdf" name="scite-65" rel="nofollow" target="_blank">
        Malware Archaeology. (2016, June). WINDOWS POWERSHELL LOGGING CHEAT SHEET - Win 7/Win 2008 or later. Retrieved June 24, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-66">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2016/02/greater_visibilityt.html" name="scite-66" rel="nofollow" target="_blank">
        Dunwoody, M. (2016, February 11). GREATER VISIBILITY THROUGH POWERSHELL LOGGING. Retrieved February 16, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
