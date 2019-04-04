<div class="container-fluid">
 <h1>
  System Firmware
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    The BIOS (Basic Input/Output System) and The Unified Extensible Firmware Interface (UEFI) or Extensible Firmware Interface (EFI) are examples of system firmware that operate as the software interface between the operating system and hardware of a computer.
    <span class="scite-citeref-number" data-reference="Wikipedia BIOS" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://en.wikipedia.org/wiki/BIOS" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Wikipedia UEFI" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://en.wikipedia.org/wiki/Unified_Extensible_Firmware_Interface" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="About UEFI" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="http://www.uefi.org/about" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    System firmware like BIOS and (U)EFI underly the functionality of a computer and may be modified by an adversary to perform or assist in malicious activity. Capabilities exist to overwrite the system firmware, which may give sophisticated adversaries a means to install malicious firmware updates as a means of persistence on a system that may be difficult to detect.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1019
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
      API monitoring, BIOS, EFI
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
      <a href="https://capec.mitre.org/data/definitions/532.html" target="_blank">
       CAPEC-532
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
      Ryan Becwar; McAfee
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
     <a href="https://attack.mitre.org/software/S0047">
      Hacking Team UEFI Rootkit
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0047">
       Hacking Team UEFI Rootkit
      </a>
      is a UEFI BIOS rootkit developed by the company Hacking Team to persist remote access software on some targeted systems.
      <span class="scite-citeref-number" data-reference="TrendMicro Hacking Team UEFI" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="http://blog.trendmicro.com/trendlabs-security-intelligence/hacking-team-uses-uefi-bios-rootkit-to-keep-rcs-9-agent-in-target-systems/" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0001">
      Trojan.Mebromi
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0001">
       Trojan.Mebromi
      </a>
      performs BIOS modification and can download and execute a file as well as protect itself from removal.
      <span class="scite-citeref-number" data-reference="Ge 2011" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="http://www.symantec.com/connect/blogs/bios-threat-showing-again" target="_blank">
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
  Prevent adversary access to privileged accounts or access necessary to perform this technique. Check the integrity of the existing BIOS or EFI to determine if it is vulnerable to modification. Patch the BIOS and EFI as necessary. Use Trusted Platform Module technology.
  <span class="scite-citeref-number" data-reference="TCG Trusted Platform Module" id="scite-ref-6-a">
   <sup>
    <a aria-describedby="qtip-5" data-hasqtip="5" href="http://www.trustedcomputinggroup.org/wp-content/uploads/Trusted-Platform-Module-Summary_04292008.pdf" target="_blank">
     [6]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  System firmware manipulation may be detected.
  <span class="scite-citeref-number" data-reference="MITRE Trustworthy Firmware Measurement" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="http://www.mitre.org/publications/project-stories/going-deep-into-the-bios-with-mitre-firmware-security-research" target="_blank">
     [7]
    </a>
   </sup>
  </span>
  Dump and inspect BIOS images on vulnerable systems and compare against known good images.
  <span class="scite-citeref-number" data-reference="MITRE Copernicus" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="http://www.mitre.org/capabilities/cybersecurity/overview/cybersecurity-blog/copernicus-question-your-assumptions-about" target="_blank">
     [8]
    </a>
   </sup>
  </span>
  Analyze differences to determine if malicious changes have occurred. Log attempts to read/write to BIOS and compare against known patching behavior.
 </p>
 <p>
  Likewise, EFI modules can be collected and compared against a known-clean list of EFI executable binaries to detect potentially malicious modules. The CHIPSEC framework can be used for analysis to determine if firmware modifications have been performed.
  <span class="scite-citeref-number" data-reference="McAfee CHIPSEC Blog" id="scite-ref-9-a">
   <sup>
    <a aria-describedby="qtip-8" data-hasqtip="8" href="https://securingtomorrow.mcafee.com/business/chipsec-support-vault-7-disclosure-scanning/" target="_blank">
     [9]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Github CHIPSEC" id="scite-ref-10-a">
   <sup>
    <a aria-describedby="qtip-9" data-hasqtip="9" href="https://github.com/chipsec/chipsec" target="_blank">
     [10]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Intel HackingTeam UEFI Rootkit" id="scite-ref-11-a">
   <sup>
    <a aria-describedby="qtip-10" data-hasqtip="10" href="http://www.intelsecurity.com/advanced-threat-research/content/data/HT-UEFI-rootkit.html" target="_blank">
     [11]
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
       <a class="external text" href="https://en.wikipedia.org/wiki/BIOS" name="scite-1" rel="nofollow" target="_blank">
        Wikipedia. (n.d.). BIOS. Retrieved January 5, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://en.wikipedia.org/wiki/Unified_Extensible_Firmware_Interface" name="scite-2" rel="nofollow" target="_blank">
        Wikipedia. (2017, July 10). Unified Extensible Firmware Interface. Retrieved July 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.uefi.org/about" name="scite-3" rel="nofollow" target="_blank">
        UEFI Forum. (n.d.). About UEFI Forum. Retrieved January 5, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.trendmicro.com/trendlabs-security-intelligence/hacking-team-uses-uefi-bios-rootkit-to-keep-rcs-9-agent-in-target-systems/" name="scite-4" rel="nofollow" target="_blank">
        Lin, P. (2015, July 13). Hacking Team Uses UEFI BIOS Rootkit to Keep RCS 9 Agent in Target Systems. Retrieved December 11, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/connect/blogs/bios-threat-showing-again" name="scite-5" rel="nofollow" target="_blank">
        Ge, L. (2011, September 9). BIOS Threat is Showing up Again!. Retrieved November 14, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.trustedcomputinggroup.org/wp-content/uploads/Trusted-Platform-Module-Summary_04292008.pdf" name="scite-6" rel="nofollow" target="_blank">
        Trusted Computing Group. (2008, April 29). Trusted Platform Module (TPM) Summary. Retrieved June 8, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="7.5">
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.mitre.org/publications/project-stories/going-deep-into-the-bios-with-mitre-firmware-security-research" name="scite-7" rel="nofollow" target="_blank">
        Upham, K. (2014, March). Going Deep into the BIOS with MITRE Firmware Security Research. Retrieved January 5, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.mitre.org/capabilities/cybersecurity/overview/cybersecurity-blog/copernicus-question-your-assumptions-about" name="scite-8" rel="nofollow" target="_blank">
        Butterworth, J. (2013, July 30). Copernicus: Question Your Assumptions about BIOS Security. Retrieved December 11, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/business/chipsec-support-vault-7-disclosure-scanning/" name="scite-9" rel="nofollow" target="_blank">
        Beek, C., Samani, R. (2017, March 8). CHIPSEC Support Against Vault 7 Disclosure Scanning. Retrieved March 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/chipsec/chipsec" name="scite-10" rel="nofollow" target="_blank">
        Intel. (2017, March 18). CHIPSEC Platform Security Assessment Framework. Retrieved March 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.intelsecurity.com/advanced-threat-research/content/data/HT-UEFI-rootkit.html" name="scite-11" rel="nofollow" target="_blank">
        Intel Security. (2005, July 16). HackingTeam's UEFI Rootkit Details. Retrieved March 20, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
