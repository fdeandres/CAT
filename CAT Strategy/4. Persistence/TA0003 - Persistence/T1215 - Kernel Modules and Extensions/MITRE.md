<div class="container-fluid">
 <h1>
  Kernel Modules and Extensions
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Loadable Kernel Modules (or LKMs) are pieces of code that can be loaded and unloaded into the kernel upon demand. They extend the functionality of the kernel without the need to reboot the system. For example, one type of module is the device driver, which allows the kernel to access hardware connected to the system.
    <span class="scite-citeref-number" data-reference="Linux Kernel Programming" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.tldp.org/LDP/lkmpg/2.4/lkmpg.pdf" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    When used maliciously, Loadable Kernel Modules (LKMs) can be a type of kernel-mode
    <a href="https://attack.mitre.org/techniques/T1014">
     Rootkit
    </a>
    that run with the highest operating system privilege (Ring 0).
    <span class="scite-citeref-number" data-reference="Linux Kernel Module Programming Guide" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="http://www.tldp.org/LDP/lkmpg/2.4/html/x437.html" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    Adversaries can use loadable kernel modules to covertly persist on a system and evade defenses. Examples have been found in the wild and there are some open source projects.
    <span class="scite-citeref-number" data-reference="Volatility Phalanx2" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://volatility-labs.blogspot.com/2012/10/phalanx-2-revealed-using-volatility-to.html" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="CrowdStrike Linux Rootkit" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.crowdstrike.com/blog/http-iframe-injecting-linux-rootkit/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="GitHub Reptile" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://github.com/f0rb1dd3n/Reptile" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="GitHub Diamorphine" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://github.com/m0nad/Diamorphine" target="_blank">
       [6]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Common features of LKM based rootkits include: hiding itself, selective hiding of files, processes and network activity, as well as log tampering, providing authenticated backdoors and enabling root access to non-privileged users.
    <span class="scite-citeref-number" data-reference="iDefense Rootkit Overview" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="http://www.megasecurity.org/papers/Rootkits.pdf" target="_blank">
       [7]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Kernel extensions, also called kext, are used for macOS to load functionality onto a system similar to LKMs for Linux. They are loaded and unloaded through
    <code>
     kextload
    </code>
    and
    <code>
     kextunload
    </code>
    commands. Several examples have been found where this can be used.
    <span class="scite-citeref-number" data-reference="RSAC 2015 San Francisco Patrick Wardle" id="scite-ref-8-a">
     <sup>
      <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.rsaconference.com/writable/presentations/file_upload/ht-r03-malware-persistence-on-os-x-yosemite_final.pdf" target="_blank">
       [8]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Synack Secure Kernel Extension Broken" id="scite-ref-9-a">
     <sup>
      <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.synack.com/2017/09/08/high-sierras-secure-kernel-extension-loading-is-broken/" target="_blank">
       [9]
      </a>
     </sup>
    </span>
    Examples have been found in the wild.
    <span class="scite-citeref-number" data-reference="Securelist Ventir" id="scite-ref-10-a">
     <sup>
      <a aria-describedby="qtip-9" data-hasqtip="9" href="https://securelist.com/the-ventir-trojan-assemble-your-macos-spy/67267/" target="_blank">
       [10]
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
      : T1215
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
      root
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
      System calls, Process monitoring, Process command-line parameters
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
      Jeremy Galloway; Red Canary
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
 <h2 class="pt-3" id="mitigation">
  Mitigation
 </h2>
 <p>
  Common tools for detecting Linux rootkits include: rkhunter
  <span class="scite-citeref-number" data-reference="SourceForge rkhunter" id="scite-ref-11-a">
   <sup>
    <a aria-describedby="qtip-10" data-hasqtip="10" href="http://rkhunter.sourceforge.net" target="_blank">
     [11]
    </a>
   </sup>
  </span>
  , chrootkit
  <span class="scite-citeref-number" data-reference="Chkrootkit Main" id="scite-ref-12-a">
   <sup>
    <a aria-describedby="qtip-11" data-hasqtip="11" href="http://www.chkrootkit.org/" target="_blank">
     [12]
    </a>
   </sup>
  </span>
  , although rootkits may be designed to evade certain detection tools.
 </p>
 <p>
  LKMs and Kernel extensions require root level permissions to be installed. Limit access to the root account and prevent users from loading kernel modules and extensions through proper privilege separation and limiting Privilege Escalation opportunities.
 </p>
 <p>
  Application whitelisting and software restriction tools, such as SELinux, can also aide in restricting kernel module loading.
  <span class="scite-citeref-number" data-reference="Kernel.org Restrict Kernel Module" id="scite-ref-13-a">
   <sup>
    <a aria-describedby="qtip-12" data-hasqtip="12" href="https://patchwork.kernel.org/patch/8754821/" target="_blank">
     [13]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  LKMs are typically loaded into
  <code>
   /lib/modules
  </code>
  and have had the extension .ko ("kernel object") since version 2.6 of the Linux kernel.
  <span class="scite-citeref-number" data-reference="Wikipedia Loadable Kernel Module" id="scite-ref-14-a">
   <sup>
    <a aria-describedby="qtip-13" data-hasqtip="13" href="https://en.wikipedia.org/wiki/Loadable_kernel_module#Linux" target="_blank">
     [14]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Many LKMs require Linux headers (specific to the target kernel) in order to compile properly. These are typically obtained through the operating systems package manager and installed like a normal package.
 </p>
 <p>
  Adversaries will likely run these commands on the target system before loading a malicious module in order to ensure that it is properly compiled.
  <span class="scite-citeref-number" data-reference="iDefense Rootkit Overview" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="http://www.megasecurity.org/papers/Rootkits.pdf" target="_blank">
     [7]
    </a>
   </sup>
  </span>
 </p>
 <p>
  On Ubuntu and Debian based systems this can be accomplished by running:
  <code>
   apt-get install linux-headers-$(uname -r)
  </code>
 </p>
 <p>
  On RHEL and CentOS based systems this can be accomplished by running:
  <code>
   yum install kernel-devel-$(uname -r)
  </code>
 </p>
 <p>
  Loading, unloading, and manipulating modules on Linux systems can be detected by monitoring for the following commands:
  <code>
   modprobe insmod lsmod rmmod modinfo
  </code>
  <span class="scite-citeref-number" data-reference="Linux Loadable Kernel Module Insert and Remove LKMs" id="scite-ref-15-a">
   <sup>
    <a aria-describedby="qtip-14" data-hasqtip="14" href="http://tldp.org/HOWTO/Module-HOWTO/x197.html" target="_blank">
     [15]
    </a>
   </sup>
  </span>
 </p>
 <p>
  For macOS, monitor for execution of
  <code>
   kextload
  </code>
  commands and correlate with other unknown or suspicious activity.
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
       <a class="external text" href="https://www.tldp.org/LDP/lkmpg/2.4/lkmpg.pdf" name="scite-1" rel="nofollow" target="_blank">
        Pomerantz, O., Salzman, P. (2003, April 4). The  (Citation: Linux Kernel Module Programming Guide). Retrieved April 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.tldp.org/LDP/lkmpg/2.4/html/x437.html" name="scite-2" rel="nofollow" target="_blank">
        Pomerantz, O., Salzman, P. (2003, April 4). Modules vs Programs. Retrieved April 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://volatility-labs.blogspot.com/2012/10/phalanx-2-revealed-using-volatility-to.html" name="scite-3" rel="nofollow" target="_blank">
        Case, A. (2012, October 10). Phalanx 2 Revealed: Using Volatility to Analyze an Advanced Linux Rootkit. Retrieved April 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.crowdstrike.com/blog/http-iframe-injecting-linux-rootkit/" name="scite-4" rel="nofollow" target="_blank">
        Kurtz, G. (2012, November 19). HTTP iframe Injecting Linux Rootkit. Retrieved December 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/f0rb1dd3n/Reptile" name="scite-5" rel="nofollow" target="_blank">
        Augusto, I. (2018, March 8). Reptile - LMK Linux rootkit. Retrieved April 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/m0nad/Diamorphine" name="scite-6" rel="nofollow" target="_blank">
        Mello, V. (2018, March 8). Diamorphine - LMK rootkit for Linux Kernels 2.6.x/3.x/4.x (x86 and x86_64). Retrieved April 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.megasecurity.org/papers/Rootkits.pdf" name="scite-7" rel="nofollow" target="_blank">
        Chuvakin, A. (2003, February). An Overview of Rootkits. Retrieved April 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.rsaconference.com/writable/presentations/file_upload/ht-r03-malware-persistence-on-os-x-yosemite_final.pdf" name="scite-8" rel="nofollow" target="_blank">
        Wardle, P. (2015, April). Malware Persistence on OS X Yosemite. Retrieved April 6, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="9.5">
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.synack.com/2017/09/08/high-sierras-secure-kernel-extension-loading-is-broken/" name="scite-9" rel="nofollow" target="_blank">
        Wardle, P. (2017, September 8). High Sierra’s ‘Secure Kernel Extension Loading’ is Broken. Retrieved April 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/the-ventir-trojan-assemble-your-macos-spy/67267/" name="scite-10" rel="nofollow" target="_blank">
        Mikhail, K. (2014, October 16). The Ventir Trojan: assemble your MacOS spy. Retrieved April 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="http://rkhunter.sourceforge.net" name="scite-11" rel="nofollow" target="_blank">
        Rootkit Hunter Project. (2018, February 20). The Rootkit Hunter project. Retrieved April 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.chkrootkit.org/" name="scite-12" rel="nofollow" target="_blank">
        Murilo, N., Steding-Jessen, K. (2017, August 23). Chkrootkit. Retrieved April 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://patchwork.kernel.org/patch/8754821/" name="scite-13" rel="nofollow" target="_blank">
        Vander Stoep, J. (2016, April 5). [v3] selinux: restrict kernel module loadinglogin  register. Retrieved April 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://en.wikipedia.org/wiki/Loadable_kernel_module#Linux" name="scite-14" rel="nofollow" target="_blank">
        Wikipedia. (2018, March 17). Loadable kernel module. Retrieved April 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="http://tldp.org/HOWTO/Module-HOWTO/x197.html" name="scite-15" rel="nofollow" target="_blank">
        Henderson, B. (2006, September 24). How To Insert And Remove LKMs. Retrieved April 9, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
