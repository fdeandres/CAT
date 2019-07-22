<div class="container-fluid">
 <h1>
  Data Encrypted for Impact
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries may encrypt data on target systems or on large numbers of systems in a network to interrupt availability to system and network resources. They can attempt to render stored data inaccessible by encrypting files or data on local and remote drives and withholding access to a decryption key. This may be done in order to extract monetary compensation from a victim in exchange for decryption or a decryption key (ransomware) or to render data permanently inaccessible in cases where the key is not saved or transmitted.
    <span class="scite-citeref-number" data-reference="US-CERT Ransomware 2016" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.us-cert.gov/ncas/alerts/TA16-091A" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="FireEye WannaCry 2017" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.fireeye.com/blog/threat-research/2017/05/wannacry-malware-profile.html" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="US-CERT NotPetya 2017" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.us-cert.gov/ncas/alerts/TA17-181A" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="US-CERT SamSam 2018" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.us-cert.gov/ncas/alerts/AA18-337A" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    In the case of ransomware, it is typical that common user files like Office documents, PDFs, images, videos, audio, text, and source code files will be encrypted. In some cases, adversaries may encrypt critical system files, disk partitions, and the MBR.
    <span class="scite-citeref-number" data-reference="US-CERT NotPetya 2017" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.us-cert.gov/ncas/alerts/TA17-181A" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    To maximize impact on the target organization, malware designed for encrypting data may have worm-like features to propagate across a network by leveraging other attack techniques like
    <a href="https://attack.mitre.org/techniques/T1078">
     Valid Accounts
    </a>
    ,
    <a href="https://attack.mitre.org/techniques/T1003">
     Credential Dumping
    </a>
    , and
    <a href="https://attack.mitre.org/techniques/T1077">
     Windows Admin Shares
    </a>
    .
    <span class="scite-citeref-number" data-reference="FireEye WannaCry 2017" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.fireeye.com/blog/threat-research/2017/05/wannacry-malware-profile.html" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="US-CERT NotPetya 2017" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.us-cert.gov/ncas/alerts/TA17-181A" target="_blank">
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
      : T1486
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
      : Impact
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
      User, Administrator, root, SYSTEM
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
      Kernel drivers, File monitoring, Process command-line parameters, Process monitoring
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
       Impact Type:
      </span>
      Availability
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
     <a href="https://attack.mitre.org/groups/G0082">
      APT38
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0082">
       APT38
      </a>
      has used Hermes ransomware to encrypt files with AES256.
      <span class="scite-citeref-number" data-reference="FireEye APT38 Oct 2018" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://content.fireeye.com/apt/rpt-apt38" target="_blank">
         [5]
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
      has encrypted files, including core Windows OS files, using RSA-OAEP MGF1 and then demanded Bitcoin be paid for the decryption key.
      <span class="scite-citeref-number" data-reference="CarbonBlack LockerGoga 2019" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.carbonblack.com/2019/03/22/tau-threat-intelligence-notification-lockergoga-ransomware/" target="_blank">
         [6]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Unit42 LockerGoga 2019" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://unit42.paloaltonetworks.com/born-this-way-origins-of-lockergoga/" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0368">
      NotPetya
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0368">
       NotPetya
      </a>
      encrypts user files and disk structures like the MBR with 2048-bit RSA.
      <span class="scite-citeref-number" data-reference="Talos Nyetya June 2017" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://blog.talosintelligence.com/2017/06/worldwide-ransomware-variant.html" target="_blank">
         [8]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT NotPetya 2017" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.us-cert.gov/ncas/alerts/TA17-181A" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0370">
      SamSam
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0370">
       SamSam
      </a>
      encrypts victim files using RSA-2048 encryption and demands a ransom be paid in Bitcoin to decrypt those files.
      <span class="scite-citeref-number" data-reference="Sophos SamSam Apr 2018" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.sophos.com/en-us/medialibrary/PDFs/technical-papers/SamSam-ransomware-chooses-Its-targets-carefully-wpna.pdf" target="_blank">
         [9]
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
      has an operational mode for encrypting data instead of overwriting it.
      <span class="scite-citeref-number" data-reference="Palo Alto Shamoon Nov 2016" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="http://researchcenter.paloaltonetworks.com/2016/11/unit42-shamoon-2-return-disttrack-wiper/" target="_blank">
         [10]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Unit 42 Shamoon3 2018" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://unit42.paloaltonetworks.com/shamoon-3-targets-oil-gas-organization/" target="_blank">
         [11]
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
      encrypts user files and demands that a ransom be paid in Bitcoin to decrypt those files.
      <span class="scite-citeref-number" data-reference="LogRhythm WannaCry" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://logrhythm.com/blog/a-technical-analysis-of-wannacry-ransomware/" target="_blank">
         [12]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye WannaCry 2017" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.fireeye.com/blog/threat-research/2017/05/wannacry-malware-profile.html" target="_blank">
         [2]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="SecureWorks WannaCry Analysis" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://www.secureworks.com/research/wcry-ransomware-analysis" target="_blank">
         [13]
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
  Consider implementing IT disaster recovery plans that contain procedures for regularly taking and testing data backups that can be used to restore organizational data.
  <span class="scite-citeref-number" data-reference="Ready.gov IT DRP" id="scite-ref-14-a">
   <sup>
    <a aria-describedby="qtip-13" data-hasqtip="13" href="https://www.ready.gov/business/implementation/IT" target="_blank">
     [14]
    </a>
   </sup>
  </span>
 </p>
 <p>
  In some cases, the means to decrypt files affected by a ransomware campaign is released to the public. Research trusted sources for public releases of decryptor tools/keys to reverse the effects of ransomware.
 </p>
 <p>
  Identify potentially malicious software and audit and/or block it by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-15-a">
   <sup>
    <a aria-describedby="qtip-14" data-hasqtip="14" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [15]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-16-a">
   <sup>
    <a aria-describedby="qtip-15" data-hasqtip="15" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [16]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-17-a">
   <sup>
    <a aria-describedby="qtip-16" data-hasqtip="16" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [17]
    </a>
   </sup>
  </span>
  or Software Restriction Policies
  <span class="scite-citeref-number" data-reference="Corio 2008" id="scite-ref-18-a">
   <sup>
    <a aria-describedby="qtip-17" data-hasqtip="17" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" target="_blank">
     [18]
    </a>
   </sup>
  </span>
  where appropriate.
  <span class="scite-citeref-number" data-reference="TechNet Applocker vs SRP" id="scite-ref-19-a">
   <sup>
    <a aria-describedby="qtip-18" data-hasqtip="18" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" target="_blank">
     [19]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Use process monitoring to monitor the execution and command line parameters of of binaries involved in data destruction activity, such as vssadmin, wbadmin, and bcdedit. Monitor for the creation of suspicious files as well as unusual file modification activity. In particular, look for large quantities of file modifications in user directories.
 </p>
 <p>
  In some cases, monitoring for unusual kernel driver installation activity can aid in detection.
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
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA16-091A" name="scite-1" rel="nofollow" target="_blank">
        US-CERT. (2016, March 31). Alert (TA16-091A): Ransomware and Recent Variants. Retrieved March 15, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/05/wannacry-malware-profile.html" name="scite-2" rel="nofollow" target="_blank">
        Berry, A., Homan, J., and Eitzman, R. (2017, May 23). WannaCry Malware Profile. Retrieved March 15, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA17-181A" name="scite-3" rel="nofollow" target="_blank">
        US-CERT. (2017, July 1). Alert (TA17-181A): Petya Ransomware. Retrieved March 15, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/AA18-337A" name="scite-4" rel="nofollow" target="_blank">
        US-CERT. (2018, December 3). Alert (AA18-337A): SamSam Ransomware. Retrieved March 15, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://content.fireeye.com/apt/rpt-apt38" name="scite-5" rel="nofollow" target="_blank">
        FireEye. (2018, October 03). APT38: Un-usual Suspects. Retrieved November 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.carbonblack.com/2019/03/22/tau-threat-intelligence-notification-lockergoga-ransomware/" name="scite-6" rel="nofollow" target="_blank">
        undefined. (2019, March 22). TAU Threat Intelligence Notification – LockerGoga Ransomware. Retrieved April 16, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://unit42.paloaltonetworks.com/born-this-way-origins-of-lockergoga/" name="scite-7" rel="nofollow" target="_blank">
        Harbison, M.. (2019, March 26). Born This Way? Origins of LockerGoga. Retrieved April 16, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2017/06/worldwide-ransomware-variant.html" name="scite-8" rel="nofollow" target="_blank">
        Chiu, A. (2016, June 27). New Ransomware Variant "Nyetya" Compromises Systems Worldwide. Retrieved March 26, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.sophos.com/en-us/medialibrary/PDFs/technical-papers/SamSam-ransomware-chooses-Its-targets-carefully-wpna.pdf" name="scite-9" rel="nofollow" target="_blank">
        Palotay, D. and Mackenzie, P. (2018, April). SamSam Ransomware Chooses Its Targets Carefully. Retrieved April 15, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/11/unit42-shamoon-2-return-disttrack-wiper/" name="scite-10" rel="nofollow" target="_blank">
        Falcone, R.. (2016, November 30). Shamoon 2: Return of the Disttrack Wiper. Retrieved January 11, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="11.5">
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://unit42.paloaltonetworks.com/shamoon-3-targets-oil-gas-organization/" name="scite-11" rel="nofollow" target="_blank">
        Falcone, R. (2018, December 13). Shamoon 3 Targets Oil and Gas Organization. Retrieved March 14, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://logrhythm.com/blog/a-technical-analysis-of-wannacry-ransomware/" name="scite-12" rel="nofollow" target="_blank">
        Noerenberg, E., Costis, A., and Quist, N. (2017, May 16). A Technical Analysis of WannaCry Ransomware. Retrieved March 25, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/wcry-ransomware-analysis" name="scite-13" rel="nofollow" target="_blank">
        Counter Threat Unit Research Team. (2017, May 18). WCry Ransomware Analysis. Retrieved March 26, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.ready.gov/business/implementation/IT" name="scite-14" rel="nofollow" target="_blank">
        Ready.gov. (n.d.). IT Disaster Recovery Plan. Retrieved March 15, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-15" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-16" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-17" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" name="scite-18" rel="nofollow" target="_blank">
        Corio, C., &amp; Sayana, D. P. (2008, June). Application Lockdown with Software Restriction Policies. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" name="scite-19" rel="nofollow" target="_blank">
        Microsoft. (2012, June 27). Using Software Restriction Policies and AppLocker Policies. Retrieved April 7, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
