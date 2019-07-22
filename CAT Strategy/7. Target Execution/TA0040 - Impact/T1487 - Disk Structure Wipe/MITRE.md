<div class="container-fluid">
 <h1>
  Disk Structure Wipe
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries may corrupt or wipe the disk data structures on hard drive necessary to boot systems; targeting specific critical systems as well as a large number of systems in a network to interrupt availability to system and network resources.
   </p>
   <p>
    Adversaries may attempt to render the system unable to boot by overwriting critical data located in structures such as the master boot record (MBR) or partition table.
    <span class="scite-citeref-number" data-reference="Symantec Shamoon 2012" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.symantec.com/connect/blogs/shamoon-attacks" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="FireEye Shamoon Nov 2016" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.fireeye.com/blog/threat-research/2016/11/fireeye_respondsto.html" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Palo Alto Shamoon Nov 2016" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="http://researchcenter.paloaltonetworks.com/2016/11/unit42-shamoon-2-return-disttrack-wiper/" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Kaspersky StoneDrill 2017" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07180722/Report_Shamoon_StoneDrill_final.pdf" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Unit 42 Shamoon3 2018" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://unit42.paloaltonetworks.com/shamoon-3-targets-oil-gas-organization/" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    The data contained in disk structures may include the initial executable code for loading an operating system or the location of the file system partitions on disk. If this information is not present, the computer will not be able to load an operating system during the boot process, leaving the computer unavailable.
    <a href="https://attack.mitre.org/techniques/T1487">
     Disk Structure Wipe
    </a>
    may be performed in isolation, or along with
    <a href="https://attack.mitre.org/techniques/T1488">
     Disk Content Wipe
    </a>
    if all sectors of a disk are wiped.
   </p>
   <p>
    To maximize impact on the target organization, malware designed for destroying disk structures may have worm-like features to propagate across a network by leveraging other techniques like
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
    <span class="scite-citeref-number" data-reference="Symantec Shamoon 2012" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.symantec.com/connect/blogs/shamoon-attacks" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="FireEye Shamoon Nov 2016" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.fireeye.com/blog/threat-research/2016/11/fireeye_respondsto.html" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Palo Alto Shamoon Nov 2016" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="http://researchcenter.paloaltonetworks.com/2016/11/unit42-shamoon-2-return-disttrack-wiper/" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Kaspersky StoneDrill 2017" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07180722/Report_Shamoon_StoneDrill_final.pdf" target="_blank">
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
      : T1487
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
      Windows, macOS, Linux
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
      Administrator, root, SYSTEM
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
      Kernel drivers, MBR
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
     <a href="https://attack.mitre.org/groups/G0067">
      APT37
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0067">
       APT37
      </a>
      has access to destructive malware that is capable of overwriting a machine's Master Boot Record (MBR).
      <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
         [6]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Talos Group123" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://blog.talosintelligence.com/2018/01/korea-in-crosshairs.html" target="_blank">
         [7]
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
      has used a custom MBR wiper named BOOTWRECK to render systems inoperable.
      <span class="scite-citeref-number" data-reference="FireEye APT38 Oct 2018" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://content.fireeye.com/apt/rpt-apt38" target="_blank">
         [8]
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
      malware SHARPKNOT overwrites and deletes the Master Boot Record (MBR) on the victim's machine and has possessed MBR wiper malware since at least 2009.
      <span class="scite-citeref-number" data-reference="US-CERT SHARPKNOT June 2018" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536.11.WHITE.pdf" target="_blank">
         [9]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0364">
      RawDisk
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0364">
       RawDisk
      </a>
      was used in
      <a href="https://attack.mitre.org/software/S0140">
       Shamoon
      </a>
      to help overwrite components of disk structure like the MBR and disk partitions.
      <span class="scite-citeref-number" data-reference="Palo Alto Shamoon Nov 2016" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="http://researchcenter.paloaltonetworks.com/2016/11/unit42-shamoon-2-return-disttrack-wiper/" target="_blank">
         [3]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Unit 42 Shamoon3 2018" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://unit42.paloaltonetworks.com/shamoon-3-targets-oil-gas-organization/" target="_blank">
         [5]
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
      has been seen overwriting features of disk structure such as the MBR.
      <span class="scite-citeref-number" data-reference="Symantec Shamoon 2012" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.symantec.com/connect/blogs/shamoon-attacks" target="_blank">
         [1]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye Shamoon Nov 2016" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.fireeye.com/blog/threat-research/2016/11/fireeye_respondsto.html" target="_blank">
         [2]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Palo Alto Shamoon Nov 2016" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="http://researchcenter.paloaltonetworks.com/2016/11/unit42-shamoon-2-return-disttrack-wiper/" target="_blank">
         [3]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Unit 42 Shamoon3 2018" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://unit42.paloaltonetworks.com/shamoon-3-targets-oil-gas-organization/" target="_blank">
         [5]
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
  Consider implementing IT disaster recovery plans that contain procedures for taking regular data backups that can be used to restore organizational data.
  <span class="scite-citeref-number" data-reference="Ready.gov IT DRP" id="scite-ref-11-a">
   <sup>
    <a aria-describedby="qtip-10" data-hasqtip="10" href="https://www.ready.gov/business/implementation/IT" target="_blank">
     [11]
    </a>
   </sup>
  </span>
  Ensure backups are stored off system and is protected from common methods adversaries may use to gain access and destroy the backups to prevent recovery.
 </p>
 <p>
  Identify potentially malicious software and audit and/or block it by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-12-a">
   <sup>
    <a aria-describedby="qtip-11" data-hasqtip="11" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [12]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-13-a">
   <sup>
    <a aria-describedby="qtip-12" data-hasqtip="12" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [13]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-14-a">
   <sup>
    <a aria-describedby="qtip-13" data-hasqtip="13" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [14]
    </a>
   </sup>
  </span>
  or Software Restriction Policies
  <span class="scite-citeref-number" data-reference="Corio 2008" id="scite-ref-15-a">
   <sup>
    <a aria-describedby="qtip-14" data-hasqtip="14" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" target="_blank">
     [15]
    </a>
   </sup>
  </span>
  where appropriate.
  <span class="scite-citeref-number" data-reference="TechNet Applocker vs SRP" id="scite-ref-16-a">
   <sup>
    <a aria-describedby="qtip-15" data-hasqtip="15" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" target="_blank">
     [16]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Look for attempts to read/write to sensitive locations like the master boot record and the disk partition table. Monitor for unusual kernel driver installation activity.
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
       <a class="external text" href="https://www.symantec.com/connect/blogs/shamoon-attacks" name="scite-1" rel="nofollow" target="_blank">
        Symantec. (2012, August 16). The Shamoon Attacks. Retrieved March 14, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2016/11/fireeye_respondsto.html" name="scite-2" rel="nofollow" target="_blank">
        FireEye. (2016, November 30). FireEye Responds to Wave of Destructive Cyber Attacks in Gulf Region. Retrieved January 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/11/unit42-shamoon-2-return-disttrack-wiper/" name="scite-3" rel="nofollow" target="_blank">
        Falcone, R.. (2016, November 30). Shamoon 2: Return of the Disttrack Wiper. Retrieved January 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07180722/Report_Shamoon_StoneDrill_final.pdf" name="scite-4" rel="nofollow" target="_blank">
        Kaspersky Lab. (2017, March 7). From Shamoon to StoneDrill: Wipers attacking Saudi organizations and beyond. Retrieved March 14, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://unit42.paloaltonetworks.com/shamoon-3-targets-oil-gas-organization/" name="scite-5" rel="nofollow" target="_blank">
        Falcone, R. (2018, December 13). Shamoon 3 Targets Oil and Gas Organization. Retrieved March 14, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" name="scite-6" rel="nofollow" target="_blank">
        FireEye. (2018, February 20). APT37 (Reaper): The Overlooked North Korean Actor. Retrieved March 1, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/01/korea-in-crosshairs.html" name="scite-7" rel="nofollow" target="_blank">
        Mercer, W., Rascagneres, P. (2018, January 16). Korea In The Crosshairs. Retrieved May 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://content.fireeye.com/apt/rpt-apt38" name="scite-8" rel="nofollow" target="_blank">
        FireEye. (2018, October 03). APT38: Un-usual Suspects. Retrieved November 6, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="9.0">
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536.11.WHITE.pdf" name="scite-9" rel="nofollow" target="_blank">
        US-CERT. (2018, March 09). Malware Analysis Report (MAR) - 10135536.11.WHITE. Retrieved June 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" name="scite-10" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Unraveling the Long Thread of the Sony Attack. Retrieved February 25, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.ready.gov/business/implementation/IT" name="scite-11" rel="nofollow" target="_blank">
        Ready.gov. (n.d.). IT Disaster Recovery Plan. Retrieved March 15, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-12" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-13" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-14" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" name="scite-15" rel="nofollow" target="_blank">
        Corio, C., &amp; Sayana, D. P. (2008, June). Application Lockdown with Software Restriction Policies. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" name="scite-16" rel="nofollow" target="_blank">
        Microsoft. (2012, June 27). Using Software Restriction Policies and AppLocker Policies. Retrieved April 7, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
