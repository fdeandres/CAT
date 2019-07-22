<div class="container-fluid">
 <h1>
  Windows Admin Shares
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Windows systems have hidden network shares that are accessible only to administrators and provide the ability for remote file copy and other administrative functions. Example network shares include
    <code>
     C$
    </code>
    ,
    <code>
     ADMIN$
    </code>
    , and
    <code>
     IPC$
    </code>
    .
   </p>
   <p>
    Adversaries may use this technique in conjunction with administrator-level
    <a href="https://attack.mitre.org/techniques/T1078">
     Valid Accounts
    </a>
    to remotely access a networked system over server message block (SMB)
    <span class="scite-citeref-number" data-reference="Wikipedia SMB" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://en.wikipedia.org/wiki/Server_Message_Block" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    to interact with systems using remote procedure calls (RPCs),
    <span class="scite-citeref-number" data-reference="TechNet RPC" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://technet.microsoft.com/en-us/library/cc787851.aspx" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    transfer files, and run transferred binaries through remote Execution. Example execution techniques that rely on authenticated sessions over SMB/RPC are
    <a href="https://attack.mitre.org/techniques/T1053">
     Scheduled Task
    </a>
    ,
    <a href="https://attack.mitre.org/techniques/T1035">
     Service Execution
    </a>
    , and
    <a href="https://attack.mitre.org/techniques/T1047">
     Windows Management Instrumentation
    </a>
    . Adversaries can also use NTLM hashes to access administrator shares on systems with
    <a href="https://attack.mitre.org/techniques/T1075">
     Pass the Hash
    </a>
    and certain configuration and patch levels.
    <span class="scite-citeref-number" data-reference="Microsoft Admin Shares" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="http://support.microsoft.com/kb/314984" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    The
    <a href="https://attack.mitre.org/software/S0039">
     Net
    </a>
    utility can be used to connect to Windows admin shares on remote systems using
    <code>
     net use
    </code>
    commands with valid credentials.
    <span class="scite-citeref-number" data-reference="Technet Net Use" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://technet.microsoft.com/bb490717.aspx" target="_blank">
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
      : T1077
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
      : Lateral Movement
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
       System Requirements:
      </span>
      File and printer sharing over SMB enabled; Host/network firewalls not blocking SMB ports between source and destination; Use of domain account in administrator group on remote system or default system admin account.
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Permissions Required:
      </span>
      Administrator
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
      Process use of network, Authentication logs, Process monitoring, Process command-line parameters
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
       CAPEC ID:
      </span>
      <a href="https://capec.mitre.org/data/definitions/561.html" target="_blank">
       CAPEC-561
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
     <a href="https://attack.mitre.org/groups/G0022">
      APT3
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0022">
       APT3
      </a>
      will copy files over to Windows Admin Shares (like ADMIN$) as part of lateral movement.
      <span class="scite-citeref-number" data-reference="Symantec Buckeye" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="http://www.symantec.com/connect/blogs/buckeye-cyberespionage-group-shifts-gaze-us-hong-kong" target="_blank">
         [5]
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
      used
      <a href="https://attack.mitre.org/software/S0039">
       Net
      </a>
      to use Windows' hidden network shares to copy their tools to remote machines for execution.
      <span class="scite-citeref-number" data-reference="Cybereason Cobalt Kitty 2017" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://cdn2.hubspot.net/hubfs/3354902/Cybereason%20Labs%20Analysis%20Operation%20Cobalt%20Kitty.pdf" target="_blank">
         [6]
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
      <a href="https://attack.mitre.org/software/S0089">
       BlackEnergy
      </a>
      has run a plug-in on a victim to spread through the local network by using
      <a href="https://attack.mitre.org/software/S0029">
       PsExec
      </a>
      and accessing admin shares.
      <span class="scite-citeref-number" data-reference="Securelist BlackEnergy Nov 2014" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://securelist.com/be2-custom-plugins-router-abuse-and-target-profiles/67353/" target="_blank">
         [7]
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
      can use Window admin shares (C$ and ADMIN$) for lateral movement.
      <span class="scite-citeref-number" data-reference="Cobalt Strike TTPs Dec 2017" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.cobaltstrike.com/downloads/reports/tacticstechniquesandprocedures.pdf" target="_blank">
         [8]
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
      uses net.exe to connect to network shares using
      <code>
       net use
      </code>
      commands with compromised credentials.
      <span class="scite-citeref-number" data-reference="Alperovitch 2014" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://blog.crowdstrike.com/deep-thought-chinese-targeting-national-security-think-tanks/" target="_blank">
         [9]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0038">
      Duqu
     </a>
    </td>
    <td>
     <p>
      Adversaries can instruct
      <a href="https://attack.mitre.org/software/S0038">
       Duqu
      </a>
      to spread laterally by copying itself to shares it has enumerated and for which it has obtained legitimate credentials (via keylogging or other means). The remote host is then infected by using the compromised credentials to schedule a task on remote machines that executes the malware.
      <span class="scite-citeref-number" data-reference="Symantec W32.Duqu" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/w32_duqu_the_precursor_to_the_next_stuxnet.pdf" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0367">
      Emotet
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0367">
       Emotet
      </a>
      leverages the Admin$ share for lateral movement once the local admin password has been brute forced.
      <span class="scite-citeref-number" data-reference="Malwarebytes Emotet Dec 2017" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://support.malwarebytes.com/docs/DOC-2295" target="_blank">
         [11]
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
      has attempted to map to C$ on enumerated hosts to test the scope of their current credentials/context.
      <span class="scite-citeref-number" data-reference="FireEye Know Your Enemy FIN8 Aug 2016" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" target="_blank">
         [12]
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
      actors have been known to copy files to the network shares of other computers to move laterally.
      <span class="scite-citeref-number" data-reference="Villeneuve et al 2014" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/wp-operation-ke3chang.pdf" target="_blank">
         [13]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="NCC Group APT15 Alive and Strong" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/" target="_blank">
         [14]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0236">
      Kwampirs
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0236">
       Kwampirs
      </a>
      copies itself over network shares to move laterally on a victim network.
      <span class="scite-citeref-number" data-reference="Symantec Orangeworm April 2018" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://www.symantec.com/blogs/threat-intelligence/orangeworm-targets-healthcare-us-europe-asia" target="_blank">
         [15]
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
      <a href="https://attack.mitre.org/groups/G0032">
       Lazarus Group
      </a>
      malware SierraAlfa accesses the
      <code>
       ADMIN$
      </code>
      share via SMB to conduct lateral movement.
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" target="_blank">
         [16]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster RATs" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-RAT-and-Staging-Report.pdf" target="_blank">
         [17]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0039">
      Net
     </a>
    </td>
    <td>
     <p>
      Lateral movement can be done with
      <a href="https://attack.mitre.org/software/S0039">
       Net
      </a>
      through
      <code>
       net use
      </code>
      commands to connect to the on remote systems.
      <span class="scite-citeref-number" data-reference="Savill 1999" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="http://windowsitpro.com/windows/netexe-reference" target="_blank">
         [18]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0056">
      Net Crawler
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0056">
       Net Crawler
      </a>
      uses Windows admin shares to establish authenticated sessions to remote systems over SMB as part of lateral movement.
      <span class="scite-citeref-number" data-reference="Cylance Cleaver" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf" target="_blank">
         [19]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0368">
      NotPetya
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0368">
       NotPetya
      </a>
      can use
      <a href="https://attack.mitre.org/software/S0029">
       PsExec
      </a>
      , which interacts with the
      <code>
       ADMIN$
      </code>
      network share to execute commands on remote systems.
      <span class="scite-citeref-number" data-reference="Talos Nyetya June 2017" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://blog.talosintelligence.com/2017/06/worldwide-ransomware-variant.html" target="_blank">
         [20]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT NotPetya 2017" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="https://www.us-cert.gov/ncas/alerts/TA17-181A" target="_blank">
         [21]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PsExec Russinovich" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="http://windowsitpro.com/systems-management/psexec" target="_blank">
         [22]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0365">
      Olympic Destroyer
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0365">
       Olympic Destroyer
      </a>
      uses
      <a href="https://attack.mitre.org/software/S0029">
       PsExec
      </a>
      to interact with the
      <code>
       ADMIN$
      </code>
      network share to execute commands on remote systems.
      <span class="scite-citeref-number" data-reference="Talos Olympic Destroyer 2018" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="https://blog.talosintelligence.com/2018/02/olympic-destroyer.html" target="_blank">
         [23]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PsExec Russinovich" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="http://windowsitpro.com/systems-management/psexec" target="_blank">
         [22]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0071">
      Orangeworm
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0071">
       Orangeworm
      </a>
      has copied its backdoor across open network shares, including ADMIN$, C$WINDOWS, D$WINDOWS, and E$WINDOWS.
      <span class="scite-citeref-number" data-reference="Symantec Orangeworm April 2018" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://www.symantec.com/blogs/threat-intelligence/orangeworm-targets-healthcare-us-europe-asia" target="_blank">
         [15]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0029">
      PsExec
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0029">
       PsExec
      </a>
      , a tool that has been used by adversaries, writes programs to the
      <code>
       ADMIN$
      </code>
      network share to execute commands on remote systems.
      <span class="scite-citeref-number" data-reference="PsExec Russinovich" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="http://windowsitpro.com/systems-management/psexec" target="_blank">
         [22]
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
      malware platform can use Windows admin shares to move laterally.
      <span class="scite-citeref-number" data-reference="Kaspersky Regin" id="scite-ref-24-a" onclick="scrollToRef('scite-24')">
       <sup>
        <a aria-describedby="qtip-23" data-hasqtip="23" href="https://securelist.com/files/2014/11/Kaspersky_Lab_whitepaper_Regin_platform_eng.pdf" target="_blank">
         [24]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0140">
      Shamoon
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0140">
       Shamoon
      </a>
      accesses network share(s), enables share access to the target device, copies an executable payload to the target system, and uses a
      <a href="https://attack.mitre.org/techniques/T1053">
       Scheduled Task
      </a>
      to execute the malware.
      <span class="scite-citeref-number" data-reference="FireEye Shamoon Nov 2016" id="scite-ref-25-a" onclick="scrollToRef('scite-25')">
       <sup>
        <a aria-describedby="qtip-24" data-hasqtip="24" href="https://www.fireeye.com/blog/threat-research/2016/11/fireeye_respondsto.html" target="_blank">
         [25]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0028">
      Threat Group-1314
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0028">
       Threat Group-1314
      </a>
      actors mapped network drives using
      <code>
       net use
      </code>
      .
      <span class="scite-citeref-number" data-reference="Dell TG-1314" id="scite-ref-26-a" onclick="scrollToRef('scite-26')">
       <sup>
        <a aria-describedby="qtip-25" data-hasqtip="25" href="http://www.secureworks.com/resources/blog/living-off-the-land/" target="_blank">
         [26]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0010">
      Turla
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0010">
       Turla
      </a>
      used
      <code>
       net use
      </code>
      commands to connect to lateral systems within a network.
      <span class="scite-citeref-number" data-reference="Kaspersky Turla" id="scite-ref-27-a" onclick="scrollToRef('scite-27')">
       <sup>
        <a aria-describedby="qtip-26" data-hasqtip="26" href="https://securelist.com/the-epic-turla-operation/65545/" target="_blank">
         [27]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0350">
      zwShell
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0350">
       zwShell
      </a>
      has been copied over network shares to move laterally.
      <span class="scite-citeref-number" data-reference="McAfee Night Dragon" id="scite-ref-28-a" onclick="scrollToRef('scite-28')">
       <sup>
        <a aria-describedby="qtip-27" data-hasqtip="27" href="https://securingtomorrow.mcafee.com/wp-content/uploads/2011/02/McAfee_NightDragon_wp_draft_to_customersv1-1.pdf" target="_blank">
         [28]
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
  Do not reuse local administrator account passwords across systems. Ensure password complexity and uniqueness such that the passwords cannot be cracked or guessed. Deny remote use of local admin credentials to log into systems. Do not allow domain user accounts to be in the local Administrators group multiple systems.
 </p>
 <p>
  Identify unnecessary system utilities or potentially malicious software that may be used to leverage SMB and the Windows admin shares, and audit and/or block them by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-29-a">
   <sup>
    <a aria-describedby="qtip-28" data-hasqtip="28" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [29]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-30-a">
   <sup>
    <a aria-describedby="qtip-29" data-hasqtip="29" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [30]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-31-a">
   <sup>
    <a aria-describedby="qtip-30" data-hasqtip="30" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [31]
    </a>
   </sup>
  </span>
  or Software Restriction Policies
  <span class="scite-citeref-number" data-reference="Corio 2008" id="scite-ref-32-a">
   <sup>
    <a aria-describedby="qtip-31" data-hasqtip="31" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" target="_blank">
     [32]
    </a>
   </sup>
  </span>
  where appropriate.
  <span class="scite-citeref-number" data-reference="TechNet Applocker vs SRP" id="scite-ref-33-a">
   <sup>
    <a aria-describedby="qtip-32" data-hasqtip="32" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" target="_blank">
     [33]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Ensure that proper logging of accounts used to log into systems is turned on and centrally collected. Windows logging is able to collect success/failure for accounts that may be used to move laterally and can be collected using tools such as Windows Event Forwarding.
  <span class="scite-citeref-number" data-reference="Lateral Movement Payne" id="scite-ref-34-a">
   <sup>
    <a aria-describedby="qtip-33" data-hasqtip="33" href="http://blogs.technet.com/b/jepayne/archive/2015/11/27/tracking-lateral-movement-part-one-special-groups-and-specific-service-accounts.aspx" target="_blank">
     [34]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Windows Event Forwarding Payne" id="scite-ref-35-a">
   <sup>
    <a aria-describedby="qtip-34" data-hasqtip="34" href="http://blogs.technet.com/b/jepayne/archive/2015/11/24/monitoring-what-matters-windows-event-forwarding-for-everyone-even-if-you-already-have-a-siem.aspx" target="_blank">
     [35]
    </a>
   </sup>
  </span>
  Monitor remote login events and associated SMB activity for file transfers and remote process execution. Monitor the actions of remote users who connect to administrative shares. Monitor for use of tools and commands to connect to remote shares, such as
  <a href="https://attack.mitre.org/software/S0039">
   Net
  </a>
  , on the command-line interface and Discovery techniques that could be used to find remotely accessible systems.
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
       <a class="external text" href="https://en.wikipedia.org/wiki/Server_Message_Block" name="scite-1" rel="nofollow" target="_blank">
        Wikipedia. (2016, June 12). Server Message Block. Retrieved June 12, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/cc787851.aspx" name="scite-2" rel="nofollow" target="_blank">
        Microsoft. (2003, March 28). What Is RPC?. Retrieved June 12, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="http://support.microsoft.com/kb/314984" name="scite-3" rel="nofollow" target="_blank">
        Microsoft. (n.d.). How to create and delete hidden or administrative shares on client computers. Retrieved November 20, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/bb490717.aspx" name="scite-4" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Net Use. Retrieved November 25, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/connect/blogs/buckeye-cyberespionage-group-shifts-gaze-us-hong-kong" name="scite-5" rel="nofollow" target="_blank">
        Symantec Security Response. (2016, September 6). Buckeye cyberespionage group shifts gaze from US to Hong Kong. Retrieved September 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://cdn2.hubspot.net/hubfs/3354902/Cybereason%20Labs%20Analysis%20Operation%20Cobalt%20Kitty.pdf" name="scite-6" rel="nofollow" target="_blank">
        Dahan, A. (2017). Operation Cobalt Kitty. Retrieved December 27, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/be2-custom-plugins-router-abuse-and-target-profiles/67353/" name="scite-7" rel="nofollow" target="_blank">
        Baumgartner, K. and Garnaeva, M.. (2014, November 3). BE2 custom plugins, router abuse, and target profiles. Retrieved March 24, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cobaltstrike.com/downloads/reports/tacticstechniquesandprocedures.pdf" name="scite-8" rel="nofollow" target="_blank">
        Cobalt Strike. (2017, December 8). Tactics, Techniques, and Procedures. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.crowdstrike.com/deep-thought-chinese-targeting-national-security-think-tanks/" name="scite-9" rel="nofollow" target="_blank">
        Alperovitch, D. (2014, July 7). Deep in Thought: Chinese Targeting of National Security Think Tanks. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/w32_duqu_the_precursor_to_the_next_stuxnet.pdf" name="scite-10" rel="nofollow" target="_blank">
        Symantec Security Response. (2011, November). W32.Duqu: The precursor to the next Stuxnet. Retrieved September 17, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://support.malwarebytes.com/docs/DOC-2295" name="scite-11" rel="nofollow" target="_blank">
        Smith, A.. (2017, December 22). Protect your network from Emotet Trojan with Malwarebytes Endpoint Security. Retrieved January 17, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" name="scite-12" rel="nofollow" target="_blank">
        Elovitz, S. &amp; Ahl, I. (2016, August 18). Know Your Enemy:  New Financially-Motivated &amp; Spear-Phishing Group. Retrieved February 26, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/wp-operation-ke3chang.pdf" name="scite-13" rel="nofollow" target="_blank">
        Villeneuve, N., Bennett, J. T., Moran, N., Haq, T., Scott, M., &amp; Geers, K. (2014). OPERATION “KE3CHANG”: Targeted Attacks Against Ministries of Foreign Affairs. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/" name="scite-14" rel="nofollow" target="_blank">
        Smallridge, R. (2018, March 10). APT15 is alive and strong: An analysis of RoyalCli and RoyalDNS. Retrieved April 4, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/orangeworm-targets-healthcare-us-europe-asia" name="scite-15" rel="nofollow" target="_blank">
        Symantec Security Response Attack Investigation Team. (2018, April 23). New Orangeworm attack group targets the healthcare sector in the U.S., Europe, and Asia. Retrieved May 8, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" name="scite-16" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Unraveling the Long Thread of the Sony Attack. Retrieved February 25, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-RAT-and-Staging-Report.pdf" name="scite-17" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Remote Administration Tools &amp; Content Staging Malware Report. Retrieved March 16, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="http://windowsitpro.com/windows/netexe-reference" name="scite-18" rel="nofollow" target="_blank">
        Savill, J. (1999, March 4). Net.exe reference. Retrieved September 22, 2015.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="19.5">
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf" name="scite-19" rel="nofollow" target="_blank">
        Cylance. (2014, December). Operation Cleaver. Retrieved September 14, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2017/06/worldwide-ransomware-variant.html" name="scite-20" rel="nofollow" target="_blank">
        Chiu, A. (2016, June 27). New Ransomware Variant "Nyetya" Compromises Systems Worldwide. Retrieved March 26, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA17-181A" name="scite-21" rel="nofollow" target="_blank">
        US-CERT. (2017, July 1). Alert (TA17-181A): Petya Ransomware. Retrieved March 15, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="http://windowsitpro.com/systems-management/psexec" name="scite-22" rel="nofollow" target="_blank">
        Russinovich, M. (2004, June 28). PsExec. Retrieved December 17, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-23">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/02/olympic-destroyer.html" name="scite-23" rel="nofollow" target="_blank">
        Mercer, W. and Rascagneres, P. (2018, February 12). Olympic Destroyer Takes Aim At Winter Olympics. Retrieved March 14, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-24">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/files/2014/11/Kaspersky_Lab_whitepaper_Regin_platform_eng.pdf" name="scite-24" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2014, November 24). THE REGIN PLATFORM NATION-STATE OWNAGE OF GSM NETWORKS. Retrieved December 1, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-25">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2016/11/fireeye_respondsto.html" name="scite-25" rel="nofollow" target="_blank">
        FireEye. (2016, November 30). FireEye Responds to Wave of Destructive Cyber Attacks in Gulf Region. Retrieved January 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-26">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.secureworks.com/resources/blog/living-off-the-land/" name="scite-26" rel="nofollow" target="_blank">
        Dell SecureWorks Counter Threat Unit Special Operations Team. (2015, May 28). Living off the Land. Retrieved January 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-27">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/the-epic-turla-operation/65545/" name="scite-27" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2014, August 7). The Epic Turla Operation: Solving some of the mysteries of Snake/Uroburos. Retrieved December 11, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-28">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/wp-content/uploads/2011/02/McAfee_NightDragon_wp_draft_to_customersv1-1.pdf" name="scite-28" rel="nofollow" target="_blank">
        McAfee® Foundstone® Professional Services and McAfee Labs™. (2011, February 10). Global Energy Cyberattacks: “Night Dragon”. Retrieved February 19, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-29">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-29" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-30">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-30" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-31">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-31" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-32">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" name="scite-32" rel="nofollow" target="_blank">
        Corio, C., &amp; Sayana, D. P. (2008, June). Application Lockdown with Software Restriction Policies. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-33">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" name="scite-33" rel="nofollow" target="_blank">
        Microsoft. (2012, June 27). Using Software Restriction Policies and AppLocker Policies. Retrieved April 7, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-34">
      <span class="scite-citation-text">
       <a class="external text" href="http://blogs.technet.com/b/jepayne/archive/2015/11/27/tracking-lateral-movement-part-one-special-groups-and-specific-service-accounts.aspx" name="scite-34" rel="nofollow" target="_blank">
        Payne, J. (2015, November 26). Tracking Lateral Movement Part One - Special Groups and Specific Service Accounts. Retrieved February 1, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-35">
      <span class="scite-citation-text">
       <a class="external text" href="http://blogs.technet.com/b/jepayne/archive/2015/11/24/monitoring-what-matters-windows-event-forwarding-for-everyone-even-if-you-already-have-a-siem.aspx" name="scite-35" rel="nofollow" target="_blank">
        Payne, J. (2015, November 23). Monitoring what matters - Windows Event Forwarding for everyone (even if you already have a SIEM.). Retrieved February 1, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
