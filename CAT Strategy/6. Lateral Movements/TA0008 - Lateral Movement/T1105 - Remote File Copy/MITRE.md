<div class="container-fluid">
 <h1>
  Remote File Copy
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Files may be copied from one system to another to stage adversary tools or other files over the course of an operation. Files may be copied from an external adversary-controlled system through the Command and Control channel to bring tools into the victim network or through alternate protocols with another tool such as
    <a href="https://attack.mitre.org/software/S0095">
     FTP
    </a>
    . Files can also be copied over on Mac and Linux with native tools like scp, rsync, and sftp.
   </p>
   <p>
    Adversaries may also copy files laterally between internal victim systems to support Lateral Movement with remote Execution using inherent file sharing protocols such as file sharing over SMB to connected network shares or with authenticated connections with
    <a href="https://attack.mitre.org/techniques/T1077">
     Windows Admin Shares
    </a>
    or
    <a href="https://attack.mitre.org/techniques/T1076">
     Remote Desktop Protocol
    </a>
    .
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1105
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
      : Command And Control, Lateral Movement
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
      File monitoring, Packet capture, Process use of network, Netflow/Enclave netflow, Network protocol analysis, Process monitoring
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Requires Network:
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
     <a href="https://attack.mitre.org/software/S0331">
      Agent Tesla
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0331">
       Agent Tesla
      </a>
      can download additional files for execution on the victim’s machine.
      <span class="scite-citeref-number" data-reference="Talos Agent Tesla Oct 2018" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://blog.talosintelligence.com/2018/10/old-dog-new-tricks-analysing-new-rtf_15.html" target="_blank">
         [1]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="DigiTrust Agent Tesla Jan 2017" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.digitrustgroup.com/agent-tesla-keylogger/" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0092">
      Agent.btz
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0092">
       Agent.btz
      </a>
      attempts to download an encrypted binary from a specified domain.
      <span class="scite-citeref-number" data-reference="ThreatExpert Agent.btz" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="http://blog.threatexpert.com/2008/11/agentbtz-threat-that-hit-pentagon.html" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0026">
      APT18
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0026">
       APT18
      </a>
      can upload a file to the victim’s machine.
      <span class="scite-citeref-number" data-reference="PaloAlto DNS Requests May 2016" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://researchcenter.paloaltonetworks.com/2016/05/unit42-new-wekby-attacks-use-dns-requests-as-command-and-control-mechanism/" target="_blank">
         [4]
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
      has downloaded additional files, including by using a first-stage downloader to contact the C2 server to obtain the second-stage implant.
      <span class="scite-citeref-number" data-reference="Bitdefender APT28 Dec 2015" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://download.bitdefender.com/resources/media/materials/white-papers/en/Bitdefender_In-depth_analysis_of_APT28%E2%80%93The_Political_Cyber-Espionage.pdf" target="_blank">
         [5]
        </a>
       </sup>
      </span>
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
     <a href="https://attack.mitre.org/groups/G0022">
      APT3
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0022">
       APT3
      </a>
      has a tool that can copy files to remote machines.
      <span class="scite-citeref-number" data-reference="FireEye Clandestine Fox" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.fireeye.com/blog/threat-research/2014/04/new-zero-day-exploit-targeting-internet-explorer-versions-9-through-11-identified-in-targeted-attacks.html" target="_blank">
         [7]
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
      has added JavaScript to victim websites to download additional frameworks that profile and compromise website visitors.
      <span class="scite-citeref-number" data-reference="Volexity OceanLotus Nov 2017" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.volexity.com/blog/2017/11/06/oceanlotus-blossoms-mass-digital-surveillance-and-exploitation-of-asean-nations-the-media-human-rights-and-civil-society/" target="_blank">
         [8]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Cybereason Oceanlotus May 2017" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.cybereason.com/blog/operation-cobalt-kitty-apt" target="_blank">
         [9]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0064">
      APT33
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0064">
       APT33
      </a>
      has downloaded additional files and programs from its C2 server.
      <br/>
      <span class="scite-citeref-number" data-reference="Symantec Elfin Mar 2019" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www.symantec.com/blogs/threat-intelligence/elfin-apt33-espionage" target="_blank">
         [10]
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
      has downloaded second stage malware from compromised websites.
      <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
         [11]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0082">
      APT38
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0082">
       APT38
      </a>
      used a backdoor, NESTEGG, that has the capability to download and upload files to and from a victim’s machine.
      <span class="scite-citeref-number" data-reference="FireEye APT38 Oct 2018" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://content.fireeye.com/apt/rpt-apt38" target="_blank">
         [12]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0373">
      Astaroth
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0373">
       Astaroth
      </a>
      uses
      <a href="https://attack.mitre.org/software/S0160">
       certutil
      </a>
      and
      <a href="https://attack.mitre.org/software/S0190">
       BITSAdmin
      </a>
      to download additional malware.
      <span class="scite-citeref-number" data-reference="Cofense Astaroth Sept 2018" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://cofense.com/seeing-resurgence-demonic-astaroth-wmic-trojan/" target="_blank">
         [13]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Cybereason Astaroth Feb 2019" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://www.cybereason.com/blog/information-stealing-malware-targeting-brazil-full-research" target="_blank">
         [14]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0347">
      AuditCred
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0347">
       AuditCred
      </a>
      can download files and additional malware.
      <span class="scite-citeref-number" data-reference="TrendMicro Lazarus Nov 2018" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://blog.trendmicro.com/trendlabs-security-intelligence/lazarus-continues-heists-mounts-attacks-on-financial-organizations-in-latin-america/" target="_blank">
         [15]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0344">
      Azorult
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0344">
       Azorult
      </a>
      can download and execute additional files.
      <a href="https://attack.mitre.org/software/S0344">
       Azorult
      </a>
      has also downloaded a ransomware payload called Hermes.
      <span class="scite-citeref-number" data-reference="Unit42 Azorult Nov 2018" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="https://researchcenter.paloaltonetworks.com/2018/11/unit42-new-wine-old-bottle-new-azorult-variant-found-findmyname-campaign-using-fallout-exploit-kit/" target="_blank">
         [16]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Proofpoint Azorult July 2018" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://www.proofpoint.com/us/threat-insight/post/new-version-azorult-stealer-improves-loading-features-spreads-alongside" target="_blank">
         [17]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0128">
      BADNEWS
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0128">
       BADNEWS
      </a>
      is capable of downloading additional files through C2 channels, including a new version of itself.
      <span class="scite-citeref-number" data-reference="Forcepoint Monsoon" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" target="_blank">
         [18]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PaloAlto Patchwork Mar 2018" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="https://researchcenter.paloaltonetworks.com/2018/03/unit42-patchwork-continues-deliver-badnews-indian-subcontinent/" target="_blank">
         [19]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="TrendMicro Patchwork Dec 2017" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" target="_blank">
         [20]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0337">
      BadPatch
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0337">
       BadPatch
      </a>
      can download and execute or update malware.
      <span class="scite-citeref-number" data-reference="Unit 42 BadPatch Oct 2017" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="https://researchcenter.paloaltonetworks.com/2017/10/unit42-badpatch/" target="_blank">
         [21]
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
      uploads files and secondary payloads to the victim's machine.
      <span class="scite-citeref-number" data-reference="US-CERT Bankshot Dec 2017" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-B_WHITE.PDF" target="_blank">
         [22]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0017">
      BISCUIT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0017">
       BISCUIT
      </a>
      has a command to download a file from the C2 server.
      <span class="scite-citeref-number" data-reference="Mandiant APT1 Appendix" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report-appendix.zip" target="_blank">
         [23]
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
      has the capability to download files to execute on the victim’s machine.
      <span class="scite-citeref-number" data-reference="Unit 42 Bisonal July 2018" id="scite-ref-24-a" onclick="scrollToRef('scite-24')">
       <sup>
        <a aria-describedby="qtip-23" data-hasqtip="23" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-bisonal-malware-used-attacks-russia-south-korea/" target="_blank">
         [24]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0190">
      BITSAdmin
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0190">
       BITSAdmin
      </a>
      can be used to create
      <a href="https://attack.mitre.org/techniques/T1197">
       BITS Jobs
      </a>
      to upload and/or download files.
      <span class="scite-citeref-number" data-reference="Microsoft BITSAdmin" id="scite-ref-25-a" onclick="scrollToRef('scite-25')">
       <sup>
        <a aria-describedby="qtip-24" data-hasqtip="24" href="https://msdn.microsoft.com/library/aa362813.aspx" target="_blank">
         [25]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0360">
      BONDUPDATER
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0360">
       BONDUPDATER
      </a>
      can download or upload files from its C2 server.
      <span class="scite-citeref-number" data-reference="Palo Alto OilRig Sep 2018" id="scite-ref-26-a" onclick="scrollToRef('scite-26')">
       <sup>
        <a aria-describedby="qtip-25" data-hasqtip="25" href="https://unit42.paloaltonetworks.com/unit42-oilrig-uses-updated-bondupdater-target-middle-eastern-government/" target="_blank">
         [26]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0204">
      Briba
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0204">
       Briba
      </a>
      downloads files onto infected hosts.
      <span class="scite-citeref-number" data-reference="Symantec Briba May 2012" id="scite-ref-27-a" onclick="scrollToRef('scite-27')">
       <sup>
        <a aria-describedby="qtip-26" data-hasqtip="26" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051515-2843-99" target="_blank">
         [27]
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
      has used various tools to download files, including DGet (a similar tool to wget).
      <span class="scite-citeref-number" data-reference="Secureworks BRONZE BUTLER Oct 2017" id="scite-ref-28-a" onclick="scrollToRef('scite-28')">
       <sup>
        <a aria-describedby="qtip-27" data-hasqtip="27" href="https://www.secureworks.com/research/bronze-butler-targets-japanese-businesses" target="_blank">
         [28]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0274">
      Calisto
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0274">
       Calisto
      </a>
      has the capability to upload and download files to the victim's machine.
      <span class="scite-citeref-number" data-reference="Symantec Calisto July 2018" id="scite-ref-29-a" onclick="scrollToRef('scite-29')">
       <sup>
        <a aria-describedby="qtip-28" data-hasqtip="28" href="https://www.symantec.com/security-center/writeup/2018-073014-2512-99?om_rssid=sr-latestthreats30days" target="_blank">
         [29]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0077">
      CallMe
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0077">
       CallMe
      </a>
      has the capability to download a file to the victim from the C2 server.
      <span class="scite-citeref-number" data-reference="Scarlet Mimic Jan 2016" id="scite-ref-30-a" onclick="scrollToRef('scite-30')">
       <sup>
        <a aria-describedby="qtip-29" data-hasqtip="29" href="http://researchcenter.paloaltonetworks.com/2016/01/scarlet-mimic-years-long-espionage-targets-minority-activists/" target="_blank">
         [30]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0351">
      Cannon
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0351">
       Cannon
      </a>
      can download a payload for execution.
      <span class="scite-citeref-number" data-reference="Unit42 Cannon Nov 2018" id="scite-ref-31-a" onclick="scrollToRef('scite-31')">
       <sup>
        <a aria-describedby="qtip-30" data-hasqtip="30" href="https://researchcenter.paloaltonetworks.com/2018/11/unit42-sofacy-continues-global-attacks-wheels-new-cannon-trojan/" target="_blank">
         [31]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0348">
      Cardinal RAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0348">
       Cardinal RAT
      </a>
      is downloaded and installed via an executed
      <a href="https://attack.mitre.org/techniques/T1224">
       Assess leadership areas of interest
      </a>
      payload.
      <a href="https://attack.mitre.org/software/S0348">
       Cardinal RAT
      </a>
      can also download and execute additional payloads.
      <span class="scite-citeref-number" data-reference="PaloAlto CardinalRat Apr 2017" id="scite-ref-32-a" onclick="scrollToRef('scite-32')">
       <sup>
        <a aria-describedby="qtip-31" data-hasqtip="31" href="https://researchcenter.paloaltonetworks.com/2017/04/unit42-cardinal-rat-active-two-years/" target="_blank">
         [32]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0160">
      certutil
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0160">
       certutil
      </a>
      can be used to download files from a given URL.
      <span class="scite-citeref-number" data-reference="TechNet Certutil" id="scite-ref-33-a" onclick="scrollToRef('scite-33')">
       <sup>
        <a aria-describedby="qtip-32" data-hasqtip="32" href="https://technet.microsoft.com/library/cc732443.aspx" target="_blank">
         [33]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Twitter subTee Certutil Downloader" id="scite-ref-34-a" onclick="scrollToRef('scite-34')">
       <sup>
        <a aria-describedby="qtip-33" data-hasqtip="33" href="https://twitter.com/subTee/status/888102593838362624" target="_blank">
         [34]
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
      is capable of downloading files, including additional modules.
      <span class="scite-citeref-number" data-reference="Palo Alto menuPass Feb 2017" id="scite-ref-35-a" onclick="scrollToRef('scite-35')">
       <sup>
        <a aria-describedby="qtip-34" data-hasqtip="34" href="http://researchcenter.paloaltonetworks.com/2017/02/unit42-menupass-returns-new-malware-new-attacks-japanese-academics-organizations/" target="_blank">
         [35]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="JPCERT ChChes Feb 2017" id="scite-ref-36-a" onclick="scrollToRef('scite-36')">
       <sup>
        <a aria-describedby="qtip-35" data-hasqtip="35" href="http://blog.jpcert.or.jp/2017/02/chches-malware--93d6.html" target="_blank">
         [36]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye APT10 April 2017" id="scite-ref-37-a" onclick="scrollToRef('scite-37')">
       <sup>
        <a aria-describedby="qtip-36" data-hasqtip="36" href="https://www.fireeye.com/blog/threat-research/2017/04/apt10_menupass_grou.html" target="_blank">
         [37]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0020">
      China Chopper
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0020">
       China Chopper
      </a>
      's server component can download remote files.
      <span class="scite-citeref-number" data-reference="FireEye Periscope March 2018" id="scite-ref-38-a" onclick="scrollToRef('scite-38')">
       <sup>
        <a aria-describedby="qtip-37" data-hasqtip="37" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" target="_blank">
         [38]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Lee 2013" id="scite-ref-39-a" onclick="scrollToRef('scite-39')">
       <sup>
        <a aria-describedby="qtip-38" data-hasqtip="38" href="https://www.fireeye.com/blog/threat-research/2013/08/breaking-down-the-china-chopper-web-shell-part-i.html" target="_blank">
         [39]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="NCSC Joint Report Public Tools" id="scite-ref-40-a" onclick="scrollToRef('scite-40')">
       <sup>
        <a aria-describedby="qtip-39" data-hasqtip="39" href="https://s3.eu-west-1.amazonaws.com/ncsc-content/files/Joint%20report%20on%20publicly%20available%20hacking%20tools%20%28NCSC%29.pdf" target="_blank">
         [40]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0023">
      CHOPSTICK
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0023">
       CHOPSTICK
      </a>
      is capable of performing remote file transmission.
      <span class="scite-citeref-number" data-reference="Crowdstrike DNC June 2016" id="scite-ref-41-a" onclick="scrollToRef('scite-41')">
       <sup>
        <a aria-describedby="qtip-40" data-hasqtip="40" href="https://www.crowdstrike.com/blog/bears-midst-intrusion-democratic-national-committee/" target="_blank">
         [41]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0054">
      CloudDuke
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0054">
       CloudDuke
      </a>
      downloads and executes additional malware from either a Web address or a Microsoft OneDrive account.
      <span class="scite-citeref-number" data-reference="F-Secure The Dukes" id="scite-ref-42-a" onclick="scrollToRef('scite-42')">
       <sup>
        <a aria-describedby="qtip-41" data-hasqtip="41" href="https://www.f-secure.com/documents/996508/1030745/dukes_whitepaper.pdf" target="_blank">
         [42]
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
      can be used to copy files to a remotely connected system.
      <span class="scite-citeref-number" data-reference="TechNet Copy" id="scite-ref-43-a" onclick="scrollToRef('scite-43')">
       <sup>
        <a aria-describedby="qtip-42" data-hasqtip="42" href="https://technet.microsoft.com/en-us/library/bb490886.aspx" target="_blank">
         [43]
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
      has used public sites such as github.com and sendspace.com to upload files and then download them to victim computers. The group's JavaScript backdoor is also capable of downloading files.
      <span class="scite-citeref-number" data-reference="PTSecurity Cobalt Group Aug 2017" id="scite-ref-44-a" onclick="scrollToRef('scite-44')">
       <sup>
        <a aria-describedby="qtip-43" data-hasqtip="43" href="https://www.ptsecurity.com/upload/corporate/ww-en/analytics/Cobalt-2017-eng.pdf" target="_blank">
         [44]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PTSecurity Cobalt Dec 2016" id="scite-ref-45-a" onclick="scrollToRef('scite-45')">
       <sup>
        <a aria-describedby="qtip-44" data-hasqtip="44" href="https://www.ptsecurity.com/upload/corporate/ww-en/analytics/Cobalt-Snatch-eng.pdf" target="_blank">
         [45]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Morphisec Cobalt Gang Oct 2018" id="scite-ref-46-a" onclick="scrollToRef('scite-46')">
       <sup>
        <a aria-describedby="qtip-45" data-hasqtip="45" href="https://blog.morphisec.com/cobalt-gang-2.0" target="_blank">
         [46]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0369">
      CoinTicker
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0369">
       CoinTicker
      </a>
      executes a Python script to download its second stage.
      <span class="scite-citeref-number" data-reference="CoinTicker 2019" id="scite-ref-47-a" onclick="scrollToRef('scite-47')">
       <sup>
        <a aria-describedby="qtip-46" data-hasqtip="46" href="https://blog.malwarebytes.com/threat-analysis/2018/10/mac-cryptocurrency-ticker-app-installs-backdoors/" target="_blank">
         [47]
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
      downloads another dropper from its C2 server.
      <span class="scite-citeref-number" data-reference="FireEye APT28" id="scite-ref-48-a" onclick="scrollToRef('scite-48')">
       <sup>
        <a aria-describedby="qtip-47" data-hasqtip="47" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/rpt-apt28.pdf" target="_blank">
         [48]
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
      contains a command to retrieve files from its C2 server.
      <span class="scite-citeref-number" data-reference="Proofpoint Operation Transparent Tribe March 2016" id="scite-ref-49-a" onclick="scrollToRef('scite-49')">
       <sup>
        <a aria-describedby="qtip-48" data-hasqtip="48" href="https://www.proofpoint.com/sites/default/files/proofpoint-operation-transparent-tribe-threat-insight-en.pdf" target="_blank">
         [49]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0334">
      DarkComet
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0334">
       DarkComet
      </a>
      can load any files onto the infected machine to execute.
      <span class="scite-citeref-number" data-reference="TrendMicro DarkComet Sept 2014" id="scite-ref-50-a" onclick="scrollToRef('scite-50')">
       <sup>
        <a aria-describedby="qtip-49" data-hasqtip="49" href="https://www.trendmicro.com/vinfo/us/threat-encyclopedia/malware/DARKCOMET" target="_blank">
         [50]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Malwarebytes DarkComet March 2018" id="scite-ref-51-a" onclick="scrollToRef('scite-51')">
       <sup>
        <a aria-describedby="qtip-50" data-hasqtip="50" href="https://blog.malwarebytes.com/threat-analysis/2012/06/you-dirty-rat-part-1-darkcomet/" target="_blank">
         [51]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0187">
      Daserf
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0187">
       Daserf
      </a>
      can download remote files.
      <span class="scite-citeref-number" data-reference="Trend Micro Daserf Nov 2017" id="scite-ref-52-a" onclick="scrollToRef('scite-52')">
       <sup>
        <a aria-describedby="qtip-51" data-hasqtip="51" href="http://blog.trendmicro.com/trendlabs-security-intelligence/redbaldknight-bronze-butler-daserf-backdoor-now-using-steganography/" target="_blank">
         [52]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Secureworks BRONZE BUTLER Oct 2017" id="scite-ref-28-a" onclick="scrollToRef('scite-28')">
       <sup>
        <a aria-describedby="qtip-27" data-hasqtip="27" href="https://www.secureworks.com/research/bronze-butler-targets-japanese-businesses" target="_blank">
         [28]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0255">
      DDKONG
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0255">
       DDKONG
      </a>
      downloads and uploads files on the victim’s machine.
      <span class="scite-citeref-number" data-reference="Rancor Unit42 June 2018" id="scite-ref-53-a" onclick="scrollToRef('scite-53')">
       <sup>
        <a aria-describedby="qtip-52" data-hasqtip="52" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-rancor-targeted-attacks-south-east-asia-using-plaintee-ddkong-malware-families/" target="_blank">
         [53]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0354">
      Denis
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0354">
       Denis
      </a>
      deploys additional backdoors and hacking tools to the system.
      <span class="scite-citeref-number" data-reference="Cybereason Cobalt Kitty 2017" id="scite-ref-54-a" onclick="scrollToRef('scite-54')">
       <sup>
        <a aria-describedby="qtip-53" data-hasqtip="53" href="https://cdn2.hubspot.net/hubfs/3354902/Cybereason%20Labs%20Analysis%20Operation%20Cobalt%20Kitty.pdf" target="_blank">
         [54]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0200">
      Dipsind
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0200">
       Dipsind
      </a>
      can download remote files.
      <span class="scite-citeref-number" data-reference="Microsoft PLATINUM April 2016" id="scite-ref-55-a" onclick="scrollToRef('scite-55')">
       <sup>
        <a aria-describedby="qtip-54" data-hasqtip="54" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" target="_blank">
         [55]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0213">
      DOGCALL
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0213">
       DOGCALL
      </a>
      can download and execute additional payloads.
      <span class="scite-citeref-number" data-reference="Unit 42 Nokki Oct 2018" id="scite-ref-56-a" onclick="scrollToRef('scite-56')">
       <sup>
        <a aria-describedby="qtip-55" data-hasqtip="55" href="https://researchcenter.paloaltonetworks.com/2018/10/unit42-nokki-almost-ties-the-knot-with-dogcall-reaper-group-uses-new-malware-to-deploy-rat/" target="_blank">
         [56]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0134">
      Downdelph
     </a>
    </td>
    <td>
     <p>
      After downloading its main config file,
      <a href="https://attack.mitre.org/software/S0134">
       Downdelph
      </a>
      downloads multiple payloads from C2 servers.
      <span class="scite-citeref-number" data-reference="ESET Sednit Part 3" id="scite-ref-57-a" onclick="scrollToRef('scite-57')">
       <sup>
        <a aria-describedby="qtip-56" data-hasqtip="56" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part3.pdf" target="_blank">
         [57]
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
      copied and installed tools for operations once in the victim environment.
      <span class="scite-citeref-number" data-reference="US-CERT TA18-074A" id="scite-ref-58-a" onclick="scrollToRef('scite-58')">
       <sup>
        <a aria-describedby="qtip-57" data-hasqtip="57" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" target="_blank">
         [58]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT APT Energy Oct 2017" id="scite-ref-59-a" onclick="scrollToRef('scite-59')">
       <sup>
        <a aria-describedby="qtip-58" data-hasqtip="58" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" target="_blank">
         [59]
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
      searches for network drives and removable media and duplicates itself onto them.
      <span class="scite-citeref-number" data-reference="DustySky" id="scite-ref-60-a" onclick="scrollToRef('scite-60')">
       <sup>
        <a aria-describedby="qtip-59" data-hasqtip="59" href="https://www.clearskysec.com/wp-content/uploads/2016/01/Operation%20DustySky_TLP_WHITE.pdf" target="_blank">
         [60]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0024">
      Dyre
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0024">
       Dyre
      </a>
      has a command to download and executes additional files.
      <span class="scite-citeref-number" data-reference="Symantec Dyre June 2015" id="scite-ref-61-a" onclick="scrollToRef('scite-61')">
       <sup>
        <a aria-describedby="qtip-60" data-hasqtip="60" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/dyre-emerging-threat.pdf" target="_blank">
         [61]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0066">
      Elderwood
     </a>
    </td>
    <td>
     <p>
      The Ritsol backdoor trojan used by
      <a href="https://attack.mitre.org/groups/G0066">
       Elderwood
      </a>
      can download files onto a compromised host from a remote location.
      <span class="scite-citeref-number" data-reference="Symantec Ristol May 2012" id="scite-ref-62-a" onclick="scrollToRef('scite-62')">
       <sup>
        <a aria-describedby="qtip-61" data-hasqtip="61" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051515-3909-99" target="_blank">
         [62]
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
      can download additional files from the C2 server for execution.
      <span class="scite-citeref-number" data-reference="Accenture Dragonfish Jan 2018" id="scite-ref-63-a" onclick="scrollToRef('scite-63')">
       <sup>
        <a aria-describedby="qtip-62" data-hasqtip="62" href="https://www.accenture.com/t20180127T003755Z_w_/us-en/_acnmedia/PDF-46/Accenture-Security-Dragonfish-Threat-Analysis.pdf" target="_blank">
         [63]
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
      has the capability to download files from the C2 server.
      <span class="scite-citeref-number" data-reference="Lotus Blossom Dec 2015" id="scite-ref-64-a" onclick="scrollToRef('scite-64')">
       <sup>
        <a aria-describedby="qtip-63" data-hasqtip="63" href="http://researchcenter.paloaltonetworks.com/2015/12/attack-on-french-diplomat-linked-to-operation-lotus-blossom/" target="_blank">
         [64]
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
      can upload and download to and from a victim machine.
      <span class="scite-citeref-number" data-reference="Github PowerShell Empire" id="scite-ref-65-a" onclick="scrollToRef('scite-65')">
       <sup>
        <a aria-describedby="qtip-64" data-hasqtip="64" href="https://github.com/PowerShellEmpire/Empire" target="_blank">
         [65]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0343">
      Exaramel
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0343">
       Exaramel
      </a>
      has a command to download a file from a remote server to execute.
      <span class="scite-citeref-number" data-reference="ESET TeleBots Oct 2018" id="scite-ref-66-a" onclick="scrollToRef('scite-66')">
       <sup>
        <a aria-describedby="qtip-65" data-hasqtip="65" href="https://www.welivesecurity.com/2018/10/11/new-telebots-backdoor-linking-industroyer-notpetya/" target="_blank">
         [66]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0361">
      Expand
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0361">
       Expand
      </a>
      can be used to download or upload a file over a network share.
      <span class="scite-citeref-number" data-reference="LOLBAS Expand" id="scite-ref-67-a" onclick="scrollToRef('scite-67')">
       <sup>
        <a aria-describedby="qtip-66" data-hasqtip="66" href="https://lolbas-project.github.io/lolbas/Binaries/Expand/" target="_blank">
         [67]
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
      can download files from remote servers.
      <span class="scite-citeref-number" data-reference="Forcepoint Felismus Mar 2017" id="scite-ref-68-a" onclick="scrollToRef('scite-68')">
       <sup>
        <a aria-describedby="qtip-67" data-hasqtip="67" href="https://blogs.forcepoint.com/security-labs/playing-cat-mouse-introducing-felismus-malware" target="_blank">
         [68]
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
      downloads and uploads files to and from the victim’s machine.
      <span class="scite-citeref-number" data-reference="FireEye FELIXROOT July 2018" id="scite-ref-69-a" onclick="scrollToRef('scite-69')">
       <sup>
        <a aria-describedby="qtip-68" data-hasqtip="68" href="https://www.fireeye.com/blog/threat-research/2018/07/microsoft-office-vulnerabilities-used-to-distribute-felixroot-backdoor.html" target="_blank">
         [69]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="ESET GreyEnergy Oct 2018" id="scite-ref-70-a" onclick="scrollToRef('scite-70')">
       <sup>
        <a aria-describedby="qtip-69" data-hasqtip="69" href="https://www.welivesecurity.com/wp-content/uploads/2018/10/ESET_GreyEnergy.pdf" target="_blank">
         [70]
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
      has deployed Meterpreter stagers and SplinterRAT instances in the victim network after moving laterally.
      <span class="scite-citeref-number" data-reference="FireEye FIN10 June 2017" id="scite-ref-71-a" onclick="scrollToRef('scite-71')">
       <sup>
        <a aria-describedby="qtip-70" data-hasqtip="70" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin10.pdf" target="_blank">
         [71]
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
      has downloaded additional malware to execute on the victim's machine, including by using a PowerShell script to launch shellcode that retrieves an additional payload.
      <span class="scite-citeref-number" data-reference="FireEye FIN7 April 2017" id="scite-ref-72-a" onclick="scrollToRef('scite-72')">
       <sup>
        <a aria-describedby="qtip-71" data-hasqtip="71" href="https://www.fireeye.com/blog/threat-research/2017/04/fin7-phishing-lnk.html" target="_blank">
         [72]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="DOJ FIN7 Aug 2018" id="scite-ref-73-a" onclick="scrollToRef('scite-73')">
       <sup>
        <a aria-describedby="qtip-72" data-hasqtip="72" href="https://www.justice.gov/opa/press-release/file/1084361/download" target="_blank">
         [73]
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
      has used remote code execution to download subsequent payloads.
      <span class="scite-citeref-number" data-reference="FireEye Fin8 May 2016" id="scite-ref-74-a" onclick="scrollToRef('scite-74')">
       <sup>
        <a aria-describedby="qtip-73" data-hasqtip="73" href="https://www.fireeye.com/blog/threat-research/2016/05/windows-zero-day-payment-cards.html" target="_blank">
         [74]
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
      Tools used by
      <a href="https://attack.mitre.org/groups/G0047">
       Gamaredon Group
      </a>
      are capable of downloading and executing additional payloads.
      <span class="scite-citeref-number" data-reference="Palo Alto Gamaredon Feb 2017" id="scite-ref-75-a" onclick="scrollToRef('scite-75')">
       <sup>
        <a aria-describedby="qtip-74" data-hasqtip="74" href="https://researchcenter.paloaltonetworks.com/2017/02/unit-42-title-gamaredon-group-toolset-evolution/" target="_blank">
         [75]
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
      can execute a task to download a file.
      <span class="scite-citeref-number" data-reference="ESET Gazer Aug 2017" id="scite-ref-76-a" onclick="scrollToRef('scite-76')">
       <sup>
        <a aria-describedby="qtip-75" data-hasqtip="75" href="https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf" target="_blank">
         [76]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Securelist WhiteBear Aug 2017" id="scite-ref-77-a" onclick="scrollToRef('scite-77')">
       <sup>
        <a aria-describedby="qtip-76" data-hasqtip="76" href="https://securelist.com/introducing-whitebear/81638/" target="_blank">
         [77]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0032">
      gh0st RAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0032">
       gh0st RAT
      </a>
      can download files to the victim’s machine.
      <span class="scite-citeref-number" data-reference="Nccgroup Gh0st April 2018" id="scite-ref-78-a" onclick="scrollToRef('scite-78')">
       <sup>
        <a aria-describedby="qtip-77" data-hasqtip="77" href="https://www.nccgroup.trust/us/about-us/newsroom-and-events/blog/2018/april/decoding-network-data-from-a-gh0st-rat-variant/" target="_blank">
         [78]
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
      can download additional components from the C2 server.
      <span class="scite-citeref-number" data-reference="McAfee Gold Dragon" id="scite-ref-79-a" onclick="scrollToRef('scite-79')">
       <sup>
        <a aria-describedby="qtip-78" data-hasqtip="78" href="https://securingtomorrow.mcafee.com/mcafee-labs/gold-dragon-widens-olympics-malware-attacks-gains-permanent-presence-on-victims-systems/" target="_blank">
         [79]
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
      malware can download additional files from C2 servers.
      <span class="scite-citeref-number" data-reference="Unit 42 Gorgon Group Aug 2018" id="scite-ref-80-a" onclick="scrollToRef('scite-80')">
       <sup>
        <a aria-describedby="qtip-79" data-hasqtip="79" href="https://researchcenter.paloaltonetworks.com/2018/08/unit42-gorgon-group-slithering-nation-state-cybercrime/" target="_blank">
         [80]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0342">
      GreyEnergy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0342">
       GreyEnergy
      </a>
      can download additional modules and payloads.
      <span class="scite-citeref-number" data-reference="ESET GreyEnergy Oct 2018" id="scite-ref-70-a" onclick="scrollToRef('scite-70')">
       <sup>
        <a aria-describedby="qtip-69" data-hasqtip="69" href="https://www.welivesecurity.com/wp-content/uploads/2018/10/ESET_GreyEnergy.pdf" target="_blank">
         [70]
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
      contains a command to download and execute a file from a remotely hosted URL using WinINet HTTP requests.
      <span class="scite-citeref-number" data-reference="Cisco H1N1 Part 2" id="scite-ref-81-a" onclick="scrollToRef('scite-81')">
       <sup>
        <a aria-describedby="qtip-80" data-hasqtip="80" href="http://blogs.cisco.com/security/h1n1-technical-analysis-reveals-new-capabilities-part-2" target="_blank">
         [81]
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
      can download and execute a second-stage payload.
      <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
         [11]
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
      can download additional files.
      <span class="scite-citeref-number" data-reference="Palo Alto OilRig May 2016" id="scite-ref-82-a" onclick="scrollToRef('scite-82')">
       <sup>
        <a aria-describedby="qtip-81" data-hasqtip="81" href="http://researchcenter.paloaltonetworks.com/2016/05/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/" target="_blank">
         [82]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0087">
      Hi-Zor
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0087">
       Hi-Zor
      </a>
      has the ability to upload and download files from its C2 server.
      <span class="scite-citeref-number" data-reference="Fidelis INOCNATION" id="scite-ref-83-a" onclick="scrollToRef('scite-83')">
       <sup>
        <a aria-describedby="qtip-82" data-hasqtip="82" href="https://www.fidelissecurity.com/sites/default/files/FTA_1020_Fidelis_Inocnation_FINAL_0.pdf" target="_blank">
         [83]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0376">
      HOPLIGHT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0376">
       HOPLIGHT
      </a>
      has the ability to connect to a remote host in order to upload and download files.
      <span class="scite-citeref-number" data-reference="US-CERT HOPLIGHT Apr 2019" id="scite-ref-84-a" onclick="scrollToRef('scite-84')">
       <sup>
        <a aria-describedby="qtip-83" data-hasqtip="83" href="https://www.us-cert.gov/ncas/analysis-reports/AR19-100A" target="_blank">
         [84]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0070">
      HTTPBrowser
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0070">
       HTTPBrowser
      </a>
      is capable of writing a file to the compromised system from the C2 server.
      <span class="scite-citeref-number" data-reference="Dell TG-3390" id="scite-ref-85-a" onclick="scrollToRef('scite-85')">
       <sup>
        <a aria-describedby="qtip-84" data-hasqtip="84" href="https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage" target="_blank">
         [85]
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
      creates a backdoor through which remote attackers can download files and additional malware components.
      <span class="scite-citeref-number" data-reference="Symantec Trojan.Hydraq Jan 2010" id="scite-ref-86-a" onclick="scrollToRef('scite-86')">
       <sup>
        <a aria-describedby="qtip-85" data-hasqtip="85" href="https://www.symantec.com/connect/blogs/trojanhydraq-incident" target="_blank">
         [86]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Symantec Hydraq Jan 2010" id="scite-ref-87-a" onclick="scrollToRef('scite-87')">
       <sup>
        <a aria-describedby="qtip-86" data-hasqtip="86" href="https://www.symantec.com/security_response/writeup.jsp?docid=2010-011114-1830-99" target="_blank">
         [87]
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
      can upload files to the victim's machine for operations.
      <span class="scite-citeref-number" data-reference="ESET InvisiMole June 2018" id="scite-ref-88-a" onclick="scrollToRef('scite-88')">
       <sup>
        <a aria-describedby="qtip-87" data-hasqtip="87" href="https://www.welivesecurity.com/2018/06/07/invisimole-equipped-spyware-undercover/" target="_blank">
         [88]
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
      can retrieve an additional payload from its C2 server.
      <a href="https://attack.mitre.org/software/S0044">
       JHUHUGIT
      </a>
      has a command to download files to the victim’s machine.
      <span class="scite-citeref-number" data-reference="ESET Sednit Part 1" id="scite-ref-89-a" onclick="scrollToRef('scite-89')">
       <sup>
        <a aria-describedby="qtip-88" data-hasqtip="88" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part1.pdf" target="_blank">
         [89]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Unit 42 Sofacy Feb 2018" id="scite-ref-90-a" onclick="scrollToRef('scite-90')">
       <sup>
        <a aria-describedby="qtip-89" data-hasqtip="89" href="https://researchcenter.paloaltonetworks.com/2018/02/unit42-sofacy-attacks-multiple-government-entities/" target="_blank">
         [90]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Talos Seduploader Oct 2017" id="scite-ref-91-a" onclick="scrollToRef('scite-91')">
       <sup>
        <a aria-describedby="qtip-90" data-hasqtip="90" href="https://blog.talosintelligence.com/2017/10/cyber-conflict-decoy-document.html" target="_blank">
         [91]
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
      can download files and upgrade itself.
      <span class="scite-citeref-number" data-reference="Microsoft PLATINUM April 2016" id="scite-ref-55-a" onclick="scrollToRef('scite-55')">
       <sup>
        <a aria-describedby="qtip-54" data-hasqtip="54" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" target="_blank">
         [55]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0283">
      jRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0283">
       jRAT
      </a>
      can download and execute files.
      <span class="scite-citeref-number" data-reference="jRAT Symantec Aug 2018" id="scite-ref-92-a" onclick="scrollToRef('scite-92')">
       <sup>
        <a aria-describedby="qtip-91" data-hasqtip="91" href="https://www.symantec.com/blogs/threat-intelligence/jrat-new-anti-parsing-techniques" target="_blank">
         [92]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Kaspersky Adwind Feb 2016" id="scite-ref-93-a" onclick="scrollToRef('scite-93')">
       <sup>
        <a aria-describedby="qtip-92" data-hasqtip="92" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07195002/KL_AdwindPublicReport_2016.pdf" target="_blank">
         [93]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Symantec Frutas Feb 2013" id="scite-ref-94-a" onclick="scrollToRef('scite-94')">
       <sup>
        <a aria-describedby="qtip-93" data-hasqtip="93" href="https://www.symantec.com/connect/blogs/cross-platform-frutas-rat-builder-and-back-door" target="_blank">
         [94]
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
      can upload and download files, including second-stage malware.
      <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
         [11]
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
      has the ability to download and execute additional files.
      <span class="scite-citeref-number" data-reference="Zscaler Kasidet" id="scite-ref-95-a" onclick="scrollToRef('scite-95')">
       <sup>
        <a aria-describedby="qtip-94" data-hasqtip="94" href="http://research.zscaler.com/2016/01/malicious-office-files-dropping-kasidet.html" target="_blank">
         [95]
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
      downloads additional plug-ins to load on the victim’s machine, including the ability to upgrade and replace its own binary.
      <span class="scite-citeref-number" data-reference="Unit 42 Kazuar May 2017" id="scite-ref-96-a" onclick="scrollToRef('scite-96')">
       <sup>
        <a aria-describedby="qtip-95" data-hasqtip="95" href="https://researchcenter.paloaltonetworks.com/2017/05/unit42-kazuar-multiplatform-espionage-backdoor-api-access/" target="_blank">
         [96]
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
      can upload files to the victim’s machine and can download additional payloads.
      <span class="scite-citeref-number" data-reference="US-CERT KEYMARBLE Aug 2018" id="scite-ref-97-a" onclick="scrollToRef('scite-97')">
       <sup>
        <a aria-describedby="qtip-96" data-hasqtip="96" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-221A" target="_blank">
         [97]
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
      can download additional files.
      <span class="scite-citeref-number" data-reference="Github Koadic" id="scite-ref-98-a" onclick="scrollToRef('scite-98')">
       <sup>
        <a aria-describedby="qtip-97" data-hasqtip="97" href="https://github.com/zerosum0x0/koadic" target="_blank">
         [98]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0356">
      KONNI
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0356">
       KONNI
      </a>
      can download files and execute them on the victim’s machine.
      <span class="scite-citeref-number" data-reference="Talos Konni May 2017" id="scite-ref-99-a" onclick="scrollToRef('scite-99')">
       <sup>
        <a aria-describedby="qtip-98" data-hasqtip="98" href="https://blog.talosintelligence.com/2017/05/konni-malware-under-radar-for-years.html" target="_blank">
         [99]
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
      downloads additional files from C2 servers.
      <span class="scite-citeref-number" data-reference="Symantec Security Center Trojan.Kwampirs" id="scite-ref-100-a" onclick="scrollToRef('scite-100')">
       <sup>
        <a aria-describedby="qtip-99" data-hasqtip="99" href="https://www.symantec.com/security-center/writeup/2016-081923-2700-99" target="_blank">
         [100]
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
      malware families are capable of downloading and executing binaries from its C2 server.
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster" id="scite-ref-101-a" onclick="scrollToRef('scite-101')">
       <sup>
        <a aria-describedby="qtip-100" data-hasqtip="100" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" target="_blank">
         [101]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster Destructive Malware" id="scite-ref-102-a" onclick="scrollToRef('scite-102')">
       <sup>
        <a aria-describedby="qtip-101" data-hasqtip="101" href="https://operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Destructive-Malware-Report.pdf" target="_blank">
         [102]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster Loaders" id="scite-ref-103-a" onclick="scrollToRef('scite-103')">
       <sup>
        <a aria-describedby="qtip-102" data-hasqtip="102" href="https://operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Loaders-Installers-and-Uninstallers-Report.pdf" target="_blank">
         [103]
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
      has downloaded additional scripts and files from adversary-controlled servers.
      <a href="https://attack.mitre.org/groups/G0065">
       Leviathan
      </a>
      has also used an uploader known as LUNCHMONEY that can exfiltrate files to Dropbox.
      <span class="scite-citeref-number" data-reference="Proofpoint Leviathan Oct 2017" id="scite-ref-104-a" onclick="scrollToRef('scite-104')">
       <sup>
        <a aria-describedby="qtip-103" data-hasqtip="103" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" target="_blank">
         [104]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye Periscope March 2018" id="scite-ref-38-a" onclick="scrollToRef('scite-38')">
       <sup>
        <a aria-describedby="qtip-37" data-hasqtip="37" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" target="_blank">
         [38]
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
      creates a backdoor through which remote attackers can download files onto compromised hosts.
      <span class="scite-citeref-number" data-reference="Symantec Linfo May 2012" id="scite-ref-105-a" onclick="scrollToRef('scite-105')">
       <sup>
        <a aria-describedby="qtip-104" data-hasqtip="104" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051605-2535-99" target="_blank">
         [105]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0372">
      LockerGoga
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0372">
       LockerGoga
      </a>
      has been observed moving around the victim network via SMB, indicating the actors behind this ransomware are manually copying files form computer to computer instead of self-propagating.
      <span class="scite-citeref-number" data-reference="Unit42 LockerGoga 2019" id="scite-ref-106-a" onclick="scrollToRef('scite-106')">
       <sup>
        <a aria-describedby="qtip-105" data-hasqtip="105" href="https://unit42.paloaltonetworks.com/born-this-way-origins-of-lockergoga/" target="_blank">
         [106]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0042">
      LOWBALL
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0042">
       LOWBALL
      </a>
      uses the Dropbox API to request two files, one of which is the same file as the one dropped by the malicious email attachment. This is most likely meant to be a mechanism to update the compromised host with a new version of the
      <a href="https://attack.mitre.org/software/S0042">
       LOWBALL
      </a>
      malware.
      <span class="scite-citeref-number" data-reference="FireEye admin@338" id="scite-ref-107-a" onclick="scrollToRef('scite-107')">
       <sup>
        <a aria-describedby="qtip-106" data-hasqtip="106" href="https://www.fireeye.com/blog/threat-research/2015/11/china-based-threat.html" target="_blank">
         [107]
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
      has downloaded additional code and files from servers onto victims.
      <span class="scite-citeref-number" data-reference="Unit 42 Magic Hound Feb 2017" id="scite-ref-108-a" onclick="scrollToRef('scite-108')">
       <sup>
        <a aria-describedby="qtip-107" data-hasqtip="107" href="https://researchcenter.paloaltonetworks.com/2017/02/unit42-magic-hound-campaign-attacks-saudi-targets/" target="_blank">
         [108]
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
      has installed updates and new malware on victims.
      <span class="scite-citeref-number" data-reference="PWC Cloud Hopper April 2017" id="scite-ref-109-a" onclick="scrollToRef('scite-109')">
       <sup>
        <a aria-describedby="qtip-108" data-hasqtip="108" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-report-final-v4.pdf" target="_blank">
         [109]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="DOJ APT10 Dec 2018" id="scite-ref-110-a" onclick="scrollToRef('scite-110')">
       <sup>
        <a aria-describedby="qtip-109" data-hasqtip="109" href="https://www.justice.gov/opa/press-release/file/1121706/download" target="_blank">
         [110]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0339">
      Micropsia
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0339">
       Micropsia
      </a>
      can download and execute an executable from the C2 server.
      <span class="scite-citeref-number" data-reference="Talos Micropsia June 2017" id="scite-ref-111-a" onclick="scrollToRef('scite-111')">
       <sup>
        <a aria-describedby="qtip-110" data-hasqtip="110" href="https://blog.talosintelligence.com/2017/06/palestine-delphi.html" target="_blank">
         [111]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Radware Micropsia July 2018" id="scite-ref-112-a" onclick="scrollToRef('scite-112')">
       <sup>
        <a aria-describedby="qtip-111" data-hasqtip="111" href="https://blog.radware.com/security/2018/07/micropsia-malware/" target="_blank">
         [112]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0051">
      MiniDuke
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0051">
       MiniDuke
      </a>
      can download additional encrypted backdoors onto the victim via GIF files.
      <span class="scite-citeref-number" data-reference="Securelist MiniDuke Feb 2013" id="scite-ref-113-a" onclick="scrollToRef('scite-113')">
       <sup>
        <a aria-describedby="qtip-112" data-hasqtip="112" href="https://cdn.securelist.com/files/2014/07/themysteryofthepdf0-dayassemblermicrobackdoor.pdf" target="_blank">
         [113]
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
      <a href="https://attack.mitre.org/software/S0083">
       Misdat
      </a>
      is capable of downloading files from the C2.
      <span class="scite-citeref-number" data-reference="Cylance Dust Storm" id="scite-ref-114-a" onclick="scrollToRef('scite-114')">
       <sup>
        <a aria-describedby="qtip-113" data-hasqtip="113" href="https://www.cylance.com/content/dam/cylance/pdfs/reports/Op_Dust_Storm_Report.pdf" target="_blank">
         [114]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0080">
      Mivast
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0080">
       Mivast
      </a>
      has the capability to download and execute .exe files.
      <span class="scite-citeref-number" data-reference="Symantec Backdoor.Mivast" id="scite-ref-115-a" onclick="scrollToRef('scite-115')">
       <sup>
        <a aria-describedby="qtip-114" data-hasqtip="114" href="http://www.symantec.com/security_response/writeup.jsp?docid=2015-020623-0740-99&amp;tabid=2" target="_blank">
         [115]
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
      has a command to download a file from the C2 server to the victim mobile device's SD card.
      <span class="scite-citeref-number" data-reference="Scarlet Mimic Jan 2016" id="scite-ref-30-a" onclick="scrollToRef('scite-30')">
       <sup>
        <a aria-describedby="qtip-29" data-hasqtip="29" href="http://researchcenter.paloaltonetworks.com/2016/01/scarlet-mimic-years-long-espionage-targets-minority-activists/" target="_blank">
         [30]
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
      can download and launch additional payloads.
      <span class="scite-citeref-number" data-reference="Talos Cobalt Group July 2018" id="scite-ref-116-a" onclick="scrollToRef('scite-116')">
       <sup>
        <a aria-describedby="qtip-115" data-hasqtip="115" href="https://blog.talosintelligence.com/2018/07/multiple-cobalt-personality-disorder.html" target="_blank">
         [116]
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
      can upload and download files to the victim.
      <span class="scite-citeref-number" data-reference="ESET Turla Mosquito Jan 2018" id="scite-ref-117-a" onclick="scrollToRef('scite-117')">
       <sup>
        <a aria-describedby="qtip-116" data-hasqtip="116" href="https://www.welivesecurity.com/wp-content/uploads/2018/01/ESET_Turla_Mosquito.pdf" target="_blank">
         [117]
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
      has used malware that can upload additional files to the victim’s machine.
      <span class="scite-citeref-number" data-reference="Securelist MuddyWater Oct 2018" id="scite-ref-118-a" onclick="scrollToRef('scite-118')">
       <sup>
        <a aria-describedby="qtip-117" data-hasqtip="117" href="https://securelist.com/muddywater/88059/" target="_blank">
         [118]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="ClearSky MuddyWater Nov 2018" id="scite-ref-119-a" onclick="scrollToRef('scite-119')">
       <sup>
        <a aria-describedby="qtip-118" data-hasqtip="118" href="https://www.clearskysec.com/wp-content/uploads/2018/11/MuddyWater-Operations-in-Lebanon-and-Oman.pdf" target="_blank">
         [119]
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
      can download additional files from URLs.
      <span class="scite-citeref-number" data-reference="Proofpoint Leviathan Oct 2017" id="scite-ref-104-a" onclick="scrollToRef('scite-104')">
       <sup>
        <a aria-describedby="qtip-103" data-hasqtip="103" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" target="_blank">
         [104]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0336">
      NanoCore
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0336">
       NanoCore
      </a>
      has the capability to download and activate additional modules for execution.
      <span class="scite-citeref-number" data-reference="DigiTrust NanoCore Jan 2017" id="scite-ref-120-a" onclick="scrollToRef('scite-120')">
       <sup>
        <a aria-describedby="qtip-119" data-hasqtip="119" href="https://www.digitrustgroup.com/nanocore-not-your-average-rat/" target="_blank">
         [120]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PaloAlto NanoCore Feb 2016" id="scite-ref-121-a" onclick="scrollToRef('scite-121')">
       <sup>
        <a aria-describedby="qtip-120" data-hasqtip="120" href="https://researchcenter.paloaltonetworks.com/2016/02/nanocorerat-behind-an-increase-in-tax-themed-phishing-e-mails/" target="_blank">
         [121]
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
      can download files remotely.
      <span class="scite-citeref-number" data-reference="Talos NavRAT May 2018" id="scite-ref-122-a" onclick="scrollToRef('scite-122')">
       <sup>
        <a aria-describedby="qtip-121" data-hasqtip="121" href="https://blog.talosintelligence.com/2018/05/navrat.html" target="_blank">
         [122]
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
      can download and execute a file from given URL.
      <span class="scite-citeref-number" data-reference="TrendMicro Patchwork Dec 2017" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" target="_blank">
         [20]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0210">
      Nerex
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0210">
       Nerex
      </a>
      creates a backdoor through which remote attackers can download files onto a compromised host.
      <span class="scite-citeref-number" data-reference="Symantec Ristol May 2012" id="scite-ref-62-a" onclick="scrollToRef('scite-62')">
       <sup>
        <a aria-describedby="qtip-61" data-hasqtip="61" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051515-3909-99" target="_blank">
         [62]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0118">
      Nidiran
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0118">
       Nidiran
      </a>
      can download and execute files.
      <span class="scite-citeref-number" data-reference="Symantec Backdoor.Nidiran" id="scite-ref-123-a" onclick="scrollToRef('scite-123')">
       <sup>
        <a aria-describedby="qtip-122" data-hasqtip="122" href="https://www.symantec.com/security_response/writeup.jsp?docid=2015-120123-5521-99" target="_blank">
         [123]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0353">
      NOKKI
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0353">
       NOKKI
      </a>
      has downloaded a remote module for execution.
      <span class="scite-citeref-number" data-reference="Unit 42 NOKKI Sept 2018" id="scite-ref-124-a" onclick="scrollToRef('scite-124')">
       <sup>
        <a aria-describedby="qtip-123" data-hasqtip="123" href="https://researchcenter.paloaltonetworks.com/2018/09/unit42-new-konni-malware-attacking-eurasia-southeast-asia/" target="_blank">
         [124]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0340">
      Octopus
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0340">
       Octopus
      </a>
      can upload and download files to and from the victim’s machine.[
      <span class="scite-citeref-number" data-reference="Securelist Octopus Oct 2018" id="scite-ref-125-a" onclick="scrollToRef('scite-125')">
       <sup>
        <a aria-describedby="qtip-124" data-hasqtip="124" href="https://securelist.com/octopus-infested-seas-of-central-asia/88200/" target="_blank">
         [125]
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
      can download remote files onto victims.
      <span class="scite-citeref-number" data-reference="FireEye APT34 Dec 2017" id="scite-ref-126-a" onclick="scrollToRef('scite-126')">
       <sup>
        <a aria-describedby="qtip-125" data-hasqtip="125" href="https://www.fireeye.com/blog/threat-research/2017/12/targeted-attack-in-middle-east-by-apt34.html" target="_blank">
         [126]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0365">
      Olympic Destroyer
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0365">
       Olympic Destroyer
      </a>
      attempts to copy itself to remote machines on the network.
      <span class="scite-citeref-number" data-reference="Talos Olympic Destroyer 2018" id="scite-ref-127-a" onclick="scrollToRef('scite-127')">
       <sup>
        <a aria-describedby="qtip-126" data-hasqtip="126" href="https://blog.talosintelligence.com/2018/02/olympic-destroyer.html" target="_blank">
         [127]
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
      can download files from its C2 server to the victim's machine.
      <span class="scite-citeref-number" data-reference="Unit 42 OopsIE! Feb 2018" id="scite-ref-128-a" onclick="scrollToRef('scite-128')">
       <sup>
        <a aria-describedby="qtip-127" data-hasqtip="127" href="https://researchcenter.paloaltonetworks.com/2018/02/unit42-oopsie-oilrig-uses-threedollars-deliver-new-trojan/" target="_blank">
         [128]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Unit 42 OilRig Sept 2018" id="scite-ref-129-a" onclick="scrollToRef('scite-129')">
       <sup>
        <a aria-describedby="qtip-128" data-hasqtip="128" href="https://researchcenter.paloaltonetworks.com/2018/09/unit42-oilrig-targets-middle-eastern-government-adds-evasion-techniques-oopsie/" target="_blank">
         [129]
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
      can download files onto the victim.
      <span class="scite-citeref-number" data-reference="Proofpoint Leviathan Oct 2017" id="scite-ref-104-a" onclick="scrollToRef('scite-104')">
       <sup>
        <a aria-describedby="qtip-103" data-hasqtip="103" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" target="_blank">
         [104]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0352">
      OSX_OCEANLOTUS.D
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0352">
       OSX_OCEANLOTUS.D
      </a>
      has a command to download and execute a file on the victim’s machine.
      <span class="scite-citeref-number" data-reference="TrendMicro MacOS April 2018" id="scite-ref-130-a" onclick="scrollToRef('scite-130')">
       <sup>
        <a aria-describedby="qtip-129" data-hasqtip="129" href="https://blog.trendmicro.com/trendlabs-security-intelligence/new-macos-backdoor-linked-to-oceanlotus-found/" target="_blank">
         [130]
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
      creates a backdoor through which remote attackers can upload files.
      <span class="scite-citeref-number" data-reference="Symantec Pasam May 2012" id="scite-ref-131-a" onclick="scrollToRef('scite-131')">
       <sup>
        <a aria-describedby="qtip-130" data-hasqtip="130" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-050412-4128-99" target="_blank">
         [131]
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
      payloads download additional files from the C2 server.
      <span class="scite-citeref-number" data-reference="Securelist Dropping Elephant" id="scite-ref-132-a" onclick="scrollToRef('scite-132')">
       <sup>
        <a aria-describedby="qtip-131" data-hasqtip="131" href="https://securelist.com/the-dropping-elephant-actor/75328/" target="_blank">
         [132]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="TrendMicro Patchwork Dec 2017" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" target="_blank">
         [20]
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
      has a command to upload a file to the victim machine.
      <span class="scite-citeref-number" data-reference="Palo Alto DNS Requests" id="scite-ref-133-a" onclick="scrollToRef('scite-133')">
       <sup>
        <a aria-describedby="qtip-132" data-hasqtip="132" href="http://researchcenter.paloaltonetworks.com/2016/05/unit42-new-wekby-attacks-use-dns-requests-as-command-and-control-mechanism/" target="_blank">
         [133]
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
      has downloaded and executed additional plugins.
      <span class="scite-citeref-number" data-reference="Rancor Unit42 June 2018" id="scite-ref-53-a" onclick="scrollToRef('scite-53')">
       <sup>
        <a aria-describedby="qtip-52" data-hasqtip="52" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-rancor-targeted-attacks-south-east-asia-using-plaintee-ddkong-malware-families/" target="_blank">
         [53]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0068">
      PLATINUM
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0068">
       PLATINUM
      </a>
      has transferred files using the Intel® Active Management Technology (AMT) Serial-over-LAN (SOL) channel.
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0013">
      PlugX
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0013">
       PlugX
      </a>
      has a module to download and execute files on the compromised machine.
      <span class="scite-citeref-number" data-reference="CIRCL PlugX March 2013" id="scite-ref-134-a" onclick="scrollToRef('scite-134')">
       <sup>
        <a aria-describedby="qtip-133" data-hasqtip="133" href="http://circl.lu/assets/files/tr-12/tr-12-circl-plugx-analysis-v1.pdf" target="_blank">
         [134]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0012">
      PoisonIvy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0012">
       PoisonIvy
      </a>
      creates a backdoor through which remote attackers can upload files.
      <span class="scite-citeref-number" data-reference="Symantec Darkmoon Aug 2005" id="scite-ref-135-a" onclick="scrollToRef('scite-135')">
       <sup>
        <a aria-describedby="qtip-134" data-hasqtip="134" href="https://www.symantec.com/security_response/writeup.jsp?docid=2005-081910-3934-99" target="_blank">
         [135]
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
      downloads and executes additional PowerShell code and Windows binaries.
      <span class="scite-citeref-number" data-reference="FireEye POSHSPY April 2017" id="scite-ref-136-a" onclick="scrollToRef('scite-136')">
       <sup>
        <a aria-describedby="qtip-135" data-hasqtip="135" href="https://www.fireeye.com/blog/threat-research/2017/03/dissecting_one_ofap.html" target="_blank">
         [136]
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
      has a command to download a file.
      <span class="scite-citeref-number" data-reference="Volexity PowerDuke November 2016" id="scite-ref-137-a" onclick="scrollToRef('scite-137')">
       <sup>
        <a aria-describedby="qtip-136" data-hasqtip="136" href="https://www.volexity.com/blog/2016/11/09/powerduke-post-election-spear-phishing-campaigns-targeting-think-tanks-and-ngos/" target="_blank">
         [137]
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
      has been observed being used to download
      <a href="https://attack.mitre.org/software/S0146">
       TEXTMATE
      </a>
      and the Cobalt Strike Beacon payload onto victims.
      <span class="scite-citeref-number" data-reference="FireEye FIN7 March 2017" id="scite-ref-138-a" onclick="scrollToRef('scite-138')">
       <sup>
        <a aria-describedby="qtip-137" data-hasqtip="137" href="https://www.fireeye.com/blog/threat-research/2017/03/fin7_spear_phishing.html" target="_blank">
         [138]
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
      can retrieve and execute additional
      <a href="https://attack.mitre.org/techniques/T1086">
       PowerShell
      </a>
      payloads from the C2 server.
      <span class="scite-citeref-number" data-reference="FireEye MuddyWater Mar 2018" id="scite-ref-139-a" onclick="scrollToRef('scite-139')">
       <sup>
        <a aria-describedby="qtip-138" data-hasqtip="138" href="https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html" target="_blank">
         [139]
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
      can download or upload files from its C2 server.
      <span class="scite-citeref-number" data-reference="FireEye APT34 Dec 2017" id="scite-ref-126-a" onclick="scrollToRef('scite-126')">
       <sup>
        <a aria-describedby="qtip-125" data-hasqtip="125" href="https://www.fireeye.com/blog/threat-research/2017/12/targeted-attack-in-middle-east-by-apt34.html" target="_blank">
         [126]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0078">
      Psylo
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0078">
       Psylo
      </a>
      has a command to download a file to the system from its C2 server.
      <span class="scite-citeref-number" data-reference="Scarlet Mimic Jan 2016" id="scite-ref-30-a" onclick="scrollToRef('scite-30')">
       <sup>
        <a aria-describedby="qtip-29" data-hasqtip="29" href="http://researchcenter.paloaltonetworks.com/2016/01/scarlet-mimic-years-long-espionage-targets-minority-activists/" target="_blank">
         [30]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0147">
      Pteranodon
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0147">
       Pteranodon
      </a>
      can download and execute additional files.
      <span class="scite-citeref-number" data-reference="Palo Alto Gamaredon Feb 2017" id="scite-ref-75-a" onclick="scrollToRef('scite-75')">
       <sup>
        <a aria-describedby="qtip-74" data-hasqtip="74" href="https://researchcenter.paloaltonetworks.com/2017/02/unit-42-title-gamaredon-group-toolset-evolution/" target="_blank">
         [75]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0196">
      PUNCHBUGGY
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0196">
       PUNCHBUGGY
      </a>
      can download additional files and payloads to compromised hosts.
      <span class="scite-citeref-number" data-reference="FireEye Know Your Enemy FIN8 Aug 2016" id="scite-ref-140-a" onclick="scrollToRef('scite-140')">
       <sup>
        <a aria-describedby="qtip-139" data-hasqtip="139" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" target="_blank">
         [140]
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
      can upload and download to/from a victim machine.
      <span class="scite-citeref-number" data-reference="GitHub Pupy" id="scite-ref-141-a" onclick="scrollToRef('scite-141')">
       <sup>
        <a aria-describedby="qtip-140" data-hasqtip="140" href="https://github.com/n1nj4sec/pupy" target="_blank">
         [141]
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
      can download files to the victim’s machine and execute them.
      <span class="scite-citeref-number" data-reference="GitHub QuasarRAT" id="scite-ref-142-a" onclick="scrollToRef('scite-142')">
       <sup>
        <a aria-describedby="qtip-141" data-hasqtip="141" href="https://github.com/quasar/QuasarRAT" target="_blank">
         [142]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Volexity Patchwork June 2018" id="scite-ref-143-a" onclick="scrollToRef('scite-143')">
       <sup>
        <a aria-describedby="qtip-142" data-hasqtip="142" href="https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/" target="_blank">
         [143]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0075">
      Rancor
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0075">
       Rancor
      </a>
      has downloaded additional malware, including by using
      <a href="https://attack.mitre.org/software/S0160">
       certutil
      </a>
      .
      <span class="scite-citeref-number" data-reference="Rancor Unit42 June 2018" id="scite-ref-53-a" onclick="scrollToRef('scite-53')">
       <sup>
        <a aria-describedby="qtip-52" data-hasqtip="52" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-rancor-targeted-attacks-south-east-asia-using-plaintee-ddkong-malware-families/" target="_blank">
         [53]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0055">
      RARSTONE
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0055">
       RARSTONE
      </a>
      downloads its backdoor component from a C2 server and loads it directly into memory.
      <span class="scite-citeref-number" data-reference="Aquino RARSTONE" id="scite-ref-144-a" onclick="scrollToRef('scite-144')">
       <sup>
        <a aria-describedby="qtip-143" data-hasqtip="143" href="http://blog.trendmicro.com/trendlabs-security-intelligence/rarstone-found-in-targeted-attacks/" target="_blank">
         [144]
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
      uploads and downloads information.
      <span class="scite-citeref-number" data-reference="Lazarus RATANKBA" id="scite-ref-145-a" onclick="scrollToRef('scite-145')">
       <sup>
        <a aria-describedby="qtip-144" data-hasqtip="144" href="https://blog.trendmicro.com/trendlabs-security-intelligence/lazarus-campaign-targeting-cryptocurrencies-reveals-remote-controller-tool-evolved-ratankba/" target="_blank">
         [145]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="RATANKBA" id="scite-ref-146-a" onclick="scrollToRef('scite-146')">
       <sup>
        [146]
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
      is capable of downloading a file from a specified URL.
      <span class="scite-citeref-number" data-reference="PWC Cloud Hopper Technical Annex April 2017" id="scite-ref-147-a" onclick="scrollToRef('scite-147')">
       <sup>
        <a aria-describedby="qtip-146" data-hasqtip="146" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" target="_blank">
         [147]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0332">
      Remcos
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0332">
       Remcos
      </a>
      can upload and download files to and from the victim’s machine.
      <span class="scite-citeref-number" data-reference="Riskiq Remcos Jan 2018" id="scite-ref-148-a" onclick="scrollToRef('scite-148')">
       <sup>
        <a aria-describedby="qtip-147" data-hasqtip="147" href="https://www.riskiq.com/blog/labs/spear-phishing-turkish-defense-contractors/" target="_blank">
         [148]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0166">
      RemoteCMD
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0166">
       RemoteCMD
      </a>
      copies a file over to the remote system before execution.
      <span class="scite-citeref-number" data-reference="Symantec Buckeye" id="scite-ref-149-a" onclick="scrollToRef('scite-149')">
       <sup>
        <a aria-describedby="qtip-148" data-hasqtip="148" href="http://www.symantec.com/connect/blogs/buckeye-cyberespionage-group-shifts-gaze-us-hong-kong" target="_blank">
         [149]
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
      contains a network loader to receive executable modules from remote attackers and run them on the local victim. It can also upload and download files over HTTP and HTTPS.
      <span class="scite-citeref-number" data-reference="Symantec Remsec IOCs" id="scite-ref-150-a" onclick="scrollToRef('scite-150')">
       <sup>
        <a aria-describedby="qtip-149" data-hasqtip="149" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/Symantec_Remsec_IOCs.pdf" target="_blank">
         [150]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Kaspersky ProjectSauron Technical Analysis" id="scite-ref-151-a" onclick="scrollToRef('scite-151')">
       <sup>
        <a aria-describedby="qtip-150" data-hasqtip="150" href="https://securelist.com/files/2016/07/The-ProjectSauron-APT_Technical_Analysis_KL.pdf" target="_blank">
         [151]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0258">
      RGDoor
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0258">
       RGDoor
      </a>
      uploads and downloads files to and from the victim’s machine.
      <span class="scite-citeref-number" data-reference="Unit 42 RGDoor Jan 2018" id="scite-ref-152-a" onclick="scrollToRef('scite-152')">
       <sup>
        <a aria-describedby="qtip-151" data-hasqtip="151" href="https://researchcenter.paloaltonetworks.com/2018/01/unit42-oilrig-uses-rgdoor-iis-backdoor-targets-middle-east/" target="_blank">
         [152]
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
      can save a new file to the system from the C2 server.
      <span class="scite-citeref-number" data-reference="Unit 42 DarkHydrus July 2018" id="scite-ref-153-a" onclick="scrollToRef('scite-153')">
       <sup>
        <a aria-describedby="qtip-152" data-hasqtip="152" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-new-threat-actor-group-darkhydrus-targets-middle-east-government/" target="_blank">
         [153]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Unit42 DarkHydrus Jan 2019" id="scite-ref-154-a" onclick="scrollToRef('scite-154')">
       <sup>
        <a aria-describedby="qtip-153" data-hasqtip="153" href="https://unit42.paloaltonetworks.com/darkhydrus-delivers-new-trojan-that-can-use-google-drive-for-c2-communications/" target="_blank">
         [154]
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
      retrieves additional malicious payloads from the C2 server.
      <span class="scite-citeref-number" data-reference="Talos ROKRAT" id="scite-ref-155-a" onclick="scrollToRef('scite-155')">
       <sup>
        <a aria-describedby="qtip-154" data-hasqtip="154" href="https://blog.talosintelligence.com/2017/04/introducing-rokrat.html" target="_blank">
         [155]
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
      can download additional files.
      <span class="scite-citeref-number" data-reference="ESET RTM Feb 2017" id="scite-ref-156-a" onclick="scrollToRef('scite-156')">
       <sup>
        <a aria-describedby="qtip-155" data-hasqtip="155" href="https://www.welivesecurity.com/wp-content/uploads/2017/02/Read-The-Manual.pdf" target="_blank">
         [156]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0074">
      Sakula
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0074">
       Sakula
      </a>
      has the capability to download files.
      <span class="scite-citeref-number" data-reference="Dell Sakula" id="scite-ref-157-a" onclick="scrollToRef('scite-157')">
       <sup>
        <a aria-describedby="qtip-156" data-hasqtip="156" href="http://www.secureworks.com/cyber-threat-intelligence/threats/sakula-malware-family/" target="_blank">
         [157]
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
      is capable of uploading and downloading files.
      <span class="scite-citeref-number" data-reference="Unit 42 SeaDuke 2015" id="scite-ref-158-a" onclick="scrollToRef('scite-158')">
       <sup>
        <a aria-describedby="qtip-157" data-hasqtip="157" href="http://researchcenter.paloaltonetworks.com/2015/07/unit-42-technical-analysis-seaduke/" target="_blank">
         [158]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0345">
      Seasalt
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0345">
       Seasalt
      </a>
      has a command to download additional files.
      <span class="scite-citeref-number" data-reference="Mandiant APT1 Appendix" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report-appendix.zip" target="_blank">
         [23]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Mandiant APT1 Appendix" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report-appendix.zip" target="_blank">
         [23]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0185">
      SEASHARPEE
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0185">
       SEASHARPEE
      </a>
      can download remote files onto victims.
      <span class="scite-citeref-number" data-reference="FireEye APT34 Webinar Dec 2017" id="scite-ref-159-a" onclick="scrollToRef('scite-159')">
       <sup>
        <a aria-describedby="qtip-158" data-hasqtip="158" href="https://www.brighttalk.com/webcast/10703/296317/apt34-new-targeted-attack-in-the-middle-east" target="_blank">
         [159]
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
      can download an executable to run on the victim.
      <span class="scite-citeref-number" data-reference="Palo Alto Shamoon Nov 2016" id="scite-ref-160-a" onclick="scrollToRef('scite-160')">
       <sup>
        <a aria-describedby="qtip-159" data-hasqtip="159" href="http://researchcenter.paloaltonetworks.com/2016/11/unit42-shamoon-2-return-disttrack-wiper/" target="_blank">
         [160]
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
      can download and execute an arbitary executable.
      <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
         [11]
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
      downloads additional payloads.
      <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
         [11]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0226">
      Smoke Loader
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0226">
       Smoke Loader
      </a>
      downloads a new version of itself once it has installed. It also downloads additional plugins.
      <span class="scite-citeref-number" data-reference="Malwarebytes SmokeLoader 2016" id="scite-ref-161-a" onclick="scrollToRef('scite-161')">
       <sup>
        <a aria-describedby="qtip-160" data-hasqtip="160" href="https://blog.malwarebytes.com/threat-analysis/2016/08/smoke-loader-downloader-with-a-smokescreen-still-alive/" target="_blank">
         [161]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0374">
      SpeakUp
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0374">
       SpeakUp
      </a>
      downloads and executes additional files from a remote server.
      <span class="scite-citeref-number" data-reference="CheckPoint SpeakUp Feb 2019" id="scite-ref-162-a" onclick="scrollToRef('scite-162')">
       <sup>
        <a aria-describedby="qtip-161" data-hasqtip="161" href="https://research.checkpoint.com/speakup-a-new-undetected-backdoor-linux-trojan/" target="_blank">
         [162]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0164">
      TDTESS
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0164">
       TDTESS
      </a>
      has a command to download and execute an additional file.
      <span class="scite-citeref-number" data-reference="ClearSky Wilted Tulip July 2017" id="scite-ref-163-a" onclick="scrollToRef('scite-163')">
       <sup>
        <a aria-describedby="qtip-162" data-hasqtip="162" href="http://www.clearskysec.com/wp-content/uploads/2017/07/Operation_Wilted_Tulip.pdf" target="_blank">
         [163]
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
      After re-establishing access to a victim network,
      <a href="https://attack.mitre.org/groups/G0027">
       Threat Group-3390
      </a>
      actors download tools including
      <a href="https://attack.mitre.org/software/S0008">
       gsecdump
      </a>
      and WCE that are staged temporarily on websites that were previously compromised but never used.
      <span class="scite-citeref-number" data-reference="Dell TG-3390" id="scite-ref-85-a" onclick="scrollToRef('scite-85')">
       <sup>
        <a aria-describedby="qtip-84" data-hasqtip="84" href="https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage" target="_blank">
         [85]
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
      downloads several additional files and saves them to the victim's machine.
      <span class="scite-citeref-number" data-reference="Trend Micro Totbrick Oct 2016" id="scite-ref-164-a" onclick="scrollToRef('scite-164')">
       <sup>
        <a aria-describedby="qtip-163" data-hasqtip="163" href="https://www.trendmicro.com/vinfo/us/threat-encyclopedia/malware/tspy_trickload.n" target="_blank">
         [164]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0094">
      Trojan.Karagany
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0094">
       Trojan.Karagany
      </a>
      can upload, download, and execute files on the victim.
      <span class="scite-citeref-number" data-reference="Symantec Dragonfly" id="scite-ref-165-a" onclick="scrollToRef('scite-165')">
       <sup>
        <a aria-describedby="qtip-164" data-hasqtip="164" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/Dragonfly_Threat_Against_Western_Energy_Suppliers.pdf" target="_blank">
         [165]
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
      has used shellcode to download Meterpreter after compromising a victim.
      <span class="scite-citeref-number" data-reference="ESET Turla Mosquito May 2018" id="scite-ref-166-a" onclick="scrollToRef('scite-166')">
       <sup>
        <a aria-describedby="qtip-165" data-hasqtip="165" href="https://www.welivesecurity.com/2018/05/22/turla-mosquito-shift-towards-generic-tools/" target="_blank">
         [166]
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
      is capable of downloading additional files.
      <span class="scite-citeref-number" data-reference="FireEye APT33 Sept 2017" id="scite-ref-167-a" onclick="scrollToRef('scite-167')">
       <sup>
        <a aria-describedby="qtip-166" data-hasqtip="166" href="https://www.fireeye.com/blog/threat-research/2017/09/apt33-insights-into-iranian-cyber-espionage.html" target="_blank">
         [167]
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
      can upload and download files to the victim’s machine.
      <span class="scite-citeref-number" data-reference="US-CERT TYPEFRAME June 2018" id="scite-ref-168-a" onclick="scrollToRef('scite-168')">
       <sup>
        <a aria-describedby="qtip-167" data-hasqtip="167" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-165A" target="_blank">
         [168]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0333">
      UBoatRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0333">
       UBoatRAT
      </a>
      can upload and download files to the victim’s machine.
      <span class="scite-citeref-number" data-reference="PaloAlto UBoatRAT Nov 2017" id="scite-ref-169-a" onclick="scrollToRef('scite-169')">
       <sup>
        <a aria-describedby="qtip-168" data-hasqtip="168" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-uboatrat-navigates-east-asia/" target="_blank">
         [169]
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
      is capable of downloading remote files.
      <span class="scite-citeref-number" data-reference="Forcepoint Monsoon" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" target="_blank">
         [18]
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
      can download and upload files to and from the victim’s machine.
      <span class="scite-citeref-number" data-reference="FireEye APT10 Sept 2018" id="scite-ref-170-a" onclick="scrollToRef('scite-170')">
       <sup>
        <a aria-describedby="qtip-169" data-hasqtip="169" href="https://www.fireeye.com/blog/threat-research/2018/09/apt10-targeting-japanese-corporations-using-updated-ttps.html" target="_blank">
         [170]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0207">
      Vasport
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0207">
       Vasport
      </a>
      can download files.
      <span class="scite-citeref-number" data-reference="Symantec Vasport May 2012" id="scite-ref-171-a" onclick="scrollToRef('scite-171')">
       <sup>
        <a aria-describedby="qtip-170" data-hasqtip="170" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051606-5938-99" target="_blank">
         [171]
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
      can download and upload files to the victim's machine.
      <span class="scite-citeref-number" data-reference="Unit 42 VERMIN Jan 2018" id="scite-ref-172-a" onclick="scrollToRef('scite-172')">
       <sup>
        <a aria-describedby="qtip-171" data-hasqtip="171" href="https://researchcenter.paloaltonetworks.com/2018/01/unit42-vermin-quasar-rat-custom-malware-used-ukraine/" target="_blank">
         [172]
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
      can download remote files and additional payloads to the victim's machine.
      <span class="scite-citeref-number" data-reference="US-CERT Volgmer Nov 2017" id="scite-ref-173-a" onclick="scrollToRef('scite-173')">
       <sup>
        <a aria-describedby="qtip-172" data-hasqtip="172" href="https://www.us-cert.gov/ncas/alerts/TA17-318B" target="_blank">
         [173]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT Volgmer 2 Nov 2017" id="scite-ref-174-a" onclick="scrollToRef('scite-174')">
       <sup>
        <a aria-describedby="qtip-173" data-hasqtip="173" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-D_WHITE_S508C.PDF" target="_blank">
         [174]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Symantec Volgmer Aug 2014" id="scite-ref-175-a" onclick="scrollToRef('scite-175')">
       <sup>
        <a aria-describedby="qtip-174" data-hasqtip="174" href="https://www.symantec.com/security-center/writeup/2014-081811-3237-99?tabid=2" target="_blank">
         [175]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0366">
      WannaCry
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0366">
       WannaCry
      </a>
      attempts to copy itself to remote computers after gaining access via an SMB exploit.
      <span class="scite-citeref-number" data-reference="LogRhythm WannaCry" id="scite-ref-176-a" onclick="scrollToRef('scite-176')">
       <sup>
        <a aria-describedby="qtip-175" data-hasqtip="175" href="https://logrhythm.com/blog/a-technical-analysis-of-wannacry-ransomware/" target="_blank">
         [176]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0109">
      WEBC2
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0109">
       WEBC2
      </a>
      can download and execute a file.
      <span class="scite-citeref-number" data-reference="Mandiant APT1" id="scite-ref-177-a" onclick="scrollToRef('scite-177')">
       <sup>
        <a aria-describedby="qtip-176" data-hasqtip="176" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf" target="_blank">
         [177]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0206">
      Wiarp
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0206">
       Wiarp
      </a>
      creates a backdoor through which remote attackers can download files.
      <span class="scite-citeref-number" data-reference="Symantec Wiarp May 2012" id="scite-ref-178-a" onclick="scrollToRef('scite-178')">
       <sup>
        <a aria-describedby="qtip-177" data-hasqtip="177" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051606-1005-99" target="_blank">
         [178]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0341">
      Xbash
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0341">
       Xbash
      </a>
      can download additional malicious files from its C2 server.
      <span class="scite-citeref-number" data-reference="Unit42 Xbash Sept 2018" id="scite-ref-179-a" onclick="scrollToRef('scite-179')">
       <sup>
        <a aria-describedby="qtip-178" data-hasqtip="178" href="https://researchcenter.paloaltonetworks.com/2018/09/unit42-xbash-combines-botnet-ransomware-coinmining-worm-targets-linux-windows/" target="_blank">
         [179]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0117">
      XTunnel
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0117">
       XTunnel
      </a>
      is capable of downloading additional files.
      <span class="scite-citeref-number" data-reference="Invincea XTunnel" id="scite-ref-180-a" onclick="scrollToRef('scite-180')">
       <sup>
        <a aria-describedby="qtip-179" data-hasqtip="179" href="https://www.invincea.com/2016/07/tunnel-of-gov-dnc-hack-and-the-russian-xtunnel/" target="_blank">
         [180]
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
      obtains additional code to execute on the victim's machine.
      <a href="https://attack.mitre.org/software/S0251">
       Zebrocy
      </a>
      downloads a secondary payload and writes it to the victim’s machine.
      <span class="scite-citeref-number" data-reference="Palo Alto Sofacy 06-2018" id="scite-ref-181-a" onclick="scrollToRef('scite-181')">
       <sup>
        <a aria-describedby="qtip-180" data-hasqtip="180" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-sofacy-groups-parallel-attacks/" target="_blank">
         [181]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Unit42 Cannon Nov 2018" id="scite-ref-31-a" onclick="scrollToRef('scite-31')">
       <sup>
        <a aria-describedby="qtip-30" data-hasqtip="30" href="https://researchcenter.paloaltonetworks.com/2018/11/unit42-sofacy-continues-global-attacks-wheels-new-cannon-trojan/" target="_blank">
         [31]
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
      can download additional payloads onto the victim.
      <span class="scite-citeref-number" data-reference="Proofpoint ZeroT Feb 2017" id="scite-ref-182-a" onclick="scrollToRef('scite-182')">
       <sup>
        <a aria-describedby="qtip-181" data-hasqtip="181" href="https://www.proofpoint.com/us/threat-insight/post/APT-targets-russia-belarus-zerot-plugx" target="_blank">
         [182]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0330">
      Zeus Panda
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0330">
       Zeus Panda
      </a>
      can download additional malware plug-in modules and execute them on the victim’s machine.
      <span class="scite-citeref-number" data-reference="GDATA Zeus Panda June 2017" id="scite-ref-183-a" onclick="scrollToRef('scite-183')">
       <sup>
        <a aria-describedby="qtip-182" data-hasqtip="182" href="https://cyberwtf.files.wordpress.com/2017/07/panda-whitepaper.pdf" target="_blank">
         [183]
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
      has the ability to download files.
      <span class="scite-citeref-number" data-reference="Cylance Dust Storm" id="scite-ref-114-a" onclick="scrollToRef('scite-114')">
       <sup>
        <a aria-describedby="qtip-113" data-hasqtip="113" href="https://www.cylance.com/content/dam/cylance/pdfs/reports/Op_Dust_Storm_Report.pdf" target="_blank">
         [114]
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
  Network intrusion detection and prevention systems that use network signatures to identify traffic for specific adversary malware or unusual data transfer over known tools and protocols like FTP can be used to mitigate activity at the network level. Signatures are often for unique indicators within protocols and may be based on the specific obfuscation technique used by a particular adversary or tool, and will likely be different across various malware families and versions. Adversaries will likely change tool C2 signatures over time or construct protocols in such a way as to avoid detection by common defensive tools.
  <span class="scite-citeref-number" data-reference="University of Birmingham C2" id="scite-ref-184-a">
   <sup>
    <a aria-describedby="qtip-183" data-hasqtip="183" href="https://arxiv.org/ftp/arxiv/papers/1408/1408.1136.pdf" target="_blank">
     [184]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor for file creation and files transferred within a network over SMB. Unusual processes with external network connections creating files on-system may be suspicious. Use of utilities, such as FTP, that does not normally occur may also be suspicious.
 </p>
 <p>
  Analyze network data for uncommon data flows (e.g., a client sending significantly more data than it receives from a server). Processes utilizing the network that do not normally have network communication or have never been seen before are suspicious. Analyze packet contents to detect communications that do not follow the expected protocol behavior for the port that is being used.
  <span class="scite-citeref-number" data-reference="University of Birmingham C2" id="scite-ref-184-a">
   <sup>
    <a aria-describedby="qtip-183" data-hasqtip="183" href="https://arxiv.org/ftp/arxiv/papers/1408/1408.1136.pdf" target="_blank">
     [184]
    </a>
   </sup>
  </span>
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
       <a class="external text" href="https://blog.talosintelligence.com/2018/10/old-dog-new-tricks-analysing-new-rtf_15.html" name="scite-1" rel="nofollow" target="_blank">
        Brumaghin, E., et al. (2018, October 15). Old dog, new tricks - Analysing new RTF-based campaign distributing Agent Tesla, Loki with PyREbox. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.digitrustgroup.com/agent-tesla-keylogger/" name="scite-2" rel="nofollow" target="_blank">
        The DigiTrust Group. (2017, January 12). The Rise of Agent Tesla. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.threatexpert.com/2008/11/agentbtz-threat-that-hit-pentagon.html" name="scite-3" rel="nofollow" target="_blank">
        Shevchenko, S.. (2008, November 30). Agent.btz - A Threat That Hit Pentagon. Retrieved April 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2016/05/unit42-new-wekby-attacks-use-dns-requests-as-command-and-control-mechanism/" name="scite-4" rel="nofollow" target="_blank">
        Grunzweig, J., et al. (2016, May 24). New Wekby Attacks Use DNS Requests As Command and Control Mechanism. Retrieved November 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://download.bitdefender.com/resources/media/materials/white-papers/en/Bitdefender_In-depth_analysis_of_APT28%E2%80%93The_Political_Cyber-Espionage.pdf" name="scite-5" rel="nofollow" target="_blank">
        Bitdefender. (2015, December). APT28 Under the Scope. Retrieved February 23, 2017.
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
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2014/04/new-zero-day-exploit-targeting-internet-explorer-versions-9-through-11-identified-in-targeted-attacks.html" name="scite-7" rel="nofollow" target="_blank">
        Chen, X., Scott, M., Caselden, D.. (2014, April 26). New Zero-Day Exploit targeting Internet Explorer Versions 9 through 11 Identified in Targeted Attacks. Retrieved January 14, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.volexity.com/blog/2017/11/06/oceanlotus-blossoms-mass-digital-surveillance-and-exploitation-of-asean-nations-the-media-human-rights-and-civil-society/" name="scite-8" rel="nofollow" target="_blank">
        Lassalle, D., et al. (2017, November 6). OceanLotus Blossoms: Mass Digital Surveillance and Attacks Targeting ASEAN, Asian Nations, the Media, Human Rights Groups, and Civil Society. Retrieved November 6, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cybereason.com/blog/operation-cobalt-kitty-apt" name="scite-9" rel="nofollow" target="_blank">
        Dahan, A. (2017, May 24). OPERATION COBALT KITTY: A LARGE-SCALE APT IN ASIA CARRIED OUT BY THE OCEANLOTUS GROUP. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/elfin-apt33-espionage" name="scite-10" rel="nofollow" target="_blank">
        Security Response attack Investigation Team. (2019, March 27). Elfin: Relentless Espionage Group Targets Multiple Organizations in Saudi Arabia and U.S.. Retrieved April 10, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" name="scite-11" rel="nofollow" target="_blank">
        FireEye. (2018, February 20). APT37 (Reaper): The Overlooked North Korean Actor. Retrieved March 1, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://content.fireeye.com/apt/rpt-apt38" name="scite-12" rel="nofollow" target="_blank">
        FireEye. (2018, October 03). APT38: Un-usual Suspects. Retrieved November 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://cofense.com/seeing-resurgence-demonic-astaroth-wmic-trojan/" name="scite-13" rel="nofollow" target="_blank">
        Doaty, J., Garrett, P.. (2018, September 10). We’re Seeing a Resurgence of the Demonic Astaroth WMIC Trojan. Retrieved April 17, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cybereason.com/blog/information-stealing-malware-targeting-brazil-full-research" name="scite-14" rel="nofollow" target="_blank">
        Salem, E. (2019, February 13). ASTAROTH MALWARE USES LEGITIMATE OS AND ANTIVIRUS PROCESSES TO STEAL PASSWORDS AND PERSONAL DATA. Retrieved April 17, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/lazarus-continues-heists-mounts-attacks-on-financial-organizations-in-latin-america/" name="scite-15" rel="nofollow" target="_blank">
        Trend Micro. (2018, November 20). Lazarus Continues Heists, Mounts Attacks on Financial Organizations in Latin America. Retrieved December 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/11/unit42-new-wine-old-bottle-new-azorult-variant-found-findmyname-campaign-using-fallout-exploit-kit/" name="scite-16" rel="nofollow" target="_blank">
        Yan, T., et al. (2018, November 21). New Wine in Old Bottle: New Azorult Variant Found in FindMyName Campaign using Fallout Exploit Kit. Retrieved November 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/us/threat-insight/post/new-version-azorult-stealer-improves-loading-features-spreads-alongside" name="scite-17" rel="nofollow" target="_blank">
        Proofpoint. (2018, July 30). New version of AZORult stealer improves loading features, spreads alongside ransomware in new campaign. Retrieved November 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" name="scite-18" rel="nofollow" target="_blank">
        Settle, A., et al. (2016, August 8). MONSOON - Analysis Of An APT Campaign. Retrieved September 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/03/unit42-patchwork-continues-deliver-badnews-indian-subcontinent/" name="scite-19" rel="nofollow" target="_blank">
        Levene, B. et al.. (2018, March 7). Patchwork Continues to Deliver BADNEWS to the Indian Subcontinent. Retrieved March 31, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" name="scite-20" rel="nofollow" target="_blank">
        Lunghi, D., et al. (2017, December). Untangling the Patchwork Cyberespionage Group. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/10/unit42-badpatch/" name="scite-21" rel="nofollow" target="_blank">
        Bar, T., Conant, S. (2017, October 20). BadPatch. Retrieved November 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-B_WHITE.PDF" name="scite-22" rel="nofollow" target="_blank">
        US-CERT. (2017, December 13). Malware Analysis Report (MAR) - 10135536-B. Retrieved July 17, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-23">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report-appendix.zip" name="scite-23" rel="nofollow" target="_blank">
        Mandiant. (n.d.). Appendix C (Digital) - The Malware Arsenal. Retrieved July 18, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-24">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-bisonal-malware-used-attacks-russia-south-korea/" name="scite-24" rel="nofollow" target="_blank">
        Hayashi, K., Ray, V. (2018, July 31). Bisonal Malware Used in Attacks Against Russia and South Korea. Retrieved August 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-25">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/aa362813.aspx" name="scite-25" rel="nofollow" target="_blank">
        Microsoft. (n.d.). BITSAdmin Tool. Retrieved January 12, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-26">
      <span class="scite-citation-text">
       <a class="external text" href="https://unit42.paloaltonetworks.com/unit42-oilrig-uses-updated-bondupdater-target-middle-eastern-government/" name="scite-26" rel="nofollow" target="_blank">
        Wilhoit, K. and Falcone, R. (2018, September 12). OilRig Uses Updated BONDUPDATER to Target Middle Eastern Government. Retrieved February 18, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-27">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051515-2843-99" name="scite-27" rel="nofollow" target="_blank">
        Ladley, F. (2012, May 15). Backdoor.Briba. Retrieved February 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-28">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/bronze-butler-targets-japanese-businesses" name="scite-28" rel="nofollow" target="_blank">
        Counter Threat Unit Research Team. (2017, October 12). BRONZE BUTLER Targets Japanese Enterprises. Retrieved January 4, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-29">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security-center/writeup/2018-073014-2512-99?om_rssid=sr-latestthreats30days" name="scite-29" rel="nofollow" target="_blank">
        Pantig, J. (2018, July 30). OSX.Calisto. Retrieved September 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-30">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/01/scarlet-mimic-years-long-espionage-targets-minority-activists/" name="scite-30" rel="nofollow" target="_blank">
        Falcone, R. and Miller-Osborn, J.. (2016, January 24). Scarlet Mimic: Years-Long Espionage Campaign Targets Minority Activists. Retrieved February 10, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-31">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/11/unit42-sofacy-continues-global-attacks-wheels-new-cannon-trojan/" name="scite-31" rel="nofollow" target="_blank">
        Falcone, R., Lee, B. (2018, November 20). Sofacy Continues Global Attacks and Wheels Out New ‘Cannon’ Trojan. Retrieved November 26, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-32">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/04/unit42-cardinal-rat-active-two-years/" name="scite-32" rel="nofollow" target="_blank">
        Grunzweig, J.. (2017, April 20). Cardinal RAT Active for Over Two Years. Retrieved December 8, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-33">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/library/cc732443.aspx" name="scite-33" rel="nofollow" target="_blank">
        Microsoft. (2012, November 14). Certutil. Retrieved July 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-34">
      <span class="scite-citation-text">
       <a class="external text" href="https://twitter.com/subTee/status/888102593838362624" name="scite-34" rel="nofollow" target="_blank">
        Smith, Casey. (2017, July 20). SubTee Twitter Status. Retrieved July 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-35">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2017/02/unit42-menupass-returns-new-malware-new-attacks-japanese-academics-organizations/" name="scite-35" rel="nofollow" target="_blank">
        Miller-Osborn, J. and Grunzweig, J.. (2017, February 16). menuPass Returns with New Malware and New Attacks Against Japanese Academics and Organizations. Retrieved March 1, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-36">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2017/02/chches-malware--93d6.html" name="scite-36" rel="nofollow" target="_blank">
        Nakamura, Y.. (2017, February 17). ChChes - Malware that Communicates with C&amp;C Servers Using Cookie Headers. Retrieved March 1, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-37">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/04/apt10_menupass_grou.html" name="scite-37" rel="nofollow" target="_blank">
        FireEye iSIGHT Intelligence. (2017, April 6). APT10 (MenuPass Group): New Tools, Global Campaign Latest Manifestation of Longstanding Threat. Retrieved June 29, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-38">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" name="scite-38" rel="nofollow" target="_blank">
        FireEye. (2018, March 16). Suspected Chinese Cyber Espionage Group (TEMP.Periscope) Targeting U.S. Engineering and Maritime Industries. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-39">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2013/08/breaking-down-the-china-chopper-web-shell-part-i.html" name="scite-39" rel="nofollow" target="_blank">
        Lee, T., Hanzlik, D., Ahl, I. (2013, August 7). Breaking Down the China Chopper Web Shell - Part I. Retrieved March 27, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-40">
      <span class="scite-citation-text">
       <a class="external text" href="https://s3.eu-west-1.amazonaws.com/ncsc-content/files/Joint%20report%20on%20publicly%20available%20hacking%20tools%20%28NCSC%29.pdf" name="scite-40" rel="nofollow" target="_blank">
        The Australian Cyber Security Centre (ACSC), the Canadian Centre for Cyber Security (CCCS), the New Zealand National Cyber Security Centre (NZ NCSC), CERT New Zealand, the UK National Cyber Security Centre (UK NCSC) and the US National Cybersecurity and Communications Integration Center (NCCIC). (2018, October 11). Joint report on publicly available hacking tools. Retrieved March 11, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-41">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.crowdstrike.com/blog/bears-midst-intrusion-democratic-national-committee/" name="scite-41" rel="nofollow" target="_blank">
        Alperovitch, D.. (2016, June 15). Bears in the Midst: Intrusion into the Democratic National Committee. Retrieved August 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-42">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.f-secure.com/documents/996508/1030745/dukes_whitepaper.pdf" name="scite-42" rel="nofollow" target="_blank">
        F-Secure Labs. (2015, September 17). The Dukes: 7 years of Russian cyberespionage. Retrieved December 10, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-43">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/bb490886.aspx" name="scite-43" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Copy. Retrieved April 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-44">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.ptsecurity.com/upload/corporate/ww-en/analytics/Cobalt-2017-eng.pdf" name="scite-44" rel="nofollow" target="_blank">
        Positive Technologies. (2017, August 16). Cobalt Strikes Back: An Evolving Multinational Threat to Finance. Retrieved September 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-45">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.ptsecurity.com/upload/corporate/ww-en/analytics/Cobalt-Snatch-eng.pdf" name="scite-45" rel="nofollow" target="_blank">
        Positive Technologies. (2016, December 16). Cobalt Snatch. Retrieved October 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-46">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.morphisec.com/cobalt-gang-2.0" name="scite-46" rel="nofollow" target="_blank">
        Gorelik, M. (2018, October 08). Cobalt Group 2.0. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-47">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.malwarebytes.com/threat-analysis/2018/10/mac-cryptocurrency-ticker-app-installs-backdoors/" name="scite-47" rel="nofollow" target="_blank">
        Thomas Reed. (2018, October 29). Mac cryptocurrency ticker app installs backdoors. Retrieved April 23, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-48">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/rpt-apt28.pdf" name="scite-48" rel="nofollow" target="_blank">
        FireEye. (2015). APT28: A WINDOW INTO RUSSIA’S CYBER ESPIONAGE OPERATIONS?. Retrieved August 19, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-49">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/sites/default/files/proofpoint-operation-transparent-tribe-threat-insight-en.pdf" name="scite-49" rel="nofollow" target="_blank">
        Huss, D.. (2016, March 1). Operation Transparent Tribe. Retrieved June 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-50">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.trendmicro.com/vinfo/us/threat-encyclopedia/malware/DARKCOMET" name="scite-50" rel="nofollow" target="_blank">
        TrendMicro. (2014, September 03). DARKCOMET. Retrieved November 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-51">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.malwarebytes.com/threat-analysis/2012/06/you-dirty-rat-part-1-darkcomet/" name="scite-51" rel="nofollow" target="_blank">
        Kujawa, A. (2018, March 27). You dirty RAT! Part 1: DarkComet. Retrieved November 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-52">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.trendmicro.com/trendlabs-security-intelligence/redbaldknight-bronze-butler-daserf-backdoor-now-using-steganography/" name="scite-52" rel="nofollow" target="_blank">
        Chen, J. and Hsieh, M. (2017, November 7). REDBALDKNIGHT/BRONZE BUTLER’s Daserf Backdoor Now Using Steganography. Retrieved December 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-53">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-rancor-targeted-attacks-south-east-asia-using-plaintee-ddkong-malware-families/" name="scite-53" rel="nofollow" target="_blank">
        Ash, B., et al. (2018, June 26). RANCOR: Targeted Attacks in South East Asia Using PLAINTEE and DDKONG Malware Families. Retrieved July 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-54">
      <span class="scite-citation-text">
       <a class="external text" href="https://cdn2.hubspot.net/hubfs/3354902/Cybereason%20Labs%20Analysis%20Operation%20Cobalt%20Kitty.pdf" name="scite-54" rel="nofollow" target="_blank">
        Dahan, A. (2017). Operation Cobalt Kitty. Retrieved December 27, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-55">
      <span class="scite-citation-text">
       <a class="external text" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" name="scite-55" rel="nofollow" target="_blank">
        Windows Defender Advanced Threat Hunting Team. (2016, April 29). PLATINUM: Targeted attacks in South and Southeast Asia. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-56">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/10/unit42-nokki-almost-ties-the-knot-with-dogcall-reaper-group-uses-new-malware-to-deploy-rat/" name="scite-56" rel="nofollow" target="_blank">
        Grunzweig, J. (2018, October 01). NOKKI Almost Ties the Knot with DOGCALL: Reaper Group Uses New Malware to Deploy RAT. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-57">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part3.pdf" name="scite-57" rel="nofollow" target="_blank">
        ESET. (2016, October). En Route with Sednit - Part 3: A Mysterious Downloader. Retrieved November 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-58">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" name="scite-58" rel="nofollow" target="_blank">
        US-CERT. (2018, March 16). Alert (TA18-074A): Russian Government Cyber Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-59">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" name="scite-59" rel="nofollow" target="_blank">
        US-CERT. (2017, October 20). Alert (TA17-293A): Advanced Persistent Threat Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved November 2, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-60">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.clearskysec.com/wp-content/uploads/2016/01/Operation%20DustySky_TLP_WHITE.pdf" name="scite-60" rel="nofollow" target="_blank">
        ClearSky. (2016, January 7). Operation DustySky. Retrieved January 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-61">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/dyre-emerging-threat.pdf" name="scite-61" rel="nofollow" target="_blank">
        Symantec Security Response. (2015, June 23). Dyre: Emerging threat on financial fraud landscape. Retrieved August 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-62">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051515-3909-99" name="scite-62" rel="nofollow" target="_blank">
        Ladley, F. (2012, May 15). Backdoor.Ritsol. Retrieved February 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-63">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.accenture.com/t20180127T003755Z_w_/us-en/_acnmedia/PDF-46/Accenture-Security-Dragonfish-Threat-Analysis.pdf" name="scite-63" rel="nofollow" target="_blank">
        Accenture Security. (2018, January 27). DRAGONFISH DELIVERS NEW FORM OF ELISE MALWARE TARGETING ASEAN DEFENCE MINISTERS’ MEETING AND ASSOCIATES. Retrieved November 14, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-64">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2015/12/attack-on-french-diplomat-linked-to-operation-lotus-blossom/" name="scite-64" rel="nofollow" target="_blank">
        Falcone, R. and Miller-Osborn, J.. (2015, December 18). Attack on French Diplomat Linked to Operation Lotus Blossom. Retrieved February 15, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-65">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellEmpire/Empire" name="scite-65" rel="nofollow" target="_blank">
        Schroeder, W., Warner, J., Nelson, M. (n.d.). Github PowerShellEmpire. Retrieved April 28, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-66">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2018/10/11/new-telebots-backdoor-linking-industroyer-notpetya/" name="scite-66" rel="nofollow" target="_blank">
        Cherepanov, A., Lipovsky, R. (2018, October 11). New TeleBots backdoor: First evidence linking Industroyer to NotPetya. Retrieved November 27, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-67">
      <span class="scite-citation-text">
       <a class="external text" href="https://lolbas-project.github.io/lolbas/Binaries/Expand/" name="scite-67" rel="nofollow" target="_blank">
        LOLBAS. (n.d.). Expand.exe. Retrieved February 19, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-68">
      <span class="scite-citation-text">
       <a class="external text" href="https://blogs.forcepoint.com/security-labs/playing-cat-mouse-introducing-felismus-malware" name="scite-68" rel="nofollow" target="_blank">
        Somerville, L. and Toro, A. (2017, March 30). Playing Cat &amp; Mouse: Introducing the Felismus Malware. Retrieved November 16, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-69">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/07/microsoft-office-vulnerabilities-used-to-distribute-felixroot-backdoor.html" name="scite-69" rel="nofollow" target="_blank">
        Patil, S. (2018, June 26). Microsoft Office Vulnerabilities Used to Distribute FELIXROOT Backdoor in Recent Campaign. Retrieved July 31, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-70">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2018/10/ESET_GreyEnergy.pdf" name="scite-70" rel="nofollow" target="_blank">
        Cherepanov, A. (2018, October). GREYENERGY A successor to BlackEnergy. Retrieved November 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-71">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin10.pdf" name="scite-71" rel="nofollow" target="_blank">
        FireEye iSIGHT Intelligence. (2017, June 16). FIN10: Anatomy of a Cyber Extortion Operation. Retrieved June 25, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-72">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/04/fin7-phishing-lnk.html" name="scite-72" rel="nofollow" target="_blank">
        Carr, N., et al. (2017, April 24). FIN7 Evolution and the Phishing LNK. Retrieved April 24, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-73">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.justice.gov/opa/press-release/file/1084361/download" name="scite-73" rel="nofollow" target="_blank">
        Department of Justice. (2018, August 01). HOW FIN7 ATTACKED AND STOLE DATA. Retrieved August 24, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-74">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2016/05/windows-zero-day-payment-cards.html" name="scite-74" rel="nofollow" target="_blank">
        Kizhakkinan, D. et al.. (2016, May 11). Threat Actor Leverages Windows Zero-day Exploit in Payment Card Data Attacks. Retrieved February 12, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-75">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/02/unit-42-title-gamaredon-group-toolset-evolution/" name="scite-75" rel="nofollow" target="_blank">
        Kasza, A. and Reichel, D.. (2017, February 27). The Gamaredon Group Toolset Evolution. Retrieved March 1, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-76">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf" name="scite-76" rel="nofollow" target="_blank">
        ESET. (2017, August). Gazing at Gazer: Turla’s new second stage backdoor. Retrieved September 14, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-77">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/introducing-whitebear/81638/" name="scite-77" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research &amp; Analysis Team. (2017, August 30). Introducing WhiteBear. Retrieved September 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-78">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.nccgroup.trust/us/about-us/newsroom-and-events/blog/2018/april/decoding-network-data-from-a-gh0st-rat-variant/" name="scite-78" rel="nofollow" target="_blank">
        Pantazopoulos, N. (2018, April 17). Decoding network data from a Gh0st RAT variant. Retrieved November 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-79">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/gold-dragon-widens-olympics-malware-attacks-gains-permanent-presence-on-victims-systems/" name="scite-79" rel="nofollow" target="_blank">
        Sherstobitoff, R., Saavedra-Morales, J. (2018, February 02). Gold Dragon Widens Olympics Malware Attacks, Gains Permanent Presence on Victims’ Systems. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-80">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/08/unit42-gorgon-group-slithering-nation-state-cybercrime/" name="scite-80" rel="nofollow" target="_blank">
        Falcone, R., et al. (2018, August 02). The Gorgon Group: Slithering Between Nation State and Cybercrime. Retrieved August 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-81">
      <span class="scite-citation-text">
       <a class="external text" href="http://blogs.cisco.com/security/h1n1-technical-analysis-reveals-new-capabilities-part-2" name="scite-81" rel="nofollow" target="_blank">
        Reynolds, J.. (2016, September 14). H1N1: Technical analysis reveals new capabilities – part 2. Retrieved September 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-82">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/05/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/" name="scite-82" rel="nofollow" target="_blank">
        Falcone, R. and Lee, B.. (2016, May 26). The OilRig Campaign: Attacks on Saudi Arabian Organizations Deliver Helminth Backdoor. Retrieved May 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-83">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fidelissecurity.com/sites/default/files/FTA_1020_Fidelis_Inocnation_FINAL_0.pdf" name="scite-83" rel="nofollow" target="_blank">
        Fidelis Cybersecurity. (2015, December 16). Fidelis Threat Advisory #1020: Dissecting the Malware Involved in the INOCNATION Campaign. Retrieved March 24, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-84">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/analysis-reports/AR19-100A" name="scite-84" rel="nofollow" target="_blank">
        US-CERT. (2019, April 10). MAR-10135536-8 – North Korean Trojan: HOPLIGHT. Retrieved April 19, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-85">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage" name="scite-85" rel="nofollow" target="_blank">
        Dell SecureWorks Counter Threat Unit Threat Intelligence. (2015, August 5). Threat Group-3390 Targets Organizations for Cyberespionage. Retrieved August 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-86">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/connect/blogs/trojanhydraq-incident" name="scite-86" rel="nofollow" target="_blank">
        Symantec Security Response. (2010, January 18). The Trojan.Hydraq Incident. Retrieved February 20, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-87">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2010-011114-1830-99" name="scite-87" rel="nofollow" target="_blank">
        Lelli, A. (2010, January 11). Trojan.Hydraq. Retrieved February 20, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-88">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2018/06/07/invisimole-equipped-spyware-undercover/" name="scite-88" rel="nofollow" target="_blank">
        Hromcová, Z. (2018, June 07). InvisiMole: Surprisingly equipped spyware, undercover since 2013. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-89">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part1.pdf" name="scite-89" rel="nofollow" target="_blank">
        ESET. (2016, October). En Route with Sednit - Part 1: Approaching the Target. Retrieved November 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-90">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/02/unit42-sofacy-attacks-multiple-government-entities/" name="scite-90" rel="nofollow" target="_blank">
        Lee, B, et al. (2018, February 28). Sofacy Attacks Multiple Government Entities. Retrieved March 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-91">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2017/10/cyber-conflict-decoy-document.html" name="scite-91" rel="nofollow" target="_blank">
        Mercer, W., et al. (2017, October 22). "Cyber Conflict" Decoy Document Used in Real Cyber Conflict. Retrieved November 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-92">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/jrat-new-anti-parsing-techniques" name="scite-92" rel="nofollow" target="_blank">
        Sharma, R. (2018, August 15). Revamped jRAT Uses New Anti-Parsing Techniques. Retrieved September 21, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="93.0">
    <li>
     <span class="scite-citation" id="scite-93">
      <span class="scite-citation-text">
       <a class="external text" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07195002/KL_AdwindPublicReport_2016.pdf" name="scite-93" rel="nofollow" target="_blank">
        Kamluk, V. &amp; Gostev, A. (2016, February). Adwind - A Cross-Platform RAT. Retrieved April 23, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-94">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/connect/blogs/cross-platform-frutas-rat-builder-and-back-door" name="scite-94" rel="nofollow" target="_blank">
        Bingham, J. (2013, February 11). Cross-Platform Frutas RAT Builder and Back Door. Retrieved April 23, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-95">
      <span class="scite-citation-text">
       <a class="external text" href="http://research.zscaler.com/2016/01/malicious-office-files-dropping-kasidet.html" name="scite-95" rel="nofollow" target="_blank">
        Yadav, A., et al. (2016, January 29). Malicious Office files dropping Kasidet and Dridex. Retrieved March 24, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-96">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/05/unit42-kazuar-multiplatform-espionage-backdoor-api-access/" name="scite-96" rel="nofollow" target="_blank">
        Levene, B, et al. (2017, May 03). Kazuar: Multiplatform Espionage Backdoor with API Access. Retrieved July 17, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-97">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-221A" name="scite-97" rel="nofollow" target="_blank">
        US-CERT. (2018, August 09). MAR-10135536-17 – North Korean Trojan: KEYMARBLE. Retrieved August 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-98">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/zerosum0x0/koadic" name="scite-98" rel="nofollow" target="_blank">
        Magius, J., et al. (2017, July 19). Koadic. Retrieved June 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-99">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2017/05/konni-malware-under-radar-for-years.html" name="scite-99" rel="nofollow" target="_blank">
        Rascagneres, P. (2017, May 03). KONNI: A Malware Under The Radar For Years. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-100">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security-center/writeup/2016-081923-2700-99" name="scite-100" rel="nofollow" target="_blank">
        Moench, B. and Aboud, E. (2016, August 23). Trojan.Kwampirs. Retrieved May 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-101">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" name="scite-101" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Unraveling the Long Thread of the Sony Attack. Retrieved February 25, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-102">
      <span class="scite-citation-text">
       <a class="external text" href="https://operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Destructive-Malware-Report.pdf" name="scite-102" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Destructive Malware Report. Retrieved March 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-103">
      <span class="scite-citation-text">
       <a class="external text" href="https://operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Loaders-Installers-and-Uninstallers-Report.pdf" name="scite-103" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Loaders, Installers and Uninstallers Report. Retrieved March 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-104">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" name="scite-104" rel="nofollow" target="_blank">
        Axel F, Pierre T. (2017, October 16). Leviathan: Espionage actor spearphishes maritime and defense targets. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-105">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051605-2535-99" name="scite-105" rel="nofollow" target="_blank">
        Zhou, R. (2012, May 15). Backdoor.Linfo. Retrieved February 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-106">
      <span class="scite-citation-text">
       <a class="external text" href="https://unit42.paloaltonetworks.com/born-this-way-origins-of-lockergoga/" name="scite-106" rel="nofollow" target="_blank">
        Harbison, M.. (2019, March 26). Born This Way? Origins of LockerGoga. Retrieved April 16, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-107">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2015/11/china-based-threat.html" name="scite-107" rel="nofollow" target="_blank">
        FireEye Threat Intelligence. (2015, December 1). China-based Cyber Threat Group Uses Dropbox for Malware Communications and Targets Hong Kong Media Outlets. Retrieved December 4, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-108">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/02/unit42-magic-hound-campaign-attacks-saudi-targets/" name="scite-108" rel="nofollow" target="_blank">
        Lee, B. and Falcone, R. (2017, February 15). Magic Hound Campaign Attacks Saudi Targets. Retrieved December 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-109">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-report-final-v4.pdf" name="scite-109" rel="nofollow" target="_blank">
        PwC and BAE Systems. (2017, April). Operation Cloud Hopper. Retrieved April 5, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-110">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.justice.gov/opa/press-release/file/1121706/download" name="scite-110" rel="nofollow" target="_blank">
        United States District Court Southern District of New York (USDC SDNY) . (2018, December 17). United States of America v. Zhu Hua and Zhang Shilong. Retrieved April 17, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-111">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2017/06/palestine-delphi.html" name="scite-111" rel="nofollow" target="_blank">
        Rascagneres, P., Mercer, W. (2017, June 19). Delphi Used To Score Against Palestine. Retrieved November 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-112">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.radware.com/security/2018/07/micropsia-malware/" name="scite-112" rel="nofollow" target="_blank">
        Tsarfaty, Y. (2018, July 25). Micropsia Malware. Retrieved November 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-113">
      <span class="scite-citation-text">
       <a class="external text" href="https://cdn.securelist.com/files/2014/07/themysteryofthepdf0-dayassemblermicrobackdoor.pdf" name="scite-113" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research &amp; Analysis Team. (2013, February 27). The MiniDuke Mystery: PDF 0-day Government Spy Assembler 0x29A Micro Backdoor. Retrieved April 5, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-114">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cylance.com/content/dam/cylance/pdfs/reports/Op_Dust_Storm_Report.pdf" name="scite-114" rel="nofollow" target="_blank">
        Gross, J. (2016, February 23). Operation Dust Storm. Retrieved September 19, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-115">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/security_response/writeup.jsp?docid=2015-020623-0740-99&amp;tabid=2" name="scite-115" rel="nofollow" target="_blank">
        Stama, D.. (2015, February 6). Backdoor.Mivast. Retrieved February 15, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-116">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/07/multiple-cobalt-personality-disorder.html" name="scite-116" rel="nofollow" target="_blank">
        Svajcer, V. (2018, July 31). Multiple Cobalt Personality Disorder. Retrieved September 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-117">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2018/01/ESET_Turla_Mosquito.pdf" name="scite-117" rel="nofollow" target="_blank">
        ESET, et al. (2018, January). Diplomats in Eastern Europe bitten by a Turla mosquito. Retrieved July 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-118">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/muddywater/88059/" name="scite-118" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research &amp; Analysis Team. (2018, October 10). MuddyWater expands operations. Retrieved November 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-119">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.clearskysec.com/wp-content/uploads/2018/11/MuddyWater-Operations-in-Lebanon-and-Oman.pdf" name="scite-119" rel="nofollow" target="_blank">
        ClearSky Cyber Security. (2018, November). MuddyWater Operations in Lebanon and Oman: Using an Israeli compromised domain for a two-stage campaign. Retrieved November 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-120">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.digitrustgroup.com/nanocore-not-your-average-rat/" name="scite-120" rel="nofollow" target="_blank">
        The DigiTrust Group. (2017, January 01). NanoCore Is Not Your Average RAT. Retrieved November 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-121">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2016/02/nanocorerat-behind-an-increase-in-tax-themed-phishing-e-mails/" name="scite-121" rel="nofollow" target="_blank">
        Kasza, A., Halfpop, T. (2016, February 09). NanoCoreRAT Behind an Increase in Tax-Themed Phishing E-mails. Retrieved November 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-122">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/05/navrat.html" name="scite-122" rel="nofollow" target="_blank">
        Mercer, W., Rascagneres, P. (2018, May 31). NavRAT Uses US-North Korea Summit As Decoy For Attacks In South Korea. Retrieved June 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-123">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2015-120123-5521-99" name="scite-123" rel="nofollow" target="_blank">
        Sponchioni, R.. (2016, March 11). Backdoor.Nidiran. Retrieved August 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-124">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/09/unit42-new-konni-malware-attacking-eurasia-southeast-asia/" name="scite-124" rel="nofollow" target="_blank">
        Grunzweig, J., Lee, B. (2018, September 27). New KONNI Malware attacking Eurasia and Southeast Asia. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-125">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/octopus-infested-seas-of-central-asia/88200/" name="scite-125" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research &amp; Analysis Team. (2018, October 15). Octopus-infested seas of Central Asia. Retrieved November 14, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-126">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/12/targeted-attack-in-middle-east-by-apt34.html" name="scite-126" rel="nofollow" target="_blank">
        Sardiwal, M, et al. (2017, December 7). New Targeted Attack in the Middle East by APT34, a Suspected Iranian Threat Group, Using CVE-2017-11882 Exploit. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-127">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/02/olympic-destroyer.html" name="scite-127" rel="nofollow" target="_blank">
        Mercer, W. and Rascagneres, P. (2018, February 12). Olympic Destroyer Takes Aim At Winter Olympics. Retrieved March 14, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-128">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/02/unit42-oopsie-oilrig-uses-threedollars-deliver-new-trojan/" name="scite-128" rel="nofollow" target="_blank">
        Lee, B., Falcone, R. (2018, February 23). OopsIE! OilRig Uses ThreeDollars to Deliver New Trojan. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-129">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/09/unit42-oilrig-targets-middle-eastern-government-adds-evasion-techniques-oopsie/" name="scite-129" rel="nofollow" target="_blank">
        Falcone, R., et al. (2018, September 04). OilRig Targets a Middle Eastern Government and Adds Evasion Techniques to OopsIE. Retrieved September 24, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-130">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/new-macos-backdoor-linked-to-oceanlotus-found/" name="scite-130" rel="nofollow" target="_blank">
        Horejsi, J. (2018, April 04). New MacOS Backdoor Linked to OceanLotus Found. Retrieved November 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-131">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-050412-4128-99" name="scite-131" rel="nofollow" target="_blank">
        Mullaney, C. &amp; Honda, H. (2012, May 4). Trojan.Pasam. Retrieved February 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-132">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/the-dropping-elephant-actor/75328/" name="scite-132" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research &amp; Analysis Team. (2016, July 8). The Dropping Elephant – aggressive cyber-espionage in the Asian region. Retrieved August 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-133">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/05/unit42-new-wekby-attacks-use-dns-requests-as-command-and-control-mechanism/" name="scite-133" rel="nofollow" target="_blank">
        Grunzweig, J., et al. (2016, May 24). New Wekby Attacks Use DNS Requests As Command and Control Mechanism. Retrieved August 17, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-134">
      <span class="scite-citation-text">
       <a class="external text" href="http://circl.lu/assets/files/tr-12/tr-12-circl-plugx-analysis-v1.pdf" name="scite-134" rel="nofollow" target="_blank">
        Computer Incident Response Center Luxembourg. (2013, March 29). Analysis of a PlugX variant. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-135">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2005-081910-3934-99" name="scite-135" rel="nofollow" target="_blank">
        Hayashi, K. (2005, August 18). Backdoor.Darkmoon. Retrieved February 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-136">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/03/dissecting_one_ofap.html" name="scite-136" rel="nofollow" target="_blank">
        Dunwoody, M.. (2017, April 3). Dissecting One of APT29’s Fileless WMI and PowerShell Backdoors (POSHSPY). Retrieved April 5, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-137">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.volexity.com/blog/2016/11/09/powerduke-post-election-spear-phishing-campaigns-targeting-think-tanks-and-ngos/" name="scite-137" rel="nofollow" target="_blank">
        Adair, S.. (2016, November 9). PowerDuke: Widespread Post-Election Spear Phishing Campaigns Targeting Think Tanks and NGOs. Retrieved January 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-138">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/03/fin7_spear_phishing.html" name="scite-138" rel="nofollow" target="_blank">
        Miller, S., et al. (2017, March 7). FIN7 Spear Phishing Campaign Targets Personnel Involved in SEC Filings. Retrieved March 8, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-139">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html" name="scite-139" rel="nofollow" target="_blank">
        Singh, S. et al.. (2018, March 13). Iranian Threat Group Updates Tactics, Techniques and Procedures in Spear Phishing Campaign. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-140">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" name="scite-140" rel="nofollow" target="_blank">
        Elovitz, S. &amp; Ahl, I. (2016, August 18). Know Your Enemy:  New Financially-Motivated &amp; Spear-Phishing Group. Retrieved February 26, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-141">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/n1nj4sec/pupy" name="scite-141" rel="nofollow" target="_blank">
        Nicolas Verdier. (n.d.). Retrieved January 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-142">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/quasar/QuasarRAT" name="scite-142" rel="nofollow" target="_blank">
        MaxXor. (n.d.). QuasarRAT. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-143">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/" name="scite-143" rel="nofollow" target="_blank">
        Meltzer, M, et al. (2018, June 07). Patchwork APT Group Targets US Think Tanks. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-144">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.trendmicro.com/trendlabs-security-intelligence/rarstone-found-in-targeted-attacks/" name="scite-144" rel="nofollow" target="_blank">
        Aquino, M. (2013, June 13). RARSTONE Found In Targeted Attacks. Retrieved December 17, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-145">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/lazarus-campaign-targeting-cryptocurrencies-reveals-remote-controller-tool-evolved-ratankba/" name="scite-145" rel="nofollow" target="_blank">
        Lei, C., et al. (2018, January 24). Lazarus Campaign Targeting Cryptocurrencies Reveals Remote Controller Tool, an Evolved RATANKBA, and More. Retrieved May 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-146">
      <span class="scite-citation-text">
       Trend Micro. (2017, February 27). RATANKBA: Delving into Large-scale Watering Holes against Enterprises. Retrieved May 22, 2018.
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-147">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" name="scite-147" rel="nofollow" target="_blank">
        PwC and BAE Systems. (2017, April). Operation Cloud Hopper: Technical Annex. Retrieved April 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-148">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.riskiq.com/blog/labs/spear-phishing-turkish-defense-contractors/" name="scite-148" rel="nofollow" target="_blank">
        Klijnsma, Y. (2018, January 23). Espionage Campaign Leverages Spear Phishing, RATs Against Turkish Defense Contractors. Retrieved November 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-149">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/connect/blogs/buckeye-cyberespionage-group-shifts-gaze-us-hong-kong" name="scite-149" rel="nofollow" target="_blank">
        Symantec Security Response. (2016, September 6). Buckeye cyberespionage group shifts gaze from US to Hong Kong. Retrieved September 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-150">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/Symantec_Remsec_IOCs.pdf" name="scite-150" rel="nofollow" target="_blank">
        Symantec Security Response. (2016, August 8). Backdoor.Remsec indicators of compromise. Retrieved August 17, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-151">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/files/2016/07/The-ProjectSauron-APT_Technical_Analysis_KL.pdf" name="scite-151" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research &amp; Analysis Team. (2016, August 9). The ProjectSauron APT. Technical Analysis. Retrieved August 17, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-152">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/01/unit42-oilrig-uses-rgdoor-iis-backdoor-targets-middle-east/" name="scite-152" rel="nofollow" target="_blank">
        Falcone, R. (2018, January 25). OilRig uses RGDoor IIS Backdoor on Targets in the Middle East. Retrieved July 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-153">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-new-threat-actor-group-darkhydrus-targets-middle-east-government/" name="scite-153" rel="nofollow" target="_blank">
        Falcone, R., et al. (2018, July 27). New Threat Actor Group DarkHydrus Targets Middle East Government. Retrieved August 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-154">
      <span class="scite-citation-text">
       <a class="external text" href="https://unit42.paloaltonetworks.com/darkhydrus-delivers-new-trojan-that-can-use-google-drive-for-c2-communications/" name="scite-154" rel="nofollow" target="_blank">
        Lee, B., Falcone, R. (2019, January 18). DarkHydrus delivers new Trojan that can use Google Drive for C2 communications. Retrieved April 17, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-155">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2017/04/introducing-rokrat.html" name="scite-155" rel="nofollow" target="_blank">
        Mercer, W., Rascagneres, P. (2017, April 03). Introducing ROKRAT. Retrieved May 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-156">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2017/02/Read-The-Manual.pdf" name="scite-156" rel="nofollow" target="_blank">
        Faou, M. and Boutin, J.. (2017, February). Read The Manual: A Guide to the RTM Banking Trojan. Retrieved March 9, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-157">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.secureworks.com/cyber-threat-intelligence/threats/sakula-malware-family/" name="scite-157" rel="nofollow" target="_blank">
        Dell SecureWorks Counter Threat Unit Threat Intelligence. (2015, July 30). Sakula Malware Family. Retrieved January 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-158">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2015/07/unit-42-technical-analysis-seaduke/" name="scite-158" rel="nofollow" target="_blank">
        Grunzweig, J.. (2015, July 14). Unit 42 Technical Analysis: Seaduke. Retrieved August 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-159">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.brighttalk.com/webcast/10703/296317/apt34-new-targeted-attack-in-the-middle-east" name="scite-159" rel="nofollow" target="_blank">
        Davis, S. and Caban, D. (2017, December 19). APT34 - New Targeted Attack in the Middle East. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-160">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/11/unit42-shamoon-2-return-disttrack-wiper/" name="scite-160" rel="nofollow" target="_blank">
        Falcone, R.. (2016, November 30). Shamoon 2: Return of the Disttrack Wiper. Retrieved January 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-161">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.malwarebytes.com/threat-analysis/2016/08/smoke-loader-downloader-with-a-smokescreen-still-alive/" name="scite-161" rel="nofollow" target="_blank">
        Hasherezade. (2016, September 12). Smoke Loader – downloader with a smokescreen still alive. Retrieved March 20, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-162">
      <span class="scite-citation-text">
       <a class="external text" href="https://research.checkpoint.com/speakup-a-new-undetected-backdoor-linux-trojan/" name="scite-162" rel="nofollow" target="_blank">
        Check Point Research. (2019, February 4). SpeakUp: A New Undetected Backdoor Linux Trojan. Retrieved April 17, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-163">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.clearskysec.com/wp-content/uploads/2017/07/Operation_Wilted_Tulip.pdf" name="scite-163" rel="nofollow" target="_blank">
        ClearSky Cyber Security and Trend Micro. (2017, July). Operation Wilted Tulip: Exposing a cyber espionage apparatus. Retrieved August 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-164">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.trendmicro.com/vinfo/us/threat-encyclopedia/malware/tspy_trickload.n" name="scite-164" rel="nofollow" target="_blank">
        Antazo, F. (2016, October 31). TSPY_TRICKLOAD.N. Retrieved September 14, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-165">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/Dragonfly_Threat_Against_Western_Energy_Suppliers.pdf" name="scite-165" rel="nofollow" target="_blank">
        Symantec Security Response. (2014, July 7). Dragonfly: Cyberespionage Attacks Against Energy Suppliers. Retrieved April 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-166">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2018/05/22/turla-mosquito-shift-towards-generic-tools/" name="scite-166" rel="nofollow" target="_blank">
        ESET Research. (2018, May 22). Turla Mosquito: A shift towards more generic tools. Retrieved July 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-167">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/09/apt33-insights-into-iranian-cyber-espionage.html" name="scite-167" rel="nofollow" target="_blank">
        O'Leary, J., et al. (2017, September 20). Insights into Iranian Cyber Espionage: APT33 Targets Aerospace and Energy Sectors and has Ties to Destructive Malware. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-168">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-165A" name="scite-168" rel="nofollow" target="_blank">
        US-CERT. (2018, June 14). MAR-10135536-12 – North Korean Trojan: TYPEFRAME. Retrieved July 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-169">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-uboatrat-navigates-east-asia/" name="scite-169" rel="nofollow" target="_blank">
        Hayashi, K. (2017, November 28). UBoatRAT Navigates East Asia. Retrieved January 12, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-170">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/09/apt10-targeting-japanese-corporations-using-updated-ttps.html" name="scite-170" rel="nofollow" target="_blank">
        Matsuda, A., Muhammad I. (2018, September 13). APT10 Targeting Japanese Corporations Using Updated TTPs. Retrieved September 17, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-171">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051606-5938-99" name="scite-171" rel="nofollow" target="_blank">
        Zhou, R. (2012, May 15). Backdoor.Vasport. Retrieved February 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-172">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/01/unit42-vermin-quasar-rat-custom-malware-used-ukraine/" name="scite-172" rel="nofollow" target="_blank">
        Lancaster, T., Cortes, J. (2018, January 29). VERMIN: Quasar RAT and Custom Malware Used In Ukraine. Retrieved July 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-173">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA17-318B" name="scite-173" rel="nofollow" target="_blank">
        US-CERT. (2017, November 22). Alert (TA17-318B): HIDDEN COBRA – North Korean Trojan: Volgmer. Retrieved December 7, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-174">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-D_WHITE_S508C.PDF" name="scite-174" rel="nofollow" target="_blank">
        US-CERT. (2017, November 01). Malware Analysis Report (MAR) - 10135536-D. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-175">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security-center/writeup/2014-081811-3237-99?tabid=2" name="scite-175" rel="nofollow" target="_blank">
        Yagi, J. (2014, August 24). Trojan.Volgmer. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-176">
      <span class="scite-citation-text">
       <a class="external text" href="https://logrhythm.com/blog/a-technical-analysis-of-wannacry-ransomware/" name="scite-176" rel="nofollow" target="_blank">
        Noerenberg, E., Costis, A., and Quist, N. (2017, May 16). A Technical Analysis of WannaCry Ransomware. Retrieved March 25, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-177">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf" name="scite-177" rel="nofollow" target="_blank">
        Mandiant. (n.d.). APT1 Exposing One of China’s Cyber Espionage Units. Retrieved July 18, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-178">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051606-1005-99" name="scite-178" rel="nofollow" target="_blank">
        Zhou, R. (2012, May 15). Backdoor.Wiarp. Retrieved February 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-179">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/09/unit42-xbash-combines-botnet-ransomware-coinmining-worm-targets-linux-windows/" name="scite-179" rel="nofollow" target="_blank">
        Xiao, C. (2018, September 17). Xbash Combines Botnet, Ransomware, Coinmining in Worm that Targets Linux and Windows. Retrieved November 14, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-180">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.invincea.com/2016/07/tunnel-of-gov-dnc-hack-and-the-russian-xtunnel/" name="scite-180" rel="nofollow" target="_blank">
        Belcher, P.. (2016, July 28). Tunnel of Gov: DNC Hack and the Russian XTunnel. Retrieved August 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-181">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-sofacy-groups-parallel-attacks/" name="scite-181" rel="nofollow" target="_blank">
        Lee, B., Falcone, R. (2018, June 06). Sofacy Group’s Parallel Attacks. Retrieved June 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-182">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/us/threat-insight/post/APT-targets-russia-belarus-zerot-plugx" name="scite-182" rel="nofollow" target="_blank">
        Huss, D., et al. (2017, February 2). Oops, they did it again: APT Targets Russia and Belarus with ZeroT and PlugX. Retrieved April 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-183">
      <span class="scite-citation-text">
       <a class="external text" href="https://cyberwtf.files.wordpress.com/2017/07/panda-whitepaper.pdf" name="scite-183" rel="nofollow" target="_blank">
        Ebach, L. (2017, June 22). Analysis Results of Zeus.Variant.Panda. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-184">
      <span class="scite-citation-text">
       <a class="external text" href="https://arxiv.org/ftp/arxiv/papers/1408/1408.1136.pdf" name="scite-184" rel="nofollow" target="_blank">
        Gardiner, J.,  Cova, M., Nagaraja, S. (2014, February). Command &amp; Control Understanding, Denying and Detecting. Retrieved April 20, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
