<div class="container-fluid">
 <h1>
  Systemd Service
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Systemd services can be used to establish persistence on a Linux system. The systemd service manager is commonly used for managing background daemon processes (also known as services) and other system resources.
    <span class="scite-citeref-number" data-reference="Linux man-pages: systemd January 2014" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://man7.org/linux/man-pages/man1/systemd.1.html" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Freedesktop.org Linux systemd 29SEP2018" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.freedesktop.org/wiki/Software/systemd/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    Systemd is the default initialization (init) system on many Linux distributions starting with Debian 8, Ubuntu 15.04, CentOS 7, RHEL 7, Fedora 15, and replaces legacy init systems including SysVinit and Upstart while remaining backwards compatible with the aforementioned init systems.
   </p>
   <p>
    Systemd utilizes configuration files known as service units to control how services boot and under what conditions. By default, these unit files are stored in the
    <code>
     /etc/systemd/system
    </code>
    and
    <code>
     /usr/lib/systemd/system
    </code>
    directories and have the file extension
    <code>
     .service
    </code>
    . Each service unit file may contain numerous directives that can execute system commands.
   </p>
   <ul>
    <li>
     ExecStart, ExecStartPre, and ExecStartPost directives cover execution of commands when a services is started manually by 'systemctl' or on system start if the service is set to automatically start.
    </li>
    <li>
     ExecReload directive covers when a service restarts.
    </li>
    <li>
     ExecStop and ExecStopPost directives cover when a service is stopped or manually by 'systemctl'.
    </li>
   </ul>
   <p>
    Adversaries have used systemd functionality to establish persistent access to victim systems by creating and/or modifying service unit files that cause systemd to execute malicious commands at recurring intervals, such as at system boot.
    <span class="scite-citeref-number" data-reference="Anomali Rocke March 2019" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.anomali.com/blog/rocke-evolves-its-arsenal-with-a-new-malware-family-written-in-golang" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="gist Arch package compromise 10JUL2018" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://gist.github.com/campuscodi/74d0d2e35d8fd9499c76333ce027345a" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Arch Linux Package Systemd Compromise BleepingComputer 10JUL2018" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.bleepingcomputer.com/news/security/malware-found-in-arch-linux-aur-package-repository/" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="acroread package compromised Arch Linux Mail 8JUL2018" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://lists.archlinux.org/pipermail/aur-general/2018-July/034153.html" target="_blank">
       [6]
      </a>
     </sup>
    </span>
   </p>
   <p>
    While adversaries typically require root privileges to create/modify service unit files in the
    <code>
     /etc/systemd/system
    </code>
    and
    <code>
     /usr/lib/systemd/system
    </code>
    directories, low privilege users can create/modify service unit files in directories such as
    <code>
     ~/.config/systemd/user/
    </code>
    to achieve user-level persistence.
    <span class="scite-citeref-number" data-reference="Rapid7 Service Persistence 22JUNE2016" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.rapid7.com/db/modules/exploit/linux/local/service_persistence" target="_blank">
       [7]
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
      : T1501
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
      Linux
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
      root, User
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
      Process command-line parameters, Process monitoring, File monitoring
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
      Tony Lambert, Red Canary
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
     <a href="https://attack.mitre.org/software/S0192">
      Pupy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0192">
       Pupy
      </a>
      can be used to establish persistence using a systemd service.
      <span class="scite-citeref-number" data-reference="GitHub Pupy" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://github.com/n1nj4sec/pupy" target="_blank">
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
  The creation and modification of systemd service unit files is generally reserved for administrators such as the Linux root user and other users with superuser privileges. Limit user access to system utilities such as systemctl to only users who have a legitimate need. Restrict read/write access to systemd unit files to only select privileged users who have a legitimate need to manage system services. Additionally, the installation of software commonly adds and changes systemd service unit files. Restrict software installation to trusted repositories only and be cautious of orphaned software packages. Utilize malicious code protection and application whitelisting to mitigate the ability of malware to create or modify systemd services.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Systemd service unit files may be detected by auditing file creation and modification events within the
  <code>
   /etc/systemd/system
  </code>
  ,
  <code>
   /usr/lib/systemd/system/
  </code>
  , and
  <code>
   /home/
   <username>
    /.config/systemd/user/
   </username>
  </code>
  directories, as well as associated symbolic links. Suspicious processes or scripts spawned in this manner will have a parent process of ‘systemd’, a parent process ID of 1, and will usually execute as the ‘root’ user.
 </p>
 <p>
  Suspicious systemd services can also be identified by comparing results against a trusted system baseline. Malicious systemd services may be detected by using the systemctl utility to examine system wide services:
  <code>
   systemctl list-units -–type=service –all
  </code>
  . Analyze the contents of
  <code>
   .service
  </code>
  files present on the file system and ensure that they refer to legitimate, expected executables.
 </p>
 <p>
  Auditing the execution and command-line arguments of the 'systemctl' utility, as well related utilities such as
  <code>
   /usr/sbin/service
  </code>
  may reveal malicious systemd service execution.
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
       <a class="external text" href="http://man7.org/linux/man-pages/man1/systemd.1.html" name="scite-1" rel="nofollow" target="_blank">
        Linux man-pages. (2014, January). systemd(1) - Linux manual page. Retrieved April 23, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.freedesktop.org/wiki/Software/systemd/" name="scite-2" rel="nofollow" target="_blank">
        Freedesktop.org. (2018, September 29). systemd System and Service Manager. Retrieved April 23, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.anomali.com/blog/rocke-evolves-its-arsenal-with-a-new-malware-family-written-in-golang" name="scite-3" rel="nofollow" target="_blank">
        Anomali Labs. (2019, March 15). Rocke Evolves Its Arsenal With a New Malware Family Written in Golang. Retrieved April 24, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://gist.github.com/campuscodi/74d0d2e35d8fd9499c76333ce027345a" name="scite-4" rel="nofollow" target="_blank">
        Catalin Cimpanu. (2018, July 10). ~x file downloaded in public Arch package compromise. Retrieved April 23, 2019.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="5.0">
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.bleepingcomputer.com/news/security/malware-found-in-arch-linux-aur-package-repository/" name="scite-5" rel="nofollow" target="_blank">
        Catalin Cimpanu. (2018, July 10). Malware Found in Arch Linux AUR Package Repository. Retrieved April 23, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://lists.archlinux.org/pipermail/aur-general/2018-July/034153.html" name="scite-6" rel="nofollow" target="_blank">
        Eli Schwartz. (2018, June 8). acroread package compromised. Retrieved April 23, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.rapid7.com/db/modules/exploit/linux/local/service_persistence" name="scite-7" rel="nofollow" target="_blank">
        Rapid7. (2016, June 22). Service Persistence. Retrieved April 23, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/n1nj4sec/pupy" name="scite-8" rel="nofollow" target="_blank">
        Nicolas Verdier. (n.d.). Retrieved January 29, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
