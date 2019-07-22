<div class="container-fluid">
 <h1>
  Local Job Scheduling
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    On Linux and macOS systems, multiple methods are supported for creating pre-scheduled and periodic background jobs: cron,
    <span class="scite-citeref-number" data-reference="Die.net Linux crontab Man Page" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://linux.die.net/man/5/crontab" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    at,
    <span class="scite-citeref-number" data-reference="Die.net Linux at Man Page" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://linux.die.net/man/1/at" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    and launchd.
    <span class="scite-citeref-number" data-reference="AppleDocs Scheduling Timed Jobs" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/ScheduledJobs.html" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    Unlike
    <a href="https://attack.mitre.org/techniques/T1053">
     Scheduled Task
    </a>
    on Windows systems, job scheduling on Linux-based systems cannot be done remotely unless used in conjunction within an established remote session, like secure shell (SSH).
   </p>
   <h3>
    cron
   </h3>
   <p>
    System-wide cron jobs are installed by modifying
    <code>
     /etc/crontab
    </code>
    file,
    <code>
     /etc/cron.d/
    </code>
    directory or other locations supported by the Cron daemon, while per-user cron jobs are installed using crontab with specifically formatted crontab files.
    <span class="scite-citeref-number" data-reference="AppleDocs Scheduling Timed Jobs" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/ScheduledJobs.html" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    This works on macOS and Linux systems.
   </p>
   <p>
    Those methods allow for commands or scripts to be executed at specific, periodic intervals in the background without user interaction. An adversary may use job scheduling to execute programs at system startup or on a scheduled basis for Persistence,
    <span class="scite-citeref-number" data-reference="Janicab" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="http://www.thesafemac.com/new-signed-malware-called-janicab/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Methods of Mac Malware Persistence" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.virusbulletin.com/uploads/pdf/conference/vb2014/VB2014-Wardle.pdf" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Malware Persistence on OS X" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.rsaconference.com/writable/presentations/file_upload/ht-r03-malware-persistence-on-os-x-yosemite_final.pdf" target="_blank">
       [6]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Avast Linux Trojan Cron Persistence" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="https://blog.avast.com/2015/01/06/linux-ddos-trojan-hiding-itself-with-an-embedded-rootkit/" target="_blank">
       [7]
      </a>
     </sup>
    </span>
    to conduct Execution as part of Lateral Movement, to gain root privileges, or to run a process under the context of a specific account.
   </p>
   <h3>
    at
   </h3>
   <p>
    The at program is another means on POSIX-based systems, including macOS and Linux, to schedule a program or script job for execution at a later date and/or time, which could also be used for the same purposes.
   </p>
   <h3>
    launchd
   </h3>
   <p>
    Each launchd job is described by a different configuration property list (plist) file similar to
    <a href="https://attack.mitre.org/techniques/T1160">
     Launch Daemon
    </a>
    or
    <a href="https://attack.mitre.org/techniques/T1159">
     Launch Agent
    </a>
    , except there is an additional key called
    <code>
     StartCalendarInterval
    </code>
    with a dictionary of time values.
    <span class="scite-citeref-number" data-reference="AppleDocs Scheduling Timed Jobs" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/ScheduledJobs.html" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    This only works on macOS and OS X.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1168
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
      : Persistence, Execution
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Platform:
      </span>
      Linux, macOS
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
      Administrator, User, root
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
      File monitoring, Process monitoring
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
       Contributors:
      </span>
      Anastasios Pingios
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
     <a href="https://attack.mitre.org/software/S0343">
      Exaramel
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0343">
       Exaramel
      </a>
      uses crontab for persistence.
      <span class="scite-citeref-number" data-reference="ESET TeleBots Oct 2018" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.welivesecurity.com/2018/10/11/new-telebots-backdoor-linking-industroyer-notpetya/" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0163">
      Janicab
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0163">
       Janicab
      </a>
      used a cron job for persistence on Mac devices.
      <span class="scite-citeref-number" data-reference="Janicab" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="http://www.thesafemac.com/new-signed-malware-called-janicab/" target="_blank">
         [4]
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
      uses cron tasks to ensure persistence.
      <span class="scite-citeref-number" data-reference="CheckPoint SpeakUp Feb 2019" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://research.checkpoint.com/speakup-a-new-undetected-backdoor-linux-trojan/" target="_blank">
         [9]
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
      can create a cronjob for persistence if it determines it is on a Linux system.
      <span class="scite-citeref-number" data-reference="Unit42 Xbash Sept 2018" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://researchcenter.paloaltonetworks.com/2018/09/unit42-xbash-combines-botnet-ransomware-coinmining-worm-targets-linux-windows/" target="_blank">
         [10]
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
  Limit privileges of user accounts and remediate Privilege Escalation vectors so only authorized users can create scheduled jobs. Identify and block unnecessary system utilities or potentially malicious software that may be used to schedule jobs using whitelisting tools.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Legitimate scheduled jobs may be created during installation of new software or through administration functions. Jobs scheduled with launchd and cron can be monitored from their respective utilities to list out detailed information about the jobs. Monitor process execution resulting from launchd and cron tasks to look for unusual or unknown applications and behavior.
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
       <a class="external text" href="https://linux.die.net/man/5/crontab" name="scite-1" rel="nofollow" target="_blank">
        Paul Vixie. (n.d.). crontab(5) - Linux man page. Retrieved December 19, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://linux.die.net/man/1/at" name="scite-2" rel="nofollow" target="_blank">
        Thomas Koenig. (n.d.). at(1) - Linux man page. Retrieved December 19, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/ScheduledJobs.html" name="scite-3" rel="nofollow" target="_blank">
        Apple. (n.d.). Retrieved July 17, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.thesafemac.com/new-signed-malware-called-janicab/" name="scite-4" rel="nofollow" target="_blank">
        Thomas. (2013, July 15). New signed malware called Janicab. Retrieved July 17, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.virusbulletin.com/uploads/pdf/conference/vb2014/VB2014-Wardle.pdf" name="scite-5" rel="nofollow" target="_blank">
        Patrick Wardle. (2014, September). Methods of Malware Persistence on Mac OS X. Retrieved July 5, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="6.0">
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.rsaconference.com/writable/presentations/file_upload/ht-r03-malware-persistence-on-os-x-yosemite_final.pdf" name="scite-6" rel="nofollow" target="_blank">
        Patrick Wardle. (2015). Malware Persistence on OS X Yosemite. Retrieved July 10, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.avast.com/2015/01/06/linux-ddos-trojan-hiding-itself-with-an-embedded-rootkit/" name="scite-7" rel="nofollow" target="_blank">
        Threat Intelligence Team. (2015, January 6). Linux DDoS Trojan hiding itself with an embedded rootkit. Retrieved January 8, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2018/10/11/new-telebots-backdoor-linking-industroyer-notpetya/" name="scite-8" rel="nofollow" target="_blank">
        Cherepanov, A., Lipovsky, R. (2018, October 11). New TeleBots backdoor: First evidence linking Industroyer to NotPetya. Retrieved November 27, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://research.checkpoint.com/speakup-a-new-undetected-backdoor-linux-trojan/" name="scite-9" rel="nofollow" target="_blank">
        Check Point Research. (2019, February 4). SpeakUp: A New Undetected Backdoor Linux Trojan. Retrieved April 17, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/09/unit42-xbash-combines-botnet-ransomware-coinmining-worm-targets-linux-windows/" name="scite-10" rel="nofollow" target="_blank">
        Xiao, C. (2018, September 17). Xbash Combines Botnet, Ransomware, Coinmining in Worm that Targets Linux and Windows. Retrieved November 14, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
