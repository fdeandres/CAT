<div class="container-fluid">
 <h1>
  Indicator Removal on Host
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries may delete or alter generated artifacts on a host system, including logs and potentially captured files such as quarantined malware. Locations and format of logs will vary, but typical organic system logs are captured as Windows events or Linux/macOS files such as
    <a href="https://attack.mitre.org/techniques/T1139">
     Bash History
    </a>
    and /var/log/* .
   </p>
   <p>
    Actions that interfere with eventing and other notifications that can be used to detect intrusion activity may compromise the integrity of security solutions, causing events to go unreported. They may also make forensic analysis and incident response more difficult due to lack of sufficient data to determine what occurred.
   </p>
   <h3>
    Clear Windows Event Logs
   </h3>
   <p>
    Windows event logs are a record of a computer's alerts and notifications. Microsoft defines an event as "any significant occurrence in the system or in a program that requires users to be notified or an entry added to a log." There are three system-defined sources of Events: System, Application, and Security.
   </p>
   <p>
    Adversaries performing actions related to account management, account logon and directory service access, etc. may choose to clear the events in order to hide their activities.
   </p>
   <p>
    The event logs can be cleared with the following utility commands:
   </p>
   <ul>
    <li>
     <code>
      wevtutil cl system
     </code>
    </li>
    <li>
     <code>
      wevtutil cl application
     </code>
    </li>
    <li>
     <code>
      wevtutil cl security
     </code>
    </li>
   </ul>
   <p>
    Logs may also be cleared through other mechanisms, such as
    <a href="https://attack.mitre.org/techniques/T1086">
     PowerShell
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
      : T1070
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
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      File monitoring, Process monitoring, Process command-line parameters, API monitoring, Windows event logs
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
      Log analysis, Host intrusion prevention systems, Anti-virus
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       CAPEC ID:
      </span>
      <a href="https://capec.mitre.org/data/definitions/93.html" target="_blank">
       CAPEC-93
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
      Ed Williams, Trustwave, SpiderLabs
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
     <a href="https://attack.mitre.org/groups/G0007">
      APT28
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0007">
       APT28
      </a>
      has cleared event logs, including by using the commands
      <code>
       wevtutil cl System
      </code>
      and
      <code>
       wevtutil cl Security
      </code>
      .
      <span class="scite-citeref-number" data-reference="Crowdstrike DNC June 2016" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.crowdstrike.com/blog/bears-midst-intrusion-democratic-national-committee/" target="_blank">
         [1]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="DOJ GRU Indictment Jul 2018" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.justice.gov/file/1080281/download" target="_blank">
         [2]
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
      used
      <a href="https://attack.mitre.org/software/S0195">
       SDelete
      </a>
      to remove artifacts from victims.
      <span class="scite-citeref-number" data-reference="Mandiant No Easy Breach" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="http://www.slideshare.net/MatthewDunwoody1/no-easy-breach-derby-con-2016" target="_blank">
         [3]
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
      has cleared select event log entries.
      <span class="scite-citeref-number" data-reference="FireEye APT32 May 2017" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.fireeye.com/blog/threat-research/2017/05/cyber-espionage-apt32.html" target="_blank">
         [4]
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
      delets all artifacts associated with the malware from the infected machine.
      <span class="scite-citeref-number" data-reference="US-CERT Bankshot Dec 2017" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-B_WHITE.PDF" target="_blank">
         [5]
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
      component KillDisk is capable of deleting Windows Event Logs.
      <span class="scite-citeref-number" data-reference="ESEST Black Energy Jan 2016" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="http://www.welivesecurity.com/2016/01/03/blackenergy-sshbeardoor-details-2015-attacks-ukrainian-news-media-electric-industry/" target="_blank">
         [6]
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
      cleared Windows event logs and other logs produced by tools they used, including system, security, terminal services, remote services, and audit logs. The actors also deleted specific Registry keys.
      <span class="scite-citeref-number" data-reference="US-CERT TA18-074A" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" target="_blank">
         [7]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT APT Energy Oct 2017" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" target="_blank">
         [8]
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
      has cleared event logs from victims.
      <span class="scite-citeref-number" data-reference="Mandiant FIN5 GrrCON Oct 2016" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.youtube.com/watch?v=fevGZs0EQu8" target="_blank">
         [9]
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
      has cleared logs during post compromise cleanup activities.
      <span class="scite-citeref-number" data-reference="FireEye Know Your Enemy FIN8 Aug 2016" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" target="_blank">
         [10]
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
      clears the system event logs.
      <span class="scite-citeref-number" data-reference="FinFisher Citation" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="http://www.finfisher.com/FinFisher/index.html" target="_blank">
         [11]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Microsoft FinFisher March 2018" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://cloudblogs.microsoft.com/microsoftsecure/2018/03/01/finfisher-exposed-a-researchers-tale-of-defeating-traps-tricks-and-complex-virtual-machines/" target="_blank">
         [12]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0032">
      gh0st
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0032">
       gh0st
      </a>
      RAT is able to wipe event logs.
      <span class="scite-citeref-number" data-reference="FireEye Hacking Team" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://www.fireeye.com/blog/threat-research/2015/07/demonstrating_hustle.html" target="_blank">
         [13]
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
      creates a backdoor through which remote attackers can clear all system event logs.
      <span class="scite-citeref-number" data-reference="Symantec Trojan.Hydraq Jan 2010" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://www.symantec.com/connect/blogs/trojanhydraq-incident" target="_blank">
         [14]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Symantec Hydraq Jan 2010" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://www.symantec.com/security_response/writeup.jsp?docid=2010-011114-1830-99" target="_blank">
         [15]
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
      is capable of deleting Registry keys used for persistence.
      <span class="scite-citeref-number" data-reference="Cylance Dust Storm" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="https://www.cylance.com/content/dam/cylance/pdfs/reports/Op_Dust_Storm_Report.pdf" target="_blank">
         [16]
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
      can overwrite Registry settings to reduce its visibility on the victim.
      <span class="scite-citeref-number" data-reference="Proofpoint Leviathan Oct 2017" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" target="_blank">
         [17]
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
      After encrypting log files, the log encryption module in
      <a href="https://attack.mitre.org/software/S0113">
       Prikormka
      </a>
      deletes the original, unencrypted files from the host.
      <span class="scite-citeref-number" data-reference="ESET Operation Groundbait" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="http://www.welivesecurity.com/wp-content/uploads/2016/05/Operation-Groundbait.pdf" target="_blank">
         [18]
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
      removes logs from /var/logs and /Library/logs.
      <span class="scite-citeref-number" data-reference="objsee mac malware 2017" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="https://objective-see.com/blog/blog_0x25.html" target="_blank">
         [19]
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
      has a module to clear event logs with PowerShell.
      <span class="scite-citeref-number" data-reference="GitHub Pupy" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://github.com/n1nj4sec/pupy" target="_blank">
         [20]
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
      has the ability to remove Registry entries that it created during execution.
      <span class="scite-citeref-number" data-reference="ESET RTM Feb 2017" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="https://www.welivesecurity.com/wp-content/uploads/2017/02/Read-The-Manual.pdf" target="_blank">
         [21]
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
      contains code to clear event logs.
      <span class="scite-citeref-number" data-reference="McAfee Gold Dragon" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="https://securingtomorrow.mcafee.com/mcafee-labs/gold-dragon-widens-olympics-malware-attacks-gains-permanent-presence-on-victims-systems/" target="_blank">
         [22]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0242">
      SynAck
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0242">
       SynAck
      </a>
      clears event logs.
      <span class="scite-citeref-number" data-reference="SecureList SynAck Doppelgänging May 2018" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="https://securelist.com/synack-targeted-ransomware-uses-the-doppelganging-technique/85431/" target="_blank">
         [23]
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
  Automatically forward events to a log server or data repository to prevent conditions in which the adversary can locate and manipulate data on the local system. When possible, minimize time delay on event reporting to avoid prolonged storage on the local system. Protect generated event files that are stored locally with proper permissions and authentication and limit opportunities for adversaries to increase privileges by preventing Privilege Escalation opportunities. Obfuscate/encrypt event files locally and in transit to avoid giving feedback to an adversary.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  File system monitoring may be used to detect improper deletion or modification of indicator files. For example, deleting Windows event logs (via native binaries
  <span class="scite-citeref-number" data-reference="Microsoft wevtutil Oct 2017" id="scite-ref-24-a">
   <sup>
    <a aria-describedby="qtip-23" data-hasqtip="23" href="https://docs.microsoft.com/windows-server/administration/windows-commands/wevtutil" target="_blank">
     [24]
    </a>
   </sup>
  </span>
  , API functions
  <span class="scite-citeref-number" data-reference="Microsoft EventLog.Clear" id="scite-ref-25-a">
   <sup>
    <a aria-describedby="qtip-24" data-hasqtip="24" href="https://msdn.microsoft.com/library/system.diagnostics.eventlog.clear.aspx" target="_blank">
     [25]
    </a>
   </sup>
  </span>
  , or
  <a href="https://attack.mitre.org/techniques/T1086">
   PowerShell
  </a>
  <span class="scite-citeref-number" data-reference="Microsoft Clear-EventLog" id="scite-ref-26-a">
   <sup>
    <a aria-describedby="qtip-25" data-hasqtip="25" href="https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-eventlog" target="_blank">
     [26]
    </a>
   </sup>
  </span>
  ) may generate an alterable event (Event ID 1102: "The audit log was cleared"). Events not stored on the file system may require different detection mechanisms.
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
       <a class="external text" href="https://www.crowdstrike.com/blog/bears-midst-intrusion-democratic-national-committee/" name="scite-1" rel="nofollow" target="_blank">
        Alperovitch, D.. (2016, June 15). Bears in the Midst: Intrusion into the Democratic National Committee. Retrieved August 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.justice.gov/file/1080281/download" name="scite-2" rel="nofollow" target="_blank">
        Mueller, R. (2018, July 13). Indictment - United States of America vs. VIKTOR BORISOVICH NETYKSHO, et al. Retrieved September 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.slideshare.net/MatthewDunwoody1/no-easy-breach-derby-con-2016" name="scite-3" rel="nofollow" target="_blank">
        Dunwoody, M. and Carr, N.. (2016, September 27). No Easy Breach DerbyCon 2016. Retrieved October 4, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/05/cyber-espionage-apt32.html" name="scite-4" rel="nofollow" target="_blank">
        Carr, N.. (2017, May 14). Cyber Espionage is Alive and Well: APT32 and the Threat to Global Corporations. Retrieved June 18, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-B_WHITE.PDF" name="scite-5" rel="nofollow" target="_blank">
        US-CERT. (2017, December 13). Malware Analysis Report (MAR) - 10135536-B. Retrieved July 17, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.welivesecurity.com/2016/01/03/blackenergy-sshbeardoor-details-2015-attacks-ukrainian-news-media-electric-industry/" name="scite-6" rel="nofollow" target="_blank">
        Cherepanov, A.. (2016, January 3). BlackEnergy by the SSHBearDoor: attacks against Ukrainian news media and electric industry. Retrieved May 18, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" name="scite-7" rel="nofollow" target="_blank">
        US-CERT. (2018, March 16). Alert (TA18-074A): Russian Government Cyber Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" name="scite-8" rel="nofollow" target="_blank">
        US-CERT. (2017, October 20). Alert (TA17-293A): Advanced Persistent Threat Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved November 2, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.youtube.com/watch?v=fevGZs0EQu8" name="scite-9" rel="nofollow" target="_blank">
        Bromiley, M. and Lewis, P. (2016, October 7). Attacking the Hospitality and Gaming Industries: Tracking an Attacker Around the World in 7 Years. Retrieved October 6, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" name="scite-10" rel="nofollow" target="_blank">
        Elovitz, S. &amp; Ahl, I. (2016, August 18). Know Your Enemy:  New Financially-Motivated &amp; Spear-Phishing Group. Retrieved February 26, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.finfisher.com/FinFisher/index.html" name="scite-11" rel="nofollow" target="_blank">
        FinFisher. (n.d.). Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://cloudblogs.microsoft.com/microsoftsecure/2018/03/01/finfisher-exposed-a-researchers-tale-of-defeating-traps-tricks-and-complex-virtual-machines/" name="scite-12" rel="nofollow" target="_blank">
        Allievi, A.,Flori, E. (2018, March 01). FinFisher exposed: A researcher’s tale of defeating traps, tricks, and complex virtual machines. Retrieved July 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2015/07/demonstrating_hustle.html" name="scite-13" rel="nofollow" target="_blank">
        FireEye Threat Intelligence. (2015, July 13). Demonstrating Hustle, Chinese APT Groups Quickly Use Zero-Day Vulnerability (CVE-2015-5119) Following Hacking Team Leak. Retrieved January 25, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="14.0">
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/connect/blogs/trojanhydraq-incident" name="scite-14" rel="nofollow" target="_blank">
        Symantec Security Response. (2010, January 18). The Trojan.Hydraq Incident. Retrieved February 20, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2010-011114-1830-99" name="scite-15" rel="nofollow" target="_blank">
        Lelli, A. (2010, January 11). Trojan.Hydraq. Retrieved February 20, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cylance.com/content/dam/cylance/pdfs/reports/Op_Dust_Storm_Report.pdf" name="scite-16" rel="nofollow" target="_blank">
        Gross, J. (2016, February 23). Operation Dust Storm. Retrieved September 19, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" name="scite-17" rel="nofollow" target="_blank">
        Axel F, Pierre T. (2017, October 16). Leviathan: Espionage actor spearphishes maritime and defense targets. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.welivesecurity.com/wp-content/uploads/2016/05/Operation-Groundbait.pdf" name="scite-18" rel="nofollow" target="_blank">
        Cherepanov, A.. (2016, May 17). Operation Groundbait: Analysis of a surveillance toolkit. Retrieved May 18, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://objective-see.com/blog/blog_0x25.html" name="scite-19" rel="nofollow" target="_blank">
        Patrick Wardle. (n.d.). Mac Malware of 2017. Retrieved September 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/n1nj4sec/pupy" name="scite-20" rel="nofollow" target="_blank">
        Nicolas Verdier. (n.d.). Retrieved January 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2017/02/Read-The-Manual.pdf" name="scite-21" rel="nofollow" target="_blank">
        Faou, M. and Boutin, J.. (2017, February). Read The Manual: A Guide to the RTM Banking Trojan. Retrieved March 9, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/gold-dragon-widens-olympics-malware-attacks-gains-permanent-presence-on-victims-systems/" name="scite-22" rel="nofollow" target="_blank">
        Sherstobitoff, R., Saavedra-Morales, J. (2018, February 02). Gold Dragon Widens Olympics Malware Attacks, Gains Permanent Presence on Victims’ Systems. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-23">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/synack-targeted-ransomware-uses-the-doppelganging-technique/85431/" name="scite-23" rel="nofollow" target="_blank">
        Ivanov, A. et al.. (2018, May 7). SynAck targeted ransomware uses the Doppelgänging technique. Retrieved May 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-24">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/windows-server/administration/windows-commands/wevtutil" name="scite-24" rel="nofollow" target="_blank">
        Plett, C. et al.. (2017, October 16). wevtutil. Retrieved July 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-25">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/system.diagnostics.eventlog.clear.aspx" name="scite-25" rel="nofollow" target="_blank">
        Microsoft. (n.d.). EventLog.Clear Method (). Retrieved July 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-26">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-eventlog" name="scite-26" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Clear-EventLog. Retrieved July 2, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
