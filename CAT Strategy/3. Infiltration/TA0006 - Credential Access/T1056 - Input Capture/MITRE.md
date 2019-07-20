<div class="container-fluid">
 <h1>
  Input Capture
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries can use methods of capturing user input for obtaining credentials for
    <a href="https://attack.mitre.org/techniques/T1078">
     Valid Accounts
    </a>
    and information Collection that include keylogging and user input field interception.
   </p>
   <p>
    Keylogging is the most prevalent type of input capture, with many different ways of intercepting keystrokes,
    <span class="scite-citeref-number" data-reference="Adventures of a Keystroke" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://opensecuritytraining.info/Keylogging_files/The%20Adventures%20of%20a%20Keystroke.pdf" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    but other methods exist to target information for specific purposes, such as performing a UAC prompt or wrapping the Windows default credential provider.
    <span class="scite-citeref-number" data-reference="Wrightson 2012" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="http://blog.leetsys.com/2012/01/02/capturing-windows-7-credentials-at-logon-using-custom-credential-provider/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Keylogging is likely to be used to acquire credentials for new access opportunities when
    <a href="https://attack.mitre.org/techniques/T1003">
     Credential Dumping
    </a>
    efforts are not effective, and may require an adversary to remain passive on a system for a period of time before an opportunity arises.
   </p>
   <p>
    Adversaries may also install code on externally facing portals, such as a VPN login page, to capture and transmit credentials of users who attempt to log into the service. This variation on input capture may be conducted post-compromise using legitimate administrative access as a backup measure to maintain network access through
    <a href="https://attack.mitre.org/techniques/T1133">
     External Remote Services
    </a>
    and
    <a href="https://attack.mitre.org/techniques/T1078">
     Valid Accounts
    </a>
    or as part of the initial compromise by exploitation of the externally facing web service.
    <span class="scite-citeref-number" data-reference="Volexity Virtual Private Keylogging" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.volexity.com/blog/2015/10/07/virtual-private-keylogging-cisco-web-vpns-leveraged-for-access-and-persistence/" target="_blank">
       [3]
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
      : T1056
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
      : Collection, Credential Access
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
      Administrator, SYSTEM
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
      Windows Registry, Kernel drivers, Process monitoring, API monitoring
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
      <a href="https://capec.mitre.org/data/definitions/569.html" target="_blank">
       CAPEC-569
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
      John Lambert, Microsoft Threat Intelligence Center
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
      can perform keylogging.
      <span class="scite-citeref-number" data-reference="ESET Sednit Part 2" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part-2.pdf" target="_blank">
         [4]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Bitdefender APT28 Dec 2015" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://download.bitdefender.com/resources/media/materials/white-papers/en/Bitdefender_In-depth_analysis_of_APT28%E2%80%93The_Political_Cyber-Espionage.pdf" target="_blank">
         [5]
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
      can log keystrokes on the victim’s machine.
      <span class="scite-citeref-number" data-reference="Talos Agent Tesla Oct 2018" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://blog.talosintelligence.com/2018/10/old-dog-new-tricks-analysing-new-rtf_15.html" target="_blank">
         [6]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="DigiTrust Agent Tesla Jan 2017" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.digitrustgroup.com/agent-tesla-keylogger/" target="_blank">
         [7]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Fortinet Agent Tesla June 2017" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.fortinet.com/blog/threat-research/in-depth-analysis-of-net-malware-javaupdtr.html" target="_blank">
         [8]
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
      has used tools to perform keylogging.
      <span class="scite-citeref-number" data-reference="Microsoft SIR Vol 19" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="http://download.microsoft.com/download/4/4/C/44CDEF0E-7924-4787-A56A-16261691ACE3/Microsoft_Security_Intelligence_Report_Volume_19_English.pdf" target="_blank">
         [9]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="DOJ GRU Indictment Jul 2018" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www.justice.gov/file/1080281/download" target="_blank">
         [10]
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
      has used a keylogging tool that records keystrokes in encrypted files.
      <span class="scite-citeref-number" data-reference="Symantec Buckeye" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="http://www.symantec.com/connect/blogs/buckeye-cyberespionage-group-shifts-gaze-us-hong-kong" target="_blank">
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
      used a Trojan called KEYLIME to capture keystrokes from the victim’s machine.
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
      logs keystrokes from the victim's machine.
      <span class="scite-citeref-number" data-reference="Cofense Astaroth Sept 2018" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://cofense.com/seeing-resurgence-demonic-astaroth-wmic-trojan/" target="_blank">
         [13]
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
      When it first starts,
      <a href="https://attack.mitre.org/software/S0128">
       BADNEWS
      </a>
      spawns a new thread to log keystrokes.
      <span class="scite-citeref-number" data-reference="Forcepoint Monsoon" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" target="_blank">
         [14]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PaloAlto Patchwork Mar 2018" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://researchcenter.paloaltonetworks.com/2018/03/unit42-patchwork-continues-deliver-badnews-indian-subcontinent/" target="_blank">
         [15]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="TrendMicro Patchwork Dec 2017" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" target="_blank">
         [16]
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
      has a keylogging capability.
      <span class="scite-citeref-number" data-reference="Unit 42 BadPatch Oct 2017" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://researchcenter.paloaltonetworks.com/2017/10/unit42-badpatch/" target="_blank">
         [17]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0234">
      Bandook
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0234">
       Bandook
      </a>
      contains keylogging capabilities
      <span class="scite-citeref-number" data-reference="BH Manul Aug 2016" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="https://www.blackhat.com/docs/us-16/materials/us-16-Quintin-When-Governments-Attack-State-Sponsored-Malware-Attacks-Against-Activists-Lawyers-And-Journalists.pdf" target="_blank">
         [18]
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
      can capture keystrokes.
      <span class="scite-citeref-number" data-reference="Mandiant APT1 Appendix" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report-appendix.zip" target="_blank">
         [19]
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
      has run a keylogger plug-in on a victim.
      <span class="scite-citeref-number" data-reference="Securelist BlackEnergy Nov 2014" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://securelist.com/be2-custom-plugins-router-abuse-and-target-profiles/67353/" target="_blank">
         [20]
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
      logs key strokes for configured processes and sends them back to the C2 server.
      <span class="scite-citeref-number" data-reference="Kaspersky Carbanak" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08064518/Carbanak_APT_eng.pdf" target="_blank">
         [21]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye CARBANAK June 2017" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="https://www.fireeye.com/blog/threat-research/2017/06/behind-the-carbanak-backdoor.html" target="_blank">
         [22]
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
      can log keystrokes.
      <span class="scite-citeref-number" data-reference="PaloAlto CardinalRat Apr 2017" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="https://researchcenter.paloaltonetworks.com/2017/04/unit42-cardinal-rat-active-two-years/" target="_blank">
         [23]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0261">
      Catchamas
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0261">
       Catchamas
      </a>
      collects keystrokes from the victim’s machine.
      <span class="scite-citeref-number" data-reference="Symantec Catchamas April 2018" id="scite-ref-24-a" onclick="scrollToRef('scite-24')">
       <sup>
        <a aria-describedby="qtip-23" data-hasqtip="23" href="https://www-west.symantec.com/content/symantec/english/en/security-center/writeup.html/2018-040209-1742-99" target="_blank">
         [24]
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
      is capable of performing keylogging.
      <span class="scite-citeref-number" data-reference="Crowdstrike DNC June 2016" id="scite-ref-25-a" onclick="scrollToRef('scite-25')">
       <sup>
        <a aria-describedby="qtip-24" data-hasqtip="24" href="https://www.crowdstrike.com/blog/bears-midst-intrusion-democratic-national-committee/" target="_blank">
         [25]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="ESET Sednit Part 2" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part-2.pdf" target="_blank">
         [4]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="DOJ GRU Indictment Jul 2018" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www.justice.gov/file/1080281/download" target="_blank">
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
      can track key presses with a keylogger module.
      <span class="scite-citeref-number" data-reference="cobaltstrike manual" id="scite-ref-26-a" onclick="scrollToRef('scite-26')">
       <sup>
        <a aria-describedby="qtip-25" data-hasqtip="25" href="https://cobaltstrike.com/downloads/csmanual38.pdf" target="_blank">
         [26]
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
      has a feature to perform keylogging on the victim’s machine.
      <span class="scite-citeref-number" data-reference="Zscaler Cobian Aug 2017" id="scite-ref-27-a" onclick="scrollToRef('scite-27')">
       <sup>
        <a aria-describedby="qtip-26" data-hasqtip="26" href="https://www.zscaler.com/blogs/research/cobian-rat-backdoored-rat" target="_blank">
         [27]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0050">
      CosmicDuke
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0050">
       CosmicDuke
      </a>
      uses a keylogger and steals clipboard contents from victims.
      <span class="scite-citeref-number" data-reference="F-Secure The Dukes" id="scite-ref-28-a" onclick="scrollToRef('scite-28')">
       <sup>
        <a aria-describedby="qtip-27" data-hasqtip="27" href="https://www.f-secure.com/documents/996508/1030745/dukes_whitepaper.pdf" target="_blank">
         [28]
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
      has a keylogging capability.
      <span class="scite-citeref-number" data-reference="TrendMicro DarkComet Sept 2014" id="scite-ref-29-a" onclick="scrollToRef('scite-29')">
       <sup>
        <a aria-describedby="qtip-28" data-hasqtip="28" href="https://www.trendmicro.com/vinfo/us/threat-encyclopedia/malware/DARKCOMET" target="_blank">
         [29]
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
      has used a keylogger.
      <span class="scite-citeref-number" data-reference="Kaspersky Darkhotel" id="scite-ref-30-a" onclick="scrollToRef('scite-30')">
       <sup>
        <a aria-describedby="qtip-29" data-hasqtip="29" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08070903/darkhotel_kl_07.11.pdf" target="_blank">
         [30]
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
      can log keystrokes.
      <span class="scite-citeref-number" data-reference="Trend Micro Daserf Nov 2017" id="scite-ref-31-a" onclick="scrollToRef('scite-31')">
       <sup>
        <a aria-describedby="qtip-30" data-hasqtip="30" href="http://blog.trendmicro.com/trendlabs-security-intelligence/redbaldknight-bronze-butler-daserf-backdoor-now-using-steganography/" target="_blank">
         [31]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Secureworks BRONZE BUTLER Oct 2017" id="scite-ref-32-a" onclick="scrollToRef('scite-32')">
       <sup>
        <a aria-describedby="qtip-31" data-hasqtip="31" href="https://www.secureworks.com/research/bronze-butler-targets-japanese-businesses" target="_blank">
         [32]
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
      is capable of logging keystrokes.
      <span class="scite-citeref-number" data-reference="FireEye Periscope March 2018" id="scite-ref-33-a" onclick="scrollToRef('scite-33')">
       <sup>
        <a aria-describedby="qtip-32" data-hasqtip="32" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" target="_blank">
         [33]
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
      is capable of logging keystrokes.
      <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-34-a" onclick="scrollToRef('scite-34')">
       <sup>
        <a aria-describedby="qtip-33" data-hasqtip="33" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
         [34]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Unit 42 Nokki Oct 2018" id="scite-ref-35-a" onclick="scrollToRef('scite-35')">
       <sup>
        <a aria-describedby="qtip-34" data-hasqtip="34" href="https://researchcenter.paloaltonetworks.com/2018/10/unit42-nokki-almost-ties-the-knot-with-dogcall-reaper-group-uses-new-malware-to-deploy-rat/" target="_blank">
         [35]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0038">
      Duqu
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0038">
       Duqu
      </a>
      can track key presses with a keylogger module.
      <span class="scite-citeref-number" data-reference="Symantec W32.Duqu" id="scite-ref-36-a" onclick="scrollToRef('scite-36')">
       <sup>
        <a aria-describedby="qtip-35" data-hasqtip="35" href="https://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/w32_duqu_the_precursor_to_the_next_stuxnet.pdf" target="_blank">
         [36]
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
      contains a keylogger.
      <span class="scite-citeref-number" data-reference="DustySky" id="scite-ref-37-a" onclick="scrollToRef('scite-37')">
       <sup>
        <a aria-describedby="qtip-36" data-hasqtip="36" href="https://www.clearskysec.com/wp-content/uploads/2016/01/Operation%20DustySky_TLP_WHITE.pdf" target="_blank">
         [37]
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
      includes keylogging capabilities for Windows, Linux, and macOS systems.
      <span class="scite-citeref-number" data-reference="Github PowerShell Empire" id="scite-ref-38-a" onclick="scrollToRef('scite-38')">
       <sup>
        <a aria-describedby="qtip-37" data-hasqtip="37" href="https://github.com/PowerShellEmpire/Empire" target="_blank">
         [38]
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
      has the capability to capture keystrokes.
      <span class="scite-citeref-number" data-reference="PWC Cloud Hopper Technical Annex April 2017" id="scite-ref-39-a" onclick="scrollToRef('scite-39')">
       <sup>
        <a aria-describedby="qtip-38" data-hasqtip="38" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" target="_blank">
         [39]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0076">
      FakeM
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0076">
       FakeM
      </a>
      contains a keylogger module.
      <span class="scite-citeref-number" data-reference="Scarlet Mimic Jan 2016" id="scite-ref-40-a" onclick="scrollToRef('scite-40')">
       <sup>
        <a aria-describedby="qtip-39" data-hasqtip="39" href="http://researchcenter.paloaltonetworks.com/2016/01/scarlet-mimic-years-long-espionage-targets-minority-activists/" target="_blank">
         [40]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0085">
      FIN4
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0085">
       FIN4
      </a>
      has captured credentials via fake Outlook Web App (OWA) login pages and has also used a .NET based keylogger.
      <span class="scite-citeref-number" data-reference="FireEye Hacking FIN4 Dec 2014" id="scite-ref-41-a" onclick="scrollToRef('scite-41')">
       <sup>
        <a aria-describedby="qtip-40" data-hasqtip="40" href="https://www.fireeye.com/current-threats/threat-intelligence-reports/rpt-fin4.html" target="_blank">
         [41]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye Hacking FIN4 Video Dec 2014" id="scite-ref-42-a" onclick="scrollToRef('scite-42')">
       <sup>
        <a aria-describedby="qtip-41" data-hasqtip="41" href="https://www2.fireeye.com/WBNR-14Q4NAMFIN4.html" target="_blank">
         [42]
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
      has a keylogger.
      <span class="scite-citeref-number" data-reference="Alintanahin 2014" id="scite-ref-43-a" onclick="scrollToRef('scite-43')">
       <sup>
        <a aria-describedby="qtip-42" data-hasqtip="42" href="http://blog.trendmicro.com/trendlabs-security-intelligence/kunming-attack-leads-to-gh0st-rat-variant/" target="_blank">
         [43]
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
      has a module to harvest pressed keystrokes.
      <span class="scite-citeref-number" data-reference="ESET GreyEnergy Oct 2018" id="scite-ref-44-a" onclick="scrollToRef('scite-44')">
       <sup>
        <a aria-describedby="qtip-43" data-hasqtip="43" href="https://www.welivesecurity.com/wp-content/uploads/2018/10/ESET_GreyEnergy.pdf" target="_blank">
         [44]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0043">
      Group5
     </a>
    </td>
    <td>
     <p>
      Malware used by
      <a href="https://attack.mitre.org/groups/G0043">
       Group5
      </a>
      is capable of capturing keystrokes.
      <span class="scite-citeref-number" data-reference="Citizen Lab Group5" id="scite-ref-45-a" onclick="scrollToRef('scite-45')">
       <sup>
        <a aria-describedby="qtip-44" data-hasqtip="44" href="https://citizenlab.org/2016/08/group5-syria/" target="_blank">
         [45]
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
      The executable version of
      <a href="https://attack.mitre.org/software/S0170">
       Helminth
      </a>
      has a module to log keystrokes.
      <span class="scite-citeref-number" data-reference="Palo Alto OilRig May 2016" id="scite-ref-46-a" onclick="scrollToRef('scite-46')">
       <sup>
        <a aria-describedby="qtip-45" data-hasqtip="45" href="http://researchcenter.paloaltonetworks.com/2016/05/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/" target="_blank">
         [46]
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
      is capable of capturing keystrokes on victims.
      <span class="scite-citeref-number" data-reference="Dell TG-3390" id="scite-ref-47-a" onclick="scrollToRef('scite-47')">
       <sup>
        <a aria-describedby="qtip-46" data-hasqtip="46" href="https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage" target="_blank">
         [47]
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
      contains a custom keylogger.
      <span class="scite-citeref-number" data-reference="Microsoft PLATINUM April 2016" id="scite-ref-48-a" onclick="scrollToRef('scite-48')">
       <sup>
        <a aria-describedby="qtip-47" data-hasqtip="47" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" target="_blank">
         [48]
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
      has the capability to log keystrokes from the victim’s machine, both offline and online.
      <span class="scite-citeref-number" data-reference="jRAT Symantec Aug 2018" id="scite-ref-49-a" onclick="scrollToRef('scite-49')">
       <sup>
        <a aria-describedby="qtip-48" data-hasqtip="48" href="https://www.symantec.com/blogs/threat-intelligence/jrat-new-anti-parsing-techniques" target="_blank">
         [49]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Kaspersky Adwind Feb 2016" id="scite-ref-50-a" onclick="scrollToRef('scite-50')">
       <sup>
        <a aria-describedby="qtip-49" data-hasqtip="49" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07195002/KL_AdwindPublicReport_2016.pdf" target="_blank">
         [50]
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
      has the ability to initiate keylogging.
      <span class="scite-citeref-number" data-reference="Zscaler Kasidet" id="scite-ref-51-a" onclick="scrollToRef('scite-51')">
       <sup>
        <a aria-describedby="qtip-50" data-hasqtip="50" href="http://research.zscaler.com/2016/01/malicious-office-files-dropping-kasidet.html" target="_blank">
         [51]
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
      has used keyloggers.
      <span class="scite-citeref-number" data-reference="NCC Group APT15 Alive and Strong" id="scite-ref-52-a" onclick="scrollToRef('scite-52')">
       <sup>
        <a aria-describedby="qtip-51" data-hasqtip="51" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/" target="_blank">
         [52]
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
      has the capability to perform keylogging.
      <span class="scite-citeref-number" data-reference="Talos Konni May 2017" id="scite-ref-53-a" onclick="scrollToRef('scite-53')">
       <sup>
        <a aria-describedby="qtip-52" data-hasqtip="52" href="https://blog.talosintelligence.com/2017/05/konni-malware-under-radar-for-years.html" target="_blank">
         [53]
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
      malware KiloAlfa contains keylogging functionality.
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster" id="scite-ref-54-a" onclick="scrollToRef('scite-54')">
       <sup>
        <a aria-describedby="qtip-53" data-hasqtip="53" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" target="_blank">
         [54]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster Tools" id="scite-ref-55-a" onclick="scrollToRef('scite-55')">
       <sup>
        <a aria-describedby="qtip-54" data-hasqtip="54" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Tools-Report.pdf" target="_blank">
         [55]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0282">
      MacSpy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0282">
       MacSpy
      </a>
      captures keystrokes.
      <span class="scite-citeref-number" data-reference="objsee mac malware 2017" id="scite-ref-56-a" onclick="scrollToRef('scite-56')">
       <sup>
        <a aria-describedby="qtip-55" data-hasqtip="55" href="https://objective-see.com/blog/blog_0x25.html" target="_blank">
         [56]
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
      malware is capable of keylogging.
      <span class="scite-citeref-number" data-reference="Unit 42 Magic Hound Feb 2017" id="scite-ref-57-a" onclick="scrollToRef('scite-57')">
       <sup>
        <a aria-describedby="qtip-56" data-hasqtip="56" href="https://researchcenter.paloaltonetworks.com/2017/02/unit42-magic-hound-campaign-attacks-saudi-targets/" target="_blank">
         [57]
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
      is capable of keylogging.
      <span class="scite-citeref-number" data-reference="ClearSky Wilted Tulip July 2017" id="scite-ref-58-a" onclick="scrollToRef('scite-58')">
       <sup>
        <a aria-describedby="qtip-57" data-hasqtip="57" href="http://www.clearskysec.com/wp-content/uploads/2017/07/Operation_Wilted_Tulip.pdf" target="_blank">
         [58]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="CopyKittens Nov 2015" id="scite-ref-59-a" onclick="scrollToRef('scite-59')">
       <sup>
        <a aria-describedby="qtip-58" data-hasqtip="58" href="https://s3-eu-west-1.amazonaws.com/minervaresearchpublic/CopyKittens/CopyKittens.pdf" target="_blank">
         [59]
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
      has used key loggers to steal usernames and passwords.
      <span class="scite-citeref-number" data-reference="DOJ APT10 Dec 2018" id="scite-ref-60-a" onclick="scrollToRef('scite-60')">
       <sup>
        <a aria-describedby="qtip-59" data-hasqtip="59" href="https://www.justice.gov/opa/press-release/file/1121706/download" target="_blank">
         [60]
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
      has keylogging capabilities.
      <span class="scite-citeref-number" data-reference="Radware Micropsia July 2018" id="scite-ref-61-a" onclick="scrollToRef('scite-61')">
       <sup>
        <a aria-describedby="qtip-60" data-hasqtip="60" href="https://blog.radware.com/security/2018/07/micropsia-malware/" target="_blank">
         [61]
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
      has a keylogger.
      <span class="scite-citeref-number" data-reference="Palo Alto MoonWind March 2017" id="scite-ref-62-a" onclick="scrollToRef('scite-62')">
       <sup>
        <a aria-describedby="qtip-61" data-hasqtip="61" href="http://researchcenter.paloaltonetworks.com/2017/03/unit42-trochilus-rat-new-moonwind-rat-used-attack-thai-utility-organizations/" target="_blank">
         [62]
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
      can perform keylogging on the victim’s machine.
      <span class="scite-citeref-number" data-reference="PaloAlto NanoCore Feb 2016" id="scite-ref-63-a" onclick="scrollToRef('scite-63')">
       <sup>
        <a aria-describedby="qtip-62" data-hasqtip="62" href="https://researchcenter.paloaltonetworks.com/2016/02/nanocorerat-behind-an-increase-in-tax-themed-phishing-e-mails/" target="_blank">
         [63]
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
      logs the keystrokes on the targeted system.
      <span class="scite-citeref-number" data-reference="Talos NavRAT May 2018" id="scite-ref-64-a" onclick="scrollToRef('scite-64')">
       <sup>
        <a aria-describedby="qtip-63" data-hasqtip="63" href="https://blog.talosintelligence.com/2018/05/navrat.html" target="_blank">
         [64]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0033">
      NetTraveler
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0033">
       NetTraveler
      </a>
      contains a keylogger.
      <span class="scite-citeref-number" data-reference="Kaspersky NetTraveler" id="scite-ref-65-a" onclick="scrollToRef('scite-65')">
       <sup>
        <a aria-describedby="qtip-64" data-hasqtip="64" href="http://www.securelist.com/en/downloads/vlpdfs/kaspersky-the-net-traveler-part1-final.pdf" target="_blank">
         [65]
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
      can perform keylogging.
      <span class="scite-citeref-number" data-reference="McAfee Netwire Mar 2015" id="scite-ref-66-a" onclick="scrollToRef('scite-66')">
       <sup>
        <a aria-describedby="qtip-65" data-hasqtip="65" href="https://securingtomorrow.mcafee.com/mcafee-labs/netwire-rat-behind-recent-targeted-attacks/" target="_blank">
         [66]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye APT33 Webinar Sept 2017" id="scite-ref-67-a" onclick="scrollToRef('scite-67')">
       <sup>
        <a aria-describedby="qtip-66" data-hasqtip="66" href="https://www.brighttalk.com/webcast/10703/275683" target="_blank">
         [67]
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
      has used a keylogging tool called KEYPUNCH.
      <span class="scite-citeref-number" data-reference="FireEye APT34 Webinar Dec 2017" id="scite-ref-68-a" onclick="scrollToRef('scite-68')">
       <sup>
        <a aria-describedby="qtip-67" data-hasqtip="67" href="https://www.brighttalk.com/webcast/10703/296317/apt34-new-targeted-attack-in-the-middle-east" target="_blank">
         [68]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0072">
      OwaAuth
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0072">
       OwaAuth
      </a>
      captures and DES-encrypts credentials before writing the username and password to a log file,
      <code>
       C:\log.txt
      </code>
      .
      <span class="scite-citeref-number" data-reference="Dell TG-3390" id="scite-ref-47-a" onclick="scrollToRef('scite-47')">
       <sup>
        <a aria-describedby="qtip-46" data-hasqtip="46" href="https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage" target="_blank">
         [47]
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
      has used several different keyloggers.
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
      has a module for capturing keystrokes per process including window titles.
      <span class="scite-citeref-number" data-reference="CIRCL PlugX March 2013" id="scite-ref-69-a" onclick="scrollToRef('scite-69')">
       <sup>
        <a aria-describedby="qtip-68" data-hasqtip="68" href="http://circl.lu/assets/files/tr-12/tr-12-circl-plugx-analysis-v1.pdf" target="_blank">
         [69]
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
      contains a keylogger.
      <span class="scite-citeref-number" data-reference="FireEye Poison Ivy" id="scite-ref-70-a" onclick="scrollToRef('scite-70')">
       <sup>
        <a aria-describedby="qtip-69" data-hasqtip="69" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/rpt-poison-ivy.pdf" target="_blank">
         [70]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Symantec Darkmoon Aug 2005" id="scite-ref-71-a" onclick="scrollToRef('scite-71')">
       <sup>
        <a aria-describedby="qtip-70" data-hasqtip="70" href="https://www.symantec.com/security_response/writeup.jsp?docid=2005-081910-3934-99" target="_blank">
         [71]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0378">
      PoshC2
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0378">
       PoshC2
      </a>
      has modules for keystroke logging and capturing credentials from spoofed Outlook authentication messages.
      <span class="scite-citeref-number" data-reference="GitHub PoshC2" id="scite-ref-72-a" onclick="scrollToRef('scite-72')">
       <sup>
        <a aria-describedby="qtip-71" data-hasqtip="71" href="https://github.com/nettitude/PoshC2" target="_blank">
         [72]
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
       Get-Keystrokes
      </code>
      Exfiltration module can log keystrokes.
      <span class="scite-citeref-number" data-reference="GitHub PowerSploit May 2012" id="scite-ref-73-a" onclick="scrollToRef('scite-73')">
       <sup>
        <a aria-describedby="qtip-72" data-hasqtip="72" href="https://github.com/PowerShellMafia/PowerSploit" target="_blank">
         [73]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PowerSploit Documentation" id="scite-ref-74-a" onclick="scrollToRef('scite-74')">
       <sup>
        <a aria-describedby="qtip-73" data-hasqtip="73" href="http://powersploit.readthedocs.io" target="_blank">
         [74]
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
      contains a keylogger module that collects keystrokes and the titles of foreground windows.
      <span class="scite-citeref-number" data-reference="ESET Operation Groundbait" id="scite-ref-75-a" onclick="scrollToRef('scite-75')">
       <sup>
        <a aria-describedby="qtip-74" data-hasqtip="74" href="http://www.welivesecurity.com/wp-content/uploads/2016/05/Operation-Groundbait.pdf" target="_blank">
         [75]
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
      uses a keylogger to capture keystrokes.
      <span class="scite-citeref-number" data-reference="objsee mac malware 2017" id="scite-ref-56-a" onclick="scrollToRef('scite-56')">
       <sup>
        <a aria-describedby="qtip-55" data-hasqtip="55" href="https://objective-see.com/blog/blog_0x25.html" target="_blank">
         [56]
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
      uses a keylogger to capture keystrokes it then sends back to the server after it is stopped.
      <span class="scite-citeref-number" data-reference="GitHub Pupy" id="scite-ref-76-a" onclick="scrollToRef('scite-76')">
       <sup>
        <a aria-describedby="qtip-75" data-hasqtip="75" href="https://github.com/n1nj4sec/pupy" target="_blank">
         [76]
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
      has a built-in keylogger.
      <span class="scite-citeref-number" data-reference="GitHub QuasarRAT" id="scite-ref-77-a" onclick="scrollToRef('scite-77')">
       <sup>
        <a aria-describedby="qtip-76" data-hasqtip="76" href="https://github.com/quasar/QuasarRAT" target="_blank">
         [77]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Volexity Patchwork June 2018" id="scite-ref-78-a" onclick="scrollToRef('scite-78')">
       <sup>
        <a aria-describedby="qtip-77" data-hasqtip="77" href="https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/" target="_blank">
         [78]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0019">
      Regin
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0019">
       Regin
      </a>
      contains a keylogger.
      <span class="scite-citeref-number" data-reference="Kaspersky Regin" id="scite-ref-79-a" onclick="scrollToRef('scite-79')">
       <sup>
        <a aria-describedby="qtip-78" data-hasqtip="78" href="https://securelist.com/files/2014/11/Kaspersky_Lab_whitepaper_Regin_platform_eng.pdf" target="_blank">
         [79]
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
      has a command for keylogging.
      <span class="scite-citeref-number" data-reference="Fortinet Remcos Feb 2017" id="scite-ref-80-a" onclick="scrollToRef('scite-80')">
       <sup>
        <a aria-describedby="qtip-79" data-hasqtip="79" href="https://www.fortinet.com/blog/threat-research/remcos-a-new-rat-in-the-wild-2.html" target="_blank">
         [80]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Talos Remcos Aug 2018" id="scite-ref-81-a" onclick="scrollToRef('scite-81')">
       <sup>
        <a aria-describedby="qtip-80" data-hasqtip="80" href="https://blog.talosintelligence.com/2018/08/picking-apart-remcos.html" target="_blank">
         [81]
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
      gathers and exfiltrates keystrokes from the machine.
      <span class="scite-citeref-number" data-reference="Securelist Remexi Jan 2019" id="scite-ref-82-a" onclick="scrollToRef('scite-82')">
       <sup>
        <a aria-describedby="qtip-81" data-hasqtip="81" href="https://securelist.com/chafer-used-remexi-malware/89538/" target="_blank">
         [82]
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
      contains a keylogger component.
      <span class="scite-citeref-number" data-reference="Symantec Remsec IOCs" id="scite-ref-83-a" onclick="scrollToRef('scite-83')">
       <sup>
        <a aria-describedby="qtip-82" data-hasqtip="82" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/Symantec_Remsec_IOCs.pdf" target="_blank">
         [83]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Kaspersky ProjectSauron Technical Analysis" id="scite-ref-84-a" onclick="scrollToRef('scite-84')">
       <sup>
        <a aria-describedby="qtip-83" data-hasqtip="83" href="https://securelist.com/files/2016/07/The-ProjectSauron-APT_Technical_Analysis_KL.pdf" target="_blank">
         [84]
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
      uses a keylogger to capture keystrokes and location of where the user is typing.
      <span class="scite-citeref-number" data-reference="Talos ROKRAT" id="scite-ref-85-a" onclick="scrollToRef('scite-85')">
       <sup>
        <a aria-describedby="qtip-84" data-hasqtip="84" href="https://blog.talosintelligence.com/2017/04/introducing-rokrat.html" target="_blank">
         [85]
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
      has keylogging functionality.
      <span class="scite-citeref-number" data-reference="Palo Alto Rover" id="scite-ref-86-a" onclick="scrollToRef('scite-86')">
       <sup>
        <a aria-describedby="qtip-85" data-hasqtip="85" href="http://researchcenter.paloaltonetworks.com/2016/02/new-malware-rover-targets-indian-ambassador-to-afghanistan/" target="_blank">
         [86]
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
      can record keystrokes from both the keyboard and virtual keyboard.
      <span class="scite-citeref-number" data-reference="ESET RTM Feb 2017" id="scite-ref-87-a" onclick="scrollToRef('scite-87')">
       <sup>
        <a aria-describedby="qtip-86" data-hasqtip="86" href="https://www.welivesecurity.com/wp-content/uploads/2017/02/Read-The-Manual.pdf" target="_blank">
         [87]
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
      captures keystrokes and sends them back to the C2 server.
      <span class="scite-citeref-number" data-reference="McAfee Gold Dragon" id="scite-ref-88-a" onclick="scrollToRef('scite-88')">
       <sup>
        <a aria-describedby="qtip-87" data-hasqtip="87" href="https://securingtomorrow.mcafee.com/mcafee-labs/gold-dragon-widens-olympics-malware-attacks-gains-permanent-presence-on-victims-systems/" target="_blank">
         [88]
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
      has used keylogging tools.
      <span class="scite-citeref-number" data-reference="Symantec Sowbug Nov 2017" id="scite-ref-89-a" onclick="scrollToRef('scite-89')">
       <sup>
        <a aria-describedby="qtip-88" data-hasqtip="88" href="https://www.symantec.com/connect/blogs/sowbug-cyber-espionage-group-targets-south-american-and-southeast-asian-governments" target="_blank">
         [89]
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
      creates a new thread implementing a keylogging facility using Windows Keyboard Accelerators.
      <span class="scite-citeref-number" data-reference="Baumgartner Naikon 2015" id="scite-ref-90-a" onclick="scrollToRef('scite-90')">
       <sup>
        <a aria-describedby="qtip-89" data-hasqtip="89" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07205555/TheNaikonAPT-MsnMM1.pdf" target="_blank">
         [90]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0086">
      Stolen Pencil
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0086">
       Stolen Pencil
      </a>
      has a tool to log keystrokes to %userprofile%\appdata\roaming\apach.{txt,log}.
      <span class="scite-citeref-number" data-reference="Netscout Stolen Pencil Dec 2018" id="scite-ref-91-a" onclick="scrollToRef('scite-91')">
       <sup>
        <a aria-describedby="qtip-90" data-hasqtip="90" href="https://asert.arbornetworks.com/stolen-pencil-campaign-targets-academia/" target="_blank">
         [91]
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
      contains keylogging functionality to steal passwords.
      <span class="scite-citeref-number" data-reference="Alienvault Sykipot DOD Smart Cards" id="scite-ref-92-a" onclick="scrollToRef('scite-92')">
       <sup>
        <a aria-describedby="qtip-91" data-hasqtip="91" href="https://www.alienvault.com/open-threat-exchange/blog/sykipot-variant-hijacks-dod-and-windows-smart-cards" target="_blank">
         [92]
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
      actors installed a credential logger on Microsoft Exchange servers.
      <a href="https://attack.mitre.org/groups/G0027">
       Threat Group-3390
      </a>
      also leveraged the reconnaissance framework, ScanBox, to capture keystrokes.
      <span class="scite-citeref-number" data-reference="Dell TG-3390" id="scite-ref-47-a" onclick="scrollToRef('scite-47')">
       <sup>
        <a aria-describedby="qtip-46" data-hasqtip="46" href="https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage" target="_blank">
         [47]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Hacker News LuckyMouse June 2018" id="scite-ref-93-a" onclick="scrollToRef('scite-93')">
       <sup>
        <a aria-describedby="qtip-92" data-hasqtip="92" href="https://thehackernews.com/2018/06/chinese-watering-hole-attack.html" target="_blank">
         [93]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Securelist LuckyMouse June 2018" id="scite-ref-94-a" onclick="scrollToRef('scite-94')">
       <sup>
        <a aria-describedby="qtip-93" data-hasqtip="93" href="https://securelist.com/luckymouse-hits-national-data-center/86083/" target="_blank">
         [94]
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
      contains keylogger functionality.
      <span class="scite-citeref-number" data-reference="Cylance Cleaver" id="scite-ref-95-a" onclick="scrollToRef('scite-95')">
       <sup>
        <a aria-describedby="qtip-94" data-hasqtip="94" href="https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf" target="_blank">
         [95]
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
      is capable of recording keystrokes.
      <span class="scite-citeref-number" data-reference="Forcepoint Monsoon" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" target="_blank">
         [14]
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
      collects keystrokes from the victim machine.
      <span class="scite-citeref-number" data-reference="Unit 42 VERMIN Jan 2018" id="scite-ref-96-a" onclick="scrollToRef('scite-96')">
       <sup>
        <a aria-describedby="qtip-95" data-hasqtip="95" href="https://researchcenter.paloaltonetworks.com/2018/01/unit42-vermin-quasar-rat-custom-malware-used-ukraine/" target="_blank">
         [96]
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
      contains keylogging functionality that will monitor for active application windows and write them to the log, it can handle special characters, and it will buffer by default 50 characters before sending them out over the C2 infrastructure.
      <span class="scite-citeref-number" data-reference="XAgentOSX 2017" id="scite-ref-97-a" onclick="scrollToRef('scite-97')">
       <sup>
        <a aria-describedby="qtip-96" data-hasqtip="96" href="https://researchcenter.paloaltonetworks.com/2017/02/unit42-xagentosx-sofacys-xagent-macos-tool/" target="_blank">
         [97]
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
      uses a keylogger plugin to gather keystrokes.
      <span class="scite-citeref-number" data-reference="ASERT Donot March 2018" id="scite-ref-98-a" onclick="scrollToRef('scite-98')">
       <sup>
        <a aria-describedby="qtip-97" data-hasqtip="97" href="https://www.arbornetworks.com/blog/asert/donot-team-leverages-new-modular-malware-framework-south-asia/" target="_blank">
         [98]
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
      can perform keylogging on the victim’s machine by hooking the functions TranslateMessage and WM_KEYDOWN.
      <span class="scite-citeref-number" data-reference="GDATA Zeus Panda June 2017" id="scite-ref-99-a" onclick="scrollToRef('scite-99')">
       <sup>
        <a aria-describedby="qtip-98" data-hasqtip="98" href="https://cyberwtf.files.wordpress.com/2017/07/panda-whitepaper.pdf" target="_blank">
         [99]
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
  Identify and block potentially malicious software that may be used to acquire credentials or information from the user by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-100-a">
   <sup>
    <a aria-describedby="qtip-99" data-hasqtip="99" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [100]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-101-a">
   <sup>
    <a aria-describedby="qtip-100" data-hasqtip="100" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [101]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-102-a">
   <sup>
    <a aria-describedby="qtip-101" data-hasqtip="101" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [102]
    </a>
   </sup>
  </span>
  or Software Restriction Policies
  <span class="scite-citeref-number" data-reference="Corio 2008" id="scite-ref-103-a">
   <sup>
    <a aria-describedby="qtip-102" data-hasqtip="102" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" target="_blank">
     [103]
    </a>
   </sup>
  </span>
  where appropriate.
  <span class="scite-citeref-number" data-reference="TechNet Applocker vs SRP" id="scite-ref-104-a">
   <sup>
    <a aria-describedby="qtip-103" data-hasqtip="103" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" target="_blank">
     [104]
    </a>
   </sup>
  </span>
 </p>
 <p>
  In cases where this behavior is difficult to detect or mitigate, efforts can be made to lessen some of the impact that might result from an adversary acquiring credential information. It is also good practice to follow mitigation recommendations for adversary use of
  <a href="https://attack.mitre.org/techniques/T1078">
   Valid Accounts
  </a>
  .
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Keyloggers may take many forms, possibly involving modification to the Registry and installation of a driver, setting a hook, or polling to intercept keystrokes. Commonly used API calls include SetWindowsHook, GetKeyState, and GetAsyncKeyState.
  <span class="scite-citeref-number" data-reference="Adventures of a Keystroke" id="scite-ref-1-a">
   <sup>
    <a aria-describedby="qtip-0" data-hasqtip="0" href="http://opensecuritytraining.info/Keylogging_files/The%20Adventures%20of%20a%20Keystroke.pdf" target="_blank">
     [1]
    </a>
   </sup>
  </span>
  Monitor the Registry and file system for such changes and detect driver installs, as well as looking for common keylogging API calls. API calls alone are not an indicator of keylogging, but may provide behavioral data that is useful when combined with other information such as new files written to disk and unusual processes.
 </p>
 <p>
  Monitor the Registry for the addition of a Custom Credential Provider.
  <span class="scite-citeref-number" data-reference="Wrightson 2012" id="scite-ref-2-a">
   <sup>
    <a aria-describedby="qtip-1" data-hasqtip="1" href="http://blog.leetsys.com/2012/01/02/capturing-windows-7-credentials-at-logon-using-custom-credential-provider/" target="_blank">
     [2]
    </a>
   </sup>
  </span>
  Detection of compromised
  <a href="https://attack.mitre.org/techniques/T1078">
   Valid Accounts
  </a>
  in use by adversaries may help to catch the result of user input interception if new techniques are used.
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
       <a class="external text" href="http://opensecuritytraining.info/Keylogging_files/The%20Adventures%20of%20a%20Keystroke.pdf" name="scite-1" rel="nofollow" target="_blank">
        Tinaztepe,  E. (n.d.). The Adventures of a Keystroke:  An in-depth look into keyloggers on Windows. Retrieved April 27, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.leetsys.com/2012/01/02/capturing-windows-7-credentials-at-logon-using-custom-credential-provider/" name="scite-2" rel="nofollow" target="_blank">
        Wrightson, T. (2012, January 2). CAPTURING WINDOWS 7 CREDENTIALS AT LOGON USING CUSTOM CREDENTIAL PROVIDER. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.volexity.com/blog/2015/10/07/virtual-private-keylogging-cisco-web-vpns-leveraged-for-access-and-persistence/" name="scite-3" rel="nofollow" target="_blank">
        Adair, S. (2015, October 7). Virtual Private Keylogging: Cisco Web VPNs Leveraged for Access and Persistence. Retrieved March 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part-2.pdf" name="scite-4" rel="nofollow" target="_blank">
        ESET. (2016, October). En Route with Sednit - Part 2: Observing the Comings and Goings. Retrieved November 21, 2016.
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
       <a class="external text" href="https://blog.talosintelligence.com/2018/10/old-dog-new-tricks-analysing-new-rtf_15.html" name="scite-6" rel="nofollow" target="_blank">
        Brumaghin, E., et al. (2018, October 15). Old dog, new tricks - Analysing new RTF-based campaign distributing Agent Tesla, Loki with PyREbox. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.digitrustgroup.com/agent-tesla-keylogger/" name="scite-7" rel="nofollow" target="_blank">
        The DigiTrust Group. (2017, January 12). The Rise of Agent Tesla. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fortinet.com/blog/threat-research/in-depth-analysis-of-net-malware-javaupdtr.html" name="scite-8" rel="nofollow" target="_blank">
        Zhang, X. (2017, June 28). In-Depth Analysis of A New Variant of .NET Malware AgentTesla. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="http://download.microsoft.com/download/4/4/C/44CDEF0E-7924-4787-A56A-16261691ACE3/Microsoft_Security_Intelligence_Report_Volume_19_English.pdf" name="scite-9" rel="nofollow" target="_blank">
        Anthe, C. et al. (2015, October 19). Microsoft Security Intelligence Report Volume 19. Retrieved December 23, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.justice.gov/file/1080281/download" name="scite-10" rel="nofollow" target="_blank">
        Mueller, R. (2018, July 13). Indictment - United States of America vs. VIKTOR BORISOVICH NETYKSHO, et al. Retrieved September 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/connect/blogs/buckeye-cyberespionage-group-shifts-gaze-us-hong-kong" name="scite-11" rel="nofollow" target="_blank">
        Symantec Security Response. (2016, September 6). Buckeye cyberespionage group shifts gaze from US to Hong Kong. Retrieved September 26, 2016.
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
       <a class="external text" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" name="scite-14" rel="nofollow" target="_blank">
        Settle, A., et al. (2016, August 8). MONSOON - Analysis Of An APT Campaign. Retrieved September 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/03/unit42-patchwork-continues-deliver-badnews-indian-subcontinent/" name="scite-15" rel="nofollow" target="_blank">
        Levene, B. et al.. (2018, March 7). Patchwork Continues to Deliver BADNEWS to the Indian Subcontinent. Retrieved March 31, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" name="scite-16" rel="nofollow" target="_blank">
        Lunghi, D., et al. (2017, December). Untangling the Patchwork Cyberespionage Group. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/10/unit42-badpatch/" name="scite-17" rel="nofollow" target="_blank">
        Bar, T., Conant, S. (2017, October 20). BadPatch. Retrieved November 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.blackhat.com/docs/us-16/materials/us-16-Quintin-When-Governments-Attack-State-Sponsored-Malware-Attacks-Against-Activists-Lawyers-And-Journalists.pdf" name="scite-18" rel="nofollow" target="_blank">
        Galperin, E., Et al.. (2016, August 4). When Governments Attack: State Sponsored Malware Attacks Against Activists, Lawyers, and Journalists. Retrieved May 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report-appendix.zip" name="scite-19" rel="nofollow" target="_blank">
        Mandiant. (n.d.). Appendix C (Digital) - The Malware Arsenal. Retrieved July 18, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/be2-custom-plugins-router-abuse-and-target-profiles/67353/" name="scite-20" rel="nofollow" target="_blank">
        Baumgartner, K. and Garnaeva, M.. (2014, November 3). BE2 custom plugins, router abuse, and target profiles. Retrieved March 24, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08064518/Carbanak_APT_eng.pdf" name="scite-21" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2015, February). CARBANAK APT THE GREAT BANK ROBBERY. Retrieved August 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/06/behind-the-carbanak-backdoor.html" name="scite-22" rel="nofollow" target="_blank">
        Bennett, J., Vengerik, B. (2017, June 12). Behind the CARBANAK Backdoor. Retrieved June 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-23">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/04/unit42-cardinal-rat-active-two-years/" name="scite-23" rel="nofollow" target="_blank">
        Grunzweig, J.. (2017, April 20). Cardinal RAT Active for Over Two Years. Retrieved December 8, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-24">
      <span class="scite-citation-text">
       <a class="external text" href="https://www-west.symantec.com/content/symantec/english/en/security-center/writeup.html/2018-040209-1742-99" name="scite-24" rel="nofollow" target="_blank">
        Balanza, M. (2018, April 02). Infostealer.Catchamas. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-25">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.crowdstrike.com/blog/bears-midst-intrusion-democratic-national-committee/" name="scite-25" rel="nofollow" target="_blank">
        Alperovitch, D.. (2016, June 15). Bears in the Midst: Intrusion into the Democratic National Committee. Retrieved August 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-26">
      <span class="scite-citation-text">
       <a class="external text" href="https://cobaltstrike.com/downloads/csmanual38.pdf" name="scite-26" rel="nofollow" target="_blank">
        Strategic Cyber LLC. (2017, March 14). Cobalt Strike Manual. Retrieved May 24, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-27">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.zscaler.com/blogs/research/cobian-rat-backdoored-rat" name="scite-27" rel="nofollow" target="_blank">
        Yadav, A., et al. (2017, August 31). Cobian RAT – A backdoored RAT. Retrieved November 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-28">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.f-secure.com/documents/996508/1030745/dukes_whitepaper.pdf" name="scite-28" rel="nofollow" target="_blank">
        F-Secure Labs. (2015, September 17). The Dukes: 7 years of Russian cyberespionage. Retrieved December 10, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-29">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.trendmicro.com/vinfo/us/threat-encyclopedia/malware/DARKCOMET" name="scite-29" rel="nofollow" target="_blank">
        TrendMicro. (2014, September 03). DARKCOMET. Retrieved November 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-30">
      <span class="scite-citation-text">
       <a class="external text" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08070903/darkhotel_kl_07.11.pdf" name="scite-30" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2014, November). The Darkhotel APT A Story of Unusual Hospitality. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-31">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.trendmicro.com/trendlabs-security-intelligence/redbaldknight-bronze-butler-daserf-backdoor-now-using-steganography/" name="scite-31" rel="nofollow" target="_blank">
        Chen, J. and Hsieh, M. (2017, November 7). REDBALDKNIGHT/BRONZE BUTLER’s Daserf Backdoor Now Using Steganography. Retrieved December 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-32">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/bronze-butler-targets-japanese-businesses" name="scite-32" rel="nofollow" target="_blank">
        Counter Threat Unit Research Team. (2017, October 12). BRONZE BUTLER Targets Japanese Enterprises. Retrieved January 4, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-33">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" name="scite-33" rel="nofollow" target="_blank">
        FireEye. (2018, March 16). Suspected Chinese Cyber Espionage Group (TEMP.Periscope) Targeting U.S. Engineering and Maritime Industries. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-34">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" name="scite-34" rel="nofollow" target="_blank">
        FireEye. (2018, February 20). APT37 (Reaper): The Overlooked North Korean Actor. Retrieved March 1, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-35">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/10/unit42-nokki-almost-ties-the-knot-with-dogcall-reaper-group-uses-new-malware-to-deploy-rat/" name="scite-35" rel="nofollow" target="_blank">
        Grunzweig, J. (2018, October 01). NOKKI Almost Ties the Knot with DOGCALL: Reaper Group Uses New Malware to Deploy RAT. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-36">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/w32_duqu_the_precursor_to_the_next_stuxnet.pdf" name="scite-36" rel="nofollow" target="_blank">
        Symantec Security Response. (2011, November). W32.Duqu: The precursor to the next Stuxnet. Retrieved September 17, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-37">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.clearskysec.com/wp-content/uploads/2016/01/Operation%20DustySky_TLP_WHITE.pdf" name="scite-37" rel="nofollow" target="_blank">
        ClearSky. (2016, January 7). Operation DustySky. Retrieved January 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-38">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellEmpire/Empire" name="scite-38" rel="nofollow" target="_blank">
        Schroeder, W., Warner, J., Nelson, M. (n.d.). Github PowerShellEmpire. Retrieved April 28, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-39">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" name="scite-39" rel="nofollow" target="_blank">
        PwC and BAE Systems. (2017, April). Operation Cloud Hopper: Technical Annex. Retrieved April 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-40">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/01/scarlet-mimic-years-long-espionage-targets-minority-activists/" name="scite-40" rel="nofollow" target="_blank">
        Falcone, R. and Miller-Osborn, J.. (2016, January 24). Scarlet Mimic: Years-Long Espionage Campaign Targets Minority Activists. Retrieved February 10, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-41">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/current-threats/threat-intelligence-reports/rpt-fin4.html" name="scite-41" rel="nofollow" target="_blank">
        Vengerik, B. et al.. (2014, December 5). Hacking the Street? FIN4 Likely Playing the Market. Retrieved December 17, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-42">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/WBNR-14Q4NAMFIN4.html" name="scite-42" rel="nofollow" target="_blank">
        Vengerik, B. &amp; Dennesen, K.. (2014, December 5). Hacking the Street?  FIN4 Likely Playing the Market. Retrieved January 15, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-43">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.trendmicro.com/trendlabs-security-intelligence/kunming-attack-leads-to-gh0st-rat-variant/" name="scite-43" rel="nofollow" target="_blank">
        Alintanahin, K. (2014, March 13). Kunming Attack Leads to Gh0st RAT Variant. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-44">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2018/10/ESET_GreyEnergy.pdf" name="scite-44" rel="nofollow" target="_blank">
        Cherepanov, A. (2018, October). GREYENERGY A successor to BlackEnergy. Retrieved November 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-45">
      <span class="scite-citation-text">
       <a class="external text" href="https://citizenlab.org/2016/08/group5-syria/" name="scite-45" rel="nofollow" target="_blank">
        Scott-Railton, J., et al. (2016, August 2). Group5: Syria and the Iranian Connection. Retrieved September 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-46">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/05/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/" name="scite-46" rel="nofollow" target="_blank">
        Falcone, R. and Lee, B.. (2016, May 26). The OilRig Campaign: Attacks on Saudi Arabian Organizations Deliver Helminth Backdoor. Retrieved May 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-47">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage" name="scite-47" rel="nofollow" target="_blank">
        Dell SecureWorks Counter Threat Unit Threat Intelligence. (2015, August 5). Threat Group-3390 Targets Organizations for Cyberespionage. Retrieved August 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-48">
      <span class="scite-citation-text">
       <a class="external text" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" name="scite-48" rel="nofollow" target="_blank">
        Windows Defender Advanced Threat Hunting Team. (2016, April 29). PLATINUM: Targeted attacks in South and Southeast Asia. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-49">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/jrat-new-anti-parsing-techniques" name="scite-49" rel="nofollow" target="_blank">
        Sharma, R. (2018, August 15). Revamped jRAT Uses New Anti-Parsing Techniques. Retrieved September 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-50">
      <span class="scite-citation-text">
       <a class="external text" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07195002/KL_AdwindPublicReport_2016.pdf" name="scite-50" rel="nofollow" target="_blank">
        Kamluk, V. &amp; Gostev, A. (2016, February). Adwind - A Cross-Platform RAT. Retrieved April 23, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-51">
      <span class="scite-citation-text">
       <a class="external text" href="http://research.zscaler.com/2016/01/malicious-office-files-dropping-kasidet.html" name="scite-51" rel="nofollow" target="_blank">
        Yadav, A., et al. (2016, January 29). Malicious Office files dropping Kasidet and Dridex. Retrieved March 24, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-52">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/" name="scite-52" rel="nofollow" target="_blank">
        Smallridge, R. (2018, March 10). APT15 is alive and strong: An analysis of RoyalCli and RoyalDNS. Retrieved April 4, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="53.0">
    <li>
     <span class="scite-citation" id="scite-53">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2017/05/konni-malware-under-radar-for-years.html" name="scite-53" rel="nofollow" target="_blank">
        Rascagneres, P. (2017, May 03). KONNI: A Malware Under The Radar For Years. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-54">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" name="scite-54" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Unraveling the Long Thread of the Sony Attack. Retrieved February 25, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-55">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Tools-Report.pdf" name="scite-55" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Tools Report. Retrieved March 10, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-56">
      <span class="scite-citation-text">
       <a class="external text" href="https://objective-see.com/blog/blog_0x25.html" name="scite-56" rel="nofollow" target="_blank">
        Patrick Wardle. (n.d.). Mac Malware of 2017. Retrieved September 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-57">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/02/unit42-magic-hound-campaign-attacks-saudi-targets/" name="scite-57" rel="nofollow" target="_blank">
        Lee, B. and Falcone, R. (2017, February 15). Magic Hound Campaign Attacks Saudi Targets. Retrieved December 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-58">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.clearskysec.com/wp-content/uploads/2017/07/Operation_Wilted_Tulip.pdf" name="scite-58" rel="nofollow" target="_blank">
        ClearSky Cyber Security and Trend Micro. (2017, July). Operation Wilted Tulip: Exposing a cyber espionage apparatus. Retrieved August 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-59">
      <span class="scite-citation-text">
       <a class="external text" href="https://s3-eu-west-1.amazonaws.com/minervaresearchpublic/CopyKittens/CopyKittens.pdf" name="scite-59" rel="nofollow" target="_blank">
        Minerva Labs LTD and ClearSky Cyber Security. (2015, November 23). CopyKittens Attack Group. Retrieved September 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-60">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.justice.gov/opa/press-release/file/1121706/download" name="scite-60" rel="nofollow" target="_blank">
        United States District Court Southern District of New York (USDC SDNY) . (2018, December 17). United States of America v. Zhu Hua and Zhang Shilong. Retrieved April 17, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-61">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.radware.com/security/2018/07/micropsia-malware/" name="scite-61" rel="nofollow" target="_blank">
        Tsarfaty, Y. (2018, July 25). Micropsia Malware. Retrieved November 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-62">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2017/03/unit42-trochilus-rat-new-moonwind-rat-used-attack-thai-utility-organizations/" name="scite-62" rel="nofollow" target="_blank">
        Miller-Osborn, J. and Grunzweig, J.. (2017, March 30). Trochilus and New MoonWind RATs Used In Attack Against Thai Organizations. Retrieved March 30, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-63">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2016/02/nanocorerat-behind-an-increase-in-tax-themed-phishing-e-mails/" name="scite-63" rel="nofollow" target="_blank">
        Kasza, A., Halfpop, T. (2016, February 09). NanoCoreRAT Behind an Increase in Tax-Themed Phishing E-mails. Retrieved November 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-64">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/05/navrat.html" name="scite-64" rel="nofollow" target="_blank">
        Mercer, W., Rascagneres, P. (2018, May 31). NavRAT Uses US-North Korea Summit As Decoy For Attacks In South Korea. Retrieved June 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-65">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.securelist.com/en/downloads/vlpdfs/kaspersky-the-net-traveler-part1-final.pdf" name="scite-65" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (n.d.). The NetTraveler (aka ‘Travnet’). Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-66">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/netwire-rat-behind-recent-targeted-attacks/" name="scite-66" rel="nofollow" target="_blank">
        McAfee. (2015, March 2). Netwire RAT Behind Recent Targeted Attacks. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-67">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.brighttalk.com/webcast/10703/275683" name="scite-67" rel="nofollow" target="_blank">
        Davis, S. and Carr, N. (2017, September 21). APT33: New Insights into Iranian Cyber Espionage Group. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-68">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.brighttalk.com/webcast/10703/296317/apt34-new-targeted-attack-in-the-middle-east" name="scite-68" rel="nofollow" target="_blank">
        Davis, S. and Caban, D. (2017, December 19). APT34 - New Targeted Attack in the Middle East. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-69">
      <span class="scite-citation-text">
       <a class="external text" href="http://circl.lu/assets/files/tr-12/tr-12-circl-plugx-analysis-v1.pdf" name="scite-69" rel="nofollow" target="_blank">
        Computer Incident Response Center Luxembourg. (2013, March 29). Analysis of a PlugX variant. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-70">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/rpt-poison-ivy.pdf" name="scite-70" rel="nofollow" target="_blank">
        FireEye. (2014). POISON IVY: Assessing Damage and Extracting Intelligence. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-71">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2005-081910-3934-99" name="scite-71" rel="nofollow" target="_blank">
        Hayashi, K. (2005, August 18). Backdoor.Darkmoon. Retrieved February 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-72">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/nettitude/PoshC2" name="scite-72" rel="nofollow" target="_blank">
        Nettitude. (2016, June 8). PoshC2: Powershell C2 Server and Implants. Retrieved April 23, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-73">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellMafia/PowerSploit" name="scite-73" rel="nofollow" target="_blank">
        PowerShellMafia. (2012, May 26). PowerSploit - A PowerShell Post-Exploitation Framework. Retrieved February 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-74">
      <span class="scite-citation-text">
       <a class="external text" href="http://powersploit.readthedocs.io" name="scite-74" rel="nofollow" target="_blank">
        PowerSploit. (n.d.). PowerSploit. Retrieved February 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-75">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.welivesecurity.com/wp-content/uploads/2016/05/Operation-Groundbait.pdf" name="scite-75" rel="nofollow" target="_blank">
        Cherepanov, A.. (2016, May 17). Operation Groundbait: Analysis of a surveillance toolkit. Retrieved May 18, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-76">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/n1nj4sec/pupy" name="scite-76" rel="nofollow" target="_blank">
        Nicolas Verdier. (n.d.). Retrieved January 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-77">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/quasar/QuasarRAT" name="scite-77" rel="nofollow" target="_blank">
        MaxXor. (n.d.). QuasarRAT. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-78">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/" name="scite-78" rel="nofollow" target="_blank">
        Meltzer, M, et al. (2018, June 07). Patchwork APT Group Targets US Think Tanks. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-79">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/files/2014/11/Kaspersky_Lab_whitepaper_Regin_platform_eng.pdf" name="scite-79" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2014, November 24). THE REGIN PLATFORM NATION-STATE OWNAGE OF GSM NETWORKS. Retrieved December 1, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-80">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fortinet.com/blog/threat-research/remcos-a-new-rat-in-the-wild-2.html" name="scite-80" rel="nofollow" target="_blank">
        Bacurio, F., Salvio, J. (2017, February 14). REMCOS: A New RAT In The Wild. Retrieved November 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-81">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/08/picking-apart-remcos.html" name="scite-81" rel="nofollow" target="_blank">
        Brumaghin, E., Unterbrink, H. (2018, August 22). Picking Apart Remcos Botnet-In-A-Box. Retrieved November 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-82">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/chafer-used-remexi-malware/89538/" name="scite-82" rel="nofollow" target="_blank">
        Legezo, D. (2019, January 30). Chafer used Remexi malware to spy on Iran-based foreign diplomatic entities. Retrieved April 17, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-83">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/Symantec_Remsec_IOCs.pdf" name="scite-83" rel="nofollow" target="_blank">
        Symantec Security Response. (2016, August 8). Backdoor.Remsec indicators of compromise. Retrieved August 17, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-84">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/files/2016/07/The-ProjectSauron-APT_Technical_Analysis_KL.pdf" name="scite-84" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research &amp; Analysis Team. (2016, August 9). The ProjectSauron APT. Technical Analysis. Retrieved August 17, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-85">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2017/04/introducing-rokrat.html" name="scite-85" rel="nofollow" target="_blank">
        Mercer, W., Rascagneres, P. (2017, April 03). Introducing ROKRAT. Retrieved May 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-86">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/02/new-malware-rover-targets-indian-ambassador-to-afghanistan/" name="scite-86" rel="nofollow" target="_blank">
        Ray, V., Hayashi, K. (2016, February 29). New Malware ‘Rover’ Targets Indian Ambassador to Afghanistan. Retrieved February 29, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-87">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2017/02/Read-The-Manual.pdf" name="scite-87" rel="nofollow" target="_blank">
        Faou, M. and Boutin, J.. (2017, February). Read The Manual: A Guide to the RTM Banking Trojan. Retrieved March 9, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-88">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/gold-dragon-widens-olympics-malware-attacks-gains-permanent-presence-on-victims-systems/" name="scite-88" rel="nofollow" target="_blank">
        Sherstobitoff, R., Saavedra-Morales, J. (2018, February 02). Gold Dragon Widens Olympics Malware Attacks, Gains Permanent Presence on Victims’ Systems. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-89">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/connect/blogs/sowbug-cyber-espionage-group-targets-south-american-and-southeast-asian-governments" name="scite-89" rel="nofollow" target="_blank">
        Symantec Security Response. (2017, November 7). Sowbug: Cyber espionage group targets South American and Southeast Asian governments. Retrieved November 16, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-90">
      <span class="scite-citation-text">
       <a class="external text" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07205555/TheNaikonAPT-MsnMM1.pdf" name="scite-90" rel="nofollow" target="_blank">
        Baumgartner, K., Golovkin, M.. (2015, May). The MsnMM Campaigns: The Earliest Naikon APT Campaigns. Retrieved April 10, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-91">
      <span class="scite-citation-text">
       <a class="external text" href="https://asert.arbornetworks.com/stolen-pencil-campaign-targets-academia/" name="scite-91" rel="nofollow" target="_blank">
        ASERT team. (2018, December 5). STOLEN PENCIL Campaign Targets Academia. Retrieved February 5, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-92">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.alienvault.com/open-threat-exchange/blog/sykipot-variant-hijacks-dod-and-windows-smart-cards" name="scite-92" rel="nofollow" target="_blank">
        Blasco, J. (2012, January 12). Sykipot variant hijacks DOD and Windows smart cards. Retrieved January 10, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-93">
      <span class="scite-citation-text">
       <a class="external text" href="https://thehackernews.com/2018/06/chinese-watering-hole-attack.html" name="scite-93" rel="nofollow" target="_blank">
        Khandelwal, S. (2018, June 14). Chinese Hackers Carried Out Country-Level Watering Hole Attack. Retrieved August 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-94">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/luckymouse-hits-national-data-center/86083/" name="scite-94" rel="nofollow" target="_blank">
        Legezo, D. (2018, June 13). LuckyMouse hits national data center to organize country-level waterholing campaign. Retrieved August 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-95">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf" name="scite-95" rel="nofollow" target="_blank">
        Cylance. (2014, December). Operation Cleaver. Retrieved September 14, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-96">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/01/unit42-vermin-quasar-rat-custom-malware-used-ukraine/" name="scite-96" rel="nofollow" target="_blank">
        Lancaster, T., Cortes, J. (2018, January 29). VERMIN: Quasar RAT and Custom Malware Used In Ukraine. Retrieved July 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-97">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/02/unit42-xagentosx-sofacys-xagent-macos-tool/" name="scite-97" rel="nofollow" target="_blank">
        Robert Falcone. (2017, February 14). XAgentOSX: Sofacy's Xagent macOS Tool. Retrieved July 12, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-98">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.arbornetworks.com/blog/asert/donot-team-leverages-new-modular-malware-framework-south-asia/" name="scite-98" rel="nofollow" target="_blank">
        Schwarz, D., Sopko J. (2018, March 08). Donot Team Leverages New Modular Malware Framework in South Asia. Retrieved June 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-99">
      <span class="scite-citation-text">
       <a class="external text" href="https://cyberwtf.files.wordpress.com/2017/07/panda-whitepaper.pdf" name="scite-99" rel="nofollow" target="_blank">
        Ebach, L. (2017, June 22). Analysis Results of Zeus.Variant.Panda. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-100">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-100" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-101">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-101" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-102">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-102" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-103">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" name="scite-103" rel="nofollow" target="_blank">
        Corio, C., &amp; Sayana, D. P. (2008, June). Application Lockdown with Software Restriction Policies. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-104">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" name="scite-104" rel="nofollow" target="_blank">
        Microsoft. (2012, June 27). Using Software Restriction Policies and AppLocker Policies. Retrieved April 7, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
