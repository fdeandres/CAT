<div class="container-fluid">
 <h1>
  Virtualization/Sandbox Evasion
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries may check for the presence of a virtual machine environment (VME) or sandbox to avoid potential detection of tools and activities. If the adversary detects a VME, they may alter their malware to conceal the core functions of the implant or disengage from the victim. They may also search for VME artifacts before dropping secondary or additional payloads.
   </p>
   <p>
    Adversaries may use several methods including
    <a href="https://attack.mitre.org/techniques/T1063">
     Security Software Discovery
    </a>
    to accomplish
    <a href="https://attack.mitre.org/techniques/T1497">
     Virtualization/Sandbox Evasion
    </a>
    by searching for security monitoring tools (e.g., Sysinternals, Wireshark, etc.) to help determine if it is an analysis environment. Additional methods include use of sleep timers or loops within malware code to avoid operating within a temporary sandboxes.
    <span class="scite-citeref-number" data-reference="Unit 42 Pirpi July 2015" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://unit42.paloaltonetworks.com/ups-observations-on-cve-2015-3113-prior-zero-days-and-the-pirpi-payload/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <h3>
    Virtual Machine Environment Artifacts Discovery
   </h3>
   <p>
    Adversaries may use utilities such as
    <a href="https://attack.mitre.org/techniques/T1047">
     Windows Management Instrumentation
    </a>
    ,
    <a href="https://attack.mitre.org/techniques/T1086">
     PowerShell
    </a>
    ,
    <a href="https://attack.mitre.org/software/S0096">
     Systeminfo
    </a>
    , and the
    <a href="https://attack.mitre.org/techniques/T1012">
     Query Registry
    </a>
    to obtain system information and search for VME artifacts. Adversaries may search for VME artifacts in memory, processes, file system, and/or the Registry. Adversaries may use
    <a href="https://attack.mitre.org/techniques/T1064">
     Scripting
    </a>
    to combine these checks into one script and then have the program exit if it determines the system to be a virtual environment. Also, in applications like VMWare, adversaries can use a special I/O port to send commands and receive output. Adversaries may also check the drive size. For example, this can be done using the Win32 DeviceIOControl function.
   </p>
   <p>
    Example VME Artifacts in the Registry
    <span class="scite-citeref-number" data-reference="McAfee Virtual Jan 2017" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://securingtomorrow.mcafee.com/other-blogs/mcafee-labs/stopping-malware-fake-virtual-machine/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <ul>
    <li>
     <code>
      HKLM\SOFTWARE\Oracle\VirtualBox Guest Additions
     </code>
    </li>
    <li>
     <code>
      HKLM\HARDWARE\Description\System\"SystemBiosVersion";"VMWARE"
     </code>
    </li>
    <li>
     <code>
      HKLM\HARDWARE\ACPI\DSDT\BOX_
     </code>
    </li>
   </ul>
   <p>
    Example VME files and DLLs on the system
    <span class="scite-citeref-number" data-reference="McAfee Virtual Jan 2017" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://securingtomorrow.mcafee.com/other-blogs/mcafee-labs/stopping-malware-fake-virtual-machine/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <ul>
    <li>
     <code>
      WINDOWS\system32\drivers\vmmouse.sys
     </code>
    </li>
    <li>
     <code>
      WINDOWS\system32\vboxhook.dll
     </code>
    </li>
    <li>
     <code>
      Windows\system32\vboxdisp.dll
     </code>
    </li>
   </ul>
   <p>
    Common checks may enumerate services running that are unique to these applications, installed programs on the system, manufacturer/product fields for strings relating to virtual machine applications, and VME-specific hardware/processor instructions.
    <span class="scite-citeref-number" data-reference="McAfee Virtual Jan 2017" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://securingtomorrow.mcafee.com/other-blogs/mcafee-labs/stopping-malware-fake-virtual-machine/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <h3>
    User Activity Discovery
   </h3>
   <p>
    Adversaries may search for user activity on the host (e.g., browser history, cache, bookmarks, number of files in the home directories, etc.) for reassurance of an authentic environment. They might detect this type of information via user interaction and digital signatures. They may have malware check the speed and frequency of mouse clicks to determine if it’s a sandboxed environment.
    <span class="scite-citeref-number" data-reference="Sans Virtual Jan 2016" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.sans.org/reading-room/whitepapers/forensics/detecting-malware-sandbox-evasion-techniques-36667" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    Other methods may rely on specific user interaction with the system before the malicious code is activated. Examples include waiting for a document to close before activating a macro
    <span class="scite-citeref-number" data-reference="Unit 42 Sofacy Nov 2018" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://unit42.paloaltonetworks.com/unit42-sofacy-continues-global-attacks-wheels-new-cannon-trojan/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    and waiting for a user to double click on an embedded image to activate
    <span class="scite-citeref-number" data-reference="FireEye FIN7 April 2017" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.fireeye.com/blog/threat-research/2017/04/fin7-phishing-lnk.html" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    .
   </p>
   <h3>
    Virtual Hardware Fingerprinting Discovery
   </h3>
   <p>
    Adversaries may check the fan and temperature of the system to gather evidence that can be indicative a virtual environment. An adversary may perform a CPU check using a WMI query
    <code>
     $q = "Select * from Win32_Fan" Get-WmiObject -Query $q
    </code>
    . If the results of the WMI query return more than zero elements, this might tell them that the machine is a physical one.
    <span class="scite-citeref-number" data-reference="Unit 42 OilRig Sept 2018" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://researchcenter.paloaltonetworks.com/2018/09/unit42-oilrig-targets-middle-eastern-government-adds-evasion-techniques-oopsie/" target="_blank">
       [6]
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
      : T1497
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
      : Defense Evasion, Discovery
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
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      Process monitoring, Process command-line parameters
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
      Anti-virus, Host forensic analysis, Signature-based detection, Static File Analysis
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
       Contributors:
      </span>
      Sunny Neo
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
     <a href="https://attack.mitre.org/software/S0337">
      BadPatch
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0337">
       BadPatch
      </a>
      attempts to detect if it is being run in a Virtual Machine (VM) using a WMI query for disk drive name, BIOS, and motherboard information.
      <span class="scite-citeref-number" data-reference="Unit 42 BadPatch Oct 2017" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://researchcenter.paloaltonetworks.com/2017/10/unit42-badpatch/" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0023">
      CHOPSTICK
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0023">
       CHOPSTICK
      </a>
      checks for virtualization software.
      <span class="scite-citeref-number" data-reference="FireEye APT28" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/rpt-apt28.pdf" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0046">
      CozyCar
     </a>
    </td>
    <td>
     <p>
      Some versions of
      <a href="https://attack.mitre.org/software/S0046">
       CozyCar
      </a>
      will check to ensure it is not being executed inside a virtual machine or a known malware analysis sandbox environment. If it detects that it is, it will exit.
      <span class="scite-citeref-number" data-reference="F-Secure CozyDuke" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.f-secure.com/documents/996508/1030745/CozyDuke" target="_blank">
         [9]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0024">
      Dyre
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0024">
       Dyre
      </a>
      can detect sandbox analysis environments by inspecting the process list and Registry.
      <span class="scite-citeref-number" data-reference="Symantec Dyre June 2015" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/dyre-emerging-threat.pdf" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0046">
      FIN7
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0046">
       FIN7
      </a>
      used images embedded into document lures that only activate the payload when a user double clicks to avoid sandboxes.
      <span class="scite-citeref-number" data-reference="FireEye FIN7 April 2017" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.fireeye.com/blog/threat-research/2017/04/fin7-phishing-lnk.html" target="_blank">
         [5]
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
      probes the system to check for sandbox/virtualized environments.
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
     <a href="https://attack.mitre.org/software/S0237">
      GravityRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0237">
       GravityRAT
      </a>
      uses WMI to check the BIOS and manufacturer information for strings like "VMWare", "Virtual", and "XEN" and another WMI request to get the current temperature of the hardware to determine if it's a virtual machine environment.
      <span class="scite-citeref-number" data-reference="Talos GravityRAT" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://blog.talosintelligence.com/2018/04/gravityrat-two-year-evolution-of-apt.html" target="_blank">
         [13]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0264">
      OopsIE
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0264">
       OopsIE
      </a>
      performs several anti-VM and sandbox checks on the victim's machine. One technique the group has used was to perform a WMI query
      <code>
       SELECT * FROM MSAcpi_ThermalZoneTemperature
      </code>
      to check the temperature to see if it’s running in a virtual environment.
      <span class="scite-citeref-number" data-reference="Unit 42 OilRig Sept 2018" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://researchcenter.paloaltonetworks.com/2018/09/unit42-oilrig-targets-middle-eastern-government-adds-evasion-techniques-oopsie/" target="_blank">
         [6]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0013">
      PlugX
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0013">
       PlugX
      </a>
      checks if VMware tools is running in the background by searching for any process named "vmtoolsd".
      <span class="scite-citeref-number" data-reference="Unit42 PlugX June 2017" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://unit42.paloaltonetworks.com/unit42-paranoid-plugx/" target="_blank">
         [14]
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
      has a module to check if its running on a virtual machine.
      <span class="scite-citeref-number" data-reference="GitHub Pupy" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://github.com/n1nj4sec/pupy" target="_blank">
         [15]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0332">
      Remcos
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0332">
       Remcos
      </a>
      searches for Sandboxie and VMware on the system.
      <span class="scite-citeref-number" data-reference="Talos Remcos Aug 2018" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="https://blog.talosintelligence.com/2018/08/picking-apart-remcos.html" target="_blank">
         [16]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0270">
      RogueRobin
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0270">
       RogueRobin
      </a>
      uses WMI to check BIOS version for VBOX, bochs, qemu, virtualbox, and vm to check for evidence that the script might be executing within an analysis environment.
      <span class="scite-citeref-number" data-reference="Unit 42 DarkHydrus July 2018" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-new-threat-actor-group-darkhydrus-targets-middle-east-government/" target="_blank">
         [17]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Unit42 DarkHydrus Jan 2019" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="https://unit42.paloaltonetworks.com/darkhydrus-delivers-new-trojan-that-can-use-google-drive-for-c2-communications/" target="_blank">
         [18]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0240">
      ROKRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0240">
       ROKRAT
      </a>
      checks for sandboxing libraries.
      <span class="scite-citeref-number" data-reference="Talos Group123" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="https://blog.talosintelligence.com/2018/01/korea-in-crosshairs.html" target="_blank">
         [19]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0226">
      Smoke Loader
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0226">
       Smoke Loader
      </a>
      scans processes to perform anti-VM checks.
      <span class="scite-citeref-number" data-reference="Talos Smoke Loader July 2018" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://blog.talosintelligence.com/2018/07/smoking-guns-smoke-loader-learned-new.html#more" target="_blank">
         [20]
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
      checks its directory location in an attempt to avoid launching in a sandbox.
      <span class="scite-citeref-number" data-reference="SecureList SynAck Doppelgänging May 2018" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="https://securelist.com/synack-targeted-ransomware-uses-the-doppelganging-technique/85431/" target="_blank">
         [21]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Kaspersky Lab SynAck May 2018" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="https://usa.kaspersky.com/about/press-releases/2018_synack-doppelganging" target="_blank">
         [22]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0333">
      UBoatRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0333">
       UBoatRAT
      </a>
      checks for virtualization software such as VMWare, VirtualBox, or QEmu on the compromised machine.
      <span class="scite-citeref-number" data-reference="PaloAlto UBoatRAT Nov 2017" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-uboatrat-navigates-east-asia/" target="_blank">
         [23]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0248">
      yty
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0248">
       yty
      </a>
      has some basic anti-sandbox detection that tries to detect Virtual PC, Sandboxie, and VMware.
      <span class="scite-citeref-number" data-reference="ASERT Donot March 2018" id="scite-ref-24-a" onclick="scrollToRef('scite-24')">
       <sup>
        <a aria-describedby="qtip-23" data-hasqtip="23" href="https://www.arbornetworks.com/blog/asert/donot-team-leverages-new-modular-malware-framework-south-asia/" target="_blank">
         [24]
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
  Mitigation of this technique with preventative controls may impact the adversary's decision process depending on what they're looking for, how they use the information, and what their objectives are. Since it may be difficult to mitigate all aspects of information that could be gathered, efforts should be focused on preventing adversary tools from running earlier in the chain of activity and on identifying subsequent malicious behavior if compromised.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Virtualization, sandbox, and related discovery techniques will likely occur in the first steps of an operation but may also occur throughout as an adversary learns the environment. Data and events should not be viewed in isolation, but as part of a chain of behavior that could lead to other activities, such as lateral movement, based on the information obtained. Detecting actions related to virtualization and sandbox identification may be difficult depending on the adversary's implementation and monitoring required. Monitoring for suspicious processes being spawned that gather a variety of system information or perform other forms of
  <a href="https://attack.mitre.org/tactics/TA0007">
   Discovery
  </a>
  , especially in a short period of time, may aid in detection.
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
       <a class="external text" href="https://unit42.paloaltonetworks.com/ups-observations-on-cve-2015-3113-prior-zero-days-and-the-pirpi-payload/" name="scite-1" rel="nofollow" target="_blank">
        Falcone, R., Wartell, R.. (2015, July 27). UPS: Observations on CVE-2015-3113, Prior Zero-Days and the Pirpi Payload. Retrieved April 23, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/other-blogs/mcafee-labs/stopping-malware-fake-virtual-machine/" name="scite-2" rel="nofollow" target="_blank">
        Roccia, T. (2017, January 19). Stopping Malware With a Fake Virtual Machine. Retrieved April 17, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.sans.org/reading-room/whitepapers/forensics/detecting-malware-sandbox-evasion-techniques-36667" name="scite-3" rel="nofollow" target="_blank">
        Keragala, D. (2016, January 16). Detecting Malware and Sandbox Evasion Techniques. Retrieved April 17, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://unit42.paloaltonetworks.com/unit42-sofacy-continues-global-attacks-wheels-new-cannon-trojan/" name="scite-4" rel="nofollow" target="_blank">
        Falcone, R., Lee, B.. (2018, November 20). Sofacy Continues Global Attacks and Wheels Out New ‘Cannon’ Trojan. Retrieved April 23, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/04/fin7-phishing-lnk.html" name="scite-5" rel="nofollow" target="_blank">
        Carr, N., et al. (2017, April 24). FIN7 Evolution and the Phishing LNK. Retrieved April 24, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/09/unit42-oilrig-targets-middle-eastern-government-adds-evasion-techniques-oopsie/" name="scite-6" rel="nofollow" target="_blank">
        Falcone, R., et al. (2018, September 04). OilRig Targets a Middle Eastern Government and Adds Evasion Techniques to OopsIE. Retrieved September 24, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/10/unit42-badpatch/" name="scite-7" rel="nofollow" target="_blank">
        Bar, T., Conant, S. (2017, October 20). BadPatch. Retrieved November 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/rpt-apt28.pdf" name="scite-8" rel="nofollow" target="_blank">
        FireEye. (2015). APT28: A WINDOW INTO RUSSIA’S CYBER ESPIONAGE OPERATIONS?. Retrieved August 19, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.f-secure.com/documents/996508/1030745/CozyDuke" name="scite-9" rel="nofollow" target="_blank">
        F-Secure Labs. (2015, April 22). CozyDuke: Malware Analysis. Retrieved December 10, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/dyre-emerging-threat.pdf" name="scite-10" rel="nofollow" target="_blank">
        Symantec Security Response. (2015, June 23). Dyre: Emerging threat on financial fraud landscape. Retrieved August 23, 2018.
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
   </ol>
  </div>
  <div class="col">
   <ol start="13.0">
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/04/gravityrat-two-year-evolution-of-apt.html" name="scite-13" rel="nofollow" target="_blank">
        Mercer, W., Rascagneres, P. (2018, April 26). GravityRAT - The Two-Year Evolution Of An APT Targeting India. Retrieved May 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://unit42.paloaltonetworks.com/unit42-paranoid-plugx/" name="scite-14" rel="nofollow" target="_blank">
        Lancaster, T., Idrizovic, E. (2017, June 27). Paranoid PlugX. Retrieved April 19, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/n1nj4sec/pupy" name="scite-15" rel="nofollow" target="_blank">
        Nicolas Verdier. (n.d.). Retrieved January 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/08/picking-apart-remcos.html" name="scite-16" rel="nofollow" target="_blank">
        Brumaghin, E., Unterbrink, H. (2018, August 22). Picking Apart Remcos Botnet-In-A-Box. Retrieved November 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-new-threat-actor-group-darkhydrus-targets-middle-east-government/" name="scite-17" rel="nofollow" target="_blank">
        Falcone, R., et al. (2018, July 27). New Threat Actor Group DarkHydrus Targets Middle East Government. Retrieved August 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://unit42.paloaltonetworks.com/darkhydrus-delivers-new-trojan-that-can-use-google-drive-for-c2-communications/" name="scite-18" rel="nofollow" target="_blank">
        Lee, B., Falcone, R. (2019, January 18). DarkHydrus delivers new Trojan that can use Google Drive for C2 communications. Retrieved April 17, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/01/korea-in-crosshairs.html" name="scite-19" rel="nofollow" target="_blank">
        Mercer, W., Rascagneres, P. (2018, January 16). Korea In The Crosshairs. Retrieved May 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/07/smoking-guns-smoke-loader-learned-new.html#more" name="scite-20" rel="nofollow" target="_blank">
        Baker, B., Unterbrink H. (2018, July 03). Smoking Guns - Smoke Loader learned new tricks. Retrieved July 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/synack-targeted-ransomware-uses-the-doppelganging-technique/85431/" name="scite-21" rel="nofollow" target="_blank">
        Ivanov, A. et al.. (2018, May 7). SynAck targeted ransomware uses the Doppelgänging technique. Retrieved May 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="https://usa.kaspersky.com/about/press-releases/2018_synack-doppelganging" name="scite-22" rel="nofollow" target="_blank">
        Bettencourt, J. (2018, May 7). Kaspersky Lab finds new variant of SynAck ransomware using sophisticated Doppelgänging technique. Retrieved May 24, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-23">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-uboatrat-navigates-east-asia/" name="scite-23" rel="nofollow" target="_blank">
        Hayashi, K. (2017, November 28). UBoatRAT Navigates East Asia. Retrieved January 12, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-24">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.arbornetworks.com/blog/asert/donot-team-leverages-new-modular-malware-framework-south-asia/" name="scite-24" rel="nofollow" target="_blank">
        Schwarz, D., Sopko J. (2018, March 08). Donot Team Leverages New Modular Malware Framework in South Asia. Retrieved June 11, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
