<div class="container-fluid">
 <h1>
  Scripting
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries may use scripts to aid in operations and perform multiple actions that would otherwise be manual. Scripting is useful for speeding up operational tasks and reducing the time required to gain access to critical resources. Some scripting languages may be used to bypass process monitoring mechanisms by directly interacting with the operating system at an API level instead of calling other programs. Common scripting languages for Windows include VBScript and PowerShell but could also be in the form of command-line batch scripts.
   </p>
   <p>
    Scripts can be embedded inside Office documents as macros that can be set to execute when files used in
    <a href="https://attack.mitre.org/techniques/T1193">
     Spearphishing Attachment
    </a>
    and other types of spearphishing are opened. Malicious embedded macros are an alternative means of execution than software exploitation through
    <a href="https://attack.mitre.org/techniques/T1203">
     Exploitation for Client Execution
    </a>
    , where adversaries will rely on macos being allowed or that the user will accept to activate them.
   </p>
   <p>
    Many popular offensive frameworks exist which use forms of scripting for security testers and adversaries alike.
    <span class="scite-citeref-number" data-reference="Metasploit" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://www.metasploit.com" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Metasploit" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://www.metasploit.com" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    ,
    <span class="scite-citeref-number" data-reference="Veil" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.veil-framework.com/framework/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Veil" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.veil-framework.com/framework/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    , and PowerSploit
    <span class="scite-citeref-number" data-reference="Powersploit" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://github.com/mattifestation/PowerSploit" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    are three examples that are popular among penetration testers for exploit and post-compromise operations and include many features for evading defenses. Some adversaries are known to use PowerShell.
    <span class="scite-citeref-number" data-reference="Alperovitch 2014" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://blog.crowdstrike.com/deep-thought-chinese-targeting-national-security-think-tanks/" target="_blank">
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
      : T1064
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
      : Defense Evasion, Execution
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
      Process monitoring, File monitoring, Process command-line parameters
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
      Process whitelisting, Data Execution Prevention, Exploit Prevention
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
     <a href="https://attack.mitre.org/groups/G0006">
      APT1
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0006">
       APT1
      </a>
      has used batch scripting to automate execution of commands.
      <span class="scite-citeref-number" data-reference="Mandiant APT1" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0073">
      APT19
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0073">
       APT19
      </a>
      downloaded and launched code within a SCT file.
      <span class="scite-citeref-number" data-reference="FireEye APT19" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.fireeye.com/blog/threat-research/2017/06/phished-at-the-request-of-counsel.html" target="_blank">
         [6]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0007">
      APT28
     </a>
    </td>
    <td>
     <p>
      An
      <a href="https://attack.mitre.org/groups/G0007">
       APT28
      </a>
      loader Trojan uses a batch script to run its payload.
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
     <a href="https://attack.mitre.org/groups/G0016">
      APT29
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0016">
       APT29
      </a>
      has used encoded PowerShell scripts uploaded to
      <a href="https://attack.mitre.org/software/S0046">
       CozyCar
      </a>
      installations to download and install
      <a href="https://attack.mitre.org/software/S0053">
       SeaDuke
      </a>
      , as well as to evade defenses.
      <span class="scite-citeref-number" data-reference="Symantec Seaduke 2015" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="http://www.symantec.com/connect/blogs/forkmeiamfamous-seaduke-latest-weapon-duke-armory" target="_blank">
         [8]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Mandiant No Easy Breach" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="http://www.slideshare.net/MatthewDunwoody1/no-easy-breach-derby-con-2016" target="_blank">
         [9]
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
      has used PowerShell on victim systems to download and run payloads after exploitation.
      <span class="scite-citeref-number" data-reference="FireEye Operation Double Tap" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www.fireeye.com/blog/threat-research/2014/11/operation_doubletap.html" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
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
      executes shellcode and a script to decode Base64 strings.
      <span class="scite-citeref-number" data-reference="Talos Group123" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://blog.talosintelligence.com/2018/01/korea-in-crosshairs.html" target="_blank">
         [11]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0268">
      Bisonal
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0268">
       Bisonal
      </a>
      's dropper creates VBS scripts on the victim’s machine.
      <span class="scite-citeref-number" data-reference="Unit 42 Bisonal July 2018" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-bisonal-malware-used-attacks-russia-south-korea/" target="_blank">
         [12]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0060">
      BRONZE BUTLER
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0060">
       BRONZE BUTLER
      </a>
      has used VBS, VBE, and batch scripts for execution.
      <span class="scite-citeref-number" data-reference="Secureworks BRONZE BUTLER Oct 2017" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://www.secureworks.com/research/bronze-butler-targets-japanese-businesses" target="_blank">
         [13]
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
      has sent Word OLE compound documents with malicious obfuscated VBA macros that will run upon user execution. The group has also used an exploit toolkit known as Threadkit that launches .bat files.
      <span class="scite-citeref-number" data-reference="Talos Cobalt Group July 2018" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://blog.talosintelligence.com/2018/07/multiple-cobalt-personality-disorder.html" target="_blank">
         [14]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PTSecurity Cobalt Group Aug 2017" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://www.ptsecurity.com/upload/corporate/ww-en/analytics/Cobalt-2017-eng.pdf" target="_blank">
         [15]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Group IB Cobalt Aug 2017" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="https://www.group-ib.com/blog/cobalt" target="_blank">
         [16]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0154">
      Cobalt Strike
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0154">
       Cobalt Strike
      </a>
      can use PowerSploit or other scripting frameworks to perform execution.
      <span class="scite-citeref-number" data-reference="Cobalt Strike TTPs Dec 2017" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://www.cobaltstrike.com/downloads/reports/tacticstechniquesandprocedures.pdf" target="_blank">
         [17]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0244">
      Comnie
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0244">
       Comnie
      </a>
      executes BAT and VBS scripts.
      <span class="scite-citeref-number" data-reference="Palo Alto Comnie" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="https://researchcenter.paloaltonetworks.com/2018/01/unit42-comnie-continues-target-organizations-east-asia/" target="_blank">
         [18]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0070">
      Dark Caracal
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0070">
       Dark Caracal
      </a>
      has used macros in Word documents that would download a second stage if executed.
      <span class="scite-citeref-number" data-reference="Lookout Dark Caracal Jan 2018" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="https://info.lookout.com/rs/051-ESQ-475/images/Lookout_Dark-Caracal_srr_20180118_us_v.1.0.pdf" target="_blank">
         [19]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0243">
      DealersChoice
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0243">
       DealersChoice
      </a>
      makes modifications to open-source scripts from GitHub and executes them on the victim’s machine.
      <span class="scite-citeref-number" data-reference="Sofacy DealersChoice" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://researchcenter.paloaltonetworks.com/2018/03/unit42-sofacy-uses-dealerschoice-target-european-government-agency/" target="_blank">
         [20]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0009">
      Deep Panda
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0009">
       Deep Panda
      </a>
      has used PowerShell scripts to download and execute programs in memory, without writing to disk.
      <span class="scite-citeref-number" data-reference="Alperovitch 2014" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://blog.crowdstrike.com/deep-thought-chinese-targeting-national-security-think-tanks/" target="_blank">
         [4]
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
      used various types of scripting to perform operations, including Python and batch scripts. The group was observed installing Python 2.7 on a victim.
      <span class="scite-citeref-number" data-reference="US-CERT TA18-074A" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" target="_blank">
         [21]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT APT Energy Oct 2017" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" target="_blank">
         [22]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0267">
      FELIXROOT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0267">
       FELIXROOT
      </a>
      executes batch scripts on the victim’s machine.
      <span class="scite-citeref-number" data-reference="FireEye FELIXROOT July 2018" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="https://www.fireeye.com/blog/threat-research/2018/07/microsoft-office-vulnerabilities-used-to-distribute-felixroot-backdoor.html" target="_blank">
         [23]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0051">
      FIN10
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0051">
       FIN10
      </a>
      has executed malicious .bat files containing PowerShell commands.
      <span class="scite-citeref-number" data-reference="FireEye FIN10 June 2017" id="scite-ref-24-a" onclick="scrollToRef('scite-24')">
       <sup>
        <a aria-describedby="qtip-23" data-hasqtip="23" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin10.pdf" target="_blank">
         [24]
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
      scans processes on all victim systems in the environment and uses automated scripts to pull back the results.
      <span class="scite-citeref-number" data-reference="Mandiant FIN5 GrrCON Oct 2016" id="scite-ref-25-a" onclick="scrollToRef('scite-25')">
       <sup>
        <a aria-describedby="qtip-24" data-hasqtip="24" href="https://www.youtube.com/watch?v=fevGZs0EQu8" target="_blank">
         [25]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0037">
      FIN6
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0037">
       FIN6
      </a>
      has used a Metasploit PowerShell module to download and execute shellcode and to set up a local listener.
      <a href="https://attack.mitre.org/groups/G0037">
       FIN6
      </a>
      has also used scripting to iterate through a list of compromised PoS systems, copy data to a log file, and remove the original data files.
      <span class="scite-citeref-number" data-reference="FireEye FIN6 April 2016" id="scite-ref-26-a" onclick="scrollToRef('scite-26')">
       <sup>
        <a aria-describedby="qtip-25" data-hasqtip="25" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin6.pdf" target="_blank">
         [26]
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
      used VBS and JavaScript scripts to help perform tasks on the victim's machine.
      <span class="scite-citeref-number" data-reference="FireEye FIN7 Aug 2018" id="scite-ref-27-a" onclick="scrollToRef('scite-27')">
       <sup>
        <a aria-describedby="qtip-26" data-hasqtip="26" href="https://www.fireeye.com/blog/threat-research/2018/08/fin7-pursuing-an-enigmatic-and-evasive-global-criminal-operation.html" target="_blank">
         [27]
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
      has used a Batch file to automate frequently executed post compromise cleanup activities.
      <span class="scite-citeref-number" data-reference="FireEye Know Your Enemy FIN8 Aug 2016" id="scite-ref-28-a" onclick="scrollToRef('scite-28')">
       <sup>
        <a aria-describedby="qtip-27" data-hasqtip="27" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" target="_blank">
         [28]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0047">
      Gamaredon Group
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0047">
       Gamaredon Group
      </a>
      has used various batch scripts to establish C2, download additional files, and conduct other functions.
      <span class="scite-citeref-number" data-reference="Palo Alto Gamaredon Feb 2017" id="scite-ref-29-a" onclick="scrollToRef('scite-29')">
       <sup>
        <a aria-describedby="qtip-28" data-hasqtip="28" href="https://researchcenter.paloaltonetworks.com/2017/02/unit-42-title-gamaredon-group-toolset-evolution/" target="_blank">
         [29]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0078">
      Gorgon Group
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0078">
       Gorgon Group
      </a>
      has used macros in
      <a href="https://attack.mitre.org/techniques/T1193">
       Spearphishing Attachment
      </a>
      s as well as executed VBScripts on victim machines.
      <span class="scite-citeref-number" data-reference="Unit 42 Gorgon Group Aug 2018" id="scite-ref-30-a" onclick="scrollToRef('scite-30')">
       <sup>
        <a aria-describedby="qtip-29" data-hasqtip="29" href="https://researchcenter.paloaltonetworks.com/2018/08/unit42-gorgon-group-slithering-nation-state-cybercrime/" target="_blank">
         [30]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0170">
      Helminth
     </a>
    </td>
    <td>
     <p>
      One version of
      <a href="https://attack.mitre.org/software/S0170">
       Helminth
      </a>
      consists of VBScript and PowerShell scripts. The malware also uses batch scripting.
      <span class="scite-citeref-number" data-reference="Palo Alto OilRig May 2016" id="scite-ref-31-a" onclick="scrollToRef('scite-31')">
       <sup>
        <a aria-describedby="qtip-30" data-hasqtip="30" href="http://researchcenter.paloaltonetworks.com/2016/05/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/" target="_blank">
         [31]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0072">
      Honeybee
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0072">
       Honeybee
      </a>
      embeds a Visual Basic script within a malicious Word document as part of initial access; the script is executed when the Word document is opened. The actors also used batch scripting.
      <span class="scite-citeref-number" data-reference="McAfee Honeybee" id="scite-ref-32-a" onclick="scrollToRef('scite-32')">
       <sup>
        <a aria-describedby="qtip-31" data-hasqtip="31" href="https://securingtomorrow.mcafee.com/mcafee-labs/mcafee-uncovers-operation-honeybee-malicious-document-campaign-targeting-humanitarian-aid-groups/" target="_blank">
         [32]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0004">
      Ke3chang
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0004">
       Ke3chang
      </a>
      has used batch scripts in its malware to install persistence mechanisms.
      <span class="scite-citeref-number" data-reference="NCC Group APT15 Alive and Strong" id="scite-ref-33-a" onclick="scrollToRef('scite-33')">
       <sup>
        <a aria-describedby="qtip-32" data-hasqtip="32" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/" target="_blank">
         [33]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0276">
      Keydnap
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0276">
       Keydnap
      </a>
      uses Python for scripting to execute additional commands.
      <span class="scite-citeref-number" data-reference="synack 2016 review" id="scite-ref-34-a" onclick="scrollToRef('scite-34')">
       <sup>
        <a aria-describedby="qtip-33" data-hasqtip="33" href="https://www.synack.com/2017/01/01/mac-malware-2016/" target="_blank">
         [34]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0250">
      Koadic
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0250">
       Koadic
      </a>
      performs most of its operations using Windows Script Host (Jscript and VBScript) and runs arbitrary shellcode .
      <span class="scite-citeref-number" data-reference="Github Koadic" id="scite-ref-35-a" onclick="scrollToRef('scite-35')">
       <sup>
        <a aria-describedby="qtip-34" data-hasqtip="34" href="https://github.com/zerosum0x0/koadic" target="_blank">
         [35]
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
      A Destover-like variant used by
      <a href="https://attack.mitre.org/groups/G0032">
       Lazarus Group
      </a>
      uses a batch file mechanism to delete its binaries from the system.
      <span class="scite-citeref-number" data-reference="McAfee GhostSecret" id="scite-ref-36-a" onclick="scrollToRef('scite-36')">
       <sup>
        <a aria-describedby="qtip-35" data-hasqtip="35" href="https://securingtomorrow.mcafee.com/mcafee-labs/analyzing-operation-ghostsecret-attack-seeks-to-steal-data-worldwide/" target="_blank">
         [36]
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
      infected victims using JavaScript code.
      <span class="scite-citeref-number" data-reference="Symantec Leafminer July 2018" id="scite-ref-37-a" onclick="scrollToRef('scite-37')">
       <sup>
        <a aria-describedby="qtip-36" data-hasqtip="36" href="https://www.symantec.com/blogs/threat-intelligence/leafminer-espionage-middle-east" target="_blank">
         [37]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0065">
      Leviathan
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0065">
       Leviathan
      </a>
      has used multiple types of scripting for execution, including JavaScript, JavaScript Scriptlets in XML, and VBScript.
      <span class="scite-citeref-number" data-reference="Proofpoint Leviathan Oct 2017" id="scite-ref-38-a" onclick="scrollToRef('scite-38')">
       <sup>
        <a aria-describedby="qtip-37" data-hasqtip="37" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" target="_blank">
         [38]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0059">
      Magic Hound
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0059">
       Magic Hound
      </a>
      malware has used .vbs scripts for execution.
      <span class="scite-citeref-number" data-reference="Unit 42 Magic Hound Feb 2017" id="scite-ref-39-a" onclick="scrollToRef('scite-39')">
       <sup>
        <a aria-describedby="qtip-38" data-hasqtip="38" href="https://researchcenter.paloaltonetworks.com/2017/02/unit42-magic-hound-campaign-attacks-saudi-targets/" target="_blank">
         [39]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0045">
      menuPass
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0045">
       menuPass
      </a>
      has used malicious macros embedded inside Office documents to execute files.
      <span class="scite-citeref-number" data-reference="Accenture Hogfish April 2018" id="scite-ref-40-a" onclick="scrollToRef('scite-40')">
       <sup>
        <a aria-describedby="qtip-39" data-hasqtip="39" href="https://www.accenture.com/t20180423T055005Z_w_/se-en/_acnmedia/PDF-76/Accenture-Hogfish-Threat-Analysis.pdf" target="_blank">
         [40]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye APT10 Sept 2018" id="scite-ref-41-a" onclick="scrollToRef('scite-41')">
       <sup>
        <a aria-describedby="qtip-40" data-hasqtip="40" href="https://www.fireeye.com/blog/threat-research/2018/09/apt10-targeting-japanese-corporations-using-updated-ttps.html" target="_blank">
         [41]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0149">
      MoonWind
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0149">
       MoonWind
      </a>
      uses batch scripts for various purposes, including to restart and uninstall itself.
      <span class="scite-citeref-number" data-reference="Palo Alto MoonWind March 2017" id="scite-ref-42-a" onclick="scrollToRef('scite-42')">
       <sup>
        <a aria-describedby="qtip-41" data-hasqtip="41" href="http://researchcenter.paloaltonetworks.com/2017/03/unit42-trochilus-rat-new-moonwind-rat-used-attack-thai-utility-organizations/" target="_blank">
         [42]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0069">
      MuddyWater
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0069">
       MuddyWater
      </a>
      has used VBScript and JavaScript files to execute its
      <a href="https://attack.mitre.org/software/S0223">
       POWERSTATS
      </a>
      payload.
      <span class="scite-citeref-number" data-reference="FireEye MuddyWater Mar 2018" id="scite-ref-43-a" onclick="scrollToRef('scite-43')">
       <sup>
        <a aria-describedby="qtip-42" data-hasqtip="42" href="https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html" target="_blank">
         [43]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="MuddyWater TrendMicro June 2018" id="scite-ref-44-a" onclick="scrollToRef('scite-44')">
       <sup>
        <a aria-describedby="qtip-43" data-hasqtip="43" href="https://blog.trendmicro.com/trendlabs-security-intelligence/another-potential-muddywater-campaign-uses-powershell-based-prb-backdoor/" target="_blank">
         [44]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0228">
      NanHaiShu
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0228">
       NanHaiShu
      </a>
      executes additional Jscript and VBScript code on the victim's machine.
      <span class="scite-citeref-number" data-reference="fsecure NanHaiShu July 2016" id="scite-ref-45-a" onclick="scrollToRef('scite-45')">
       <sup>
        <a aria-describedby="qtip-44" data-hasqtip="44" href="https://www.f-secure.com/documents/996508/1030745/nanhaishu_whitepaper.pdf" target="_blank">
         [45]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0247">
      NavRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0247">
       NavRAT
      </a>
      loads malicious shellcode and executes it in memory.
      <span class="scite-citeref-number" data-reference="Talos NavRAT May 2018" id="scite-ref-46-a" onclick="scrollToRef('scite-46')">
       <sup>
        <a aria-describedby="qtip-45" data-hasqtip="45" href="https://blog.talosintelligence.com/2018/05/navrat.html" target="_blank">
         [46]
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
      has used various types of scripting for execution, including .bat and .vbs scripts. The group has also used macros to deliver malware such as
      <a href="https://attack.mitre.org/software/S0269">
       QUADAGENT
      </a>
      and
      <a href="https://attack.mitre.org/software/S0264">
       OopsIE
      </a>
      .
      <span class="scite-citeref-number" data-reference="FireEye APT34 Dec 2017" id="scite-ref-47-a" onclick="scrollToRef('scite-47')">
       <sup>
        <a aria-describedby="qtip-46" data-hasqtip="46" href="https://www.fireeye.com/blog/threat-research/2017/12/targeted-attack-in-middle-east-by-apt34.html" target="_blank">
         [47]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="OilRig ISMAgent July 2017" id="scite-ref-48-a" onclick="scrollToRef('scite-48')">
       <sup>
        <a aria-describedby="qtip-47" data-hasqtip="47" href="https://researchcenter.paloaltonetworks.com/2017/07/unit42-oilrig-uses-ismdoor-variant-possibly-linked-greenbug-threat-group/" target="_blank">
         [48]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Unit 42 OopsIE! Feb 2018" id="scite-ref-49-a" onclick="scrollToRef('scite-49')">
       <sup>
        <a aria-describedby="qtip-48" data-hasqtip="48" href="https://researchcenter.paloaltonetworks.com/2018/02/unit42-oopsie-oilrig-uses-threedollars-deliver-new-trojan/" target="_blank">
         [49]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Unit 42 QUADAGENT July 2018" id="scite-ref-50-a" onclick="scrollToRef('scite-50')">
       <sup>
        <a aria-describedby="qtip-49" data-hasqtip="49" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-oilrig-targets-technology-service-provider-government-agency-quadagent/" target="_blank">
         [50]
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
      creates and uses a VBScript as part of its persistent execution.
      <span class="scite-citeref-number" data-reference="Unit 42 OopsIE! Feb 2018" id="scite-ref-49-a" onclick="scrollToRef('scite-49')">
       <sup>
        <a aria-describedby="qtip-48" data-hasqtip="48" href="https://researchcenter.paloaltonetworks.com/2018/02/unit42-oopsie-oilrig-uses-threedollars-deliver-new-trojan/" target="_blank">
         [49]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Unit 42 OilRig Sept 2018" id="scite-ref-51-a" onclick="scrollToRef('scite-51')">
       <sup>
        <a aria-describedby="qtip-50" data-hasqtip="50" href="https://researchcenter.paloaltonetworks.com/2018/09/unit42-oilrig-targets-middle-eastern-government-adds-evasion-techniques-oopsie/" target="_blank">
         [51]
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
      can execute commands with script as well as execute JavaScript.
      <span class="scite-citeref-number" data-reference="Proofpoint Leviathan Oct 2017" id="scite-ref-38-a" onclick="scrollToRef('scite-38')">
       <sup>
        <a aria-describedby="qtip-37" data-hasqtip="37" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" target="_blank">
         [38]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0040">
      Patchwork
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0040">
       Patchwork
      </a>
      used Visual Basic Scripts (VBS), JavaScript code, batch files, and .SCT files on victim machines.
      <span class="scite-citeref-number" data-reference="TrendMicro Patchwork Dec 2017" id="scite-ref-52-a" onclick="scrollToRef('scite-52')">
       <sup>
        <a aria-describedby="qtip-51" data-hasqtip="51" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" target="_blank">
         [52]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Volexity Patchwork June 2018" id="scite-ref-53-a" onclick="scrollToRef('scite-53')">
       <sup>
        <a aria-describedby="qtip-52" data-hasqtip="52" href="https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/" target="_blank">
         [53]
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
      uses macOS' .command file type to script actions.
      <span class="scite-citeref-number" data-reference="objsee mac malware 2017" id="scite-ref-54-a" onclick="scrollToRef('scite-54')">
       <sup>
        <a aria-describedby="qtip-53" data-hasqtip="53" href="https://objective-see.com/blog/blog_0x25.html" target="_blank">
         [54]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0238">
      Proxysvc
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0238">
       Proxysvc
      </a>
      uses a batch file to delete itself.
      <span class="scite-citeref-number" data-reference="McAfee GhostSecret" id="scite-ref-36-a" onclick="scrollToRef('scite-36')">
       <sup>
        <a aria-describedby="qtip-35" data-hasqtip="35" href="https://securingtomorrow.mcafee.com/mcafee-labs/analyzing-operation-ghostsecret-attack-seeks-to-steal-data-worldwide/" target="_blank">
         [36]
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
      can use an add on feature when creating payloads that allows you to create custom Python scripts ("scriptlets") to perform tasks offline (without requiring a session) such as sandbox detection, adding persistence, etc.
      <span class="scite-citeref-number" data-reference="GitHub Pupy" id="scite-ref-55-a" onclick="scrollToRef('scite-55')">
       <sup>
        <a aria-describedby="qtip-54" data-hasqtip="54" href="https://github.com/n1nj4sec/pupy" target="_blank">
         [55]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0269">
      QUADAGENT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0269">
       QUADAGENT
      </a>
      uses VBScripts and batch scripts.
      <span class="scite-citeref-number" data-reference="Unit 42 QUADAGENT July 2018" id="scite-ref-50-a" onclick="scrollToRef('scite-50')">
       <sup>
        <a aria-describedby="qtip-49" data-hasqtip="49" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-oilrig-targets-technology-service-provider-government-agency-quadagent/" target="_blank">
         [50]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0075">
      Rancor
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0075">
       Rancor
      </a>
      has used shell and VBS scripts as well as embedded macros for execution.
      <span class="scite-citeref-number" data-reference="Rancor Unit42 June 2018" id="scite-ref-56-a" onclick="scrollToRef('scite-56')">
       <sup>
        <a aria-describedby="qtip-55" data-hasqtip="55" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-rancor-targeted-attacks-south-east-asia-using-plaintee-ddkong-malware-families/" target="_blank">
         [56]
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
      To assist in establishing persistence,
      <a href="https://attack.mitre.org/software/S0270">
       RogueRobin
      </a>
      creates
      <code>
       %APPDATA%\OneDrive.bat
      </code>
      and saves the following string to it:
      <code>
       powershell.exe -WindowStyle Hidden -exec bypass -File "%APPDATA%\OneDrive.ps1"
      </code>
      .
      <span class="scite-citeref-number" data-reference="Unit 42 DarkHydrus July 2018" id="scite-ref-57-a" onclick="scrollToRef('scite-57')">
       <sup>
        <a aria-describedby="qtip-56" data-hasqtip="56" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-new-threat-actor-group-darkhydrus-targets-middle-east-government/" target="_blank">
         [57]
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
      uses a batch file to kill a security program task and then attempts to remove itself.
      <span class="scite-citeref-number" data-reference="McAfee Gold Dragon" id="scite-ref-58-a" onclick="scrollToRef('scite-58')">
       <sup>
        <a aria-describedby="qtip-57" data-hasqtip="57" href="https://securingtomorrow.mcafee.com/mcafee-labs/gold-dragon-widens-olympics-malware-attacks-gains-permanent-presence-on-victims-systems/" target="_blank">
         [58]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0053">
      SeaDuke
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0053">
       SeaDuke
      </a>
      uses a module to execute Mimikatz with PowerShell to perform
      <a href="https://attack.mitre.org/techniques/T1097">
       Pass the Ticket
      </a>
      .
      <span class="scite-citeref-number" data-reference="Symantec Seaduke 2015" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="http://www.symantec.com/connect/blogs/forkmeiamfamous-seaduke-latest-weapon-duke-armory" target="_blank">
         [8]
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
      adds a Visual Basic script in the Startup folder to deploy the payload.
      <span class="scite-citeref-number" data-reference="Malwarebytes SmokeLoader 2016" id="scite-ref-59-a" onclick="scrollToRef('scite-59')">
       <sup>
        <a aria-describedby="qtip-58" data-hasqtip="58" href="https://blog.malwarebytes.com/threat-analysis/2016/08/smoke-loader-downloader-with-a-smokescreen-still-alive/" target="_blank">
         [59]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0038">
      Stealth Falcon
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0038">
       Stealth Falcon
      </a>
      malware uses PowerShell and WMI to script data collection and command execution on the victim.
      <span class="scite-citeref-number" data-reference="Citizen Lab Stealth Falcon May 2016" id="scite-ref-60-a" onclick="scrollToRef('scite-60')">
       <sup>
        <a aria-describedby="qtip-59" data-hasqtip="59" href="https://citizenlab.org/2016/05/stealth-falcon/" target="_blank">
         [60]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0062">
      TA459
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0062">
       TA459
      </a>
      has a VBScript for execution.
      <span class="scite-citeref-number" data-reference="Proofpoint TA459 April 2017" id="scite-ref-61-a" onclick="scrollToRef('scite-61')">
       <sup>
        <a aria-describedby="qtip-60" data-hasqtip="60" href="https://www.proofpoint.com/us/threat-insight/post/apt-targets-financial-analysts" target="_blank">
         [61]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0263">
      TYPEFRAME
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0263">
       TYPEFRAME
      </a>
      can uninstall malware components using a batch script. Additionally, a malicious Word document used for delivery uses VBA macros for execution.
      <span class="scite-citeref-number" data-reference="US-CERT TYPEFRAME June 2018" id="scite-ref-62-a" onclick="scrollToRef('scite-62')">
       <sup>
        <a aria-describedby="qtip-61" data-hasqtip="61" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-165A" target="_blank">
         [62]
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
  Turn off unused features or restrict access to scripting engines such as VBScript or scriptable administration frameworks such as PowerShell.
 </p>
 <p>
  Configure Office security settings enable Protected View, to execute within a sandbox environment, and to block macros through Group Policy.
  <span class="scite-citeref-number" data-reference="Microsoft Block Office Macros" id="scite-ref-63-a">
   <sup>
    <a aria-describedby="qtip-62" data-hasqtip="62" href="https://cloudblogs.microsoft.com/microsoftsecure/2016/03/22/new-feature-in-office-2016-can-block-macros-and-help-prevent-infection/" target="_blank">
     [63]
    </a>
   </sup>
  </span>
  Other types of virtualization and application microsegmentation may also mitigate the impact of compromise. The risks of additional exploits and weaknesses in implementation may still exist.
  <span class="scite-citeref-number" data-reference="Ars Technica Pwn2Own 2017 VM Escape" id="scite-ref-64-a">
   <sup>
    <a aria-describedby="qtip-63" data-hasqtip="63" href="https://arstechnica.com/information-technology/2017/03/hack-that-escapes-vm-by-exploiting-edge-browser-fetches-105000-at-pwn2own/" target="_blank">
     [64]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Scripting may be common on admin, developer, or power user systems, depending on job function. If scripting is restricted for normal users, then any attempts to enable scripts running on a system would be considered suspicious. If scripts are not commonly used on a system, but enabled, scripts running out of cycle from patching or other administrator functions are suspicious. Scripts should be captured from the file system when possible to determine their actions and intent.
 </p>
 <p>
  Scripts are likely to perform actions with various effects on a system that may generate events, depending on the types of monitoring used. Monitor processes and command-line arguments for script execution and subsequent behavior. Actions may be related to network and system information Discovery, Collection, or other scriptable post-compromise behaviors and could be used as indicators of detection leading back to the source script.
 </p>
 <p>
  Analyze Office file attachments for potentially malicious macros. Execution of macros may create suspicious process trees depending on what the macro is designed to do. Office processes, such as winword.exe, spawning instances of cmd.exe, script application like wscript.exe or powershell.exe, or other suspicious processes may indicate malicious activity.
  <span class="scite-citeref-number" data-reference="Uperesia Malicious Office Documents" id="scite-ref-65-a">
   <sup>
    <a aria-describedby="qtip-64" data-hasqtip="64" href="https://www.uperesia.com/analyzing-malicious-office-documents" target="_blank">
     [65]
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
       <a class="external text" href="http://www.metasploit.com" name="scite-1" rel="nofollow" target="_blank">
        Metasploit. (n.d.). Retrieved December 4, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.veil-framework.com/framework/" name="scite-2" rel="nofollow" target="_blank">
        Veil Framework. (n.d.). Retrieved December 4, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/mattifestation/PowerSploit" name="scite-3" rel="nofollow" target="_blank">
        PowerSploit. (n.d.). Retrieved December 4, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.crowdstrike.com/deep-thought-chinese-targeting-national-security-think-tanks/" name="scite-4" rel="nofollow" target="_blank">
        Alperovitch, D. (2014, July 7). Deep in Thought: Chinese Targeting of National Security Think Tanks. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf" name="scite-5" rel="nofollow" target="_blank">
        Mandiant. (n.d.). APT1 Exposing One of China’s Cyber Espionage Units. Retrieved July 18, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/06/phished-at-the-request-of-counsel.html" name="scite-6" rel="nofollow" target="_blank">
        Ahl, I. (2017, June 06). Privileges and Credentials: Phished at the Request of Counsel. Retrieved May 17, 2018.
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
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/connect/blogs/forkmeiamfamous-seaduke-latest-weapon-duke-armory" name="scite-8" rel="nofollow" target="_blank">
        Symantec Security Response. (2015, July 13). “Forkmeiamfamous”: Seaduke, latest weapon in the Duke armory. Retrieved July 22, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.slideshare.net/MatthewDunwoody1/no-easy-breach-derby-con-2016" name="scite-9" rel="nofollow" target="_blank">
        Dunwoody, M. and Carr, N.. (2016, September 27). No Easy Breach DerbyCon 2016. Retrieved October 4, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2014/11/operation_doubletap.html" name="scite-10" rel="nofollow" target="_blank">
        Moran, N., et al. (2014, November 21). Operation Double Tap. Retrieved January 14, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/01/korea-in-crosshairs.html" name="scite-11" rel="nofollow" target="_blank">
        Mercer, W., Rascagneres, P. (2018, January 16). Korea In The Crosshairs. Retrieved May 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-bisonal-malware-used-attacks-russia-south-korea/" name="scite-12" rel="nofollow" target="_blank">
        Hayashi, K., Ray, V. (2018, July 31). Bisonal Malware Used in Attacks Against Russia and South Korea. Retrieved August 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/bronze-butler-targets-japanese-businesses" name="scite-13" rel="nofollow" target="_blank">
        Counter Threat Unit Research Team. (2017, October 12). BRONZE BUTLER Targets Japanese Enterprises. Retrieved January 4, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/07/multiple-cobalt-personality-disorder.html" name="scite-14" rel="nofollow" target="_blank">
        Svajcer, V. (2018, July 31). Multiple Cobalt Personality Disorder. Retrieved September 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.ptsecurity.com/upload/corporate/ww-en/analytics/Cobalt-2017-eng.pdf" name="scite-15" rel="nofollow" target="_blank">
        Positive Technologies. (2017, August 16). Cobalt Strikes Back: An Evolving Multinational Threat to Finance. Retrieved September 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.group-ib.com/blog/cobalt" name="scite-16" rel="nofollow" target="_blank">
        Matveeva, V. (2017, August 15). Secrets of Cobalt. Retrieved October 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cobaltstrike.com/downloads/reports/tacticstechniquesandprocedures.pdf" name="scite-17" rel="nofollow" target="_blank">
        Cobalt Strike. (2017, December 8). Tactics, Techniques, and Procedures. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/01/unit42-comnie-continues-target-organizations-east-asia/" name="scite-18" rel="nofollow" target="_blank">
        Grunzweig, J. (2018, January 31). Comnie Continues to Target Organizations in East Asia. Retrieved June 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://info.lookout.com/rs/051-ESQ-475/images/Lookout_Dark-Caracal_srr_20180118_us_v.1.0.pdf" name="scite-19" rel="nofollow" target="_blank">
        Blaich, A., et al. (2018, January 18). Dark Caracal: Cyber-espionage at a Global Scale. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/03/unit42-sofacy-uses-dealerschoice-target-european-government-agency/" name="scite-20" rel="nofollow" target="_blank">
        Falcone, R. (2018, March 15). Sofacy Uses DealersChoice to Target European Government Agency. Retrieved June 4, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" name="scite-21" rel="nofollow" target="_blank">
        US-CERT. (2018, March 16). Alert (TA18-074A): Russian Government Cyber Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" name="scite-22" rel="nofollow" target="_blank">
        US-CERT. (2017, October 20). Alert (TA17-293A): Advanced Persistent Threat Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved November 2, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-23">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/07/microsoft-office-vulnerabilities-used-to-distribute-felixroot-backdoor.html" name="scite-23" rel="nofollow" target="_blank">
        Patil, S. (2018, June 26). Microsoft Office Vulnerabilities Used to Distribute FELIXROOT Backdoor in Recent Campaign. Retrieved July 31, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-24">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin10.pdf" name="scite-24" rel="nofollow" target="_blank">
        FireEye iSIGHT Intelligence. (2017, June 16). FIN10: Anatomy of a Cyber Extortion Operation. Retrieved June 25, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-25">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.youtube.com/watch?v=fevGZs0EQu8" name="scite-25" rel="nofollow" target="_blank">
        Bromiley, M. and Lewis, P. (2016, October 7). Attacking the Hospitality and Gaming Industries: Tracking an Attacker Around the World in 7 Years. Retrieved October 6, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-26">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin6.pdf" name="scite-26" rel="nofollow" target="_blank">
        FireEye Threat Intelligence. (2016, April). Follow the Money: Dissecting the Operations of the Cyber Crime Group FIN6. Retrieved June 1, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-27">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/08/fin7-pursuing-an-enigmatic-and-evasive-global-criminal-operation.html" name="scite-27" rel="nofollow" target="_blank">
        Carr, N., et al. (2018, August 01). On the Hunt for FIN7: Pursuing an Enigmatic and Evasive Global Criminal Operation. Retrieved August 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-28">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" name="scite-28" rel="nofollow" target="_blank">
        Elovitz, S. &amp; Ahl, I. (2016, August 18). Know Your Enemy:  New Financially-Motivated &amp; Spear-Phishing Group. Retrieved February 26, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-29">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/02/unit-42-title-gamaredon-group-toolset-evolution/" name="scite-29" rel="nofollow" target="_blank">
        Kasza, A. and Reichel, D.. (2017, February 27). The Gamaredon Group Toolset Evolution. Retrieved March 1, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-30">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/08/unit42-gorgon-group-slithering-nation-state-cybercrime/" name="scite-30" rel="nofollow" target="_blank">
        Falcone, R., et al. (2018, August 02). The Gorgon Group: Slithering Between Nation State and Cybercrime. Retrieved August 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-31">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/05/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/" name="scite-31" rel="nofollow" target="_blank">
        Falcone, R. and Lee, B.. (2016, May 26). The OilRig Campaign: Attacks on Saudi Arabian Organizations Deliver Helminth Backdoor. Retrieved May 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-32">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/mcafee-uncovers-operation-honeybee-malicious-document-campaign-targeting-humanitarian-aid-groups/" name="scite-32" rel="nofollow" target="_blank">
        Sherstobitoff, R. (2018, March 02). McAfee Uncovers Operation Honeybee, a Malicious Document Campaign Targeting Humanitarian Aid Groups. Retrieved May 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-33">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/" name="scite-33" rel="nofollow" target="_blank">
        Smallridge, R. (2018, March 10). APT15 is alive and strong: An analysis of RoyalCli and RoyalDNS. Retrieved April 4, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="34.5">
    <li>
     <span class="scite-citation" id="scite-34">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.synack.com/2017/01/01/mac-malware-2016/" name="scite-34" rel="nofollow" target="_blank">
        Patrick Wardle. (2017, January 1). Mac Malware of 2016. Retrieved September 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-35">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/zerosum0x0/koadic" name="scite-35" rel="nofollow" target="_blank">
        Magius, J., et al. (2017, July 19). Koadic. Retrieved June 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-36">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/analyzing-operation-ghostsecret-attack-seeks-to-steal-data-worldwide/" name="scite-36" rel="nofollow" target="_blank">
        Sherstobitoff, R., Malhotra, A. (2018, April 24). Analyzing Operation GhostSecret: Attack Seeks to Steal Data Worldwide. Retrieved May 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-37">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/leafminer-espionage-middle-east" name="scite-37" rel="nofollow" target="_blank">
        Symantec Security Response. (2018, July 25). Leafminer: New Espionage Campaigns Targeting Middle Eastern Regions. Retrieved August 28, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-38">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets" name="scite-38" rel="nofollow" target="_blank">
        Axel F, Pierre T. (2017, October 16). Leviathan: Espionage actor spearphishes maritime and defense targets. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-39">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/02/unit42-magic-hound-campaign-attacks-saudi-targets/" name="scite-39" rel="nofollow" target="_blank">
        Lee, B. and Falcone, R. (2017, February 15). Magic Hound Campaign Attacks Saudi Targets. Retrieved December 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-40">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.accenture.com/t20180423T055005Z_w_/se-en/_acnmedia/PDF-76/Accenture-Hogfish-Threat-Analysis.pdf" name="scite-40" rel="nofollow" target="_blank">
        Accenture Security. (2018, April 23). Hogfish Redleaves Campaign. Retrieved July 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-41">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/09/apt10-targeting-japanese-corporations-using-updated-ttps.html" name="scite-41" rel="nofollow" target="_blank">
        Matsuda, A., Muhammad I. (2018, September 13). APT10 Targeting Japanese Corporations Using Updated TTPs. Retrieved September 17, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-42">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2017/03/unit42-trochilus-rat-new-moonwind-rat-used-attack-thai-utility-organizations/" name="scite-42" rel="nofollow" target="_blank">
        Miller-Osborn, J. and Grunzweig, J.. (2017, March 30). Trochilus and New MoonWind RATs Used In Attack Against Thai Organizations. Retrieved March 30, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-43">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html" name="scite-43" rel="nofollow" target="_blank">
        Singh, S. et al.. (2018, March 13). Iranian Threat Group Updates Tactics, Techniques and Procedures in Spear Phishing Campaign. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-44">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/another-potential-muddywater-campaign-uses-powershell-based-prb-backdoor/" name="scite-44" rel="nofollow" target="_blank">
        Villanueva, M., Co, M. (2018, June 14). Another Potential MuddyWater Campaign uses Powershell-based PRB-Backdoor. Retrieved July 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-45">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.f-secure.com/documents/996508/1030745/nanhaishu_whitepaper.pdf" name="scite-45" rel="nofollow" target="_blank">
        F-Secure Labs. (2016, July). NANHAISHU RATing the South China Sea. Retrieved July 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-46">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/05/navrat.html" name="scite-46" rel="nofollow" target="_blank">
        Mercer, W., Rascagneres, P. (2018, May 31). NavRAT Uses US-North Korea Summit As Decoy For Attacks In South Korea. Retrieved June 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-47">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/12/targeted-attack-in-middle-east-by-apt34.html" name="scite-47" rel="nofollow" target="_blank">
        Sardiwal, M, et al. (2017, December 7). New Targeted Attack in the Middle East by APT34, a Suspected Iranian Threat Group, Using CVE-2017-11882 Exploit. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-48">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/07/unit42-oilrig-uses-ismdoor-variant-possibly-linked-greenbug-threat-group/" name="scite-48" rel="nofollow" target="_blank">
        Falcone, R. and Lee, B. (2017, July 27). OilRig Uses ISMDoor Variant; Possibly Linked to Greenbug Threat Group. Retrieved January 8, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-49">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/02/unit42-oopsie-oilrig-uses-threedollars-deliver-new-trojan/" name="scite-49" rel="nofollow" target="_blank">
        Lee, B., Falcone, R. (2018, February 23). OopsIE! OilRig Uses ThreeDollars to Deliver New Trojan. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-50">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-oilrig-targets-technology-service-provider-government-agency-quadagent/" name="scite-50" rel="nofollow" target="_blank">
        Lee, B., Falcone, R. (2018, July 25). OilRig Targets Technology Service Provider and Government Agency with QUADAGENT. Retrieved August 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-51">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/09/unit42-oilrig-targets-middle-eastern-government-adds-evasion-techniques-oopsie/" name="scite-51" rel="nofollow" target="_blank">
        Falcone, R., et al. (2018, September 04). OilRig Targets a Middle Eastern Government and Adds Evasion Techniques to OopsIE. Retrieved September 24, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-52">
      <span class="scite-citation-text">
       <a class="external text" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" name="scite-52" rel="nofollow" target="_blank">
        Lunghi, D., et al. (2017, December). Untangling the Patchwork Cyberespionage Group. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-53">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/" name="scite-53" rel="nofollow" target="_blank">
        Meltzer, M, et al. (2018, June 07). Patchwork APT Group Targets US Think Tanks. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-54">
      <span class="scite-citation-text">
       <a class="external text" href="https://objective-see.com/blog/blog_0x25.html" name="scite-54" rel="nofollow" target="_blank">
        Patrick Wardle. (n.d.). Mac Malware of 2017. Retrieved September 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-55">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/n1nj4sec/pupy" name="scite-55" rel="nofollow" target="_blank">
        Nicolas Verdier. (n.d.). Retrieved January 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-56">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-rancor-targeted-attacks-south-east-asia-using-plaintee-ddkong-malware-families/" name="scite-56" rel="nofollow" target="_blank">
        Ash, B., et al. (2018, June 26). RANCOR: Targeted Attacks in South East Asia Using PLAINTEE and DDKONG Malware Families. Retrieved July 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-57">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-new-threat-actor-group-darkhydrus-targets-middle-east-government/" name="scite-57" rel="nofollow" target="_blank">
        Falcone, R., et al. (2018, July 27). New Threat Actor Group DarkHydrus Targets Middle East Government. Retrieved August 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-58">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/gold-dragon-widens-olympics-malware-attacks-gains-permanent-presence-on-victims-systems/" name="scite-58" rel="nofollow" target="_blank">
        Sherstobitoff, R., Saavedra-Morales, J. (2018, February 02). Gold Dragon Widens Olympics Malware Attacks, Gains Permanent Presence on Victims’ Systems. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-59">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.malwarebytes.com/threat-analysis/2016/08/smoke-loader-downloader-with-a-smokescreen-still-alive/" name="scite-59" rel="nofollow" target="_blank">
        Hasherezade. (2016, September 12). Smoke Loader – downloader with a smokescreen still alive. Retrieved March 20, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-60">
      <span class="scite-citation-text">
       <a class="external text" href="https://citizenlab.org/2016/05/stealth-falcon/" name="scite-60" rel="nofollow" target="_blank">
        Marczak, B. and Scott-Railton, J.. (2016, May 29). Keep Calm and (Don’t) Enable Macros: A New Threat Actor Targets UAE Dissidents. Retrieved June 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-61">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/us/threat-insight/post/apt-targets-financial-analysts" name="scite-61" rel="nofollow" target="_blank">
        Axel F. (2017, April 27). APT Targets Financial Analysts with CVE-2017-0199. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-62">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-165A" name="scite-62" rel="nofollow" target="_blank">
        US-CERT. (2018, June 14). MAR-10135536-12 – North Korean Trojan: TYPEFRAME. Retrieved July 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-63">
      <span class="scite-citation-text">
       <a class="external text" href="https://cloudblogs.microsoft.com/microsoftsecure/2016/03/22/new-feature-in-office-2016-can-block-macros-and-help-prevent-infection/" name="scite-63" rel="nofollow" target="_blank">
        Windows Defender Research. (2016, March 22). New feature in Office 2016 can block macros and help prevent infection. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-64">
      <span class="scite-citation-text">
       <a class="external text" href="https://arstechnica.com/information-technology/2017/03/hack-that-escapes-vm-by-exploiting-edge-browser-fetches-105000-at-pwn2own/" name="scite-64" rel="nofollow" target="_blank">
        Goodin, D. (2017, March 17). Virtual machine escape fetches $105,000 at Pwn2Own hacking contest - updated. Retrieved March 12, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-65">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.uperesia.com/analyzing-malicious-office-documents" name="scite-65" rel="nofollow" target="_blank">
        Felix. (2016, September). Analyzing Malicious Office Documents. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
