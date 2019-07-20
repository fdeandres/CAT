<div class="container-fluid">
 <h1>
  Modify Existing Service
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Windows service configuration information, including the file path to the service's executable or recovery programs/commands, is stored in the Registry. Service configurations can be modified using utilities such as sc.exe and
    <a href="https://attack.mitre.org/software/S0075">
     Reg
    </a>
    .
   </p>
   <p>
    Adversaries can modify an existing service to persist malware on a system by using system utilities or by using custom tools to interact with the Windows API. Use of existing services is a type of
    <a href="https://attack.mitre.org/techniques/T1036">
     Masquerading
    </a>
    that may make detection analysis more challenging. Modifying existing services may interrupt their functionality or may enable services that are disabled or otherwise not commonly used.
   </p>
   <p>
    Adversaries may also intentionally corrupt or kill services to execute malicious recovery programs/commands.
    <span class="scite-citeref-number" data-reference="Twitter Service Recovery Nov 2017" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://twitter.com/r0wdy_/status/936365549553991680" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Microsoft Service Recovery Feb 2013" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753662(v=ws.11)" target="_blank">
       [2]
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
      : T1031
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
       Permissions Required:
      </span>
      Administrator, SYSTEM
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
      Windows Registry, File monitoring, Process monitoring, Process command-line parameters
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
      <a href="https://capec.mitre.org/data/definitions/551.html" target="_blank">
       CAPEC-551
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
      Travis Smith, Tripwire; Matthew Demaske, Adaptforward
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
     <a href="https://attack.mitre.org/groups/G0073">
      APT19
     </a>
    </td>
    <td>
     <p>
      An
      <a href="https://attack.mitre.org/groups/G0073">
       APT19
      </a>
      Port 22 malware variant registers itself as a service.
      <span class="scite-citeref-number" data-reference="Unit 42 C0d0so0 Jan 2016" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://researchcenter.paloaltonetworks.com/2016/01/new-attacks-linked-to-c0d0s0-group/" target="_blank">
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
      modified Windows Services to ensure PowerShell scripts were loaded on the system.
      <span class="scite-citeref-number" data-reference="Cybereason Cobalt Kitty 2017" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://cdn2.hubspot.net/hubfs/3354902/Cybereason%20Labs%20Analysis%20Operation%20Cobalt%20Kitty.pdf" target="_blank">
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
      can terminate a specific process by its process id.
      <span class="scite-citeref-number" data-reference="McAfee Bankshot" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://securingtomorrow.mcafee.com/mcafee-labs/hidden-cobra-targets-turkish-financial-sector-new-bankshot-implant/" target="_blank">
         [5]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT Bankshot Dec 2017" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-B_WHITE.PDF" target="_blank">
         [6]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0127">
      BBSRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0127">
       BBSRAT
      </a>
      can modify service configurations.
      <span class="scite-citeref-number" data-reference="Palo Alto Networks BBSRAT" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="http://researchcenter.paloaltonetworks.com/2015/12/bbsrat-attacks-targeting-russian-organizations-linked-to-roaming-tiger/" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0363">
      Empire
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0363">
       Empire
      </a>
      can utilize built-in modules to modify service binaries and restore them to their original state.
      <span class="scite-citeref-number" data-reference="Github PowerShell Empire" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://github.com/PowerShellEmpire/Empire" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0342">
      GreyEnergy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0342">
       GreyEnergy
      </a>
      chooses a service, drops a DLL file, and writes it to that serviceDLL Registry key.
      <span class="scite-citeref-number" data-reference="ESET GreyEnergy Oct 2018" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.welivesecurity.com/wp-content/uploads/2018/10/ESET_GreyEnergy.pdf" target="_blank">
         [9]
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
      has batch files that modify the system service COMSysApp to load a malicious DLL.
      <span class="scite-citeref-number" data-reference="McAfee Honeybee" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://securingtomorrow.mcafee.com/mcafee-labs/mcafee-uncovers-operation-honeybee-malicious-document-campaign-targeting-humanitarian-aid-groups/" target="_blank">
         [10]
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
      has a module to change service configurations as well as start, control, and delete services.
      <span class="scite-citeref-number" data-reference="CIRCL PlugX March 2013" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="http://circl.lu/assets/files/tr-12/tr-12-circl-plugx-analysis-v1.pdf" target="_blank">
         [11]
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
      creates a Registry entry modifying the Logical Disk Manager service to point to a malicious DLL dropped to disk.
      <span class="scite-citeref-number" data-reference="Symantec Darkmoon Aug 2005" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://www.symantec.com/security_response/writeup.jsp?docid=2005-081910-3934-99" target="_blank">
         [12]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0194">
      PowerSploit
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0194">
       PowerSploit
      </a>
      contains a collection of Privesc-PowerUp modules that can discover and replace/modify service binaries, paths, and configs.
      <span class="scite-citeref-number" data-reference="GitHub PowerSploit May 2012" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://github.com/PowerShellMafia/PowerSploit" target="_blank">
         [13]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PowerSploit Documentation" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="http://powersploit.readthedocs.io" target="_blank">
         [14]
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
      can delete services from the victim’s machine.
      <span class="scite-citeref-number" data-reference="US-CERT TYPEFRAME June 2018" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-165A" target="_blank">
         [15]
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
      <a href="https://attack.mitre.org/software/S0180">
       Volgmer
      </a>
      installs a copy of itself in a randomly selected service, then overwrites the ServiceDLL entry in the service's Registry entry.
      <span class="scite-citeref-number" data-reference="US-CERT Volgmer Nov 2017" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="https://www.us-cert.gov/ncas/alerts/TA17-318B" target="_blank">
         [16]
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
  Use auditing tools capable of detecting privilege and service abuse opportunities on systems within an enterprise and correct them. Limit privileges of user accounts and groups so that only authorized administrators can interact with service changes and service configurations. Toolkits like the PowerSploit framework contain the PowerUp modules that can be used to explore systems for Privilege Escalation weaknesses.
  <span class="scite-citeref-number" data-reference="Powersploit" id="scite-ref-17-a">
   <sup>
    <a aria-describedby="qtip-16" data-hasqtip="16" href="https://github.com/mattifestation/PowerSploit" target="_blank">
     [17]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Identify and block potentially malicious software that may be executed through service abuse by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-18-a">
   <sup>
    <a aria-describedby="qtip-17" data-hasqtip="17" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [18]
    </a>
   </sup>
  </span>
  tools like AppLocker
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-19-a">
   <sup>
    <a aria-describedby="qtip-18" data-hasqtip="18" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [19]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-20-a">
   <sup>
    <a aria-describedby="qtip-19" data-hasqtip="19" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [20]
    </a>
   </sup>
  </span>
  that are capable of auditing and/or blocking unknown programs.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Look for changes to service Registry entries that do not correlate with known software, patch cycles, etc. Changes to the binary path and the service startup type changed from manual or disabled to automatic, if it does not typically do so, may be suspicious. Tools such as Sysinternals Autoruns may also be used to detect system service changes that could be attempts at persistence.
  <span class="scite-citeref-number" data-reference="TechNet Autoruns" id="scite-ref-21-a">
   <sup>
    <a aria-describedby="qtip-20" data-hasqtip="20" href="https://technet.microsoft.com/en-us/sysinternals/bb963902" target="_blank">
     [21]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Service information is stored in the Registry at
  <code>
   HKLM\SYSTEM\CurrentControlSet\Services
  </code>
  .
 </p>
 <p>
  Command-line invocation of tools capable of modifying services may be unusual, depending on how systems are typically used in a particular environment. Collect service utility execution and service binary path arguments used for analysis. Service binary paths may even be changed to execute
  <a href="https://attack.mitre.org/software/S0106">
   cmd
  </a>
  commands or scripts.
 </p>
 <p>
  Look for abnormal process call trees from known services and for execution of other commands that could relate to Discovery or other adversary techniques. Services may also be modified through Windows system management tools such as
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
       <a class="external text" href="https://twitter.com/r0wdy_/status/936365549553991680" name="scite-1" rel="nofollow" target="_blank">
        The Cyber (@r0wdy_). (2017, November 30). Service Recovery Parameters. Retrieved April 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753662(v=ws.11)" name="scite-2" rel="nofollow" target="_blank">
        Microsoft. (2013, February 22). Set up Recovery Actions to Take Place When a Service Fails. Retrieved April 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2016/01/new-attacks-linked-to-c0d0s0-group/" name="scite-3" rel="nofollow" target="_blank">
        Grunzweig, J., Lee, B. (2016, January 22). New Attacks Linked to C0d0so0 Group. Retrieved August 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://cdn2.hubspot.net/hubfs/3354902/Cybereason%20Labs%20Analysis%20Operation%20Cobalt%20Kitty.pdf" name="scite-4" rel="nofollow" target="_blank">
        Dahan, A. (2017). Operation Cobalt Kitty. Retrieved December 27, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/hidden-cobra-targets-turkish-financial-sector-new-bankshot-implant/" name="scite-5" rel="nofollow" target="_blank">
        Sherstobitoff, R. (2018, March 08). Hidden Cobra Targets Turkish Financial Sector With New Bankshot Implant. Retrieved May 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-B_WHITE.PDF" name="scite-6" rel="nofollow" target="_blank">
        US-CERT. (2017, December 13). Malware Analysis Report (MAR) - 10135536-B. Retrieved July 17, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2015/12/bbsrat-attacks-targeting-russian-organizations-linked-to-roaming-tiger/" name="scite-7" rel="nofollow" target="_blank">
        Lee, B. Grunzweig, J. (2015, December 22). BBSRAT Attacks Targeting Russian Organizations Linked to Roaming Tiger. Retrieved August 19, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellEmpire/Empire" name="scite-8" rel="nofollow" target="_blank">
        Schroeder, W., Warner, J., Nelson, M. (n.d.). Github PowerShellEmpire. Retrieved April 28, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2018/10/ESET_GreyEnergy.pdf" name="scite-9" rel="nofollow" target="_blank">
        Cherepanov, A. (2018, October). GREYENERGY A successor to BlackEnergy. Retrieved November 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/mcafee-uncovers-operation-honeybee-malicious-document-campaign-targeting-humanitarian-aid-groups/" name="scite-10" rel="nofollow" target="_blank">
        Sherstobitoff, R. (2018, March 02). McAfee Uncovers Operation Honeybee, a Malicious Document Campaign Targeting Humanitarian Aid Groups. Retrieved May 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="http://circl.lu/assets/files/tr-12/tr-12-circl-plugx-analysis-v1.pdf" name="scite-11" rel="nofollow" target="_blank">
        Computer Incident Response Center Luxembourg. (2013, March 29). Analysis of a PlugX variant. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="12.5">
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2005-081910-3934-99" name="scite-12" rel="nofollow" target="_blank">
        Hayashi, K. (2005, August 18). Backdoor.Darkmoon. Retrieved February 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellMafia/PowerSploit" name="scite-13" rel="nofollow" target="_blank">
        PowerShellMafia. (2012, May 26). PowerSploit - A PowerShell Post-Exploitation Framework. Retrieved February 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="http://powersploit.readthedocs.io" name="scite-14" rel="nofollow" target="_blank">
        PowerSploit. (n.d.). PowerSploit. Retrieved February 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-165A" name="scite-15" rel="nofollow" target="_blank">
        US-CERT. (2018, June 14). MAR-10135536-12 – North Korean Trojan: TYPEFRAME. Retrieved July 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA17-318B" name="scite-16" rel="nofollow" target="_blank">
        US-CERT. (2017, November 22). Alert (TA17-318B): HIDDEN COBRA – North Korean Trojan: Volgmer. Retrieved December 7, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/mattifestation/PowerSploit" name="scite-17" rel="nofollow" target="_blank">
        PowerSploit. (n.d.). Retrieved December 4, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-18" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-19" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-20" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/sysinternals/bb963902" name="scite-21" rel="nofollow" target="_blank">
        Russinovich, M. (2016, January 4). Autoruns for Windows v13.51. Retrieved June 6, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
