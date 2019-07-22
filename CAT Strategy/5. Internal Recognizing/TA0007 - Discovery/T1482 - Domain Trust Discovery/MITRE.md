<div class="container-fluid">
 <h1>
  Domain Trust Discovery
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries may attempt to gather information on domain trust relationships that may be used to identify
    <a href="https://attack.mitre.org/tactics/TA0008">
     Lateral Movement
    </a>
    opportunities in Windows multi-domain/forest environments. Domain trusts provide a mechanism for a domain to allow access to resources based on the authentication procedures of another domain.
    <span class="scite-citeref-number" data-reference="Microsoft Trusts" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2003/cc759554(v=ws.10)" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    Domain trusts allow the users of the trusted domain to access resources in the trusting domain. The information discovered may help the adversary conduct
    <a href="https://attack.mitre.org/techniques/T1178">
     SID-History Injection
    </a>
    ,
    <a href="https://attack.mitre.org/techniques/T1097">
     Pass the Ticket
    </a>
    , and
    <a href="https://attack.mitre.org/techniques/T1208">
     Kerberoasting
    </a>
    .
    <span class="scite-citeref-number" data-reference="AdSecurity Forging Trust Tickets" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://adsecurity.org/?p=1588" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Harmj0y Domain Trusts" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="http://www.harmj0y.net/blog/redteaming/a-guide-to-attacking-domain-trusts/ " target="_blank">
       [3]
      </a>
     </sup>
    </span>
    Domain trusts can be enumerated using the DSEnumerateDomainTrusts() Win32 API call, .NET methods, and LDAP.
    <span class="scite-citeref-number" data-reference="Harmj0y Domain Trusts" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="http://www.harmj0y.net/blog/redteaming/a-guide-to-attacking-domain-trusts/ " target="_blank">
       [3]
      </a>
     </sup>
    </span>
    The Windows utility
    <a href="https://attack.mitre.org/software/S0359">
     Nltest
    </a>
    is known to be used by adversaries to enumerate domain trusts.
    <span class="scite-citeref-number" data-reference="Microsoft Operation Wilysupply" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.microsoft.com/security/blog/2017/05/04/windows-defender-atp-thwarts-operation-wilysupply-software-supply-chain-cyberattack/" target="_blank">
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
      : T1482
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
      : Discovery
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
      PowerShell logs, API monitoring, Process command-line parameters, Process monitoring
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
      Dave Westgard; Elia Florio, Microsoft; Mnemonic; RedHuntLabs (@redhuntlabs)
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
     <a href="https://attack.mitre.org/software/S0105">
      dsquery
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0105">
       dsquery
      </a>
      can be used to gather information on domain trusts with
      <code>
       dsquery * -filter "(objectClass=trustedDomain)" -attr *
      </code>
      .
      <span class="scite-citeref-number" data-reference="Harmj0y Domain Trusts" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="http://www.harmj0y.net/blog/redteaming/a-guide-to-attacking-domain-trusts/ " target="_blank">
         [3]
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
      has modules for enumerating domain trusts.
      <span class="scite-citeref-number" data-reference="Github PowerShell Empire" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://github.com/PowerShellEmpire/Empire" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0359">
      Nltest
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0359">
       Nltest
      </a>
      may be used to enumerate trusted domains by using commands such as
      <code>
       nltest /domain_trusts
      </code>
      .
      <span class="scite-citeref-number" data-reference="Nltest Manual" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://ss64.com/nt/nltest.html" target="_blank">
         [6]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Fortinet TrickBot" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.fortinet.com/blog/threat-research/trickbot-s-new-reconnaissance-plugin.html" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0378">
      PoshC2
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0378">
       PoshC2
      </a>
      has modules for enumerating domain trusts.
      <span class="scite-citeref-number" data-reference="GitHub PoshC2" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://github.com/nettitude/PoshC2" target="_blank">
         [8]
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
      has modules such as
      <code>
       Get-NetDomainTrust
      </code>
      and
      <code>
       Get-NetForestTrust
      </code>
      to enumerate domain and forest trusts.
      <span class="scite-citeref-number" data-reference="GitHub PowerSploit May 2012" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://github.com/PowerShellMafia/PowerSploit" target="_blank">
         [9]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PowerSploit Documentation" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="http://powersploit.readthedocs.io" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0266">
      TrickBot
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0266">
       TrickBot
      </a>
      can gather information about domain trusts by utilizing
      <a href="https://attack.mitre.org/software/S0359">
       Nltest
      </a>
      .
      <span class="scite-citeref-number" data-reference="Fortinet TrickBot" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.fortinet.com/blog/threat-research/trickbot-s-new-reconnaissance-plugin.html" target="_blank">
         [7]
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
  Map the trusts within existing domains/forests and keep trust relationships to a minimum. Employ network segmentation for sensitive domains.
  <span class="scite-citeref-number" data-reference="Harmj0y Domain Trusts" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="http://www.harmj0y.net/blog/redteaming/a-guide-to-attacking-domain-trusts/ " target="_blank">
     [3]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  System and network discovery techniques normally occur throughout an operation as an adversary learns the environment. Data and events should not be viewed in isolation but as part of a chain of behavior that could lead to other activities based on the information obtained.
 </p>
 <p>
  Monitor processes and command-line arguments for actions that could be taken to gather system and network information, such as
  <code>
   nltest /domain_trusts
  </code>
  . Remote access tools with built-in features may interact directly with the Windows API to gather information. Look for the DSEnumerateDomainTrusts() Win32 API call to spot activity associated with
  <a href="https://attack.mitre.org/techniques/T1482">
   Domain Trust Discovery
  </a>
  .
  <span class="scite-citeref-number" data-reference="Harmj0y Domain Trusts" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="http://www.harmj0y.net/blog/redteaming/a-guide-to-attacking-domain-trusts/ " target="_blank">
     [3]
    </a>
   </sup>
  </span>
  Information may also be acquired through Windows system management tools such as
  <a href="https://attack.mitre.org/techniques/T1086">
   PowerShell
  </a>
  . The .NET method GetAllTrustRelationships() can be an indicator of
  <a href="https://attack.mitre.org/techniques/T1482">
   Domain Trust Discovery
  </a>
  .
  <span class="scite-citeref-number" data-reference="Microsoft GetAllTrustRelationships" id="scite-ref-11-a">
   <sup>
    <a aria-describedby="qtip-10" data-hasqtip="10" href="https://docs.microsoft.com/en-us/dotnet/api/system.directoryservices.activedirectory.domain.getalltrustrelationships?redirectedfrom=MSDN&amp;view=netframework-4.7.2#System_DirectoryServices_ActiveDirectory_Domain_GetAllTrustRelationships" target="_blank">
     [11]
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
       <a class="external text" href="https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2003/cc759554(v=ws.10)" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (2009, October 7). Trust Technologies. Retrieved February 14, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://adsecurity.org/?p=1588" name="scite-2" rel="nofollow" target="_blank">
        Metcalf, S. (2015, July 15). It’s All About Trust – Forging Kerberos Trust Tickets to Spoof Access across Active Directory Trusts. Retrieved February 14, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.harmj0y.net/blog/redteaming/a-guide-to-attacking-domain-trusts/ " name="scite-3" rel="nofollow" target="_blank">
        Schroeder, W. (2017, October 30). A Guide to Attacking Domain Trusts. Retrieved February 14, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.microsoft.com/security/blog/2017/05/04/windows-defender-atp-thwarts-operation-wilysupply-software-supply-chain-cyberattack/" name="scite-4" rel="nofollow" target="_blank">
        Florio, E.. (2017, May 4). Windows Defender ATP thwarts Operation WilySupply software supply chain cyberattack. Retrieved February 14, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellEmpire/Empire" name="scite-5" rel="nofollow" target="_blank">
        Schroeder, W., Warner, J., Nelson, M. (n.d.). Github PowerShellEmpire. Retrieved April 28, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://ss64.com/nt/nltest.html" name="scite-6" rel="nofollow" target="_blank">
        ss64. (n.d.). NLTEST.exe - Network Location Test. Retrieved February 14, 2019.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="7.5">
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fortinet.com/blog/threat-research/trickbot-s-new-reconnaissance-plugin.html" name="scite-7" rel="nofollow" target="_blank">
        Bacurio Jr., F. and Salvio, J. (2018, April 9). Trickbot’s New Reconnaissance Plugin. Retrieved February 14, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/nettitude/PoshC2" name="scite-8" rel="nofollow" target="_blank">
        Nettitude. (2016, June 8). PoshC2: Powershell C2 Server and Implants. Retrieved April 23, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellMafia/PowerSploit" name="scite-9" rel="nofollow" target="_blank">
        PowerShellMafia. (2012, May 26). PowerSploit - A PowerShell Post-Exploitation Framework. Retrieved February 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="http://powersploit.readthedocs.io" name="scite-10" rel="nofollow" target="_blank">
        PowerSploit. (n.d.). PowerSploit. Retrieved February 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/en-us/dotnet/api/system.directoryservices.activedirectory.domain.getalltrustrelationships?redirectedfrom=MSDN&amp;view=netframework-4.7.2#System_DirectoryServices_ActiveDirectory_Domain_GetAllTrustRelationships" name="scite-11" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Domain.GetAllTrustRelationships Method. Retrieved February 14, 2019.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
