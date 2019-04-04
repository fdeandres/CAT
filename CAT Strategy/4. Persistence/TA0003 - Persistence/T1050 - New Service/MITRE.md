<div class="container-fluid">
 <h1>
  New Service
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    When operating systems boot up, they can start programs or applications called services that perform background system functions.
    <span class="scite-citeref-number" data-reference="TechNet Services" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://technet.microsoft.com/en-us/library/cc772408.aspx" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    A service's configuration information, including the file path to the service's executable, is stored in the Windows Registry.
   </p>
   <p>
    Adversaries may install a new service that can be configured to execute at startup by using utilities to interact with services or by directly modifying the Registry. The service name may be disguised by using a name from a related operating system or benign software with
    <a href="https://attack.mitre.org/techniques/T1036">
     Masquerading
    </a>
    . Services may be created with administrator privileges but are executed under SYSTEM privileges, so an adversary may also use a service to escalate privileges from administrator to SYSTEM. Adversaries may also directly start services through
    <a href="https://attack.mitre.org/techniques/T1035">
     Service Execution
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
      : T1050
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
      : Persistence, Privilege Escalation
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
       Effective Permissions:
      </span>
      SYSTEM
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      Windows Registry, Process monitoring, Process command-line parameters, Windows event logs
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
      <a href="https://capec.mitre.org/data/definitions/550.html" target="_blank">
       CAPEC-550
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
      Pedro Harrison
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
     <a href="https://attack.mitre.org/groups/G0022">
      APT3
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0022">
       APT3
      </a>
      has a tool that creates a new service for persistence.
      <span class="scite-citeref-number" data-reference="FireEye Operation Double Tap" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.fireeye.com/blog/threat-research/2014/11/operation_doubletap.html" target="_blank">
         [2]
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
      creates a Windows service to establish persistence.
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
     <a href="https://attack.mitre.org/software/S0089">
      BlackEnergy
     </a>
    </td>
    <td>
     <p>
      One variant of
      <a href="https://attack.mitre.org/software/S0089">
       BlackEnergy
      </a>
      creates a new service using either a hard-coded or randomly generated name.
      <span class="scite-citeref-number" data-reference="F-Secure BlackEnergy 2014" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.f-secure.com/documents/996508/1030745/blackenergy_whitepaper.pdf" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0204">
      Briba
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0204">
       Briba
      </a>
      installs a service pointing to a malicious DLL dropped to disk.
      <span class="scite-citeref-number" data-reference="Symantec Briba May 2012" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051515-2843-99" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0008">
      Carbanak
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0008">
       Carbanak
      </a>
      malware installs itself as a service to provide persistence and SYSTEM privileges.
      <span class="scite-citeref-number" data-reference="Kaspersky Carbanak" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08064518/Carbanak_APT_eng.pdf" target="_blank">
         [6]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0261">
      Catchamas
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0261">
       Catchamas
      </a>
      adds a new service named NetAdapter to establish persistence.
      <span class="scite-citeref-number" data-reference="Symantec Catchamas April 2018" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www-west.symantec.com/content/symantec/english/en/security-center/writeup.html/2018-040209-1742-99" target="_blank">
         [7]
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
      has created new services to establish persistence.
      <span class="scite-citeref-number" data-reference="Group IB Cobalt Aug 2017" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.group-ib.com/blog/cobalt" target="_blank">
         [8]
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
      can install a new service.
      <span class="scite-citeref-number" data-reference="Cobalt Strike TTPs Dec 2017" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.cobaltstrike.com/downloads/reports/tacticstechniquesandprocedures.pdf" target="_blank">
         [9]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0050">
      CosmicDuke
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0050">
       CosmicDuke
      </a>
      uses Windows services typically named "javamtsup" for persistence.
      <span class="scite-citeref-number" data-reference="F-Secure Cosmicduke" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www.f-secure.com/documents/996508/1030745/cosmicduke_whitepaper.pdf" target="_blank">
         [10]
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
      One persistence mechanism used by
      <a href="https://attack.mitre.org/software/S0046">
       CozyCar
      </a>
      is to register itself as a Windows service.
      <span class="scite-citeref-number" data-reference="F-Secure CozyDuke" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://www.f-secure.com/documents/996508/1030745/CozyDuke" target="_blank">
         [11]
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
      <a href="https://attack.mitre.org/software/S0038">
       Duqu
      </a>
      creates a new service that loads a malicious driver when the system starts. When Duqu is active, the operating system believes that the driver is legitimate, as it has been signed with a valid private key.
      <span class="scite-citeref-number" data-reference="Symantec W32.Duqu" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/w32_duqu_the_precursor_to_the_next_stuxnet.pdf" target="_blank">
         [12]
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
      registers itself as a service by adding several Registry keys.
      <span class="scite-citeref-number" data-reference="Symantec Dyre June 2015" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/dyre-emerging-threat.pdf" target="_blank">
         [13]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0081">
      Elise
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0081">
       Elise
      </a>
      configures itself as a service.
      <span class="scite-citeref-number" data-reference="Lotus Blossom Jun 2015" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://www.paloaltonetworks.com/resources/research/unit42-operation-lotus-blossom.html" target="_blank">
         [14]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0082">
      Emissary
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0082">
       Emissary
      </a>
      is capable of configuring itself as a service.
      <span class="scite-citeref-number" data-reference="Emissary Trojan Feb 2016" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="http://researchcenter.paloaltonetworks.com/2016/02/emissary-trojan-changelog-did-operation-lotus-blossom-cause-it-to-evolve/" target="_blank">
         [15]
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
      created new Windows services and added them to the startup directories for persistence.
      <span class="scite-citeref-number" data-reference="FireEye FIN7 Aug 2018" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="https://www.fireeye.com/blog/threat-research/2018/08/fin7-pursuing-an-enigmatic-and-evasive-global-criminal-operation.html" target="_blank">
         [16]
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
      creates a new Windows service with the malicious executable for persistence.
      <span class="scite-citeref-number" data-reference="FinFisher Citation" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="http://www.finfisher.com/FinFisher/index.html" target="_blank">
         [17]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Microsoft FinFisher March 2018" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="https://cloudblogs.microsoft.com/microsoftsecure/2018/03/01/finfisher-exposed-a-researchers-tale-of-defeating-traps-tricks-and-complex-virtual-machines/" target="_blank">
         [18]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0071">
      hcdLoader
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0071">
       hcdLoader
      </a>
      installs itself as a service for persistence.
      <span class="scite-citeref-number" data-reference="Dell Lateral Movement" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="http://www.secureworks.com/resources/blog/where-you-at-indicators-of-lateral-movement-using-at-exe-on-windows-7-systems/" target="_blank">
         [19]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="ThreatStream Evasion Analysis" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://www.threatstream.com/blog/evasive-maneuvers-the-wekby-group-attempts-to-evade-analysis-via-custom-rop" target="_blank">
         [20]
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
      creates new services to establish persistence.
      <span class="scite-citeref-number" data-reference="Symantec Trojan.Hydraq Jan 2010" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="https://www.symantec.com/connect/blogs/trojanhydraq-incident" target="_blank">
         [21]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Symantec Hydraq Jan 2010" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="https://www.symantec.com/security_response/writeup.jsp?docid=2010-011114-1830-99" target="_blank">
         [22]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Symantec Hydraq Persistence Jan 2010" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="https://www.symantec.com/connect/blogs/how-trojanhydraq-stays-your-computer" target="_blank">
         [23]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0259">
      InnaputRAT
     </a>
    </td>
    <td>
     <p>
      Some
      <a href="https://attack.mitre.org/software/S0259">
       InnaputRAT
      </a>
      variants create a new Windows service to establish persistence.
      <span class="scite-citeref-number" data-reference="ASERT InnaputRAT April 2018" id="scite-ref-24-a" onclick="scrollToRef('scite-24')">
       <sup>
        <a aria-describedby="qtip-23" data-hasqtip="23" href="https://asert.arbornetworks.com/innaput-actors-utilize-remote-access-trojan-since-2016-presumably-targeting-victim-files/" target="_blank">
         [24]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0044">
      JHUHUGIT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0044">
       JHUHUGIT
      </a>
      has registered itself as a service to establish persistence.
      <span class="scite-citeref-number" data-reference="ESET Sednit Part 1" id="scite-ref-25-a" onclick="scrollToRef('scite-25')">
       <sup>
        <a aria-describedby="qtip-24" data-hasqtip="24" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part1.pdf" target="_blank">
         [25]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0265">
      Kazuar
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0265">
       Kazuar
      </a>
      can install itself as a new service.
      <span class="scite-citeref-number" data-reference="Unit 42 Kazuar May 2017" id="scite-ref-26-a" onclick="scrollToRef('scite-26')">
       <sup>
        <a aria-describedby="qtip-25" data-hasqtip="25" href="https://researchcenter.paloaltonetworks.com/2017/05/unit42-kazuar-multiplatform-espionage-backdoor-api-access/" target="_blank">
         [26]
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
      backdoor RoyalDNS established persistence through adding a service called
      <code>
       Nwsapagent
      </code>
      .
      <span class="scite-citeref-number" data-reference="NCC Group APT15 Alive and Strong" id="scite-ref-27-a" onclick="scrollToRef('scite-27')">
       <sup>
        <a aria-describedby="qtip-26" data-hasqtip="26" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/" target="_blank">
         [27]
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
      creates a new service named WmiApSrvEx to establish persistence.
      <span class="scite-citeref-number" data-reference="Symantec Orangeworm April 2018" id="scite-ref-28-a" onclick="scrollToRef('scite-28')">
       <sup>
        <a aria-describedby="qtip-27" data-hasqtip="27" href="https://www.symantec.com/blogs/threat-intelligence/orangeworm-targets-healthcare-us-europe-asia" target="_blank">
         [28]
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
      Several
      <a href="https://attack.mitre.org/groups/G0032">
       Lazarus Group
      </a>
      malware families install themselves as new services on victims.
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster" id="scite-ref-29-a" onclick="scrollToRef('scite-29')">
       <sup>
        <a aria-describedby="qtip-28" data-hasqtip="28" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" target="_blank">
         [29]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster Destructive Malware" id="scite-ref-30-a" onclick="scrollToRef('scite-30')">
       <sup>
        <a aria-describedby="qtip-29" data-hasqtip="29" href="https://operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Destructive-Malware-Report.pdf" target="_blank">
         [30]
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
      installs itself as a new service with automatic startup to establish persistence. The service checks every 60 seconds to determine if the malware is running; if not, it will spawn a new instance.
      <span class="scite-citeref-number" data-reference="Palo Alto MoonWind March 2017" id="scite-ref-31-a" onclick="scrollToRef('scite-31')">
       <sup>
        <a aria-describedby="qtip-30" data-hasqtip="30" href="http://researchcenter.paloaltonetworks.com/2017/03/unit42-trochilus-rat-new-moonwind-rat-used-attack-thai-utility-organizations/" target="_blank">
         [31]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0205">
      Naid
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0205">
       Naid
      </a>
      creates a new service to establish.
      <span class="scite-citeref-number" data-reference="Symantec Naid June 2012" id="scite-ref-32-a" onclick="scrollToRef('scite-32')">
       <sup>
        <a aria-describedby="qtip-31" data-hasqtip="31" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-061518-4639-99" target="_blank">
         [32]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0210">
      Nerex
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0210">
       Nerex
      </a>
      creates a Registry subkey that registers a new service.
      <span class="scite-citeref-number" data-reference="Symantec Nerex May 2012" id="scite-ref-33-a" onclick="scrollToRef('scite-33')">
       <sup>
        <a aria-describedby="qtip-32" data-hasqtip="32" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051515-3445-99" target="_blank">
         [33]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0118">
      Nidiran
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0118">
       Nidiran
      </a>
      can create a new service named msamger (Microsoft Security Accounts Manager).
      <span class="scite-citeref-number" data-reference="Symantec Backdoor.Nidiran" id="scite-ref-34-a" onclick="scrollToRef('scite-34')">
       <sup>
        <a aria-describedby="qtip-33" data-hasqtip="33" href="https://www.symantec.com/security_response/writeup.jsp?docid=2015-120123-5521-99" target="_blank">
         [34]
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
      can be added as a service to establish persistence.
      <span class="scite-citeref-number" data-reference="Lastline PlugX Analysis" id="scite-ref-35-a" onclick="scrollToRef('scite-35')">
       <sup>
        <a aria-describedby="qtip-34" data-hasqtip="34" href="http://labs.lastline.com/an-analysis-of-plugx" target="_blank">
         [35]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PWC Cloud Hopper Technical Annex April 2017" id="scite-ref-36-a" onclick="scrollToRef('scite-36')">
       <sup>
        <a aria-describedby="qtip-35" data-hasqtip="35" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" target="_blank">
         [36]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye APT10 April 2017" id="scite-ref-37-a" onclick="scrollToRef('scite-37')">
       <sup>
        <a aria-describedby="qtip-36" data-hasqtip="36" href="https://www.fireeye.com/blog/threat-research/2017/04/apt10_menupass_grou.html" target="_blank">
         [37]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Proofpoint ZeroT Feb 2017" id="scite-ref-38-a" onclick="scrollToRef('scite-38')">
       <sup>
        <a aria-describedby="qtip-37" data-hasqtip="37" href="https://www.proofpoint.com/us/threat-insight/post/APT-targets-russia-belarus-zerot-plugx" target="_blank">
         [38]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0012">
      PoisonIvy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0012">
       PoisonIvy
      </a>
      creates a Registry subkey that registers a new service.
      <span class="scite-citeref-number" data-reference="Symantec Darkmoon Aug 2005" id="scite-ref-39-a" onclick="scrollToRef('scite-39')">
       <sup>
        <a aria-describedby="qtip-38" data-hasqtip="38" href="https://www.symantec.com/security_response/writeup.jsp?docid=2005-081910-3934-99" target="_blank">
         [39]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0169">
      RawPOS
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0169">
       RawPOS
      </a>
      installs itself as a service to maintain persistence.
      <span class="scite-citeref-number" data-reference="Kroll RawPOS Jan 2017" id="scite-ref-40-a" onclick="scrollToRef('scite-40')">
       <sup>
        <a aria-describedby="qtip-39" data-hasqtip="39" href="http://www.kroll.com/CMSPages/GetAzureFile.aspx?path=~%5Cmedia%5Cfiles%5Cintelligence-center%5Ckroll_malware-analysis-report.pdf&amp;hash=d5b5d2697118f30374b954f28a08c0ba69836c0ffd99566aa7ec62d1fc72b105" target="_blank">
         [40]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="TrendMicro RawPOS April 2015" id="scite-ref-41-a" onclick="scrollToRef('scite-41')">
       <sup>
        <a aria-describedby="qtip-40" data-hasqtip="40" href="http://sjc1-te-ftp.trendmicro.com/images/tex/pdf/RawPOS%20Technical%20Brief.pdf" target="_blank">
         [41]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Mandiant FIN5 GrrCON Oct 2016" id="scite-ref-42-a" onclick="scrollToRef('scite-42')">
       <sup>
        <a aria-describedby="qtip-41" data-hasqtip="41" href="https://www.youtube.com/watch?v=fevGZs0EQu8" target="_blank">
         [42]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0172">
      Reaver
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0172">
       Reaver
      </a>
      installs itself as a new service.
      <span class="scite-citeref-number" data-reference="Palo Alto Reaver Nov 2017" id="scite-ref-43-a" onclick="scrollToRef('scite-43')">
       <sup>
        <a aria-describedby="qtip-42" data-hasqtip="42" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-new-malware-with-ties-to-sunorcal-discovered/" target="_blank">
         [43]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0074">
      Sakula
     </a>
    </td>
    <td>
     <p>
      Some
      <a href="https://attack.mitre.org/software/S0074">
       Sakula
      </a>
      samples install themselves as services for persistence by calling WinExec with the
      <code>
       net start
      </code>
      argument.
      <span class="scite-citeref-number" data-reference="Dell Sakula" id="scite-ref-44-a" onclick="scrollToRef('scite-44')">
       <sup>
        <a aria-describedby="qtip-43" data-hasqtip="43" href="http://www.secureworks.com/cyber-threat-intelligence/threats/sakula-malware-family/" target="_blank">
         [44]
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
      creates a new service named "ntssrv" to execute the payload.
      <span class="scite-citeref-number" data-reference="Palo Alto Shamoon Nov 2016" id="scite-ref-45-a" onclick="scrollToRef('scite-45')">
       <sup>
        <a aria-describedby="qtip-44" data-hasqtip="44" href="http://researchcenter.paloaltonetworks.com/2016/11/unit42-shamoon-2-return-disttrack-wiper/" target="_blank">
         [45]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0142">
      StreamEx
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0142">
       StreamEx
      </a>
      establishes persistence by installing a new service pointing to its DLL and setting the service to auto-start.
      <span class="scite-citeref-number" data-reference="Cylance Shell Crew Feb 2017" id="scite-ref-46-a" onclick="scrollToRef('scite-46')">
       <sup>
        <a aria-describedby="qtip-45" data-hasqtip="45" href="https://www.cylance.com/shell-crew-variants-continue-to-fly-under-big-avs-radar" target="_blank">
         [46]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0164">
      TDTESS
     </a>
    </td>
    <td>
     <p>
      If running as administrator,
      <a href="https://attack.mitre.org/software/S0164">
       TDTESS
      </a>
      installs itself as a new service named bmwappushservice to establish persistence.
      <span class="scite-citeref-number" data-reference="ClearSky Wilted Tulip July 2017" id="scite-ref-47-a" onclick="scrollToRef('scite-47')">
       <sup>
        <a aria-describedby="qtip-46" data-hasqtip="46" href="http://www.clearskysec.com/wp-content/uploads/2017/07/Operation_Wilted_Tulip.pdf" target="_blank">
         [47]
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
      A
      <a href="https://attack.mitre.org/groups/G0027">
       Threat Group-3390
      </a>
      tool can create a new service, naming it after the config information, to gain persistence.
      <span class="scite-citeref-number" data-reference="Nccgroup Emissary Panda May 2018" id="scite-ref-48-a" onclick="scrollToRef('scite-48')">
       <sup>
        <a aria-describedby="qtip-47" data-hasqtip="47" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/may/emissary-panda-a-potential-new-malicious-tool/" target="_blank">
         [48]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0004">
      TinyZBot
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0004">
       TinyZBot
      </a>
      can install as a Windows service for persistence.
      <span class="scite-citeref-number" data-reference="Cylance Cleaver" id="scite-ref-49-a" onclick="scrollToRef('scite-49')">
       <sup>
        <a aria-describedby="qtip-48" data-hasqtip="48" href="https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf" target="_blank">
         [49]
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
      variants can add malicious DLL modules as new services.
      <span class="scite-citeref-number" data-reference="US-CERT TYPEFRAME June 2018" id="scite-ref-50-a" onclick="scrollToRef('scite-50')">
       <sup>
        <a aria-describedby="qtip-49" data-hasqtip="49" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-165A" target="_blank">
         [50]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0180">
      Volgmer
     </a>
    </td>
    <td>
     <p>
      Some
      <a href="https://attack.mitre.org/software/S0180">
       Volgmer
      </a>
      variants install .dll files as services with names generated by a list of hard-coded strings.
      <span class="scite-citeref-number" data-reference="US-CERT Volgmer 2 Nov 2017" id="scite-ref-51-a" onclick="scrollToRef('scite-51')">
       <sup>
        <a aria-describedby="qtip-50" data-hasqtip="50" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-D_WHITE_S508C.PDF" target="_blank">
         [51]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Symantec Volgmer Aug 2014" id="scite-ref-52-a" onclick="scrollToRef('scite-52')">
       <sup>
        <a aria-describedby="qtip-51" data-hasqtip="51" href="https://www.symantec.com/security-center/writeup/2014-081811-3237-99?tabid=2" target="_blank">
         [52]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0206">
      Wiarp
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0206">
       Wiarp
      </a>
      creates a backdoor through which remote attackers can create a service.
      <span class="scite-citeref-number" data-reference="Symantec Wiarp May 2012" id="scite-ref-53-a" onclick="scrollToRef('scite-53')">
       <sup>
        <a aria-describedby="qtip-52" data-hasqtip="52" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051606-1005-99" target="_blank">
         [53]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0176">
      Wingbird
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0176">
       Wingbird
      </a>
      uses services.exe to register a new autostart service named "Audit Service" using a copy of the local lsass.exe file.
      <span class="scite-citeref-number" data-reference="Microsoft SIR Vol 21" id="scite-ref-54-a" onclick="scrollToRef('scite-54')">
       <sup>
        <a aria-describedby="qtip-53" data-hasqtip="53" href="http://download.microsoft.com/download/E/B/0/EB0F50CC-989C-4B66-B7F6-68CD3DC90DE3/Microsoft_Security_Intelligence_Report_Volume_21_English.pdf" target="_blank">
         [54]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Microsoft Wingbird Nov 2017" id="scite-ref-55-a" onclick="scrollToRef('scite-55')">
       <sup>
        <a aria-describedby="qtip-54" data-hasqtip="54" href="https://www.microsoft.com/wdsi/threats/malware-encyclopedia-description?Name=Backdoor:Win32/Wingbird.A!dha" target="_blank">
         [55]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0141">
      Winnti
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0141">
       Winnti
      </a>
      sets its DLL file as a new service in the Registry to establish persistence.
      <span class="scite-citeref-number" data-reference="Microsoft Winnti Jan 2017" id="scite-ref-56-a" onclick="scrollToRef('scite-56')">
       <sup>
        <a aria-describedby="qtip-55" data-hasqtip="55" href="https://blogs.technet.microsoft.com/mmpc/2017/01/25/detecting-threat-actors-in-recent-german-industrial-attacks-with-windows-defender-atp/" target="_blank">
         [56]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0230">
      ZeroT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0230">
       ZeroT
      </a>
      can add a new service to ensure
      <a href="https://attack.mitre.org/software/S0013">
       PlugX
      </a>
      persists on the system when delivered as another payload onto the system.
      <span class="scite-citeref-number" data-reference="Proofpoint ZeroT Feb 2017" id="scite-ref-38-a" onclick="scrollToRef('scite-38')">
       <sup>
        <a aria-describedby="qtip-37" data-hasqtip="37" href="https://www.proofpoint.com/us/threat-insight/post/APT-targets-russia-belarus-zerot-plugx" target="_blank">
         [38]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0086">
      ZLib
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0086">
       ZLib
      </a>
      creates Registry keys to allow itself to run as various services.
      <span class="scite-citeref-number" data-reference="Cylance Dust Storm" id="scite-ref-57-a" onclick="scrollToRef('scite-57')">
       <sup>
        <a aria-describedby="qtip-56" data-hasqtip="56" href="https://www.cylance.com/content/dam/cylance/pdfs/reports/Op_Dust_Storm_Report.pdf" target="_blank">
         [57]
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
  Limit privileges of user accounts and remediate Privilege Escalation vectors so only  authorized administrators can create new services.
 </p>
 <p>
  Identify and block unnecessary system utilities or potentially malicious software that may be used to create services by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-58-a">
   <sup>
    <a aria-describedby="qtip-57" data-hasqtip="57" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [58]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-59-a">
   <sup>
    <a aria-describedby="qtip-58" data-hasqtip="58" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [59]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-60-a">
   <sup>
    <a aria-describedby="qtip-59" data-hasqtip="59" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [60]
    </a>
   </sup>
  </span>
  or Software Restriction Policies
  <span class="scite-citeref-number" data-reference="Corio 2008" id="scite-ref-61-a">
   <sup>
    <a aria-describedby="qtip-60" data-hasqtip="60" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" target="_blank">
     [61]
    </a>
   </sup>
  </span>
  where appropriate.
  <span class="scite-citeref-number" data-reference="TechNet Applocker vs SRP" id="scite-ref-62-a">
   <sup>
    <a aria-describedby="qtip-61" data-hasqtip="61" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" target="_blank">
     [62]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor service creation through changes in the Registry and common utilities using command-line invocation. Creation of new services may generate an alterable event (ex: Event ID 4697 and/or 7045
  <span class="scite-citeref-number" data-reference="Microsoft 4697 APR 2017" id="scite-ref-63-a">
   <sup>
    <a aria-describedby="qtip-62" data-hasqtip="62" href="https://docs.microsoft.com/windows/security/threat-protection/auditing/event-4697" target="_blank">
     [63]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Microsoft Windows Event Forwarding FEB 2018" id="scite-ref-64-a">
   <sup>
    <a aria-describedby="qtip-63" data-hasqtip="63" href="https://docs.microsoft.com/windows/security/threat-protection/use-windows-event-forwarding-to-assist-in-intrusion-detection" target="_blank">
     [64]
    </a>
   </sup>
  </span>
  ). New, benign services may be created during installation of new software. Data and events should not be viewed in isolation, but as part of a chain of behavior that could lead to other activities, such as network connections made for Command and Control, learning details about the environment through Discovery, and Lateral Movement.
 </p>
 <p>
  Tools such as Sysinternals Autoruns may also be used to detect system changes that could be attempts at persistence.
  <span class="scite-citeref-number" data-reference="TechNet Autoruns" id="scite-ref-65-a">
   <sup>
    <a aria-describedby="qtip-64" data-hasqtip="64" href="https://technet.microsoft.com/en-us/sysinternals/bb963902" target="_blank">
     [65]
    </a>
   </sup>
  </span>
  Look for changes to services that do not correlate with known software, patch cycles, etc. Suspicious program execution through services may show up as outlier processes that have not been seen before when compared against historical data.
 </p>
 <p>
  Monitor processes and command-line arguments for actions that could create services. Remote access tools with built-in features may interact directly with the Windows API to perform these functions outside of typical system utilities. Services may also be created through Windows system management tools such as
  <a href="https://attack.mitre.org/techniques/T1047">
   Windows Management Instrumentation
  </a>
  and
  <a href="https://attack.mitre.org/techniques/T1086">
   PowerShell
  </a>
  , so additional logging may need to be configured to gather the appropriate data.
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
       <a class="external text" href="https://technet.microsoft.com/en-us/library/cc772408.aspx" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Services. Retrieved June 7, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2014/11/operation_doubletap.html" name="scite-2" rel="nofollow" target="_blank">
        Moran, N., et al. (2014, November 21). Operation Double Tap. Retrieved January 14, 2016.
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
       <a class="external text" href="https://www.f-secure.com/documents/996508/1030745/blackenergy_whitepaper.pdf" name="scite-4" rel="nofollow" target="_blank">
        F-Secure Labs. (2014). BlackEnergy &amp; Quedagh: The convergence of crimeware and APT attacks. Retrieved March 24, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051515-2843-99" name="scite-5" rel="nofollow" target="_blank">
        Ladley, F. (2012, May 15). Backdoor.Briba. Retrieved February 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08064518/Carbanak_APT_eng.pdf" name="scite-6" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2015, February). CARBANAK APT THE GREAT BANK ROBBERY. Retrieved August 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www-west.symantec.com/content/symantec/english/en/security-center/writeup.html/2018-040209-1742-99" name="scite-7" rel="nofollow" target="_blank">
        Balanza, M. (2018, April 02). Infostealer.Catchamas. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.group-ib.com/blog/cobalt" name="scite-8" rel="nofollow" target="_blank">
        Matveeva, V. (2017, August 15). Secrets of Cobalt. Retrieved October 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cobaltstrike.com/downloads/reports/tacticstechniquesandprocedures.pdf" name="scite-9" rel="nofollow" target="_blank">
        Cobalt Strike. (2017, December 8). Tactics, Techniques, and Procedures. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.f-secure.com/documents/996508/1030745/cosmicduke_whitepaper.pdf" name="scite-10" rel="nofollow" target="_blank">
        F-Secure Labs. (2014, July). COSMICDUKE Cosmu with a twist of MiniDuke. Retrieved July 3, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.f-secure.com/documents/996508/1030745/CozyDuke" name="scite-11" rel="nofollow" target="_blank">
        F-Secure Labs. (2015, April 22). CozyDuke: Malware Analysis. Retrieved December 10, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/w32_duqu_the_precursor_to_the_next_stuxnet.pdf" name="scite-12" rel="nofollow" target="_blank">
        Symantec Security Response. (2011, November). W32.Duqu: The precursor to the next Stuxnet. Retrieved September 17, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/dyre-emerging-threat.pdf" name="scite-13" rel="nofollow" target="_blank">
        Symantec Security Response. (2015, June 23). Dyre: Emerging threat on financial fraud landscape. Retrieved August 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.paloaltonetworks.com/resources/research/unit42-operation-lotus-blossom.html" name="scite-14" rel="nofollow" target="_blank">
        Falcone, R., et al.. (2015, June 16). Operation Lotus Blossom. Retrieved February 15, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/02/emissary-trojan-changelog-did-operation-lotus-blossom-cause-it-to-evolve/" name="scite-15" rel="nofollow" target="_blank">
        Falcone, R. and Miller-Osborn, J.. (2016, February 3). Emissary Trojan Changelog: Did Operation Lotus Blossom Cause It to Evolve?. Retrieved February 15, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/08/fin7-pursuing-an-enigmatic-and-evasive-global-criminal-operation.html" name="scite-16" rel="nofollow" target="_blank">
        Carr, N., et al. (2018, August 01). On the Hunt for FIN7: Pursuing an Enigmatic and Evasive Global Criminal Operation. Retrieved August 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.finfisher.com/FinFisher/index.html" name="scite-17" rel="nofollow" target="_blank">
        FinFisher. (n.d.). Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://cloudblogs.microsoft.com/microsoftsecure/2018/03/01/finfisher-exposed-a-researchers-tale-of-defeating-traps-tricks-and-complex-virtual-machines/" name="scite-18" rel="nofollow" target="_blank">
        Allievi, A.,Flori, E. (2018, March 01). FinFisher exposed: A researcher’s tale of defeating traps, tricks, and complex virtual machines. Retrieved July 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.secureworks.com/resources/blog/where-you-at-indicators-of-lateral-movement-using-at-exe-on-windows-7-systems/" name="scite-19" rel="nofollow" target="_blank">
        Carvey, H.. (2014, September 2). Where you AT?: Indicators of lateral movement using at.exe on Windows 7 systems. Retrieved January 25, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.threatstream.com/blog/evasive-maneuvers-the-wekby-group-attempts-to-evade-analysis-via-custom-rop" name="scite-20" rel="nofollow" target="_blank">
        Shelmire, A.. (2015, July 6). Evasive Maneuvers. Retrieved January 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/connect/blogs/trojanhydraq-incident" name="scite-21" rel="nofollow" target="_blank">
        Symantec Security Response. (2010, January 18). The Trojan.Hydraq Incident. Retrieved February 20, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2010-011114-1830-99" name="scite-22" rel="nofollow" target="_blank">
        Lelli, A. (2010, January 11). Trojan.Hydraq. Retrieved February 20, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-23">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/connect/blogs/how-trojanhydraq-stays-your-computer" name="scite-23" rel="nofollow" target="_blank">
        Fitzgerald, P. (2010, January 26). How Trojan.Hydraq Stays On Your Computer. Retrieved February 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-24">
      <span class="scite-citation-text">
       <a class="external text" href="https://asert.arbornetworks.com/innaput-actors-utilize-remote-access-trojan-since-2016-presumably-targeting-victim-files/" name="scite-24" rel="nofollow" target="_blank">
        ASERT Team. (2018, April 04). Innaput Actors Utilize Remote Access Trojan Since 2016, Presumably Targeting Victim Files. Retrieved July 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-25">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part1.pdf" name="scite-25" rel="nofollow" target="_blank">
        ESET. (2016, October). En Route with Sednit - Part 1: Approaching the Target. Retrieved November 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-26">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/05/unit42-kazuar-multiplatform-espionage-backdoor-api-access/" name="scite-26" rel="nofollow" target="_blank">
        Levene, B, et al. (2017, May 03). Kazuar: Multiplatform Espionage Backdoor with API Access. Retrieved July 17, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-27">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/" name="scite-27" rel="nofollow" target="_blank">
        Smallridge, R. (2018, March 10). APT15 is alive and strong: An analysis of RoyalCli and RoyalDNS. Retrieved April 4, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-28">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/orangeworm-targets-healthcare-us-europe-asia" name="scite-28" rel="nofollow" target="_blank">
        Symantec Security Response Attack Investigation Team. (2018, April 23). New Orangeworm attack group targets the healthcare sector in the U.S., Europe, and Asia. Retrieved May 8, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-29">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" name="scite-29" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Unraveling the Long Thread of the Sony Attack. Retrieved February 25, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-30">
      <span class="scite-citation-text">
       <a class="external text" href="https://operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Destructive-Malware-Report.pdf" name="scite-30" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Destructive Malware Report. Retrieved March 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-31">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2017/03/unit42-trochilus-rat-new-moonwind-rat-used-attack-thai-utility-organizations/" name="scite-31" rel="nofollow" target="_blank">
        Miller-Osborn, J. and Grunzweig, J.. (2017, March 30). Trochilus and New MoonWind RATs Used In Attack Against Thai Organizations. Retrieved March 30, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-32">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-061518-4639-99" name="scite-32" rel="nofollow" target="_blank">
        Neville, A. (2012, June 15). Trojan.Naid. Retrieved February 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-33">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051515-3445-99" name="scite-33" rel="nofollow" target="_blank">
        Ladley, F. (2012, May 15). Backdoor.Nerex. Retrieved February 23, 2018.
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
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2015-120123-5521-99" name="scite-34" rel="nofollow" target="_blank">
        Sponchioni, R.. (2016, March 11). Backdoor.Nidiran. Retrieved August 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-35">
      <span class="scite-citation-text">
       <a class="external text" href="http://labs.lastline.com/an-analysis-of-plugx" name="scite-35" rel="nofollow" target="_blank">
        Vasilenko, R. (2013, December 17). An Analysis of PlugX Malware. Retrieved November 24, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-36">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" name="scite-36" rel="nofollow" target="_blank">
        PwC and BAE Systems. (2017, April). Operation Cloud Hopper: Technical Annex. Retrieved April 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-37">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/04/apt10_menupass_grou.html" name="scite-37" rel="nofollow" target="_blank">
        FireEye iSIGHT Intelligence. (2017, April 6). APT10 (MenuPass Group): New Tools, Global Campaign Latest Manifestation of Longstanding Threat. Retrieved June 29, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-38">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/us/threat-insight/post/APT-targets-russia-belarus-zerot-plugx" name="scite-38" rel="nofollow" target="_blank">
        Huss, D., et al. (2017, February 2). Oops, they did it again: APT Targets Russia and Belarus with ZeroT and PlugX. Retrieved April 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-39">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2005-081910-3934-99" name="scite-39" rel="nofollow" target="_blank">
        Hayashi, K. (2005, August 18). Backdoor.Darkmoon. Retrieved February 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-40">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.kroll.com/CMSPages/GetAzureFile.aspx?path=~%5Cmedia%5Cfiles%5Cintelligence-center%5Ckroll_malware-analysis-report.pdf&amp;hash=d5b5d2697118f30374b954f28a08c0ba69836c0ffd99566aa7ec62d1fc72b105" name="scite-40" rel="nofollow" target="_blank">
        Nesbit, B. and Ackerman, D. (2017, January). Malware Analysis Report - RawPOS Malware: Deconstructing an Intruder’s Toolkit. Retrieved October 4, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-41">
      <span class="scite-citation-text">
       <a class="external text" href="http://sjc1-te-ftp.trendmicro.com/images/tex/pdf/RawPOS%20Technical%20Brief.pdf" name="scite-41" rel="nofollow" target="_blank">
        TrendLabs Security Intelligence Blog. (2015, April). RawPOS Technical Brief. Retrieved October 4, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-42">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.youtube.com/watch?v=fevGZs0EQu8" name="scite-42" rel="nofollow" target="_blank">
        Bromiley, M. and Lewis, P. (2016, October 7). Attacking the Hospitality and Gaming Industries: Tracking an Attacker Around the World in 7 Years. Retrieved October 6, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-43">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-new-malware-with-ties-to-sunorcal-discovered/" name="scite-43" rel="nofollow" target="_blank">
        Grunzweig, J. and Miller-Osborn, J. (2017, November 10). New Malware with Ties to SunOrcal Discovered. Retrieved November 16, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-44">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.secureworks.com/cyber-threat-intelligence/threats/sakula-malware-family/" name="scite-44" rel="nofollow" target="_blank">
        Dell SecureWorks Counter Threat Unit Threat Intelligence. (2015, July 30). Sakula Malware Family. Retrieved January 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-45">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/11/unit42-shamoon-2-return-disttrack-wiper/" name="scite-45" rel="nofollow" target="_blank">
        Falcone, R.. (2016, November 30). Shamoon 2: Return of the Disttrack Wiper. Retrieved January 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-46">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cylance.com/shell-crew-variants-continue-to-fly-under-big-avs-radar" name="scite-46" rel="nofollow" target="_blank">
        Cylance SPEAR Team. (2017, February 9). Shell Crew Variants Continue to Fly Under Big AV’s Radar. Retrieved February 15, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-47">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.clearskysec.com/wp-content/uploads/2017/07/Operation_Wilted_Tulip.pdf" name="scite-47" rel="nofollow" target="_blank">
        ClearSky Cyber Security and Trend Micro. (2017, July). Operation Wilted Tulip: Exposing a cyber espionage apparatus. Retrieved August 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-48">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/may/emissary-panda-a-potential-new-malicious-tool/" name="scite-48" rel="nofollow" target="_blank">
        Pantazopoulos, N., Henry T. (2018, May 18). Emissary Panda – A potential new malicious tool. Retrieved June 25, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-49">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf" name="scite-49" rel="nofollow" target="_blank">
        Cylance. (2014, December). Operation Cleaver. Retrieved September 14, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-50">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-165A" name="scite-50" rel="nofollow" target="_blank">
        US-CERT. (2018, June 14). MAR-10135536-12 – North Korean Trojan: TYPEFRAME. Retrieved July 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-51">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-D_WHITE_S508C.PDF" name="scite-51" rel="nofollow" target="_blank">
        US-CERT. (2017, November 01). Malware Analysis Report (MAR) - 10135536-D. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-52">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security-center/writeup/2014-081811-3237-99?tabid=2" name="scite-52" rel="nofollow" target="_blank">
        Yagi, J. (2014, August 24). Trojan.Volgmer. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-53">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051606-1005-99" name="scite-53" rel="nofollow" target="_blank">
        Zhou, R. (2012, May 15). Backdoor.Wiarp. Retrieved February 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-54">
      <span class="scite-citation-text">
       <a class="external text" href="http://download.microsoft.com/download/E/B/0/EB0F50CC-989C-4B66-B7F6-68CD3DC90DE3/Microsoft_Security_Intelligence_Report_Volume_21_English.pdf" name="scite-54" rel="nofollow" target="_blank">
        Anthe, C. et al. (2016, December 14). Microsoft Security Intelligence Report Volume 21. Retrieved November 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-55">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.microsoft.com/wdsi/threats/malware-encyclopedia-description?Name=Backdoor:Win32/Wingbird.A!dha" name="scite-55" rel="nofollow" target="_blank">
        Microsoft. (2017, November 9). Backdoor:Win32/Wingbird.A!dha. Retrieved November 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-56">
      <span class="scite-citation-text">
       <a class="external text" href="https://blogs.technet.microsoft.com/mmpc/2017/01/25/detecting-threat-actors-in-recent-german-industrial-attacks-with-windows-defender-atp/" name="scite-56" rel="nofollow" target="_blank">
        Cap, P., et al. (2017, January 25). Detecting threat actors in recent German industrial attacks with Windows Defender ATP. Retrieved February 8, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-57">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cylance.com/content/dam/cylance/pdfs/reports/Op_Dust_Storm_Report.pdf" name="scite-57" rel="nofollow" target="_blank">
        Gross, J. (2016, February 23). Operation Dust Storm. Retrieved September 19, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-58">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-58" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-59">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-59" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-60">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-60" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-61">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" name="scite-61" rel="nofollow" target="_blank">
        Corio, C., &amp; Sayana, D. P. (2008, June). Application Lockdown with Software Restriction Policies. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-62">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" name="scite-62" rel="nofollow" target="_blank">
        Microsoft. (2012, June 27). Using Software Restriction Policies and AppLocker Policies. Retrieved April 7, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-63">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/windows/security/threat-protection/auditing/event-4697" name="scite-63" rel="nofollow" target="_blank">
        Miroshnikov, A. &amp; Hall, J. (2017, April 18). 4697(S): A service was installed in the system. Retrieved August 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-64">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/windows/security/threat-protection/use-windows-event-forwarding-to-assist-in-intrusion-detection" name="scite-64" rel="nofollow" target="_blank">
        Hardy, T. &amp; Hall, J. (2018, February 15). Use Windows Event Forwarding to help with intrusion detection. Retrieved August 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-65">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/sysinternals/bb963902" name="scite-65" rel="nofollow" target="_blank">
        Russinovich, M. (2016, January 4). Autoruns for Windows v13.51. Retrieved June 6, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
