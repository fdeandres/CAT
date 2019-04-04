<div class="container-fluid">
 <h1>
  NTFS File Attributes
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Every New Technology File System (NTFS) formatted partition contains a Master File Table (MFT) that maintains a record for every file/directory on the partition.
    <span class="scite-citeref-number" data-reference="SpectorOps Host-Based Jul 2017" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://posts.specterops.io/host-based-threat-modeling-indicator-design-a9dbbb53d5ea" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    Within MFT entries are file attributes,
    <span class="scite-citeref-number" data-reference="Microsoft NTFS File Attributes Aug 2010" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://blogs.technet.microsoft.com/askcore/2010/08/25/ntfs-file-attributes/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    such as Extended Attributes (EA) and Data [known as Alternate Data Streams (ADSs) when more than one Data attribute is present], that can be used to store arbitrary data (and even complete files).
    <span class="scite-citeref-number" data-reference="SpectorOps Host-Based Jul 2017" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://posts.specterops.io/host-based-threat-modeling-indicator-design-a9dbbb53d5ea" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Microsoft File Streams" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="http://msdn.microsoft.com/en-us/library/aa364404" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="MalwareBytes ADS July 2015" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://blog.malwarebytes.com/101/2015/07/introduction-to-alternate-data-streams/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Microsoft ADS Mar 2014" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://blogs.technet.microsoft.com/askcore/2013/03/24/alternate-data-streams-in-ntfs/" target="_blank">
       [5]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries may store malicious data or binaries in file attribute metadata instead of directly in files. This may be done to evade some defenses, such as static indicator scanning tools and anti-virus.
    <span class="scite-citeref-number" data-reference="Journey into IR ZeroAccess NTFS EA" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="http://journeyintoir.blogspot.com/2012/12/extracting-zeroaccess-from-ntfs.html" target="_blank">
       [6]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="MalwareBytes ADS July 2015" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://blog.malwarebytes.com/101/2015/07/introduction-to-alternate-data-streams/" target="_blank">
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
      : T1096
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
      Windows
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
      File monitoring, Kernel drivers, API monitoring, Process command-line parameters
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
      Signature-based detection, Host forensic analysis, Anti-virus
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
       Contributors:
      </span>
      Red Canary; Oddvar Moe, @oddvarmoe
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
     <a href="https://attack.mitre.org/software/S0168">
      Gazer
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0168">
       Gazer
      </a>
      stores configuration items in alternate data streams (ADSs) if the Registry is not accessible.
      <span class="scite-citeref-number" data-reference="ESET Gazer Aug 2017" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf" target="_blank">
         [7]
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
      hides many of its backdoor payloads in an alternate data stream (ADS).
      <span class="scite-citeref-number" data-reference="Volexity PowerDuke November 2016" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.volexity.com/blog/2016/11/09/powerduke-post-election-spear-phishing-campaigns-targeting-think-tanks-and-ngos/" target="_blank">
         [8]
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
      If the victim is using PowerShell 3.0 or later,
      <a href="https://attack.mitre.org/software/S0145">
       POWERSOURCE
      </a>
      writes its decoded payload to an alternate data stream (ADS) named kernel32.dll that is saved in
      <code>
       %PROGRAMDATA%\Windows\
      </code>
      .
      <span class="scite-citeref-number" data-reference="Cisco DNSMessenger March 2017" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="http://blog.talosintelligence.com/2017/03/dnsmessenger.html" target="_blank">
         [9]
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
      The
      <a href="https://attack.mitre.org/software/S0019">
       Regin
      </a>
      malware platform uses Extended Attributes to store encrypted executables.
      <span class="scite-citeref-number" data-reference="Kaspersky Regin" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://securelist.com/files/2014/11/Kaspersky_Lab_whitepaper_Regin_platform_eng.pdf" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0027">
      Zeroaccess
     </a>
    </td>
    <td>
     <p>
      Some variants of the
      <a href="https://attack.mitre.org/software/S0027">
       Zeroaccess
      </a>
      Trojan have been known to store data in Extended Attributes.
      <span class="scite-citeref-number" data-reference="Ciubotariu 2014" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="http://www.symantec.com/connect/blogs/trojanzeroaccessc-hidden-ntfs-ea" target="_blank">
         [11]
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
  It may be difficult or inadvisable to block access to EA and ADSs.
  <span class="scite-citeref-number" data-reference="Microsoft ADS Mar 2014" id="scite-ref-5-a">
   <sup>
    <a aria-describedby="qtip-4" data-hasqtip="4" href="https://blogs.technet.microsoft.com/askcore/2013/03/24/alternate-data-streams-in-ntfs/" target="_blank">
     [5]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Symantec ADS May 2009" id="scite-ref-12-a">
   <sup>
    <a aria-describedby="qtip-11" data-hasqtip="11" href="https://www.symantec.com/connect/articles/what-you-need-know-about-alternate-data-streams-windows-your-data-secure-can-you-restore" target="_blank">
     [12]
    </a>
   </sup>
  </span>
  Efforts should be focused on preventing potentially malicious software from running. Identify and block potentially malicious software that may contain functionality to hide information in EA and ADSs by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-13-a">
   <sup>
    <a aria-describedby="qtip-12" data-hasqtip="12" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [13]
    </a>
   </sup>
  </span>
  tools like AppLocker
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-14-a">
   <sup>
    <a aria-describedby="qtip-13" data-hasqtip="13" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [14]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-15-a">
   <sup>
    <a aria-describedby="qtip-14" data-hasqtip="14" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [15]
    </a>
   </sup>
  </span>
  or Software Restriction Policies
  <span class="scite-citeref-number" data-reference="Corio 2008" id="scite-ref-16-a">
   <sup>
    <a aria-describedby="qtip-15" data-hasqtip="15" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" target="_blank">
     [16]
    </a>
   </sup>
  </span>
  where appropriate.
  <span class="scite-citeref-number" data-reference="TechNet Applocker vs SRP" id="scite-ref-17-a">
   <sup>
    <a aria-describedby="qtip-16" data-hasqtip="16" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" target="_blank">
     [17]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Consider adjusting read and write permissions for NTFS EA, though this should be tested to ensure routine OS operations are not impeded.
  <span class="scite-citeref-number" data-reference="InsiderThreat NTFS EA Oct 2017" id="scite-ref-18-a">
   <sup>
    <a aria-describedby="qtip-17" data-hasqtip="17" href="https://blog.stealthbits.com/attack-step-3-persistence-ntfs-extended-attributes-file-system-attacks" target="_blank">
     [18]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Forensic techniques exist to identify information stored in NTFS EA.
  <span class="scite-citeref-number" data-reference="Journey into IR ZeroAccess NTFS EA" id="scite-ref-6-a">
   <sup>
    <a aria-describedby="qtip-5" data-hasqtip="5" href="http://journeyintoir.blogspot.com/2012/12/extracting-zeroaccess-from-ntfs.html" target="_blank">
     [6]
    </a>
   </sup>
  </span>
  Monitor calls to the ZwSetEaFile and ZwQueryEaFile Windows API functions as well as binaries used to interact with EA,
  <span class="scite-citeref-number" data-reference="Oddvar Moe ADS1 Jan 2018" id="scite-ref-19-a">
   <sup>
    <a aria-describedby="qtip-18" data-hasqtip="18" href="https://oddvar.moe/2018/01/14/putting-data-in-alternate-data-streams-and-how-to-execute-it/" target="_blank">
     [19]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Oddvar Moe ADS2 Apr 2018" id="scite-ref-20-a">
   <sup>
    <a aria-describedby="qtip-19" data-hasqtip="19" href="https://oddvar.moe/2018/04/11/putting-data-in-alternate-data-streams-and-how-to-execute-it-part-2/" target="_blank">
     [20]
    </a>
   </sup>
  </span>
  and consider regularly scanning for the presence of modified information.
  <span class="scite-citeref-number" data-reference="SpectorOps Host-Based Jul 2017" id="scite-ref-1-a">
   <sup>
    <a aria-describedby="qtip-0" data-hasqtip="0" href="https://posts.specterops.io/host-based-threat-modeling-indicator-design-a9dbbb53d5ea" target="_blank">
     [1]
    </a>
   </sup>
  </span>
 </p>
 <p>
  There are many ways to create and interact with ADSs using Windows utilities. Monitor for operations (execution, copies, etc.) with file names that contain colons. This syntax (ex:
  <code>
   file.ext:ads[.ext]
  </code>
  ) is commonly associated with ADSs.
  <span class="scite-citeref-number" data-reference="Microsoft ADS Mar 2014" id="scite-ref-5-a">
   <sup>
    <a aria-describedby="qtip-4" data-hasqtip="4" href="https://blogs.technet.microsoft.com/askcore/2013/03/24/alternate-data-streams-in-ntfs/" target="_blank">
     [5]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Oddvar Moe ADS1 Jan 2018" id="scite-ref-19-a">
   <sup>
    <a aria-describedby="qtip-18" data-hasqtip="18" href="https://oddvar.moe/2018/01/14/putting-data-in-alternate-data-streams-and-how-to-execute-it/" target="_blank">
     [19]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Oddvar Moe ADS2 Apr 2018" id="scite-ref-20-a">
   <sup>
    <a aria-describedby="qtip-19" data-hasqtip="19" href="https://oddvar.moe/2018/04/11/putting-data-in-alternate-data-streams-and-how-to-execute-it-part-2/" target="_blank">
     [20]
    </a>
   </sup>
  </span>
  For a more exhaustive list of utilities that can be used to execute and create ADSs, see https://gist.github.com/api0cradle/cdd2d0d0ec9abb686f0e89306e277b8f.
 </p>
 <p>
  The Streams tool of Sysinternals can be used to uncover files with ADSs. The
  <code>
   dir /r
  </code>
  command can also be used to display ADSs.
  <span class="scite-citeref-number" data-reference="Symantec ADS May 2009" id="scite-ref-12-a">
   <sup>
    <a aria-describedby="qtip-11" data-hasqtip="11" href="https://www.symantec.com/connect/articles/what-you-need-know-about-alternate-data-streams-windows-your-data-secure-can-you-restore" target="_blank">
     [12]
    </a>
   </sup>
  </span>
  Many PowerShell commands (such as Get-Item, Set-Item, Remove-Item, and Get-ChildItem) can also accept a
  <code>
   -stream
  </code>
  parameter to interact with ADSs.
  <span class="scite-citeref-number" data-reference="MalwareBytes ADS July 2015" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="https://blog.malwarebytes.com/101/2015/07/introduction-to-alternate-data-streams/" target="_blank">
     [4]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Microsoft ADS Mar 2014" id="scite-ref-5-a">
   <sup>
    <a aria-describedby="qtip-4" data-hasqtip="4" href="https://blogs.technet.microsoft.com/askcore/2013/03/24/alternate-data-streams-in-ntfs/" target="_blank">
     [5]
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
       <a class="external text" href="https://posts.specterops.io/host-based-threat-modeling-indicator-design-a9dbbb53d5ea" name="scite-1" rel="nofollow" target="_blank">
        Atkinson, J. (2017, July 18). Host-based Threat Modeling &amp; Indicator Design. Retrieved March 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://blogs.technet.microsoft.com/askcore/2010/08/25/ntfs-file-attributes/" name="scite-2" rel="nofollow" target="_blank">
        Hughes, J. (2010, August 25). NTFS File Attributes. Retrieved March 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="http://msdn.microsoft.com/en-us/library/aa364404" name="scite-3" rel="nofollow" target="_blank">
        Microsoft. (n.d.). File Streams. Retrieved December 2, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.malwarebytes.com/101/2015/07/introduction-to-alternate-data-streams/" name="scite-4" rel="nofollow" target="_blank">
        Arntz, P. (2015, July 22). Introduction to Alternate Data Streams. Retrieved March 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://blogs.technet.microsoft.com/askcore/2013/03/24/alternate-data-streams-in-ntfs/" name="scite-5" rel="nofollow" target="_blank">
        Marlin, J. (2013, March 24). Alternate Data Streams in NTFS. Retrieved March 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="http://journeyintoir.blogspot.com/2012/12/extracting-zeroaccess-from-ntfs.html" name="scite-6" rel="nofollow" target="_blank">
        Harrell, C. (2012, December 11). Extracting ZeroAccess from NTFS Extended Attributes. Retrieved June 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf" name="scite-7" rel="nofollow" target="_blank">
        ESET. (2017, August). Gazing at Gazer: Turla’s new second stage backdoor. Retrieved September 14, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.volexity.com/blog/2016/11/09/powerduke-post-election-spear-phishing-campaigns-targeting-think-tanks-and-ngos/" name="scite-8" rel="nofollow" target="_blank">
        Adair, S.. (2016, November 9). PowerDuke: Widespread Post-Election Spear Phishing Campaigns Targeting Think Tanks and NGOs. Retrieved January 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.talosintelligence.com/2017/03/dnsmessenger.html" name="scite-9" rel="nofollow" target="_blank">
        Brumaghin, E. and Grady, C.. (2017, March 2). Covert Channels and Poor Decisions: The Tale of DNSMessenger. Retrieved March 8, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/files/2014/11/Kaspersky_Lab_whitepaper_Regin_platform_eng.pdf" name="scite-10" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2014, November 24). THE REGIN PLATFORM NATION-STATE OWNAGE OF GSM NETWORKS. Retrieved December 1, 2014.
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
       <a class="external text" href="http://www.symantec.com/connect/blogs/trojanzeroaccessc-hidden-ntfs-ea" name="scite-11" rel="nofollow" target="_blank">
        Ciubotariu, M. (2014, January 23). Trojan.Zeroaccess.C Hidden in NTFS EA. Retrieved December 2, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/connect/articles/what-you-need-know-about-alternate-data-streams-windows-your-data-secure-can-you-restore" name="scite-12" rel="nofollow" target="_blank">
        Pravs. (2009, May 25). What you need to know about alternate data streams in windows? Is your Data secure? Can you restore that?. Retrieved March 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-13" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-14" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-15" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" name="scite-16" rel="nofollow" target="_blank">
        Corio, C., &amp; Sayana, D. P. (2008, June). Application Lockdown with Software Restriction Policies. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" name="scite-17" rel="nofollow" target="_blank">
        Microsoft. (2012, June 27). Using Software Restriction Policies and AppLocker Policies. Retrieved April 7, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.stealthbits.com/attack-step-3-persistence-ntfs-extended-attributes-file-system-attacks" name="scite-18" rel="nofollow" target="_blank">
        Sander, J. (2017, October 12). Attack Step 3: Persistence with NTFS Extended Attributes – File System Attacks. Retrieved March 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://oddvar.moe/2018/01/14/putting-data-in-alternate-data-streams-and-how-to-execute-it/" name="scite-19" rel="nofollow" target="_blank">
        Moe, O. (2018, January 14). Putting Data in Alternate Data Streams and How to Execute It. Retrieved June 30, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://oddvar.moe/2018/04/11/putting-data-in-alternate-data-streams-and-how-to-execute-it-part-2/" name="scite-20" rel="nofollow" target="_blank">
        Moe, O. (2018, April 11). Putting Data in Alternate Data Streams and How to Execute It - Part 2. Retrieved June 30, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
