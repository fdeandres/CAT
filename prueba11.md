<div class="container-fluid">
 <h1>
  Drive-by Compromise
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    A drive-by compromise is when an adversary gains access to a system through a user visiting a website over the normal course of browsing. With this technique, the user's web browser is targeted for exploitation. This can happen in several ways, but there are a few main components:
   </p>
   <p>
    Multiple ways of delivering exploit code to a browser exist, including:
   </p>
   <ul>
    <li>
     A legitimate website is compromised where adversaries have injected some form of malicious code such as JavaScript, iFrames, cross-site scripting.
    </li>
    <li>
     Malicious ads are paid for and served through legitimate ad providers.
    </li>
    <li>
     Built-in web application interfaces are leveraged for the insertion of any other kind of object that can be used to display web content or contain a script that executes on the visiting client (e.g. forum posts, comments, and other user controllable web content).
    </li>
   </ul>
   <p>
    Often the website used by an adversary is one visited by a specific community, such as government, a particular industry, or region, where the goal is to compromise a specific user or set of users based on a shared interest. This kind of targeted attack is referred to a strategic web compromise or watering hole attack. There are several known examples of this occurring.
    <span class="scite-citeref-number" data-reference="Shadowserver Strategic Web Compromise" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://blog.shadowserver.org/2012/05/15/cyber-espionage-strategic-web-compromises-trusted-websites-serving-dangerous-results/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Typical drive-by compromise process:
   </p>
   <ol>
    <li>
     A user visits a website that is used to host the adversary controlled content.
    </li>
    <li>
     Scripts automatically execute, typically searching versions of the browser and plugins for a potentially vulnerable version.
     <ul>
      <li>
       The user may be required to assist in this process by enabling scripting or active website components and ignoring warning dialog boxes.
      </li>
     </ul>
    </li>
    <li>
     Upon finding a vulnerable version, exploit code is delivered to the browser.
    </li>
    <li>
     If exploitation is successful, then it will give the adversary code execution on the user's system unless other protections are in place.
     <ul>
      <li>
       In some cases a second visit to the website after the initial scan is required before exploit code is delivered.
      </li>
     </ul>
    </li>
   </ol>
   <p>
    Unlike
    <a href="https://attack.mitre.orgtechniques/T1190">
     Exploit Public-Facing Application
    </a>
    , the focus of this technique is to exploit software on a client endpoint upon visiting a website. This will commonly give an adversary access to systems on the internal network instead of external systems that may be in a DMZ.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1189
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
      : Initial Access
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Platform:
      </span>
      Windows, Linux, macOS
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
      Packet capture, Network device logs, Process use of network, Web proxy, Network intrusion detection system, SSL/TLS inspection
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
     <a href="https://attack.mitre.orggroups/G0073">
      APT19
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.orggroups/G0073">
       APT19
      </a>
      performed a watering hole attack on forbes.com in 2014 to compromise targets.
      <span class="scite-citeref-number" data-reference="Unit 42 C0d0so0 Jan 2016" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://researchcenter.paloaltonetworks.com/2016/01/new-attacks-linked-to-c0d0s0-group/" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.orggroups/G0050">
      APT32
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.orggroups/G0050">
       APT32
      </a>
      has infected victims by tricking them into visiting compromised watering hole websites.
      <span class="scite-citeref-number" data-reference="ESET OceanLotus" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.welivesecurity.com/2018/03/13/oceanlotus-ships-new-backdoor/" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.orggroups/G0067">
      APT37
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.orggroups/G0067">
       APT37
      </a>
      has used strategic web compromises, particularly of South Korean websites, to distribute malware. The group has also used torrent file-sharing sites to more indiscriminately disseminate malware to victims. As part of their compromises, the group has used a Javascript based profiler called RICECURRY to profile a victim's web browser and deliver malicious code accordingly.
      <span class="scite-citeref-number" data-reference="Securelist ScarCruft Jun 2016" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://securelist.com/operation-daybreak/75100/" target="_blank">
         [4]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.orggroups/G0060">
      BRONZE BUTLER
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.orggroups/G0060">
       BRONZE BUTLER
      </a>
      compromised three Japanese websites using a Flash exploit to perform watering hole attacks.
      <span class="scite-citeref-number" data-reference="Symantec Tick Apr 2016" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.symantec.com/connect/blogs/tick-cyberespionage-group-zeros-japan" target="_blank">
         [6]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.orggroups/G0070">
      Dark Caracal
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.orggroups/G0070">
       Dark Caracal
      </a>
      leveraged a watering hole to serve up malicious code.
      <span class="scite-citeref-number" data-reference="Lookout Dark Caracal Jan 2018" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://info.lookout.com/rs/051-ESQ-475/images/Lookout_Dark-Caracal_srr_20180118_us_v.1.0.pdf" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.orggroups/G0074">
      Dragonfly 2.0
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.orggroups/G0074">
       Dragonfly 2.0
      </a>
      compromised legitimate organizations' websites to create watering holes to compromise victims.
      <span class="scite-citeref-number" data-reference="US-CERT TA18-074A" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.orggroups/G0066">
      Elderwood
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.orggroups/G0066">
       Elderwood
      </a>
      has delivered zero-day exploits and malware to victims by injecting malicious code into specific public Web pages visited by targets within a particular sector.
      <span class="scite-citeref-number" data-reference="Symantec Elderwood Sept 2012" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/the-elderwood-project.pdf" target="_blank">
         [9]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="CSM Elderwood Sept 2012" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www.csmonitor.com/USA/2012/0914/Stealing-US-business-secrets-Experts-ID-two-huge-cyber-gangs-in-China" target="_blank">
         [10]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Security Affairs Elderwood Sept 2012" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="http://securityaffairs.co/wordpress/8528/hacking/elderwood-project-who-is-behind-op-aurora-and-ongoing-attacks.html" target="_blank">
         [11]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.orgsoftware/S0215">
      KARAE
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.orgsoftware/S0215">
       KARAE
      </a>
      was distributed through torrent file-sharing websites to South Korean victims, using a YouTube video downloader application as a lure.
      <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.orggroups/G0032">
      Lazarus Group
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.orggroups/G0032">
       Lazarus Group
      </a>
      delivered
      <a href="https://attack.mitre.orgsoftware/S0241">
       RATANKBA
      </a>
      to victims via a compromised legitimate website.
      <span class="scite-citeref-number" data-reference="RATANKBA" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://blog.trendmicro.com/trendlabs-security-intelligence/ratankba-watering-holes-against-enterprises/" target="_blank">
         [12]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.orggroups/G0077">
      Leafminer
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.orggroups/G0077">
       Leafminer
      </a>
      has infected victims using watering holes.
      <span class="scite-citeref-number" data-reference="Symantec Leafminer July 2018" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://www.symantec.com/blogs/threat-intelligence/leafminer-espionage-middle-east" target="_blank">
         [13]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.orggroups/G0040">
      Patchwork
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.orggroups/G0040">
       Patchwork
      </a>
      has used watering holes to deliver files with exploits to initial victims.
      <span class="scite-citeref-number" data-reference="Symantec Patchwork" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="http://www.symantec.com/connect/blogs/patchwork-cyberespionage-group-expands-targets-governments-wide-range-industries" target="_blank">
         [14]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Volexity Patchwork June 2018" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/" target="_blank">
         [15]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.orggroups/G0068">
      PLATINUM
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.orggroups/G0068">
       PLATINUM
      </a>
      has sometimes used drive-by attacks against vulnerable browser plugins.
      <span class="scite-citeref-number" data-reference="Microsoft PLATINUM April 2016" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" target="_blank">
         [16]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.orgsoftware/S0216">
      POORAIM
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.orgsoftware/S0216">
       POORAIM
      </a>
      has been delivered through compromised sites acting as watering holes.
      <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.orggroups/G0027">
      Threat Group-3390
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.orggroups/G0027">
       Threat Group-3390
      </a>
      has has extensively used strategic Web compromises to target victims.
      <span class="scite-citeref-number" data-reference="Dell TG-3390" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage" target="_blank">
         [17]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Securelist LuckyMouse June 2018" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="https://securelist.com/luckymouse-hits-national-data-center/86083/" target="_blank">
         [18]
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
  Drive-by compromise relies on there being a vulnerable piece of software on the client end systems. Use modern browsers with security features turned on. Ensure all browsers and plugins kept updated can help prevent the exploit phase of this technique.
 </p>
 <p>
  For malicious code served up through ads, adblockers can help prevent that code from executing in the first place. Script blocking extensions can help prevent the execution of JavaScript that may commonly be used during the exploitation process.
 </p>
 <p>
  Browser sandboxes can be used to mitigate some of the impact of exploitation, but sandbox escapes may still exist.
  <span class="scite-citeref-number" data-reference="Windows Blogs Microsoft Edge Sandbox" id="scite-ref-19-a">
   <sup>
    <a aria-describedby="qtip-18" data-hasqtip="18" href="https://blogs.windows.com/msedgedev/2017/03/23/strengthening-microsoft-edge-sandbox/" target="_blank">
     [19]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Ars Technica Pwn2Own 2017 VM Escape" id="scite-ref-20-a">
   <sup>
    <a aria-describedby="qtip-19" data-hasqtip="19" href="https://arstechnica.com/information-technology/2017/03/hack-that-escapes-vm-by-exploiting-edge-browser-fetches-105000-at-pwn2own/" target="_blank">
     [20]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Other types of virtualization and application microsegmentation may also mitigate the impact of client-side exploitation. The risks of additional exploits and weaknesses in implementation may still exist.
  <span class="scite-citeref-number" data-reference="Ars Technica Pwn2Own 2017 VM Escape" id="scite-ref-20-a">
   <sup>
    <a aria-describedby="qtip-19" data-hasqtip="19" href="https://arstechnica.com/information-technology/2017/03/hack-that-escapes-vm-by-exploiting-edge-browser-fetches-105000-at-pwn2own/" target="_blank">
     [20]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Security applications that look for behavior used during exploitation such as Windows Defender Exploit Guard (WDEG) and the Enhanced Mitigation Experience Toolkit (EMET) can be used to mitigate some exploitation behavior.
  <span class="scite-citeref-number" data-reference="TechNet Moving Beyond EMET" id="scite-ref-21-a">
   <sup>
    <a aria-describedby="qtip-20" data-hasqtip="20" href="https://blogs.technet.microsoft.com/srd/2017/08/09/moving-beyond-emet-ii-windows-defender-exploit-guard/" target="_blank">
     [21]
    </a>
   </sup>
  </span>
  Control flow integrity checking is another way to potentially identify and stop a software exploit from occurring.
  <span class="scite-citeref-number" data-reference="Wikipedia Control Flow Integrity" id="scite-ref-22-a">
   <sup>
    <a aria-describedby="qtip-21" data-hasqtip="21" href="https://en.wikipedia.org/wiki/Control-flow_integrity" target="_blank">
     [22]
    </a>
   </sup>
  </span>
  Many of these protections depend on the architecture and target application binary for compatibility.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Firewalls and proxies can inspect URLs for potentially known-bad domains or parameters. They can also do reputation-based analytics on websites and their requested resources such as how old a domain is, who it's registered to, if it's on a known bad list, or how many other users have connected to it before.
 </p>
 <p>
  Network intrusion detection systems, sometimes with SSL/TLS MITM inspection, can be used to look for known malicious scripts (recon, heap spray, and browser identification scripts have been frequently reused), common script obfuscation, and exploit code.
 </p>
 <p>
  Detecting compromise based on the drive-by exploit from a legitimate website may be difficult. Also look for behavior on the endpoint system that might indicate successful compromise, such as abnormal behavior of browser processes. This could include suspicious files written to disk, evidence of
  <a href="https://attack.mitre.orgtechniques/T1055">
   Process Injection
  </a>
  for attempts to hide execution, evidence of Discovery, or other unusual network traffic that may indicate additional tools transferred to the system.
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
       <a class="external text" href="http://blog.shadowserver.org/2012/05/15/cyber-espionage-strategic-web-compromises-trusted-websites-serving-dangerous-results/" name="scite-1" rel="nofollow" target="_blank">
        Adair, S., Moran, N. (2012, May 15). Cyber Espionage &amp; Strategic Web Compromises – Trusted Websites Serving Dangerous Results. Retrieved March 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2016/01/new-attacks-linked-to-c0d0s0-group/" name="scite-2" rel="nofollow" target="_blank">
        Grunzweig, J., Lee, B. (2016, January 22). New Attacks Linked to C0d0so0 Group. Retrieved August 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2018/03/13/oceanlotus-ships-new-backdoor/" name="scite-3" rel="nofollow" target="_blank">
        Foltýn, T. (2018, March 13). OceanLotus ships new backdoor using old tricks. Retrieved May 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/operation-daybreak/75100/" name="scite-4" rel="nofollow" target="_blank">
        Raiu, C., and Ivanov, A. (2016, June 17). Operation Daybreak. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" name="scite-5" rel="nofollow" target="_blank">
        FireEye. (2018, February 20). APT37 (Reaper): The Overlooked North Korean Actor. Retrieved March 1, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/connect/blogs/tick-cyberespionage-group-zeros-japan" name="scite-6" rel="nofollow" target="_blank">
        DiMaggio, J. (2016, April 28). Tick cyberespionage group zeros in on Japan. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://info.lookout.com/rs/051-ESQ-475/images/Lookout_Dark-Caracal_srr_20180118_us_v.1.0.pdf" name="scite-7" rel="nofollow" target="_blank">
        Blaich, A., et al. (2018, January 18). Dark Caracal: Cyber-espionage at a Global Scale. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" name="scite-8" rel="nofollow" target="_blank">
        US-CERT. (2018, March 16). Alert (TA18-074A): Russian Government Cyber Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/the-elderwood-project.pdf" name="scite-9" rel="nofollow" target="_blank">
        O'Gorman, G., and McDonald, G.. (2012, September 6). The Elderwood Project. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.csmonitor.com/USA/2012/0914/Stealing-US-business-secrets-Experts-ID-two-huge-cyber-gangs-in-China" name="scite-10" rel="nofollow" target="_blank">
        Clayton, M.. (2012, September 14). Stealing US business secrets: Experts ID two huge cyber 'gangs' in China. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="http://securityaffairs.co/wordpress/8528/hacking/elderwood-project-who-is-behind-op-aurora-and-ongoing-attacks.html" name="scite-11" rel="nofollow" target="_blank">
        Paganini, P. (2012, September 9). Elderwood project, who is behind Op. Aurora and ongoing attacks?. Retrieved February 13, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="12.0">
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/ratankba-watering-holes-against-enterprises/" name="scite-12" rel="nofollow" target="_blank">
        Trend Micro. (2017, February 27). RATANKBA: Delving into Large-scale Watering Holes against Enterprises. Retrieved May 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/leafminer-espionage-middle-east" name="scite-13" rel="nofollow" target="_blank">
        Symantec Security Response. (2018, July 25). Leafminer: New Espionage Campaigns Targeting Middle Eastern Regions. Retrieved August 28, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/connect/blogs/patchwork-cyberespionage-group-expands-targets-governments-wide-range-industries" name="scite-14" rel="nofollow" target="_blank">
        Hamada, J.. (2016, July 25). Patchwork cyberespionage group expands targets from governments to wide range of industries. Retrieved August 17, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/" name="scite-15" rel="nofollow" target="_blank">
        Meltzer, M, et al. (2018, June 07). Patchwork APT Group Targets US Think Tanks. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" name="scite-16" rel="nofollow" target="_blank">
        Windows Defender Advanced Threat Hunting Team. (2016, April 29). PLATINUM: Targeted attacks in South and Southeast Asia. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage" name="scite-17" rel="nofollow" target="_blank">
        Dell SecureWorks Counter Threat Unit Threat Intelligence. (2015, August 5). Threat Group-3390 Targets Organizations for Cyberespionage. Retrieved August 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/luckymouse-hits-national-data-center/86083/" name="scite-18" rel="nofollow" target="_blank">
        Legezo, D. (2018, June 13). LuckyMouse hits national data center to organize country-level waterholing campaign. Retrieved August 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://blogs.windows.com/msedgedev/2017/03/23/strengthening-microsoft-edge-sandbox/" name="scite-19" rel="nofollow" target="_blank">
        Cowan, C. (2017, March 23). Strengthening the Microsoft Edge Sandbox. Retrieved March 12, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://arstechnica.com/information-technology/2017/03/hack-that-escapes-vm-by-exploiting-edge-browser-fetches-105000-at-pwn2own/" name="scite-20" rel="nofollow" target="_blank">
        Goodin, D. (2017, March 17). Virtual machine escape fetches $105,000 at Pwn2Own hacking contest - updated. Retrieved March 12, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://blogs.technet.microsoft.com/srd/2017/08/09/moving-beyond-emet-ii-windows-defender-exploit-guard/" name="scite-21" rel="nofollow" target="_blank">
        Nunez, N. (2017, August 9). Moving Beyond EMET II – Windows Defender Exploit Guard. Retrieved March 12, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="https://en.wikipedia.org/wiki/Control-flow_integrity" name="scite-22" rel="nofollow" target="_blank">
        Wikipedia. (2018, January 11). Control-flow integrity. Retrieved March 12, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
