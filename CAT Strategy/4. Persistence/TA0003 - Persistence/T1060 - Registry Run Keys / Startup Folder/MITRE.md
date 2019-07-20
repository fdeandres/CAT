<div class="container-fluid">
 <h1>
  Registry Run Keys / Startup Folder
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adding an entry to the "run keys" in the Registry or startup folder will cause the program referenced to be executed when a user logs in.
    <span class="scite-citeref-number" data-reference="Microsoft Run Key" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://msdn.microsoft.com/en-us/library/aa376977" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    These programs will be executed under the context of the user and will have the account's associated permissions level.
   </p>
   <p>
    The following run keys are created by default on Windows systems:
    <em>
     <code>
      HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run
     </code>
    </em>
    <code>
     HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\RunOnce
    </code>
    <em>
     <code>
      HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run
     </code>
    </em>
    <code>
     HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\RunOnce
    </code>
   </p>
   <p>
    The
    <code>
     HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\RunOnceEx
    </code>
    is also available but is not created by default on Windows Vista and newer. Registry run key entries can reference programs directly or list them as a dependency.
    <span class="scite-citeref-number" data-reference="Microsoft RunOnceEx APR 2018" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://support.microsoft.com/help/310593/description-of-the-runonceex-registry-key" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    For example, it is possible to load a DLL at logon using a "Depend" key with RunOnceEx:
    <code>
     reg add HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\RunOnceEx\0001\Depend /v 1 /d "C:\temp\evil[.]dll"
    </code>
    <span class="scite-citeref-number" data-reference="Oddvar Moe RunOnceEx Mar 2018" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://oddvar.moe/2018/03/21/persistence-using-runonceex-hidden-from-autoruns-exe/" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    The following Registry keys can be used to set startup folder items for persistence:
    <em>
     <code>
      HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders
     </code>
    </em>
    <code>
     HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Shell Folders
    </code>
    <em>
     <code>
      HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Shell Folders
     </code>
    </em>
    <code>
     HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders
    </code>
   </p>
   <p>
    Adversaries can use these configuration locations to execute malware, such as remote access tools, to maintain persistence through system reboots. Adversaries may also use
    <a href="https://attack.mitre.org/techniques/T1036">
     Masquerading
    </a>
    to make the Registry entries look as if they are associated with legitimate programs.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1060
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
       System Requirements:
      </span>
      HKEY_LOCAL_MACHINE keys require administrator access to create and modify
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
      Windows Registry, File monitoring
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
      <a href="https://capec.mitre.org/data/definitions/270.html" target="_blank">
       CAPEC-270
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
      Oddvar Moe, @oddvarmoe
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
     <a href="https://attack.mitre.org/software/S0045">
      ADVSTORESHELL
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0045">
       ADVSTORESHELL
      </a>
      achieves persistence by adding itself to the
      <code>
       HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
      </code>
      Registry key.
      <span class="scite-citeref-number" data-reference="Kaspersky Sofacy" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://securelist.com/sofacy-apt-hits-high-profile-targets-with-updated-toolset/72924/" target="_blank">
         [4]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="ESET Sednit Part 2" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part-2.pdf" target="_blank">
         [5]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Bitdefender APT28 Dec 2015" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://download.bitdefender.com/resources/media/materials/white-papers/en/Bitdefender_In-depth_analysis_of_APT28%E2%80%93The_Political_Cyber-Espionage.pdf" target="_blank">
         [6]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
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
      adds itself to the Registry as a startup program to establish persistence.
      <span class="scite-citeref-number" data-reference="Fortinet Agent Tesla April 2018" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.fortinet.com/blog/threat-research/analysis-of-new-agent-tesla-spyware-variant.html" target="_blank">
         [7]
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
      establishes persistence via the
      <code>
       HKCU\Software\Microsoft\Windows\CurrentVersion\Run
      </code>
      key.
      <span class="scite-citeref-number" data-reference="Anomali Evasive Maneuvers July 2015" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.anomali.com/blog/evasive-maneuvers-the-wekby-group-attempts-to-evade-analysis-via-custom-rop" target="_blank">
         [8]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PaloAlto DNS Requests May 2016" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://researchcenter.paloaltonetworks.com/2016/05/unit42-new-wekby-attacks-use-dns-requests-as-command-and-control-mechanism/" target="_blank">
         [9]
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
      An
      <a href="https://attack.mitre.org/groups/G0073">
       APT19
      </a>
      HTTP malware variant establishes persistence by setting the Registry key
      <code>
       HKCU\Software\Microsoft\Windows\CurrentVersion\Run\Windows Debug Tools-%LOCALAPPDATA%\
      </code>
      .
      <span class="scite-citeref-number" data-reference="Unit 42 C0d0so0 Jan 2016" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://researchcenter.paloaltonetworks.com/2016/01/new-attacks-linked-to-c0d0s0-group/" target="_blank">
         [10]
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
      added Registry Run keys to establish persistence.
      <span class="scite-citeref-number" data-reference="Mandiant No Easy Breach" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="http://www.slideshare.net/MatthewDunwoody1/no-easy-breach-derby-con-2016" target="_blank">
         [11]
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
      places scripts in the startup folder for persistence.
      <span class="scite-citeref-number" data-reference="FireEye Operation Double Tap" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://www.fireeye.com/blog/threat-research/2014/11/operation_doubletap.html" target="_blank">
         [12]
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
      established persistence using Registry Run keys, both to execute PowerShell and VBS scripts as well as to execute their backdoor directly.
      <span class="scite-citeref-number" data-reference="Cybereason Oceanlotus May 2017" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://www.cybereason.com/blog/operation-cobalt-kitty-apt" target="_blank">
         [13]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Cybereason Cobalt Kitty 2017" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://cdn2.hubspot.net/hubfs/3354902/Cybereason%20Labs%20Analysis%20Operation%20Cobalt%20Kitty.pdf" target="_blank">
         [14]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="ESET OceanLotus Mar 2019" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://www.welivesecurity.com/2019/03/20/fake-or-fake-keeping-up-with-oceanlotus-decoys/" target="_blank">
         [15]
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
      has deployed a tool known as DarkComet to the Startup folder of a victim.
      <span class="scite-citeref-number" data-reference="Symantec Elfin Mar 2019" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="https://www.symantec.com/blogs/threat-intelligence/elfin-apt33-espionage" target="_blank">
         [16]
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
      's has added persistence via the Registry key
      <code>
       HKCU\Software\Microsoft\CurrentVersion\Run\
      </code>
      .
      <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
         [17]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Talos Group123" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="https://blog.talosintelligence.com/2018/01/korea-in-crosshairs.html" target="_blank">
         [18]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0087">
      APT39
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0087">
       APT39
      </a>
      has maintained persistence using the startup folder.
      <span class="scite-citeref-number" data-reference="FireEye APT39 Jan 2019" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="https://www.fireeye.com/blog/threat-research/2019/01/apt39-iranian-cyber-espionage-group-focused-on-personal-information.html" target="_blank">
         [19]
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
      creates a startup item for persistence.
      <span class="scite-citeref-number" data-reference="Cofense Astaroth Sept 2018" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://cofense.com/seeing-resurgence-demonic-astaroth-wmic-trojan/" target="_blank">
         [20]
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
      adds Registry Run keys to achieve persistence.
      <span class="scite-citeref-number" data-reference="Symantec Dragonfly" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/Dragonfly_Threat_Against_Western_Energy_Suppliers.pdf" target="_blank">
         [21]
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
      <a href="https://attack.mitre.org/software/S0031">
       BACKSPACE
      </a>
      achieves persistence by creating a shortcut to itself in the CSIDL_STARTUP directory.
      <span class="scite-citeref-number" data-reference="FireEye APT30" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="https://www2.fireeye.com/rs/fireye/images/rpt-apt30.pdf" target="_blank">
         [22]
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
      installs a registry Run key to establish persistence.
      <span class="scite-citeref-number" data-reference="Forcepoint Monsoon" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" target="_blank">
         [23]
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
      establishes a foothold by adding a link to the malware executable in the startup folder.
      <span class="scite-citeref-number" data-reference="Unit 42 BadPatch Oct 2017" id="scite-ref-24-a" onclick="scrollToRef('scite-24')">
       <sup>
        <a aria-describedby="qtip-23" data-hasqtip="23" href="https://researchcenter.paloaltonetworks.com/2017/10/unit42-badpatch/" target="_blank">
         [24]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0127">
      BBSRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0127">
       BBSRAT
      </a>
      has been loaded through DLL side-loading of a legitimate Citrix executable that is set to persist through the Registry Run key location
      <code>
       HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run\ssonsvr.exe
      </code>
      .
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
      adds itself to the Registry key
      <code>
       HKEY_CURRENT_USER\Software\Microsoft\CurrentVersion\Run\
      </code>
      for persistence.
      <span class="scite-citeref-number" data-reference="Unit 42 Bisonal July 2018" id="scite-ref-25-a" onclick="scrollToRef('scite-25')">
       <sup>
        <a aria-describedby="qtip-24" data-hasqtip="24" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-bisonal-malware-used-attacks-russia-south-korea/" target="_blank">
         [25]
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
      The
      <a href="https://attack.mitre.org/software/S0089">
       BlackEnergy
      </a>
      3 variant drops its main DLL component and then creates a .lnk shortcut to that file in the startup folder.
      <span class="scite-citeref-number" data-reference="F-Secure BlackEnergy 2014" id="scite-ref-26-a" onclick="scrollToRef('scite-26')">
       <sup>
        <a aria-describedby="qtip-25" data-hasqtip="25" href="https://www.f-secure.com/documents/996508/1030745/blackenergy_whitepaper.pdf" target="_blank">
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
      creates run key Registry entries pointing to malicious DLLs dropped to disk.
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
      has used a batch script that adds a Registry Run key to establish malware persistence.
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
     <a href="https://attack.mitre.org/software/S0030">
      Carbanak
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0030">
       Carbanak
      </a>
      stores a configuration files in the startup directory to automatically execute commands in order to persist across reboots.
      <span class="scite-citeref-number" data-reference="FireEye CARBANAK June 2017" id="scite-ref-29-a" onclick="scrollToRef('scite-29')">
       <sup>
        <a aria-describedby="qtip-28" data-hasqtip="28" href="https://www.fireeye.com/blog/threat-research/2017/06/behind-the-carbanak-backdoor.html" target="_blank">
         [29]
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
      } establishes Persistence by setting the
      <code>
       HKCU\Software\Microsoft\Windows NT\CurrentVersion\Windows\Load
      </code>
      Registry key to point to its executable.
      <span class="scite-citeref-number" data-reference="PaloAlto CardinalRat Apr 2017" id="scite-ref-30-a" onclick="scrollToRef('scite-30')">
       <sup>
        <a aria-describedby="qtip-29" data-hasqtip="29" href="https://researchcenter.paloaltonetworks.com/2017/04/unit42-cardinal-rat-active-two-years/" target="_blank">
         [30]
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
      establishes persistence by adding a Registry Run key.
      <span class="scite-citeref-number" data-reference="PWC Cloud Hopper Technical Annex April 2017" id="scite-ref-31-a" onclick="scrollToRef('scite-31')">
       <sup>
        <a aria-describedby="qtip-30" data-hasqtip="30" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" target="_blank">
         [31]
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
      has used Registry Run keys for persistence. The group has also set a Startup path to launch the PowerShell shell command and download Cobalt Strike.
      <span class="scite-citeref-number" data-reference="Group IB Cobalt Aug 2017" id="scite-ref-32-a" onclick="scrollToRef('scite-32')">
       <sup>
        <a aria-describedby="qtip-31" data-hasqtip="31" href="https://www.group-ib.com/blog/cobalt" target="_blank">
         [32]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0338">
      Cobian RAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0338">
       Cobian RAT
      </a>
      creates an autostart Registry key to ensure persistence.
      <span class="scite-citeref-number" data-reference="Zscaler Cobian Aug 2017" id="scite-ref-33-a" onclick="scrollToRef('scite-33')">
       <sup>
        <a aria-describedby="qtip-32" data-hasqtip="32" href="https://www.zscaler.com/blogs/research/cobian-rat-backdoored-rat" target="_blank">
         [33]
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
      achieves persistence by adding a shortcut of itself to the startup path in the Registry.
      <span class="scite-citeref-number" data-reference="Palo Alto Comnie" id="scite-ref-34-a" onclick="scrollToRef('scite-34')">
       <sup>
        <a aria-describedby="qtip-33" data-hasqtip="33" href="https://researchcenter.paloaltonetworks.com/2018/01/unit42-comnie-continues-target-organizations-east-asia/" target="_blank">
         [34]
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
      has established persistence by creating autostart extensibility point (ASEP) Registry entries in the Run key and other Registry keys, as well as by creating shortcuts in the Internet Explorer Quick Start folder.
      <span class="scite-citeref-number" data-reference="Microsoft SIR Vol 19" id="scite-ref-35-a" onclick="scrollToRef('scite-35')">
       <sup>
        <a aria-describedby="qtip-34" data-hasqtip="34" href="http://download.microsoft.com/download/4/4/C/44CDEF0E-7924-4787-A56A-16261691ACE3/Microsoft_Security_Intelligence_Report_Volume_19_English.pdf" target="_blank">
         [35]
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
      One persistence mechanism used by
      <a href="https://attack.mitre.org/software/S0046">
       CozyCar
      </a>
      is to set itself to be executed at system startup by adding a Registry value under one of the following Registry keys:
      <br/>
      <code>
       HKLM\Software\Microsoft\Windows\CurrentVersion\Run\
      </code>
      <br/>
      <code>
       HKCU\Software\Microsoft\Windows\CurrentVersion\Run\
      </code>
      <br/>
      <code>
       HKLM\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\Run
      </code>
      <br/>
      <code>
       HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\Run
      </code>
      <span class="scite-citeref-number" data-reference="F-Secure CozyDuke" id="scite-ref-36-a" onclick="scrollToRef('scite-36')">
       <sup>
        <a aria-describedby="qtip-35" data-hasqtip="35" href="https://www.f-secure.com/documents/996508/1030745/CozyDuke" target="_blank">
         [36]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0235">
      CrossRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0235">
       CrossRAT
      </a>
      uses run keys for persistence on Windows
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0070">
      Dark Caracal
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0070">
       Dark Caracal
      </a>
      's version of
      <a href="https://attack.mitre.org/software/S0234">
       Bandook
      </a>
      adds a registry key to
      <code>
       HKEY_USERS\Software\Microsoft\Windows\CurrentVersion\Run
      </code>
      for persistence.
      <span class="scite-citeref-number" data-reference="Lookout Dark Caracal Jan 2018" id="scite-ref-37-a" onclick="scrollToRef('scite-37')">
       <sup>
        <a aria-describedby="qtip-36" data-hasqtip="36" href="https://info.lookout.com/rs/051-ESQ-475/images/Lookout_Dark-Caracal_srr_20180118_us_v.1.0.pdf" target="_blank">
         [37]
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
      adds several Registry entries to enable automatic execution at every system startup.
      <span class="scite-citeref-number" data-reference="TrendMicro DarkComet Sept 2014" id="scite-ref-38-a" onclick="scrollToRef('scite-38')">
       <sup>
        <a aria-describedby="qtip-37" data-hasqtip="37" href="https://www.trendmicro.com/vinfo/us/threat-encyclopedia/malware/DARKCOMET" target="_blank">
         [38]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Malwarebytes DarkComet March 2018" id="scite-ref-39-a" onclick="scrollToRef('scite-39')">
       <sup>
        <a aria-describedby="qtip-38" data-hasqtip="38" href="https://blog.malwarebytes.com/threat-analysis/2012/06/you-dirty-rat-part-1-darkcomet/" target="_blank">
         [39]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0012">
      Darkhotel
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0012">
       Darkhotel
      </a>
      has been known to establish persistence by adding programs to the Run Registry key.
      <span class="scite-citeref-number" data-reference="Kaspersky Darkhotel" id="scite-ref-40-a" onclick="scrollToRef('scite-40')">
       <sup>
        <a aria-describedby="qtip-39" data-hasqtip="39" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08070903/darkhotel_kl_07.11.pdf" target="_blank">
         [40]
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
      uses PowerShell to add a Registry Run key in order to establish persistence.
      <span class="scite-citeref-number" data-reference="ClearSky Charming Kitten Dec 2017" id="scite-ref-41-a" onclick="scrollToRef('scite-41')">
       <sup>
        <a aria-describedby="qtip-40" data-hasqtip="40" href="http://www.clearskysec.com/wp-content/uploads/2017/12/Charming_Kitten_2017.pdf" target="_blank">
         [41]
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
      added the registry value ntdll to the Registry Run key to establish persistence.
      <span class="scite-citeref-number" data-reference="US-CERT TA18-074A" id="scite-ref-42-a" onclick="scrollToRef('scite-42')">
       <sup>
        <a aria-describedby="qtip-41" data-hasqtip="41" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" target="_blank">
         [42]
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
      achieves persistence by creating a Registry entry in
      <code>
       HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
      </code>
      .
      <span class="scite-citeref-number" data-reference="DustySky" id="scite-ref-43-a" onclick="scrollToRef('scite-43')">
       <sup>
        <a aria-describedby="qtip-42" data-hasqtip="42" href="https://www.clearskysec.com/wp-content/uploads/2016/01/Operation%20DustySky_TLP_WHITE.pdf" target="_blank">
         [43]
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
      If establishing persistence by installation as a new service fails, one variant of
      <a href="https://attack.mitre.org/software/S0081">
       Elise
      </a>
      establishes persistence for the created .exe file by setting the following Registry key:
      <code>
       HKCU\Software\Microsoft\Windows\CurrentVersion\Run\svchost : %APPDATA%\Microsoft\Network\svchost.exe
      </code>
      . Other variants have set the following Registry keys for persistence:
      <code>
       HKCU\Software\Microsoft\Windows\CurrentVersion\Run\imejp : [self]
      </code>
      and
      <code>
       HKCU\Software\Microsoft\Windows\CurrentVersion\Run\IAStorD
      </code>
      .
      <span class="scite-citeref-number" data-reference="Lotus Blossom Jun 2015" id="scite-ref-44-a" onclick="scrollToRef('scite-44')">
       <sup>
        <a aria-describedby="qtip-43" data-hasqtip="43" href="https://www.paloaltonetworks.com/resources/research/unit42-operation-lotus-blossom.html" target="_blank">
         [44]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Accenture Dragonfish Jan 2018" id="scite-ref-45-a" onclick="scrollToRef('scite-45')">
       <sup>
        <a aria-describedby="qtip-44" data-hasqtip="44" href="https://www.accenture.com/t20180127T003755Z_w_/us-en/_acnmedia/PDF-46/Accenture-Security-Dragonfish-Threat-Analysis.pdf" target="_blank">
         [45]
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
      Variants of
      <a href="https://attack.mitre.org/software/S0082">
       Emissary
      </a>
      have added Run Registry keys to establish persistence.
      <span class="scite-citeref-number" data-reference="Emissary Trojan Feb 2016" id="scite-ref-46-a" onclick="scrollToRef('scite-46')">
       <sup>
        <a aria-describedby="qtip-45" data-hasqtip="45" href="http://researchcenter.paloaltonetworks.com/2016/02/emissary-trojan-changelog-did-operation-lotus-blossom-cause-it-to-evolve/" target="_blank">
         [46]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0367">
      Emotet
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0367">
       Emotet
      </a>
      has been observed adding the downloaded payload to the
      <code>
       HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run
      </code>
      key to maintain persistence.
      <span class="scite-citeref-number" data-reference="Symantec Emotet Jul 2018" id="scite-ref-47-a" onclick="scrollToRef('scite-47')">
       <sup>
        <a aria-describedby="qtip-46" data-hasqtip="46" href="https://www.symantec.com/blogs/threat-intelligence/evolution-emotet-trojan-distributor" target="_blank">
         [47]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT Emotet Jul 2018" id="scite-ref-48-a" onclick="scrollToRef('scite-48')">
       <sup>
        <a aria-describedby="qtip-47" data-hasqtip="47" href="https://www.us-cert.gov/ncas/alerts/TA18-201A" target="_blank">
         [48]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Picus Emotet Dec 2018" id="scite-ref-49-a" onclick="scrollToRef('scite-49')">
       <sup>
        <a aria-describedby="qtip-48" data-hasqtip="48" href="https://www.picussecurity.com/blog/the-christmas-card-you-never-wanted-a-new-wave-of-emotet-is-back-to-wreak-havoc.html" target="_blank">
         [49]
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
      can modify the registry run keys
      <code>
       HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run
      </code>
      and
      <code>
       HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run
      </code>
      for persistence.
      <span class="scite-citeref-number" data-reference="Github PowerShell Empire" id="scite-ref-50-a" onclick="scrollToRef('scite-50')">
       <sup>
        <a aria-describedby="qtip-49" data-hasqtip="49" href="https://github.com/PowerShellEmpire/Empire" target="_blank">
         [50]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0152">
      EvilGrab
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0152">
       EvilGrab
      </a>
      adds a Registry Run key for ctfmon.exe to establish persistence.
      <span class="scite-citeref-number" data-reference="PWC Cloud Hopper Technical Annex April 2017" id="scite-ref-31-a" onclick="scrollToRef('scite-31')">
       <sup>
        <a aria-describedby="qtip-30" data-hasqtip="30" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" target="_blank">
         [31]
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
      adds a shortcut file to the startup folder for persistence.
      <span class="scite-citeref-number" data-reference="ESET GreyEnergy Oct 2018" id="scite-ref-51-a" onclick="scrollToRef('scite-51')">
       <sup>
        <a aria-describedby="qtip-50" data-hasqtip="50" href="https://www.welivesecurity.com/wp-content/uploads/2018/10/ESET_GreyEnergy.pdf" target="_blank">
         [51]
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
      has established persistence by using the Registry option in PowerShell Empire to add a Run key.
      <span class="scite-citeref-number" data-reference="FireEye FIN10 June 2017" id="scite-ref-52-a" onclick="scrollToRef('scite-52')">
       <sup>
        <a aria-describedby="qtip-51" data-hasqtip="51" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin10.pdf" target="_blank">
         [52]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Github PowerShell Empire" id="scite-ref-50-a" onclick="scrollToRef('scite-50')">
       <sup>
        <a aria-describedby="qtip-49" data-hasqtip="49" href="https://github.com/PowerShellEmpire/Empire" target="_blank">
         [50]
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
      has used Registry Run keys to establish persistence for its downloader tools known as HARDTACK and SHIPBREAD.
      <span class="scite-citeref-number" data-reference="FireEye FIN6 April 2016" id="scite-ref-53-a" onclick="scrollToRef('scite-53')">
       <sup>
        <a aria-describedby="qtip-52" data-hasqtip="52" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin6.pdf" target="_blank">
         [53]
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
      malware has created Registry Run and RunOnce keys to establish persistence, and has also added items to the Startup folder.
      <span class="scite-citeref-number" data-reference="FireEye FIN7 April 2017" id="scite-ref-54-a" onclick="scrollToRef('scite-54')">
       <sup>
        <a aria-describedby="qtip-53" data-hasqtip="53" href="https://www.fireeye.com/blog/threat-research/2017/04/fin7-phishing-lnk.html" target="_blank">
         [54]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye FIN7 Aug 2018" id="scite-ref-55-a" onclick="scrollToRef('scite-55')">
       <sup>
        <a aria-describedby="qtip-54" data-hasqtip="54" href="https://www.fireeye.com/blog/threat-research/2018/08/fin7-pursuing-an-enigmatic-and-evasive-global-criminal-operation.html" target="_blank">
         [55]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0355">
      Final1stspy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0355">
       Final1stspy
      </a>
      creates a Registry Run key to establish persistence.
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
     <a href="https://attack.mitre.org/software/S0182">
      FinFisher
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0182">
       FinFisher
      </a>
      establishes persistence by creating the Registry key
      <code>
       HKCU\Software\Microsoft\Windows\Run
      </code>
      .
      <span class="scite-citeref-number" data-reference="FinFisher Citation" id="scite-ref-57-a" onclick="scrollToRef('scite-57')">
       <sup>
        <a aria-describedby="qtip-56" data-hasqtip="56" href="http://www.finfisher.com/FinFisher/index.html" target="_blank">
         [57]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Microsoft FinFisher March 2018" id="scite-ref-58-a" onclick="scrollToRef('scite-58')">
       <sup>
        <a aria-describedby="qtip-57" data-hasqtip="57" href="https://cloudblogs.microsoft.com/microsoftsecure/2018/03/01/finfisher-exposed-a-researchers-tale-of-defeating-traps-tricks-and-complex-virtual-machines/" target="_blank">
         [58]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0036">
      FLASHFLOOD
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0036">
       FLASHFLOOD
      </a>
      achieves persistence by making an entry in the Registry's Run key.
      <span class="scite-citeref-number" data-reference="FireEye APT30" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="https://www2.fireeye.com/rs/fireye/images/rpt-apt30.pdf" target="_blank">
         [22]
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
      can establish persistence by creating a .lnk file in the Start menu.
      <span class="scite-citeref-number" data-reference="ESET Gazer Aug 2017" id="scite-ref-59-a" onclick="scrollToRef('scite-59')">
       <sup>
        <a aria-describedby="qtip-58" data-hasqtip="58" href="https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf" target="_blank">
         [59]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Securelist WhiteBear Aug 2017" id="scite-ref-60-a" onclick="scrollToRef('scite-60')">
       <sup>
        <a aria-describedby="qtip-59" data-hasqtip="59" href="https://securelist.com/introducing-whitebear/81638/" target="_blank">
         [60]
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
      adds a Registry Run key to establish persistence.
      <span class="scite-citeref-number" data-reference="Nccgroup Gh0st April 2018" id="scite-ref-61-a" onclick="scrollToRef('scite-61')">
       <sup>
        <a aria-describedby="qtip-60" data-hasqtip="60" href="https://www.nccgroup.trust/us/about-us/newsroom-and-events/blog/2018/april/decoding-network-data-from-a-gh0st-rat-variant/" target="_blank">
         [61]
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
      establishes persistence in the Startup folder.
      <span class="scite-citeref-number" data-reference="McAfee Gold Dragon" id="scite-ref-62-a" onclick="scrollToRef('scite-62')">
       <sup>
        <a aria-describedby="qtip-61" data-hasqtip="61" href="https://securingtomorrow.mcafee.com/mcafee-labs/gold-dragon-widens-olympics-malware-attacks-gains-permanent-presence-on-victims-systems/" target="_blank">
         [62]
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
      malware can create a .lnk file and add a Registry Run key to establish persistence.
      <span class="scite-citeref-number" data-reference="Unit 42 Gorgon Group Aug 2018" id="scite-ref-63-a" onclick="scrollToRef('scite-63')">
       <sup>
        <a aria-describedby="qtip-62" data-hasqtip="62" href="https://researchcenter.paloaltonetworks.com/2018/08/unit42-gorgon-group-slithering-nation-state-cybercrime/" target="_blank">
         [63]
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
      establishes persistence by creating a shortcut in the Start Menu folder.
      <span class="scite-citeref-number" data-reference="Palo Alto OilRig May 2016" id="scite-ref-64-a" onclick="scrollToRef('scite-64')">
       <sup>
        <a aria-describedby="qtip-63" data-hasqtip="63" href="http://researchcenter.paloaltonetworks.com/2016/05/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/" target="_blank">
         [64]
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
      creates a Registry Run key to establish persistence.
      <span class="scite-citeref-number" data-reference="Fidelis INOCNATION" id="scite-ref-65-a" onclick="scrollToRef('scite-65')">
       <sup>
        <a aria-describedby="qtip-64" data-hasqtip="64" href="https://www.fidelissecurity.com/sites/default/files/FTA_1020_Fidelis_Inocnation_FINAL_0.pdf" target="_blank">
         [65]
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
      uses a batch file that configures the ComSysApp service to autostart in order to establish persistence.
      <span class="scite-citeref-number" data-reference="McAfee Honeybee" id="scite-ref-66-a" onclick="scrollToRef('scite-66')">
       <sup>
        <a aria-describedby="qtip-65" data-hasqtip="65" href="https://securingtomorrow.mcafee.com/mcafee-labs/mcafee-uncovers-operation-honeybee-malicious-document-campaign-targeting-humanitarian-aid-groups/" target="_blank">
         [66]
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
      has established persistence by setting the
      <code>
       HKCU\Software\Microsoft\Windows\CurrentVersion\Run
      </code>
      key value for
      <code>
       wdm
      </code>
      to the path of the executable. It has also used the Registry entry
      <code>
       HKEY_USERS\Software\Microsoft\Windows\CurrentVersion\Run vpdn "%ALLUSERPROFILE%\%APPDATA%\vpdn\VPDN_LU.exe"
      </code>
      to establish persistence.
      <span class="scite-citeref-number" data-reference="ZScaler Hacking Team" id="scite-ref-67-a" onclick="scrollToRef('scite-67')">
       <sup>
        <a aria-describedby="qtip-66" data-hasqtip="66" href="http://research.zscaler.com/2015/08/chinese-cyber-espionage-apt-group.html" target="_blank">
         [67]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="ThreatStream Evasion Analysis" id="scite-ref-68-a" onclick="scrollToRef('scite-68')">
       <sup>
        <a aria-describedby="qtip-67" data-hasqtip="67" href="https://www.threatstream.com/blog/evasive-maneuvers-the-wekby-group-attempts-to-evade-analysis-via-custom-rop" target="_blank">
         [68]
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
      Some
      <a href="https://attack.mitre.org/software/S0259">
       InnaputRAT
      </a>
      variants establish persistence by modifying the Registry key
      <code>
       HKU\
       <sid>
        \Software\Microsoft\Windows\CurrentVersion\Run:%appdata%\NeutralApp\NeutralApp.exe
       </sid>
      </code>
      .
      <span class="scite-citeref-number" data-reference="ASERT InnaputRAT April 2018" id="scite-ref-69-a" onclick="scrollToRef('scite-69')">
       <sup>
        <a aria-describedby="qtip-68" data-hasqtip="68" href="https://asert.arbornetworks.com/innaput-actors-utilize-remote-access-trojan-since-2016-presumably-targeting-victim-files/" target="_blank">
         [69]
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
      has used a Registry Run key to establish persistence by executing JavaScript code within the rundll32.exe process.
      <span class="scite-citeref-number" data-reference="ESET Sednit Part 1" id="scite-ref-70-a" onclick="scrollToRef('scite-70')">
       <sup>
        <a aria-describedby="qtip-69" data-hasqtip="69" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part1.pdf" target="_blank">
         [70]
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
      creates a Registry Run key to establish persistence.
      <span class="scite-citeref-number" data-reference="Zscaler Kasidet" id="scite-ref-71-a" onclick="scrollToRef('scite-71')">
       <sup>
        <a aria-describedby="qtip-70" data-hasqtip="70" href="http://research.zscaler.com/2016/01/malicious-office-files-dropping-kasidet.html" target="_blank">
         [71]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Microsoft Kasidet" id="scite-ref-72-a" onclick="scrollToRef('scite-72')">
       <sup>
        <a aria-describedby="qtip-71" data-hasqtip="71" href="http://www.microsoft.com/security/portal/threat/encyclopedia/entry.aspx?Name=Win32%2FKasidet" target="_blank">
         [72]
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
      adds a sub-key under several Registry run keys.
      <span class="scite-citeref-number" data-reference="Unit 42 Kazuar May 2017" id="scite-ref-73-a" onclick="scrollToRef('scite-73')">
       <sup>
        <a aria-describedby="qtip-72" data-hasqtip="72" href="https://researchcenter.paloaltonetworks.com/2017/05/unit42-kazuar-multiplatform-espionage-backdoor-api-access/" target="_blank">
         [73]
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
      Several
      <a href="https://attack.mitre.org/groups/G0004">
       Ke3chang
      </a>
      backdoors achieved persistence by adding a Run key.
      <span class="scite-citeref-number" data-reference="NCC Group APT15 Alive and Strong" id="scite-ref-74-a" onclick="scrollToRef('scite-74')">
       <sup>
        <a aria-describedby="qtip-73" data-hasqtip="73" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/" target="_blank">
         [74]
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
      A version of
      <a href="https://attack.mitre.org/software/S0356">
       KONNI
      </a>
      drops a Windows shortcut into the Startup folder to establish persistence.
      <span class="scite-citeref-number" data-reference="Talos Konni May 2017" id="scite-ref-75-a" onclick="scrollToRef('scite-75')">
       <sup>
        <a aria-describedby="qtip-74" data-hasqtip="74" href="https://blog.talosintelligence.com/2017/05/konni-malware-under-radar-for-years.html" target="_blank">
         [75]
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
      malware attempts to maintain persistence by saving itself in the Start menu folder or by adding a Registry Run key.
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster" id="scite-ref-76-a" onclick="scrollToRef('scite-76')">
       <sup>
        <a aria-describedby="qtip-75" data-hasqtip="75" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" target="_blank">
         [76]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster RATs" id="scite-ref-77-a" onclick="scrollToRef('scite-77')">
       <sup>
        <a aria-describedby="qtip-76" data-hasqtip="76" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-RAT-and-Staging-Report.pdf" target="_blank">
         [77]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="McAfee Lazarus Resurfaces Feb 2018" id="scite-ref-78-a" onclick="scrollToRef('scite-78')">
       <sup>
        <a aria-describedby="qtip-77" data-hasqtip="77" href="https://securingtomorrow.mcafee.com/mcafee-labs/lazarus-resurfaces-targets-global-banks-bitcoin-users/" target="_blank">
         [78]
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
      has used JavaScript to create a shortcut file in the Startup folder that points to its main backdoor.
      <span class="scite-citeref-number" data-reference="Proofpoint Leviathan Oct 2017" id="scite-ref-79-a" onclick="scrollToRef('scite-79')">
       <sup>
        <a aria-describedby="qtip-78" data-hasqtip="78" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" target="_blank">
         [79]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye Periscope March 2018" id="scite-ref-80-a" onclick="scrollToRef('scite-80')">
       <sup>
        <a aria-describedby="qtip-79" data-hasqtip="79" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" target="_blank">
         [80]
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
      malware has used Registry Run keys to establish persistence.
      <span class="scite-citeref-number" data-reference="Unit 42 Magic Hound Feb 2017" id="scite-ref-81-a" onclick="scrollToRef('scite-81')">
       <sup>
        <a aria-describedby="qtip-80" data-hasqtip="80" href="https://researchcenter.paloaltonetworks.com/2017/02/unit42-magic-hound-campaign-attacks-saudi-targets/" target="_blank">
         [81]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0167">
      Matroyshka
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0167">
       Matroyshka
      </a>
      can establish persistence by adding Registry Run keys.
      <span class="scite-citeref-number" data-reference="ClearSky Wilted Tulip July 2017" id="scite-ref-82-a" onclick="scrollToRef('scite-82')">
       <sup>
        <a aria-describedby="qtip-81" data-hasqtip="81" href="http://www.clearskysec.com/wp-content/uploads/2017/07/Operation_Wilted_Tulip.pdf" target="_blank">
         [82]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="CopyKittens Nov 2015" id="scite-ref-83-a" onclick="scrollToRef('scite-83')">
       <sup>
        <a aria-describedby="qtip-82" data-hasqtip="82" href="https://s3-eu-west-1.amazonaws.com/minervaresearchpublic/CopyKittens/CopyKittens.pdf" target="_blank">
         [83]
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
      creates the following Registry entry:
      <code>
       HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run\Micromedia
      </code>
      .
      <span class="scite-citeref-number" data-reference="Symantec Backdoor.Mivast" id="scite-ref-84-a" onclick="scrollToRef('scite-84')">
       <sup>
        <a aria-describedby="qtip-83" data-hasqtip="83" href="http://www.symantec.com/security_response/writeup.jsp?docid=2015-020623-0740-99&amp;tabid=2" target="_blank">
         [84]
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
      establishes persistence under the Registry key
      <code>
       HKCU\Software\Run auto_update
      </code>
      .
      <span class="scite-citeref-number" data-reference="ESET Turla Mosquito Jan 2018" id="scite-ref-85-a" onclick="scrollToRef('scite-85')">
       <sup>
        <a aria-describedby="qtip-84" data-hasqtip="84" href="https://www.welivesecurity.com/wp-content/uploads/2018/01/ESET_Turla_Mosquito.pdf" target="_blank">
         [85]
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
      has added Registry Run keys to establish persistence.
      <span class="scite-citeref-number" data-reference="FireEye MuddyWater Mar 2018" id="scite-ref-86-a" onclick="scrollToRef('scite-86')">
       <sup>
        <a aria-describedby="qtip-85" data-hasqtip="85" href="https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html" target="_blank">
         [86]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Securelist MuddyWater Oct 2018" id="scite-ref-87-a" onclick="scrollToRef('scite-87')">
       <sup>
        <a aria-describedby="qtip-86" data-hasqtip="86" href="https://securelist.com/muddywater/88059/" target="_blank">
         [87]
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
      modifies the %regrun% Registry to point itself to an autostart mechanism.
      <span class="scite-citeref-number" data-reference="fsecure NanHaiShu July 2016" id="scite-ref-88-a" onclick="scrollToRef('scite-88')">
       <sup>
        <a aria-describedby="qtip-87" data-hasqtip="87" href="https://www.f-secure.com/documents/996508/1030745/nanhaishu_whitepaper.pdf" target="_blank">
         [88]
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
      creates a RunOnce key in the Registry to execute its VBS scripts each time the user logs on to the machine.
      <span class="scite-citeref-number" data-reference="Cofense NanoCore Mar 2018" id="scite-ref-89-a" onclick="scrollToRef('scite-89')">
       <sup>
        <a aria-describedby="qtip-88" data-hasqtip="88" href="https://cofense.com/nanocore-rat-resurfaced-sewers/" target="_blank">
         [89]
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
      creates a Registry key to ensure a file gets executed upon reboot in order to establish persistence.
      <span class="scite-citeref-number" data-reference="Talos NavRAT May 2018" id="scite-ref-90-a" onclick="scrollToRef('scite-90')">
       <sup>
        <a aria-describedby="qtip-89" data-hasqtip="89" href="https://blog.talosintelligence.com/2018/05/navrat.html" target="_blank">
         [90]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0034">
      NETEAGLE
     </a>
    </td>
    <td>
     <p>
      The "SCOUT" variant of
      <a href="https://attack.mitre.org/software/S0034">
       NETEAGLE
      </a>
      achieves persistence by adding itself to the
      <code>
       HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
      </code>
      Registry key.
      <span class="scite-citeref-number" data-reference="FireEye APT30" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="https://www2.fireeye.com/rs/fireye/images/rpt-apt30.pdf" target="_blank">
         [22]
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
      creates a Registry start-up entry to establish persistence.
      <span class="scite-citeref-number" data-reference="McAfee Netwire Mar 2015" id="scite-ref-91-a" onclick="scrollToRef('scite-91')">
       <sup>
        <a aria-describedby="qtip-90" data-hasqtip="90" href="https://securingtomorrow.mcafee.com/mcafee-labs/netwire-rat-behind-recent-targeted-attacks/" target="_blank">
         [91]
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
      has established persistence by writing the payload to the Registry key
      <code>
       HKCU\Software\Microsoft\Windows\CurrentVersion\Run
      </code>
      .
      <span class="scite-citeref-number" data-reference="Unit 42 NOKKI Sept 2018" id="scite-ref-92-a" onclick="scrollToRef('scite-92')">
       <sup>
        <a aria-describedby="qtip-91" data-hasqtip="91" href="https://researchcenter.paloaltonetworks.com/2018/09/unit42-new-konni-malware-attacking-eurasia-southeast-asia/" target="_blank">
         [92]
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
      has added the path of its second-stage malware to the startup folder to achieve persistence. One of its file stealers has also persisted by adding a Registry Run key.
      <span class="scite-citeref-number" data-reference="Cymmetria Patchwork" id="scite-ref-93-a" onclick="scrollToRef('scite-93')">
       <sup>
        <a aria-describedby="qtip-92" data-hasqtip="92" href="https://s3-us-west-2.amazonaws.com/cymmetria-blog/public/Unveiling_Patchwork.pdf" target="_blank">
         [93]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="TrendMicro Patchwork Dec 2017" id="scite-ref-94-a" onclick="scrollToRef('scite-94')">
       <sup>
        <a aria-describedby="qtip-93" data-hasqtip="93" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" target="_blank">
         [94]
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
      establishes persistence via a Registry Run key.
      <span class="scite-citeref-number" data-reference="Palo Alto DNS Requests" id="scite-ref-95-a" onclick="scrollToRef('scite-95')">
       <sup>
        <a aria-describedby="qtip-94" data-hasqtip="94" href="http://researchcenter.paloaltonetworks.com/2016/05/unit42-new-wekby-attacks-use-dns-requests-as-command-and-control-mechanism/" target="_blank">
         [95]
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
      gains persistence by adding the Registry key
      <code>
       HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\RunOnce
      </code>
      .
      <span class="scite-citeref-number" data-reference="Rancor Unit42 June 2018" id="scite-ref-96-a" onclick="scrollToRef('scite-96')">
       <sup>
        <a aria-describedby="qtip-95" data-hasqtip="95" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-rancor-targeted-attacks-south-east-asia-using-plaintee-ddkong-malware-families/" target="_blank">
         [96]
        </a>
       </sup>
      </span>
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
      adds Run key entries in the Registry to establish persistence.
      <span class="scite-citeref-number" data-reference="Lastline PlugX Analysis" id="scite-ref-97-a" onclick="scrollToRef('scite-97')">
       <sup>
        <a aria-describedby="qtip-96" data-hasqtip="96" href="http://labs.lastline.com/an-analysis-of-plugx" target="_blank">
         [97]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PWC Cloud Hopper Technical Annex April 2017" id="scite-ref-31-a" onclick="scrollToRef('scite-31')">
       <sup>
        <a aria-describedby="qtip-30" data-hasqtip="30" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" target="_blank">
         [31]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="CIRCL PlugX March 2013" id="scite-ref-98-a" onclick="scrollToRef('scite-98')">
       <sup>
        <a aria-describedby="qtip-97" data-hasqtip="97" href="http://circl.lu/assets/files/tr-12/tr-12-circl-plugx-analysis-v1.pdf" target="_blank">
         [98]
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
      creates run key Registry entries pointing to a malicious executable dropped to disk.
      <span class="scite-citeref-number" data-reference="Symantec Darkmoon Aug 2005" id="scite-ref-99-a" onclick="scrollToRef('scite-99')">
       <sup>
        <a aria-describedby="qtip-98" data-hasqtip="98" href="https://www.symantec.com/security_response/writeup.jsp?docid=2005-081910-3934-99" target="_blank">
         [99]
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
      achieves persistence by using various Registry Run keys.
      <span class="scite-citeref-number" data-reference="Volexity PowerDuke November 2016" id="scite-ref-100-a" onclick="scrollToRef('scite-100')">
       <sup>
        <a aria-describedby="qtip-99" data-hasqtip="99" href="https://www.volexity.com/blog/2016/11/09/powerduke-post-election-spear-phishing-campaigns-targeting-think-tanks-and-ngos/" target="_blank">
         [100]
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
      achieves persistence by setting a Registry Run key, with the path depending on whether the victim account has user or administrator access.
      <span class="scite-citeref-number" data-reference="Cisco DNSMessenger March 2017" id="scite-ref-101-a" onclick="scrollToRef('scite-101')">
       <sup>
        <a aria-describedby="qtip-100" data-hasqtip="100" href="http://blog.talosintelligence.com/2017/03/dnsmessenger.html" target="_blank">
         [101]
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
      's
      <code>
       New-UserPersistenceOption
      </code>
      Persistence argument can be used to establish via the
      <code>
       HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
      </code>
      Registry key.
      <span class="scite-citeref-number" data-reference="GitHub PowerSploit May 2012" id="scite-ref-102-a" onclick="scrollToRef('scite-102')">
       <sup>
        <a aria-describedby="qtip-101" data-hasqtip="101" href="https://github.com/PowerShellMafia/PowerSploit" target="_blank">
         [102]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PowerSploit Documentation" id="scite-ref-103-a" onclick="scrollToRef('scite-103')">
       <sup>
        <a aria-describedby="qtip-102" data-hasqtip="102" href="http://powersploit.readthedocs.io" target="_blank">
         [103]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0371">
      POWERTON
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0371">
       POWERTON
      </a>
      can install a Registry Run key for persistence.
      <span class="scite-citeref-number" data-reference="FireEye APT33 Guardrail" id="scite-ref-104-a" onclick="scrollToRef('scite-104')">
       <sup>
        <a aria-describedby="qtip-103" data-hasqtip="103" href="https://www.fireeye.com/blog/threat-research/2018/12/overruled-containing-a-potentially-destructive-adversary.html" target="_blank">
         [104]
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
      <a href="https://attack.mitre.org/software/S0113">
       Prikormka
      </a>
      adds itself to a Registry Run key with the name guidVGA or guidVSA.
      <span class="scite-citeref-number" data-reference="ESET Operation Groundbait" id="scite-ref-105-a" onclick="scrollToRef('scite-105')">
       <sup>
        <a aria-describedby="qtip-104" data-hasqtip="104" href="http://www.welivesecurity.com/wp-content/uploads/2016/05/Operation-Groundbait.pdf" target="_blank">
         [105]
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
      copies itself to the Startup folder to establish persistence.
      <span class="scite-citeref-number" data-reference="Palo Alto Gamaredon Feb 2017" id="scite-ref-106-a" onclick="scrollToRef('scite-106')">
       <sup>
        <a aria-describedby="qtip-105" data-hasqtip="105" href="https://researchcenter.paloaltonetworks.com/2017/02/unit-42-title-gamaredon-group-toolset-evolution/" target="_blank">
         [106]
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
      can establish using a Registry run key.
      <span class="scite-citeref-number" data-reference="FireEye Know Your Enemy FIN8 Aug 2016" id="scite-ref-107-a" onclick="scrollToRef('scite-107')">
       <sup>
        <a aria-describedby="qtip-106" data-hasqtip="106" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" target="_blank">
         [107]
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
      adds itself to the startup folder or adds itself to the Registry key
      <code>
       SOFTWARE\Microsoft\Windows\CurrentVersion\Run
      </code>
      for persistence.
      <span class="scite-citeref-number" data-reference="GitHub Pupy" id="scite-ref-108-a" onclick="scrollToRef('scite-108')">
       <sup>
        <a aria-describedby="qtip-107" data-hasqtip="107" href="https://github.com/n1nj4sec/pupy" target="_blank">
         [108]
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
      A dropper used by
      <a href="https://attack.mitre.org/groups/G0024">
       Putter Panda
      </a>
      installs itself into the ASEP Registry key
      <code>
       HKCU\Software\Microsoft\Windows\CurrentVersion\Run
      </code>
      with a value named McUpdate.
      <span class="scite-citeref-number" data-reference="CrowdStrike Putter Panda" id="scite-ref-109-a" onclick="scrollToRef('scite-109')">
       <sup>
        <a aria-describedby="qtip-108" data-hasqtip="108" href="http://cdn0.vox-cdn.com/assets/4589853/crowdstrike-intelligence-report-putter-panda.original.pdf" target="_blank">
         [109]
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
      creates a shortcut file and saves it in a Startup folder to establish persistence.
      <span class="scite-citeref-number" data-reference="Palo Alto Reaver Nov 2017" id="scite-ref-110-a" onclick="scrollToRef('scite-110')">
       <sup>
        <a aria-describedby="qtip-109" data-hasqtip="109" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-new-malware-with-ties-to-sunorcal-discovered/" target="_blank">
         [110]
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
      attempts to add a shortcut file in the Startup folder to achieve persistence. If this fails, it attempts to add Registry Run keys.
      <span class="scite-citeref-number" data-reference="PWC Cloud Hopper Technical Annex April 2017" id="scite-ref-31-a" onclick="scrollToRef('scite-31')">
       <sup>
        <a aria-describedby="qtip-30" data-hasqtip="30" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" target="_blank">
         [31]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Accenture Hogfish April 2018" id="scite-ref-111-a" onclick="scrollToRef('scite-111')">
       <sup>
        <a aria-describedby="qtip-110" data-hasqtip="110" href="https://www.accenture.com/t20180423T055005Z_w_/se-en/_acnmedia/PDF-76/Accenture-Hogfish-Threat-Analysis.pdf" target="_blank">
         [111]
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
      can add itself to the Registry key
      <code>
       HKCU\Software\Microsoft\Windows\CurrentVersion\Run
      </code>
      for persistence.
      <span class="scite-citeref-number" data-reference="Fortinet Remcos Feb 2017" id="scite-ref-112-a" onclick="scrollToRef('scite-112')">
       <sup>
        <a aria-describedby="qtip-111" data-hasqtip="111" href="https://www.fortinet.com/blog/threat-research/remcos-a-new-rat-in-the-wild-2.html" target="_blank">
         [112]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0375">
      Remexi
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0375">
       Remexi
      </a>
      utilizes Run Registry keys in the HKLM hive as a persistence mechanism.
      <span class="scite-citeref-number" data-reference="Securelist Remexi Jan 2019" id="scite-ref-113-a" onclick="scrollToRef('scite-113')">
       <sup>
        <a aria-describedby="qtip-112" data-hasqtip="112" href="https://securelist.com/chafer-used-remexi-malware/89538/" target="_blank">
         [113]
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
      created a shortcut in the Windows startup folder to launch a PowerShell script each time the user logs in to establish persistence.
      <span class="scite-citeref-number" data-reference="Unit 42 DarkHydrus July 2018" id="scite-ref-114-a" onclick="scrollToRef('scite-114')">
       <sup>
        <a aria-describedby="qtip-113" data-hasqtip="113" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-new-threat-actor-group-darkhydrus-targets-middle-east-government/" target="_blank">
         [114]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0090">
      Rover
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0090">
       Rover
      </a>
      persists by creating a Registry entry in
      <code>
       HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Run\
      </code>
      .
      <span class="scite-citeref-number" data-reference="Palo Alto Rover" id="scite-ref-115-a" onclick="scrollToRef('scite-115')">
       <sup>
        <a aria-describedby="qtip-114" data-hasqtip="114" href="http://researchcenter.paloaltonetworks.com/2016/02/new-malware-rover-targets-indian-ambassador-to-afghanistan/" target="_blank">
         [115]
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
      tries to add a Registry Run key under the name "Windows Update" to establish persistence.
      <span class="scite-citeref-number" data-reference="ESET RTM Feb 2017" id="scite-ref-116-a" onclick="scrollToRef('scite-116')">
       <sup>
        <a aria-describedby="qtip-115" data-hasqtip="115" href="https://www.welivesecurity.com/wp-content/uploads/2017/02/Read-The-Manual.pdf" target="_blank">
         [116]
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
      adds itself to the Registry key
      <code>
       Software\Microsoft\Windows\CurrentVersion\Run
      </code>
      to establish persistence upon reboot.
      <span class="scite-citeref-number" data-reference="McAfee Gold Dragon" id="scite-ref-62-a" onclick="scrollToRef('scite-62')">
       <sup>
        <a aria-describedby="qtip-61" data-hasqtip="61" href="https://securingtomorrow.mcafee.com/mcafee-labs/gold-dragon-widens-olympics-malware-attacks-gains-permanent-presence-on-victims-systems/" target="_blank">
         [62]
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
      <a href="https://attack.mitre.org/software/S0085">
       S-Type
      </a>
      may create a .lnk file to itself that is saved in the Start menu folder. It may also create the Registry key
      <code>
       HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Run\ IMJPMIJ8.1{3 characters of Unique Identifier}
      </code>
      .
      <span class="scite-citeref-number" data-reference="Cylance Dust Storm" id="scite-ref-117-a" onclick="scrollToRef('scite-117')">
       <sup>
        <a aria-describedby="qtip-116" data-hasqtip="116" href="https://www.cylance.com/content/dam/cylance/pdfs/reports/Op_Dust_Storm_Report.pdf" target="_blank">
         [117]
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
      Most
      <a href="https://attack.mitre.org/software/S0074">
       Sakula
      </a>
      samples maintain persistence by setting the Registry Run key
      <code>
       SOFTWARE\Microsoft\Windows\CurrentVersion\Run\
      </code>
      in the HKLM or HKCU hive, with the Registry value and file name varying by sample.
      <span class="scite-citeref-number" data-reference="Dell Sakula" id="scite-ref-118-a" onclick="scrollToRef('scite-118')">
       <sup>
        <a aria-describedby="qtip-117" data-hasqtip="117" href="http://www.secureworks.com/cyber-threat-intelligence/threats/sakula-malware-family/" target="_blank">
         [118]
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
      is capable of persisting via the Registry Run key or a .lnk file stored in the Startup directory.
      <span class="scite-citeref-number" data-reference="Unit 42 SeaDuke 2015" id="scite-ref-119-a" onclick="scrollToRef('scite-119')">
       <sup>
        <a aria-describedby="qtip-118" data-hasqtip="118" href="http://researchcenter.paloaltonetworks.com/2015/07/unit-42-technical-analysis-seaduke/" target="_blank">
         [119]
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
      creates a Registry entry to ensure infection after reboot under
      <code>
       HKLM\Software\Microsoft\Windows\currentVersion\Run
      </code>
      .
      <span class="scite-citeref-number" data-reference="McAfee Oceansalt Oct 2018" id="scite-ref-120-a" onclick="scrollToRef('scite-120')">
       <sup>
        <a aria-describedby="qtip-119" data-hasqtip="119" href="https://www.mcafee.com/enterprise/en-us/assets/reports/rp-operation-oceansalt.pdf" target="_blank">
         [120]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0028">
      SHIPSHAPE
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0028">
       SHIPSHAPE
      </a>
      achieves persistence by creating a shortcut in the Startup folder.
      <span class="scite-citeref-number" data-reference="FireEye APT30" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="https://www2.fireeye.com/rs/fireye/images/rpt-apt30.pdf" target="_blank">
         [22]
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
      adds a Registry Run key for persistence and adds a script in the Startup folder to deploy the payload.
      <span class="scite-citeref-number" data-reference="Malwarebytes SmokeLoader 2016" id="scite-ref-121-a" onclick="scrollToRef('scite-121')">
       <sup>
        <a aria-describedby="qtip-120" data-hasqtip="120" href="https://blog.malwarebytes.com/threat-analysis/2016/08/smoke-loader-downloader-with-a-smokescreen-still-alive/" target="_blank">
         [121]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0159">
      SNUGRIDE
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0159">
       SNUGRIDE
      </a>
      establishes persistence through a Registry Run key.
      <span class="scite-citeref-number" data-reference="FireEye APT10 April 2017" id="scite-ref-122-a" onclick="scrollToRef('scite-122')">
       <sup>
        <a aria-describedby="qtip-121" data-hasqtip="121" href="https://www.fireeye.com/blog/threat-research/2017/04/apt10_menupass_grou.html" target="_blank">
         [122]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0035">
      SPACESHIP
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0035">
       SPACESHIP
      </a>
      achieves persistence by creating a shortcut in the current user's Startup folder.
      <span class="scite-citeref-number" data-reference="FireEye APT30" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="https://www2.fireeye.com/rs/fireye/images/rpt-apt30.pdf" target="_blank">
         [22]
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
      To establish persistence,
      <a href="https://attack.mitre.org/software/S0058">
       SslMM
      </a>
      identifies the Start Menu Startup directory and drops a link to its own executable disguised as an "Office Start," "Yahoo Talk," "MSN Gaming Z0ne," or "MSN Talk" shortcut.
      <span class="scite-citeref-number" data-reference="Baumgartner Naikon 2015" id="scite-ref-123-a" onclick="scrollToRef('scite-123')">
       <sup>
        <a aria-describedby="qtip-122" data-hasqtip="122" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07205555/TheNaikonAPT-MsnMM1.pdf" target="_blank">
         [123]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0018">
      Sykipot
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0018">
       Sykipot
      </a>
      has been known to establish persistence by adding programs to the Run Registry key.
      <span class="scite-citeref-number" data-reference="Blasco 2013" id="scite-ref-124-a" onclick="scrollToRef('scite-124')">
       <sup>
        <a aria-describedby="qtip-123" data-hasqtip="123" href="http://www.alienvault.com/open-threat-exchange/blog/new-sykipot-developments" target="_blank">
         [124]
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
      A
      <a href="https://attack.mitre.org/groups/G0027">
       Threat Group-3390
      </a>
      tool can add the binary’s path to the Registry key
      <code>
       Software\Microsoft\Windows\CurrentVersion\Run
      </code>
      to add persistence.
      <span class="scite-citeref-number" data-reference="Nccgroup Emissary Panda May 2018" id="scite-ref-125-a" onclick="scrollToRef('scite-125')">
       <sup>
        <a aria-describedby="qtip-124" data-hasqtip="124" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/may/emissary-panda-a-potential-new-malicious-tool/" target="_blank">
         [125]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0131">
      TINYTYPHON
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0131">
       TINYTYPHON
      </a>
      installs itself under Registry Run key to establish persistence.
      <span class="scite-citeref-number" data-reference="Forcepoint Monsoon" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" target="_blank">
         [23]
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
      can create a shortcut in the Windows startup folder for persistence.
      <span class="scite-citeref-number" data-reference="Cylance Cleaver" id="scite-ref-126-a" onclick="scrollToRef('scite-126')">
       <sup>
        <a aria-describedby="qtip-125" data-hasqtip="125" href="https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf" target="_blank">
         [126]
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
      establishes persistence in the Startup folder.
      <span class="scite-citeref-number" data-reference="Trend Micro Trickbot Nov 2018" id="scite-ref-127-a" onclick="scrollToRef('scite-127')">
       <sup>
        <a aria-describedby="qtip-126" data-hasqtip="126" href="https://blog.trendmicro.com/trendlabs-security-intelligence/trickbot-shows-off-new-trick-password-grabber-module/" target="_blank">
         [127]
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
      can create a link to itself in the Startup folder to automatically start itself upon system restart.
      <span class="scite-citeref-number" data-reference="Symantec Dragonfly" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/Dragonfly_Threat_Against_Western_Energy_Suppliers.pdf" target="_blank">
         [21]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0178">
      Truvasys
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0178">
       Truvasys
      </a>
      adds a Registry Run key to establish persistence.
      <span class="scite-citeref-number" data-reference="Microsoft Win Defender Truvasys Sep 2017" id="scite-ref-128-a" onclick="scrollToRef('scite-128')">
       <sup>
        <a aria-describedby="qtip-127" data-hasqtip="127" href="https://www.microsoft.com/en-us/wdsi/threats/malware-encyclopedia-description?Name=Backdoor:Win32/Truvasys.A!dha" target="_blank">
         [128]
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
      A
      <a href="https://attack.mitre.org/groups/G0010">
       Turla
      </a>
      Javascript backdoor added a local_update_check value under the Registry key
      <code>
       HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
      </code>
      to establish persistence. Additionally, a
      <a href="https://attack.mitre.org/groups/G0010">
       Turla
      </a>
      custom executable containing Metasploit shellcode is saved to the Startup folder to gain persistence.
      <span class="scite-citeref-number" data-reference="ESET Turla Mosquito Jan 2018" id="scite-ref-85-a" onclick="scrollToRef('scite-85')">
       <sup>
        <a aria-describedby="qtip-84" data-hasqtip="84" href="https://www.welivesecurity.com/wp-content/uploads/2018/01/ESET_Turla_Mosquito.pdf" target="_blank">
         [85]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="ESET Turla Mosquito May 2018" id="scite-ref-129-a" onclick="scrollToRef('scite-129')">
       <sup>
        <a aria-describedby="qtip-128" data-hasqtip="128" href="https://www.welivesecurity.com/2018/05/22/turla-mosquito-shift-towards-generic-tools/" target="_blank">
         [129]
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
      is capable of writing to a Registry Run key to establish.
      <span class="scite-citeref-number" data-reference="CyberBit Early Bird Apr 2018" id="scite-ref-130-a" onclick="scrollToRef('scite-130')">
       <sup>
        <a aria-describedby="qtip-129" data-hasqtip="129" href="https://www.cyberbit.com/blog/endpoint-security/new-early-bird-code-injection-technique-discovered/" target="_blank">
         [130]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0136">
      USBStealer
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0136">
       USBStealer
      </a>
      registers itself under a Registry Run key with the name "USB Disk Security."
      <span class="scite-citeref-number" data-reference="ESET Sednit USBStealer 2014" id="scite-ref-131-a" onclick="scrollToRef('scite-131')">
       <sup>
        <a aria-describedby="qtip-130" data-hasqtip="130" href="http://www.welivesecurity.com/2014/11/11/sednit-espionage-group-attacking-air-gapped-networks/" target="_blank">
         [131]
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
      copies itself to disk and creates an associated run key Registry entry to establish.
      <span class="scite-citeref-number" data-reference="Symantec Vasport May 2012" id="scite-ref-132-a" onclick="scrollToRef('scite-132')">
       <sup>
        <a aria-describedby="qtip-131" data-hasqtip="131" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051606-5938-99" target="_blank">
         [132]
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
      can create a Startup item for persistence if it determines it is on a Windows system.
      <span class="scite-citeref-number" data-reference="Unit42 Xbash Sept 2018" id="scite-ref-133-a" onclick="scrollToRef('scite-133')">
       <sup>
        <a aria-describedby="qtip-132" data-hasqtip="132" href="https://researchcenter.paloaltonetworks.com/2018/09/unit42-xbash-combines-botnet-ransomware-coinmining-worm-targets-linux-windows/" target="_blank">
         [133]
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
      creates an entry in the Registry’s run keys for the malware to execute on startup.
      <span class="scite-citeref-number" data-reference="ESET Zebrocy Nov 2018" id="scite-ref-134-a" onclick="scrollToRef('scite-134')">
       <sup>
        <a aria-describedby="qtip-133" data-hasqtip="133" href="https://www.welivesecurity.com/2018/11/20/sednit-whats-going-zebrocy/" target="_blank">
         [134]
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
      adds persistence by creating Registry Run keys.
      <span class="scite-citeref-number" data-reference="Talos Zeus Panda Nov 2017" id="scite-ref-135-a" onclick="scrollToRef('scite-135')">
       <sup>
        <a aria-describedby="qtip-134" data-hasqtip="134" href="https://blog.talosintelligence.com/2017/11/zeus-panda-campaign.html#More" target="_blank">
         [135]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="GDATA Zeus Panda June 2017" id="scite-ref-136-a" onclick="scrollToRef('scite-136')">
       <sup>
        <a aria-describedby="qtip-135" data-hasqtip="135" href="https://cyberwtf.files.wordpress.com/2017/07/panda-whitepaper.pdf" target="_blank">
         [136]
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
  Identify and block potentially malicious software that may be executed through run key or startup folder persistence using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-137-a">
   <sup>
    <a aria-describedby="qtip-136" data-hasqtip="136" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [137]
    </a>
   </sup>
  </span>
  tools like AppLocker
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-138-a">
   <sup>
    <a aria-describedby="qtip-137" data-hasqtip="137" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [138]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-139-a">
   <sup>
    <a aria-describedby="qtip-138" data-hasqtip="138" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [139]
    </a>
   </sup>
  </span>
  or Software Restriction Policies
  <span class="scite-citeref-number" data-reference="Corio 2008" id="scite-ref-140-a">
   <sup>
    <a aria-describedby="qtip-139" data-hasqtip="139" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" target="_blank">
     [140]
    </a>
   </sup>
  </span>
  where appropriate.
  <span class="scite-citeref-number" data-reference="TechNet Applocker vs SRP" id="scite-ref-141-a">
   <sup>
    <a aria-describedby="qtip-140" data-hasqtip="140" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" target="_blank">
     [141]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor Registry for changes to run keys that do not correlate with known software, patch cycles, etc. Monitor the start folder for additions or changes. Tools such as Sysinternals Autoruns may also be used to detect system changes that could be attempts at persistence, including listing the run keys' Registry locations and startup folders.
  <span class="scite-citeref-number" data-reference="TechNet Autoruns" id="scite-ref-142-a">
   <sup>
    <a aria-describedby="qtip-141" data-hasqtip="141" href="https://technet.microsoft.com/en-us/sysinternals/bb963902" target="_blank">
     [142]
    </a>
   </sup>
  </span>
  Suspicious program execution as startup programs may show up as outlier processes that have not been seen before when compared against historical data.
 </p>
 <p>
  Changes to these locations typically happen under normal conditions when legitimate software is installed. To increase confidence of malicious activity, data and events should not be viewed in isolation, but as part of a chain of behavior that could lead to other activities, such as network connections made for Command and Control, learning details about the environment through Discovery, and Lateral Movement.
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
       <a class="external text" href="http://msdn.microsoft.com/en-us/library/aa376977" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Run and RunOnce Registry Keys. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://support.microsoft.com/help/310593/description-of-the-runonceex-registry-key" name="scite-2" rel="nofollow" target="_blank">
        Microsoft. (2018, August 20). Description of the RunOnceEx Registry Key. Retrieved June 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://oddvar.moe/2018/03/21/persistence-using-runonceex-hidden-from-autoruns-exe/" name="scite-3" rel="nofollow" target="_blank">
        Moe, O. (2018, March 21). Persistence using RunOnceEx - Hidden from Autoruns.exe. Retrieved June 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/sofacy-apt-hits-high-profile-targets-with-updated-toolset/72924/" name="scite-4" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2015, December 4). Sofacy APT hits high profile targets with updated toolset. Retrieved December 10, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part-2.pdf" name="scite-5" rel="nofollow" target="_blank">
        ESET. (2016, October). En Route with Sednit - Part 2: Observing the Comings and Goings. Retrieved November 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://download.bitdefender.com/resources/media/materials/white-papers/en/Bitdefender_In-depth_analysis_of_APT28%E2%80%93The_Political_Cyber-Espionage.pdf" name="scite-6" rel="nofollow" target="_blank">
        Bitdefender. (2015, December). APT28 Under the Scope. Retrieved February 23, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fortinet.com/blog/threat-research/analysis-of-new-agent-tesla-spyware-variant.html" name="scite-7" rel="nofollow" target="_blank">
        Zhang, X. (2018, April 05). Analysis of New Agent Tesla Spyware Variant. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.anomali.com/blog/evasive-maneuvers-the-wekby-group-attempts-to-evade-analysis-via-custom-rop" name="scite-8" rel="nofollow" target="_blank">
        Shelmire, A. (2015, July 06). Evasive Maneuvers by the Wekby group with custom ROP-packing and DNS covert channels. Retrieved November 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2016/05/unit42-new-wekby-attacks-use-dns-requests-as-command-and-control-mechanism/" name="scite-9" rel="nofollow" target="_blank">
        Grunzweig, J., et al. (2016, May 24). New Wekby Attacks Use DNS Requests As Command and Control Mechanism. Retrieved November 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2016/01/new-attacks-linked-to-c0d0s0-group/" name="scite-10" rel="nofollow" target="_blank">
        Grunzweig, J., Lee, B. (2016, January 22). New Attacks Linked to C0d0so0 Group. Retrieved August 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.slideshare.net/MatthewDunwoody1/no-easy-breach-derby-con-2016" name="scite-11" rel="nofollow" target="_blank">
        Dunwoody, M. and Carr, N.. (2016, September 27). No Easy Breach DerbyCon 2016. Retrieved October 4, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2014/11/operation_doubletap.html" name="scite-12" rel="nofollow" target="_blank">
        Moran, N., et al. (2014, November 21). Operation Double Tap. Retrieved January 14, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cybereason.com/blog/operation-cobalt-kitty-apt" name="scite-13" rel="nofollow" target="_blank">
        Dahan, A. (2017, May 24). OPERATION COBALT KITTY: A LARGE-SCALE APT IN ASIA CARRIED OUT BY THE OCEANLOTUS GROUP. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://cdn2.hubspot.net/hubfs/3354902/Cybereason%20Labs%20Analysis%20Operation%20Cobalt%20Kitty.pdf" name="scite-14" rel="nofollow" target="_blank">
        Dahan, A. (2017). Operation Cobalt Kitty. Retrieved December 27, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2019/03/20/fake-or-fake-keeping-up-with-oceanlotus-decoys/" name="scite-15" rel="nofollow" target="_blank">
        Dumont, R. (2019, March 20). Fake or Fake: Keeping up with OceanLotus decoys. Retrieved April 1, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/elfin-apt33-espionage" name="scite-16" rel="nofollow" target="_blank">
        Security Response attack Investigation Team. (2019, March 27). Elfin: Relentless Espionage Group Targets Multiple Organizations in Saudi Arabia and U.S.. Retrieved April 10, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" name="scite-17" rel="nofollow" target="_blank">
        FireEye. (2018, February 20). APT37 (Reaper): The Overlooked North Korean Actor. Retrieved March 1, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/01/korea-in-crosshairs.html" name="scite-18" rel="nofollow" target="_blank">
        Mercer, W., Rascagneres, P. (2018, January 16). Korea In The Crosshairs. Retrieved May 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2019/01/apt39-iranian-cyber-espionage-group-focused-on-personal-information.html" name="scite-19" rel="nofollow" target="_blank">
        Hawley et al. (2019, January 29). APT39: An Iranian Cyber Espionage Group Focused on Personal Information. Retrieved February 19, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://cofense.com/seeing-resurgence-demonic-astaroth-wmic-trojan/" name="scite-20" rel="nofollow" target="_blank">
        Doaty, J., Garrett, P.. (2018, September 10). We’re Seeing a Resurgence of the Demonic Astaroth WMIC Trojan. Retrieved April 17, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/Dragonfly_Threat_Against_Western_Energy_Suppliers.pdf" name="scite-21" rel="nofollow" target="_blank">
        Symantec Security Response. (2014, July 7). Dragonfly: Cyberespionage Attacks Against Energy Suppliers. Retrieved April 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/fireye/images/rpt-apt30.pdf" name="scite-22" rel="nofollow" target="_blank">
        FireEye Labs. (2015, April). APT30 AND THE MECHANICS OF A LONG-RUNNING CYBER ESPIONAGE OPERATION. Retrieved May 1, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-23">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" name="scite-23" rel="nofollow" target="_blank">
        Settle, A., et al. (2016, August 8). MONSOON - Analysis Of An APT Campaign. Retrieved September 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-24">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/10/unit42-badpatch/" name="scite-24" rel="nofollow" target="_blank">
        Bar, T., Conant, S. (2017, October 20). BadPatch. Retrieved November 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-25">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-bisonal-malware-used-attacks-russia-south-korea/" name="scite-25" rel="nofollow" target="_blank">
        Hayashi, K., Ray, V. (2018, July 31). Bisonal Malware Used in Attacks Against Russia and South Korea. Retrieved August 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-26">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.f-secure.com/documents/996508/1030745/blackenergy_whitepaper.pdf" name="scite-26" rel="nofollow" target="_blank">
        F-Secure Labs. (2014). BlackEnergy &amp; Quedagh: The convergence of crimeware and APT attacks. Retrieved March 24, 2016.
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
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/06/behind-the-carbanak-backdoor.html" name="scite-29" rel="nofollow" target="_blank">
        Bennett, J., Vengerik, B. (2017, June 12). Behind the CARBANAK Backdoor. Retrieved June 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-30">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/04/unit42-cardinal-rat-active-two-years/" name="scite-30" rel="nofollow" target="_blank">
        Grunzweig, J.. (2017, April 20). Cardinal RAT Active for Over Two Years. Retrieved December 8, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-31">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" name="scite-31" rel="nofollow" target="_blank">
        PwC and BAE Systems. (2017, April). Operation Cloud Hopper: Technical Annex. Retrieved April 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-32">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.group-ib.com/blog/cobalt" name="scite-32" rel="nofollow" target="_blank">
        Matveeva, V. (2017, August 15). Secrets of Cobalt. Retrieved October 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-33">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.zscaler.com/blogs/research/cobian-rat-backdoored-rat" name="scite-33" rel="nofollow" target="_blank">
        Yadav, A., et al. (2017, August 31). Cobian RAT – A backdoored RAT. Retrieved November 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-34">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/01/unit42-comnie-continues-target-organizations-east-asia/" name="scite-34" rel="nofollow" target="_blank">
        Grunzweig, J. (2018, January 31). Comnie Continues to Target Organizations in East Asia. Retrieved June 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-35">
      <span class="scite-citation-text">
       <a class="external text" href="http://download.microsoft.com/download/4/4/C/44CDEF0E-7924-4787-A56A-16261691ACE3/Microsoft_Security_Intelligence_Report_Volume_19_English.pdf" name="scite-35" rel="nofollow" target="_blank">
        Anthe, C. et al. (2015, October 19). Microsoft Security Intelligence Report Volume 19. Retrieved December 23, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-36">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.f-secure.com/documents/996508/1030745/CozyDuke" name="scite-36" rel="nofollow" target="_blank">
        F-Secure Labs. (2015, April 22). CozyDuke: Malware Analysis. Retrieved December 10, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-37">
      <span class="scite-citation-text">
       <a class="external text" href="https://info.lookout.com/rs/051-ESQ-475/images/Lookout_Dark-Caracal_srr_20180118_us_v.1.0.pdf" name="scite-37" rel="nofollow" target="_blank">
        Blaich, A., et al. (2018, January 18). Dark Caracal: Cyber-espionage at a Global Scale. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-38">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.trendmicro.com/vinfo/us/threat-encyclopedia/malware/DARKCOMET" name="scite-38" rel="nofollow" target="_blank">
        TrendMicro. (2014, September 03). DARKCOMET. Retrieved November 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-39">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.malwarebytes.com/threat-analysis/2012/06/you-dirty-rat-part-1-darkcomet/" name="scite-39" rel="nofollow" target="_blank">
        Kujawa, A. (2018, March 27). You dirty RAT! Part 1: DarkComet. Retrieved November 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-40">
      <span class="scite-citation-text">
       <a class="external text" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08070903/darkhotel_kl_07.11.pdf" name="scite-40" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2014, November). The Darkhotel APT A Story of Unusual Hospitality. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-41">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.clearskysec.com/wp-content/uploads/2017/12/Charming_Kitten_2017.pdf" name="scite-41" rel="nofollow" target="_blank">
        ClearSky Cyber Security. (2017, December). Charming Kitten. Retrieved December 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-42">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" name="scite-42" rel="nofollow" target="_blank">
        US-CERT. (2018, March 16). Alert (TA18-074A): Russian Government Cyber Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-43">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.clearskysec.com/wp-content/uploads/2016/01/Operation%20DustySky_TLP_WHITE.pdf" name="scite-43" rel="nofollow" target="_blank">
        ClearSky. (2016, January 7). Operation DustySky. Retrieved January 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-44">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.paloaltonetworks.com/resources/research/unit42-operation-lotus-blossom.html" name="scite-44" rel="nofollow" target="_blank">
        Falcone, R., et al.. (2015, June 16). Operation Lotus Blossom. Retrieved February 15, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-45">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.accenture.com/t20180127T003755Z_w_/us-en/_acnmedia/PDF-46/Accenture-Security-Dragonfish-Threat-Analysis.pdf" name="scite-45" rel="nofollow" target="_blank">
        Accenture Security. (2018, January 27). DRAGONFISH DELIVERS NEW FORM OF ELISE MALWARE TARGETING ASEAN DEFENCE MINISTERS’ MEETING AND ASSOCIATES. Retrieved November 14, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-46">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/02/emissary-trojan-changelog-did-operation-lotus-blossom-cause-it-to-evolve/" name="scite-46" rel="nofollow" target="_blank">
        Falcone, R. and Miller-Osborn, J.. (2016, February 3). Emissary Trojan Changelog: Did Operation Lotus Blossom Cause It to Evolve?. Retrieved February 15, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-47">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/evolution-emotet-trojan-distributor" name="scite-47" rel="nofollow" target="_blank">
        Symantec. (2018, July 18). The Evolution of Emotet: From Banking Trojan to Threat Distributor. Retrieved March 25, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-48">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA18-201A" name="scite-48" rel="nofollow" target="_blank">
        US-CERT. (2018, July 20). Alert (TA18-201A) Emotet Malware. Retrieved March 25, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-49">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.picussecurity.com/blog/the-christmas-card-you-never-wanted-a-new-wave-of-emotet-is-back-to-wreak-havoc.html" name="scite-49" rel="nofollow" target="_blank">
        Özarslan, S. (2018, December 21). The Christmas Card you never wanted - A new wave of Emotet is back to wreak havoc. Retrieved March 25, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-50">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellEmpire/Empire" name="scite-50" rel="nofollow" target="_blank">
        Schroeder, W., Warner, J., Nelson, M. (n.d.). Github PowerShellEmpire. Retrieved April 28, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-51">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2018/10/ESET_GreyEnergy.pdf" name="scite-51" rel="nofollow" target="_blank">
        Cherepanov, A. (2018, October). GREYENERGY A successor to BlackEnergy. Retrieved November 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-52">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin10.pdf" name="scite-52" rel="nofollow" target="_blank">
        FireEye iSIGHT Intelligence. (2017, June 16). FIN10: Anatomy of a Cyber Extortion Operation. Retrieved June 25, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-53">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin6.pdf" name="scite-53" rel="nofollow" target="_blank">
        FireEye Threat Intelligence. (2016, April). Follow the Money: Dissecting the Operations of the Cyber Crime Group FIN6. Retrieved June 1, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-54">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/04/fin7-phishing-lnk.html" name="scite-54" rel="nofollow" target="_blank">
        Carr, N., et al. (2017, April 24). FIN7 Evolution and the Phishing LNK. Retrieved April 24, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-55">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/08/fin7-pursuing-an-enigmatic-and-evasive-global-criminal-operation.html" name="scite-55" rel="nofollow" target="_blank">
        Carr, N., et al. (2018, August 01). On the Hunt for FIN7: Pursuing an Enigmatic and Evasive Global Criminal Operation. Retrieved August 23, 2018.
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
       <a class="external text" href="http://www.finfisher.com/FinFisher/index.html" name="scite-57" rel="nofollow" target="_blank">
        FinFisher. (n.d.). Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-58">
      <span class="scite-citation-text">
       <a class="external text" href="https://cloudblogs.microsoft.com/microsoftsecure/2018/03/01/finfisher-exposed-a-researchers-tale-of-defeating-traps-tricks-and-complex-virtual-machines/" name="scite-58" rel="nofollow" target="_blank">
        Allievi, A.,Flori, E. (2018, March 01). FinFisher exposed: A researcher’s tale of defeating traps, tricks, and complex virtual machines. Retrieved July 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-59">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf" name="scite-59" rel="nofollow" target="_blank">
        ESET. (2017, August). Gazing at Gazer: Turla’s new second stage backdoor. Retrieved September 14, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-60">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/introducing-whitebear/81638/" name="scite-60" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research &amp; Analysis Team. (2017, August 30). Introducing WhiteBear. Retrieved September 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-61">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.nccgroup.trust/us/about-us/newsroom-and-events/blog/2018/april/decoding-network-data-from-a-gh0st-rat-variant/" name="scite-61" rel="nofollow" target="_blank">
        Pantazopoulos, N. (2018, April 17). Decoding network data from a Gh0st RAT variant. Retrieved November 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-62">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/gold-dragon-widens-olympics-malware-attacks-gains-permanent-presence-on-victims-systems/" name="scite-62" rel="nofollow" target="_blank">
        Sherstobitoff, R., Saavedra-Morales, J. (2018, February 02). Gold Dragon Widens Olympics Malware Attacks, Gains Permanent Presence on Victims’ Systems. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-63">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/08/unit42-gorgon-group-slithering-nation-state-cybercrime/" name="scite-63" rel="nofollow" target="_blank">
        Falcone, R., et al. (2018, August 02). The Gorgon Group: Slithering Between Nation State and Cybercrime. Retrieved August 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-64">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/05/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/" name="scite-64" rel="nofollow" target="_blank">
        Falcone, R. and Lee, B.. (2016, May 26). The OilRig Campaign: Attacks on Saudi Arabian Organizations Deliver Helminth Backdoor. Retrieved May 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-65">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fidelissecurity.com/sites/default/files/FTA_1020_Fidelis_Inocnation_FINAL_0.pdf" name="scite-65" rel="nofollow" target="_blank">
        Fidelis Cybersecurity. (2015, December 16). Fidelis Threat Advisory #1020: Dissecting the Malware Involved in the INOCNATION Campaign. Retrieved March 24, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-66">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/mcafee-uncovers-operation-honeybee-malicious-document-campaign-targeting-humanitarian-aid-groups/" name="scite-66" rel="nofollow" target="_blank">
        Sherstobitoff, R. (2018, March 02). McAfee Uncovers Operation Honeybee, a Malicious Document Campaign Targeting Humanitarian Aid Groups. Retrieved May 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-67">
      <span class="scite-citation-text">
       <a class="external text" href="http://research.zscaler.com/2015/08/chinese-cyber-espionage-apt-group.html" name="scite-67" rel="nofollow" target="_blank">
        Desai, D.. (2015, August 14). Chinese cyber espionage APT group leveraging recently leaked Hacking Team exploits to target a Financial Services Firm. Retrieved January 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-68">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.threatstream.com/blog/evasive-maneuvers-the-wekby-group-attempts-to-evade-analysis-via-custom-rop" name="scite-68" rel="nofollow" target="_blank">
        Shelmire, A.. (2015, July 6). Evasive Maneuvers. Retrieved January 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-69">
      <span class="scite-citation-text">
       <a class="external text" href="https://asert.arbornetworks.com/innaput-actors-utilize-remote-access-trojan-since-2016-presumably-targeting-victim-files/" name="scite-69" rel="nofollow" target="_blank">
        ASERT Team. (2018, April 04). Innaput Actors Utilize Remote Access Trojan Since 2016, Presumably Targeting Victim Files. Retrieved July 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-70">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part1.pdf" name="scite-70" rel="nofollow" target="_blank">
        ESET. (2016, October). En Route with Sednit - Part 1: Approaching the Target. Retrieved November 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-71">
      <span class="scite-citation-text">
       <a class="external text" href="http://research.zscaler.com/2016/01/malicious-office-files-dropping-kasidet.html" name="scite-71" rel="nofollow" target="_blank">
        Yadav, A., et al. (2016, January 29). Malicious Office files dropping Kasidet and Dridex. Retrieved March 24, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="72.0">
    <li>
     <span class="scite-citation" id="scite-72">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.microsoft.com/security/portal/threat/encyclopedia/entry.aspx?Name=Win32%2FKasidet" name="scite-72" rel="nofollow" target="_blank">
        Manuel, J. and Plantado, R.. (2015, August 9). Win32/Kasidet. Retrieved March 24, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-73">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/05/unit42-kazuar-multiplatform-espionage-backdoor-api-access/" name="scite-73" rel="nofollow" target="_blank">
        Levene, B, et al. (2017, May 03). Kazuar: Multiplatform Espionage Backdoor with API Access. Retrieved July 17, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-74">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/" name="scite-74" rel="nofollow" target="_blank">
        Smallridge, R. (2018, March 10). APT15 is alive and strong: An analysis of RoyalCli and RoyalDNS. Retrieved April 4, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-75">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2017/05/konni-malware-under-radar-for-years.html" name="scite-75" rel="nofollow" target="_blank">
        Rascagneres, P. (2017, May 03). KONNI: A Malware Under The Radar For Years. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-76">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" name="scite-76" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Unraveling the Long Thread of the Sony Attack. Retrieved February 25, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-77">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-RAT-and-Staging-Report.pdf" name="scite-77" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Remote Administration Tools &amp; Content Staging Malware Report. Retrieved March 16, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-78">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/lazarus-resurfaces-targets-global-banks-bitcoin-users/" name="scite-78" rel="nofollow" target="_blank">
        Sherstobitoff, R. (2018, February 12). Lazarus Resurfaces, Targets Global Banks and Bitcoin Users. Retrieved February 19, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-79">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" name="scite-79" rel="nofollow" target="_blank">
        Axel F, Pierre T. (2017, October 16). Leviathan: Espionage actor spearphishes maritime and defense targets. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-80">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" name="scite-80" rel="nofollow" target="_blank">
        FireEye. (2018, March 16). Suspected Chinese Cyber Espionage Group (TEMP.Periscope) Targeting U.S. Engineering and Maritime Industries. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-81">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/02/unit42-magic-hound-campaign-attacks-saudi-targets/" name="scite-81" rel="nofollow" target="_blank">
        Lee, B. and Falcone, R. (2017, February 15). Magic Hound Campaign Attacks Saudi Targets. Retrieved December 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-82">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.clearskysec.com/wp-content/uploads/2017/07/Operation_Wilted_Tulip.pdf" name="scite-82" rel="nofollow" target="_blank">
        ClearSky Cyber Security and Trend Micro. (2017, July). Operation Wilted Tulip: Exposing a cyber espionage apparatus. Retrieved August 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-83">
      <span class="scite-citation-text">
       <a class="external text" href="https://s3-eu-west-1.amazonaws.com/minervaresearchpublic/CopyKittens/CopyKittens.pdf" name="scite-83" rel="nofollow" target="_blank">
        Minerva Labs LTD and ClearSky Cyber Security. (2015, November 23). CopyKittens Attack Group. Retrieved September 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-84">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/security_response/writeup.jsp?docid=2015-020623-0740-99&amp;tabid=2" name="scite-84" rel="nofollow" target="_blank">
        Stama, D.. (2015, February 6). Backdoor.Mivast. Retrieved February 15, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-85">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2018/01/ESET_Turla_Mosquito.pdf" name="scite-85" rel="nofollow" target="_blank">
        ESET, et al. (2018, January). Diplomats in Eastern Europe bitten by a Turla mosquito. Retrieved July 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-86">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html" name="scite-86" rel="nofollow" target="_blank">
        Singh, S. et al.. (2018, March 13). Iranian Threat Group Updates Tactics, Techniques and Procedures in Spear Phishing Campaign. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-87">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/muddywater/88059/" name="scite-87" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research &amp; Analysis Team. (2018, October 10). MuddyWater expands operations. Retrieved November 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-88">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.f-secure.com/documents/996508/1030745/nanhaishu_whitepaper.pdf" name="scite-88" rel="nofollow" target="_blank">
        F-Secure Labs. (2016, July). NANHAISHU RATing the South China Sea. Retrieved July 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-89">
      <span class="scite-citation-text">
       <a class="external text" href="https://cofense.com/nanocore-rat-resurfaced-sewers/" name="scite-89" rel="nofollow" target="_blank">
        Patel, K. (2018, March 02). The NanoCore RAT Has Resurfaced From the Sewers. Retrieved November 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-90">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/05/navrat.html" name="scite-90" rel="nofollow" target="_blank">
        Mercer, W., Rascagneres, P. (2018, May 31). NavRAT Uses US-North Korea Summit As Decoy For Attacks In South Korea. Retrieved June 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-91">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/netwire-rat-behind-recent-targeted-attacks/" name="scite-91" rel="nofollow" target="_blank">
        McAfee. (2015, March 2). Netwire RAT Behind Recent Targeted Attacks. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-92">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/09/unit42-new-konni-malware-attacking-eurasia-southeast-asia/" name="scite-92" rel="nofollow" target="_blank">
        Grunzweig, J., Lee, B. (2018, September 27). New KONNI Malware attacking Eurasia and Southeast Asia. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-93">
      <span class="scite-citation-text">
       <a class="external text" href="https://s3-us-west-2.amazonaws.com/cymmetria-blog/public/Unveiling_Patchwork.pdf" name="scite-93" rel="nofollow" target="_blank">
        Cymmetria. (2016). Unveiling Patchwork - The Copy-Paste APT. Retrieved August 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-94">
      <span class="scite-citation-text">
       <a class="external text" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" name="scite-94" rel="nofollow" target="_blank">
        Lunghi, D., et al. (2017, December). Untangling the Patchwork Cyberespionage Group. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-95">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/05/unit42-new-wekby-attacks-use-dns-requests-as-command-and-control-mechanism/" name="scite-95" rel="nofollow" target="_blank">
        Grunzweig, J., et al. (2016, May 24). New Wekby Attacks Use DNS Requests As Command and Control Mechanism. Retrieved August 17, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-96">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-rancor-targeted-attacks-south-east-asia-using-plaintee-ddkong-malware-families/" name="scite-96" rel="nofollow" target="_blank">
        Ash, B., et al. (2018, June 26). RANCOR: Targeted Attacks in South East Asia Using PLAINTEE and DDKONG Malware Families. Retrieved July 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-97">
      <span class="scite-citation-text">
       <a class="external text" href="http://labs.lastline.com/an-analysis-of-plugx" name="scite-97" rel="nofollow" target="_blank">
        Vasilenko, R. (2013, December 17). An Analysis of PlugX Malware. Retrieved November 24, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-98">
      <span class="scite-citation-text">
       <a class="external text" href="http://circl.lu/assets/files/tr-12/tr-12-circl-plugx-analysis-v1.pdf" name="scite-98" rel="nofollow" target="_blank">
        Computer Incident Response Center Luxembourg. (2013, March 29). Analysis of a PlugX variant. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-99">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2005-081910-3934-99" name="scite-99" rel="nofollow" target="_blank">
        Hayashi, K. (2005, August 18). Backdoor.Darkmoon. Retrieved February 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-100">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.volexity.com/blog/2016/11/09/powerduke-post-election-spear-phishing-campaigns-targeting-think-tanks-and-ngos/" name="scite-100" rel="nofollow" target="_blank">
        Adair, S.. (2016, November 9). PowerDuke: Widespread Post-Election Spear Phishing Campaigns Targeting Think Tanks and NGOs. Retrieved January 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-101">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.talosintelligence.com/2017/03/dnsmessenger.html" name="scite-101" rel="nofollow" target="_blank">
        Brumaghin, E. and Grady, C.. (2017, March 2). Covert Channels and Poor Decisions: The Tale of DNSMessenger. Retrieved March 8, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-102">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellMafia/PowerSploit" name="scite-102" rel="nofollow" target="_blank">
        PowerShellMafia. (2012, May 26). PowerSploit - A PowerShell Post-Exploitation Framework. Retrieved February 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-103">
      <span class="scite-citation-text">
       <a class="external text" href="http://powersploit.readthedocs.io" name="scite-103" rel="nofollow" target="_blank">
        PowerSploit. (n.d.). PowerSploit. Retrieved February 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-104">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/12/overruled-containing-a-potentially-destructive-adversary.html" name="scite-104" rel="nofollow" target="_blank">
        Ackerman, G., et al. (2018, December 21). OVERRULED: Containing a Potentially Destructive Adversary. Retrieved January 17, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-105">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.welivesecurity.com/wp-content/uploads/2016/05/Operation-Groundbait.pdf" name="scite-105" rel="nofollow" target="_blank">
        Cherepanov, A.. (2016, May 17). Operation Groundbait: Analysis of a surveillance toolkit. Retrieved May 18, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-106">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/02/unit-42-title-gamaredon-group-toolset-evolution/" name="scite-106" rel="nofollow" target="_blank">
        Kasza, A. and Reichel, D.. (2017, February 27). The Gamaredon Group Toolset Evolution. Retrieved March 1, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-107">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" name="scite-107" rel="nofollow" target="_blank">
        Elovitz, S. &amp; Ahl, I. (2016, August 18). Know Your Enemy:  New Financially-Motivated &amp; Spear-Phishing Group. Retrieved February 26, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-108">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/n1nj4sec/pupy" name="scite-108" rel="nofollow" target="_blank">
        Nicolas Verdier. (n.d.). Retrieved January 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-109">
      <span class="scite-citation-text">
       <a class="external text" href="http://cdn0.vox-cdn.com/assets/4589853/crowdstrike-intelligence-report-putter-panda.original.pdf" name="scite-109" rel="nofollow" target="_blank">
        Crowdstrike Global Intelligence Team. (2014, June 9). CrowdStrike Intelligence Report: Putter Panda. Retrieved January 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-110">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-new-malware-with-ties-to-sunorcal-discovered/" name="scite-110" rel="nofollow" target="_blank">
        Grunzweig, J. and Miller-Osborn, J. (2017, November 10). New Malware with Ties to SunOrcal Discovered. Retrieved November 16, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-111">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.accenture.com/t20180423T055005Z_w_/se-en/_acnmedia/PDF-76/Accenture-Hogfish-Threat-Analysis.pdf" name="scite-111" rel="nofollow" target="_blank">
        Accenture Security. (2018, April 23). Hogfish Redleaves Campaign. Retrieved July 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-112">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fortinet.com/blog/threat-research/remcos-a-new-rat-in-the-wild-2.html" name="scite-112" rel="nofollow" target="_blank">
        Bacurio, F., Salvio, J. (2017, February 14). REMCOS: A New RAT In The Wild. Retrieved November 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-113">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/chafer-used-remexi-malware/89538/" name="scite-113" rel="nofollow" target="_blank">
        Legezo, D. (2019, January 30). Chafer used Remexi malware to spy on Iran-based foreign diplomatic entities. Retrieved April 17, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-114">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-new-threat-actor-group-darkhydrus-targets-middle-east-government/" name="scite-114" rel="nofollow" target="_blank">
        Falcone, R., et al. (2018, July 27). New Threat Actor Group DarkHydrus Targets Middle East Government. Retrieved August 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-115">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/02/new-malware-rover-targets-indian-ambassador-to-afghanistan/" name="scite-115" rel="nofollow" target="_blank">
        Ray, V., Hayashi, K. (2016, February 29). New Malware ‘Rover’ Targets Indian Ambassador to Afghanistan. Retrieved February 29, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-116">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2017/02/Read-The-Manual.pdf" name="scite-116" rel="nofollow" target="_blank">
        Faou, M. and Boutin, J.. (2017, February). Read The Manual: A Guide to the RTM Banking Trojan. Retrieved March 9, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-117">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cylance.com/content/dam/cylance/pdfs/reports/Op_Dust_Storm_Report.pdf" name="scite-117" rel="nofollow" target="_blank">
        Gross, J. (2016, February 23). Operation Dust Storm. Retrieved September 19, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-118">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.secureworks.com/cyber-threat-intelligence/threats/sakula-malware-family/" name="scite-118" rel="nofollow" target="_blank">
        Dell SecureWorks Counter Threat Unit Threat Intelligence. (2015, July 30). Sakula Malware Family. Retrieved January 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-119">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2015/07/unit-42-technical-analysis-seaduke/" name="scite-119" rel="nofollow" target="_blank">
        Grunzweig, J.. (2015, July 14). Unit 42 Technical Analysis: Seaduke. Retrieved August 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-120">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.mcafee.com/enterprise/en-us/assets/reports/rp-operation-oceansalt.pdf" name="scite-120" rel="nofollow" target="_blank">
        Sherstobitoff, R., Malhotra, A. (2018, October 18). ‘Operation Oceansalt’ Attacks South Korea, U.S., and Canada With Source Code From Chinese Hacker Group. Retrieved November 30, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-121">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.malwarebytes.com/threat-analysis/2016/08/smoke-loader-downloader-with-a-smokescreen-still-alive/" name="scite-121" rel="nofollow" target="_blank">
        Hasherezade. (2016, September 12). Smoke Loader – downloader with a smokescreen still alive. Retrieved March 20, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-122">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/04/apt10_menupass_grou.html" name="scite-122" rel="nofollow" target="_blank">
        FireEye iSIGHT Intelligence. (2017, April 6). APT10 (MenuPass Group): New Tools, Global Campaign Latest Manifestation of Longstanding Threat. Retrieved June 29, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-123">
      <span class="scite-citation-text">
       <a class="external text" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07205555/TheNaikonAPT-MsnMM1.pdf" name="scite-123" rel="nofollow" target="_blank">
        Baumgartner, K., Golovkin, M.. (2015, May). The MsnMM Campaigns: The Earliest Naikon APT Campaigns. Retrieved April 10, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-124">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.alienvault.com/open-threat-exchange/blog/new-sykipot-developments" name="scite-124" rel="nofollow" target="_blank">
        Blasco, J. (2013, March 21). New Sykipot developments [Blog]. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-125">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/may/emissary-panda-a-potential-new-malicious-tool/" name="scite-125" rel="nofollow" target="_blank">
        Pantazopoulos, N., Henry T. (2018, May 18). Emissary Panda – A potential new malicious tool. Retrieved June 25, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-126">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf" name="scite-126" rel="nofollow" target="_blank">
        Cylance. (2014, December). Operation Cleaver. Retrieved September 14, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-127">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/trickbot-shows-off-new-trick-password-grabber-module/" name="scite-127" rel="nofollow" target="_blank">
        Anthony, N., Pascual, C.. (2018, November 1). Trickbot Shows Off New Trick: Password Grabber Module. Retrieved November 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-128">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.microsoft.com/en-us/wdsi/threats/malware-encyclopedia-description?Name=Backdoor:Win32/Truvasys.A!dha" name="scite-128" rel="nofollow" target="_blank">
        Microsoft. (2017, September 15). Backdoor:Win32/Truvasys.A!dha. Retrieved November 30, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-129">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2018/05/22/turla-mosquito-shift-towards-generic-tools/" name="scite-129" rel="nofollow" target="_blank">
        ESET Research. (2018, May 22). Turla Mosquito: A shift towards more generic tools. Retrieved July 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-130">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cyberbit.com/blog/endpoint-security/new-early-bird-code-injection-technique-discovered/" name="scite-130" rel="nofollow" target="_blank">
        Gavriel, H. &amp; Erbesfeld, B. (2018, April 11). New ‘Early Bird’ Code Injection Technique Discovered. Retrieved May 24, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-131">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.welivesecurity.com/2014/11/11/sednit-espionage-group-attacking-air-gapped-networks/" name="scite-131" rel="nofollow" target="_blank">
        Calvet, J. (2014, November 11). Sednit Espionage Group Attacking Air-Gapped Networks. Retrieved January 4, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-132">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051606-5938-99" name="scite-132" rel="nofollow" target="_blank">
        Zhou, R. (2012, May 15). Backdoor.Vasport. Retrieved February 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-133">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/09/unit42-xbash-combines-botnet-ransomware-coinmining-worm-targets-linux-windows/" name="scite-133" rel="nofollow" target="_blank">
        Xiao, C. (2018, September 17). Xbash Combines Botnet, Ransomware, Coinmining in Worm that Targets Linux and Windows. Retrieved November 14, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-134">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2018/11/20/sednit-whats-going-zebrocy/" name="scite-134" rel="nofollow" target="_blank">
        ESET. (2018, November 20). Sednit: What’s going on with Zebrocy?. Retrieved February 12, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-135">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2017/11/zeus-panda-campaign.html#More" name="scite-135" rel="nofollow" target="_blank">
        Brumaghin, E., et al. (2017, November 02). Poisoning the Well: Banking Trojan Targets Google Search Results. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-136">
      <span class="scite-citation-text">
       <a class="external text" href="https://cyberwtf.files.wordpress.com/2017/07/panda-whitepaper.pdf" name="scite-136" rel="nofollow" target="_blank">
        Ebach, L. (2017, June 22). Analysis Results of Zeus.Variant.Panda. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-137">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-137" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-138">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-138" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-139">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-139" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-140">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" name="scite-140" rel="nofollow" target="_blank">
        Corio, C., &amp; Sayana, D. P. (2008, June). Application Lockdown with Software Restriction Policies. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-141">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" name="scite-141" rel="nofollow" target="_blank">
        Microsoft. (2012, June 27). Using Software Restriction Policies and AppLocker Policies. Retrieved April 7, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-142">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/sysinternals/bb963902" name="scite-142" rel="nofollow" target="_blank">
        Russinovich, M. (2016, January 4). Autoruns for Windows v13.51. Retrieved June 6, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
