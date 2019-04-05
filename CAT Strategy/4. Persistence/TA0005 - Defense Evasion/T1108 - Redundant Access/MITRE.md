<div class="container-fluid">
 <h1>
  Redundant Access
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries may use more than one remote access tool with varying command and control protocols as a hedge against detection. If one type of tool is detected and blocked or removed as a response but the organization did not gain a full understanding of the adversary's tools and access, then the adversary will be able to retain access to the network. Adversaries may also attempt to gain access to
    <a href="https://attack.mitre.org/techniques/T1078">
     Valid Accounts
    </a>
    to use
    <a href="https://attack.mitre.org/techniques/T1133">
     External Remote Services
    </a>
    such as external VPNs as a way to maintain access despite interruptions to remote access tools deployed within a target network.
    <span class="scite-citeref-number" data-reference="Mandiant APT1" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Use of a
    <a href="https://attack.mitre.org/techniques/T1100">
     Web Shell
    </a>
    is one such way to maintain access to a network through an externally accessible Web server.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1108
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
      : Defense Evasion, Persistence
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
      User, Administrator, SYSTEM
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
      Process monitoring, Process use of network, Packet capture, Network protocol analysis, File monitoring, Authentication logs, Binary file metadata
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
      Network intrusion detection system, Anti-virus
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
     <a href="https://attack.mitre.org/software/S0066">
      3PARA RAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0066">
       3PARA RAT
      </a>
      will sleep until after a date/time value loaded from a .dat file has passed. This allows the RAT to remain dormant until a set date, which could allow a means to regain access if other parts of the actors' toolset are removed from a victim.
      <span class="scite-citeref-number" data-reference="CrowdStrike Putter Panda" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="http://cdn0.vox-cdn.com/assets/4589853/crowdstrike-intelligence-report-putter-panda.original.pdf" target="_blank">
         [2]
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
      has been known to use multiple backdoors per campaign.
      <span class="scite-citeref-number" data-reference="APT3 Adversary Emulation Plan" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://attack.mitre.org/docs/APT3_Adversary_Emulation_Plan.pdf" target="_blank">
         [3]
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
      has used TeamViewer to preserve remote access in case control using the Cobalt Strike module was lost.
      <span class="scite-citeref-number" data-reference="Group IB Cobalt Aug 2017" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.group-ib.com/blog/cobalt" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0053">
      FIN5
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0053">
       FIN5
      </a>
      maintains access to victim environments by using
      <a href="https://attack.mitre.org/techniques/T1078">
       Valid Accounts
      </a>
      to access
      <a href="https://attack.mitre.org/techniques/T1133">
       External Remote Services
      </a>
      as well as establishing a backup RDP tunnel by using
      <a href="https://attack.mitre.org/software/S0173">
       FLIPSIDE
      </a>
      .
      <span class="scite-citeref-number" data-reference="Mandiant FIN5 GrrCON Oct 2016" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.youtube.com/watch?v=fevGZs0EQu8" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0077">
      Leafminer
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0077">
       Leafminer
      </a>
      used a tool called Imecab to set up a persistent remote access account on the victim machine.
      <span class="scite-citeref-number" data-reference="Symantec Leafminer July 2018" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.symantec.com/blogs/threat-intelligence/leafminer-espionage-middle-east" target="_blank">
         [6]
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
      has used
      <a href="https://attack.mitre.org/software/S0258">
       RGDoor
      </a>
      via Web shell to establish redundant access. The group has also used harvested credentials to gain access to Internet-accessible resources such as Outlook Web Access, which could be used for redundant access.
      <span class="scite-citeref-number" data-reference="Unit 42 Playbook Dec 2017" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://pan-unit42.github.io/playbook_viewer/" target="_blank">
         [7]
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
      has deployed backup web shells and obtained OWA account credentials during intrusions that it subsequently used to attempt to regain access when evicted from a victim network.
      <span class="scite-citeref-number" data-reference="SecureWorks BRONZE UNION June 2017" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.secureworks.com/research/bronze-union" target="_blank">
         [8]
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
  Identify and block potentially malicious software that may be used as a remote access tool, and audit and/or block it by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-9-a">
   <sup>
    <a aria-describedby="qtip-8" data-hasqtip="8" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [9]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-10-a">
   <sup>
    <a aria-describedby="qtip-9" data-hasqtip="9" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [10]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-11-a">
   <sup>
    <a aria-describedby="qtip-10" data-hasqtip="10" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [11]
    </a>
   </sup>
  </span>
  or Software Restriction Policies
  <span class="scite-citeref-number" data-reference="Corio 2008" id="scite-ref-12-a">
   <sup>
    <a aria-describedby="qtip-11" data-hasqtip="11" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" target="_blank">
     [12]
    </a>
   </sup>
  </span>
  where appropriate.
  <span class="scite-citeref-number" data-reference="TechNet Applocker vs SRP" id="scite-ref-13-a">
   <sup>
    <a aria-describedby="qtip-12" data-hasqtip="12" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" target="_blank">
     [13]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Network intrusion detection and prevention systems that use network signatures to identify traffic for specific adversary malware can be used to mitigate activity at the network level. Signatures are often for unique indicators within protocols and will be different across various malware families and versions. Adversaries will likely change tool signatures over time or construct protocols in such a way as to avoid detection by common defensive tools.
  <span class="scite-citeref-number" data-reference="University of Birmingham C2" id="scite-ref-14-a">
   <sup>
    <a aria-describedby="qtip-13" data-hasqtip="13" href="https://arxiv.org/ftp/arxiv/papers/1408/1408.1136.pdf" target="_blank">
     [14]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Existing methods of detecting remote access tools are helpful. Backup remote access tools or other access points may not have established command and control channels open during an intrusion, so the volume of data transferred may not be as high as the primary channel unless access is lost.
 </p>
 <p>
  Detection of tools based on beacon traffic, Command and Control protocol, or adversary infrastructure require prior threat intelligence on tools, IP addresses, and/or domains the adversary may use, along with the ability to detect use at the network boundary. Prior knowledge of indicators of compromise may also help detect adversary tools at the endpoint if tools are available to scan for those indicators.
 </p>
 <p>
  If an intrusion is in progress and sufficient endpoint data or decoded command and control traffic is collected, then defenders will likely be able to detect additional tools dropped as the adversary is conducting the operation.
 </p>
 <p>
  For alternative access using externally accessible VPNs or remote services, follow detection recommendations under
  <a href="https://attack.mitre.org/techniques/T1078">
   Valid Accounts
  </a>
  and
  <a href="https://attack.mitre.org/techniques/T1133">
   External Remote Services
  </a>
  to collect account use information.
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
       <a class="external text" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf" name="scite-1" rel="nofollow" target="_blank">
        Mandiant. (n.d.). APT1 Exposing One of China’s Cyber Espionage Units. Retrieved July 18, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://cdn0.vox-cdn.com/assets/4589853/crowdstrike-intelligence-report-putter-panda.original.pdf" name="scite-2" rel="nofollow" target="_blank">
        Crowdstrike Global Intelligence Team. (2014, June 9). CrowdStrike Intelligence Report: Putter Panda. Retrieved January 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://attack.mitre.org/docs/APT3_Adversary_Emulation_Plan.pdf" name="scite-3" rel="nofollow" target="_blank">
        Korban, C, et al. (2017, September). APT3 Adversary Emulation Plan. Retrieved January 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.group-ib.com/blog/cobalt" name="scite-4" rel="nofollow" target="_blank">
        Matveeva, V. (2017, August 15). Secrets of Cobalt. Retrieved October 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.youtube.com/watch?v=fevGZs0EQu8" name="scite-5" rel="nofollow" target="_blank">
        Bromiley, M. and Lewis, P. (2016, October 7). Attacking the Hospitality and Gaming Industries: Tracking an Attacker Around the World in 7 Years. Retrieved October 6, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/leafminer-espionage-middle-east" name="scite-6" rel="nofollow" target="_blank">
        Symantec Security Response. (2018, July 25). Leafminer: New Espionage Campaigns Targeting Middle Eastern Regions. Retrieved August 28, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://pan-unit42.github.io/playbook_viewer/" name="scite-7" rel="nofollow" target="_blank">
        Unit 42. (2017, December 15). Unit 42 Playbook Viewer. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="8.0">
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/bronze-union" name="scite-8" rel="nofollow" target="_blank">
        Counter Threat Unit Research Team. (2017, June 27). BRONZE UNION Cyberespionage Persists Despite Disclosures. Retrieved July 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-9" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-10" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-11" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" name="scite-12" rel="nofollow" target="_blank">
        Corio, C., &amp; Sayana, D. P. (2008, June). Application Lockdown with Software Restriction Policies. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" name="scite-13" rel="nofollow" target="_blank">
        Microsoft. (2012, June 27). Using Software Restriction Policies and AppLocker Policies. Retrieved April 7, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://arxiv.org/ftp/arxiv/papers/1408/1408.1136.pdf" name="scite-14" rel="nofollow" target="_blank">
        Gardiner, J.,  Cova, M., Nagaraja, S. (2014, February). Command &amp; Control Understanding, Denying and Detecting. Retrieved April 20, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
