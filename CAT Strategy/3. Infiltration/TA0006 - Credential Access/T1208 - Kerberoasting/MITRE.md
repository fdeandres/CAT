<div class="container-fluid">
 <h1>
  Kerberoasting
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Service principal names (SPNs) are used to uniquely identify each instance of a Windows service. To enable authentication, Kerberos requires that SPNs be associated with at least one service logon account (an account specifically tasked with running a service
    <span class="scite-citeref-number" data-reference="Microsoft Detecting Kerberoasting Feb 2018" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://blogs.technet.microsoft.com/motiba/2018/02/23/detecting-kerberoasting-activity-using-azure-security-center/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    ).
    <span class="scite-citeref-number" data-reference="Microsoft SPN" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://msdn.microsoft.com/library/ms677949.aspx" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Microsoft SetSPN" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="SANS Attacking Kerberos Nov 2014" id="scite-ref-4-a">
     <sup>
      [4]
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Harmj0y Kerberoast Nov 2016" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.harmj0y.net/blog/powershell/kerberoasting-without-mimikatz/" target="_blank">
       [5]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries possessing a valid Kerberos ticket-granting ticket (TGT) may request one or more Kerberos ticket-granting service (TGS) service tickets for any SPN from a domain controller (DC).
    <span class="scite-citeref-number" data-reference="Empire InvokeKerberoast Oct 2016" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://github.com/EmpireProject/Empire/blob/master/data/module_source/credentials/Invoke-Kerberoast.ps1" target="_blank">
       [6]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="AdSecurity Cracking Kerberos Dec 2015" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="https://adsecurity.org/?p=2293" target="_blank">
       [7]
      </a>
     </sup>
    </span>
    Portions of these tickets may be encrypted with the RC4 algorithm, meaning the Kerberos 5 TGS-REP etype 23 hash of the service account associated with the SPN is used as the private key and is thus vulnerable to offline
    <a href="https://attack.mitre.org/techniques/T1110">
     Brute Force
    </a>
    attacks that may expose plaintext credentials.
    <span class="scite-citeref-number" data-reference="AdSecurity Cracking Kerberos Dec 2015" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="https://adsecurity.org/?p=2293" target="_blank">
       [7]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Empire InvokeKerberoast Oct 2016" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://github.com/EmpireProject/Empire/blob/master/data/module_source/credentials/Invoke-Kerberoast.ps1" target="_blank">
       [6]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Harmj0y Kerberoast Nov 2016" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.harmj0y.net/blog/powershell/kerberoasting-without-mimikatz/" target="_blank">
       [5]
      </a>
     </sup>
    </span>
   </p>
   <p>
    This same attack could be executed using service tickets captured from network traffic.
    <span class="scite-citeref-number" data-reference="AdSecurity Cracking Kerberos Dec 2015" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="https://adsecurity.org/?p=2293" target="_blank">
       [7]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Cracked hashes may enable Persistence, Privilege Escalation, and  Lateral Movement via access to
    <a href="https://attack.mitre.org/techniques/T1078">
     Valid Accounts
    </a>
    .
    <span class="scite-citeref-number" data-reference="SANS Attacking Kerberos Nov 2014" id="scite-ref-4-a">
     <sup>
      [4]
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
      : T1208
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
      : Credential Access
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
      Valid domain account or the ability to sniff traffic within a domain.
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
      Windows event logs
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
      Praetorian
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
     <a href="https://attack.mitre.org/software/S0363">
      Empire
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0363">
       Empire
      </a>
      uses
      <a href="https://attack.mitre.org/software/S0194">
       PowerSploit
      </a>
      's
      <code>
       Invoke-Kerberoast
      </code>
      to request service tickets and return crackable ticket hashes.
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
     <a href="https://attack.mitre.org/software/S0357">
      Impacket
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0357">
       Impacket
      </a>
      modules like GetUserSPNs can be used to get Service Principal Names (SPNs) for user accounts. The output is formatted to be compatible with cracking tools like John the Ripper and Hashcat.
      <span class="scite-citeref-number" data-reference="Impacket Tools" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.secureauth.com/labs/open-source-tools/impacket" target="_blank">
         [9]
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
      's
      <code>
       Invoke-Kerberoast
      </code>
      module can request service tickets and return crackable ticket hashes.
      <span class="scite-citeref-number" data-reference="PowerSploit Invoke Kerberoast" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://powersploit.readthedocs.io/en/latest/Recon/Invoke-Kerberoast/" target="_blank">
         [10]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Harmj0y Kerberoast Nov 2016" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.harmj0y.net/blog/powershell/kerberoasting-without-mimikatz/" target="_blank">
         [5]
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
  Ensure strong password length (ideally 25+ characters) and complexity for service accounts and that these passwords periodically expire.
  <span class="scite-citeref-number" data-reference="AdSecurity Cracking Kerberos Dec 2015" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://adsecurity.org/?p=2293" target="_blank">
     [7]
    </a>
   </sup>
  </span>
  Also consider using Group Managed Service Accounts or another third party product such as password vaulting.
  <span class="scite-citeref-number" data-reference="AdSecurity Cracking Kerberos Dec 2015" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://adsecurity.org/?p=2293" target="_blank">
     [7]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Limit service accounts to minimal required privileges, including membership in privileged groups such as Domain Administrators.
  <span class="scite-citeref-number" data-reference="AdSecurity Cracking Kerberos Dec 2015" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://adsecurity.org/?p=2293" target="_blank">
     [7]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Enable AES Kerberos encryption (or another stronger encryption algorithm), rather than RC4, where possible.
  <span class="scite-citeref-number" data-reference="AdSecurity Cracking Kerberos Dec 2015" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://adsecurity.org/?p=2293" target="_blank">
     [7]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Enable Audit Kerberos Service Ticket Operations to log Kerberos TGS service ticket requests. Particularly investigate irregular patterns of activity (ex: accounts making numerous requests, Event ID 4769, within a small time frame, especially if they also request RC4 encryption [Type 0x17]).
  <span class="scite-citeref-number" data-reference="Microsoft Detecting Kerberoasting Feb 2018" id="scite-ref-1-a">
   <sup>
    <a aria-describedby="qtip-0" data-hasqtip="0" href="https://blogs.technet.microsoft.com/motiba/2018/02/23/detecting-kerberoasting-activity-using-azure-security-center/" target="_blank">
     [1]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="AdSecurity Cracking Kerberos Dec 2015" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://adsecurity.org/?p=2293" target="_blank">
     [7]
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
       <a class="external text" href="https://blogs.technet.microsoft.com/motiba/2018/02/23/detecting-kerberoasting-activity-using-azure-security-center/" name="scite-1" rel="nofollow" target="_blank">
        Bani, M. (2018, February 23). Detecting Kerberoasting activity using Azure Security Center. Retrieved March 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/ms677949.aspx" name="scite-2" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Service Principal Names. Retrieved March 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx" name="scite-3" rel="nofollow" target="_blank">
        Microsoft. (2010, April 13). Service Principal Names (SPNs) SetSPN Syntax (Setspn.exe). Retrieved March 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       Medin, T. (2014, November). Attacking Kerberos - Kicking the Guard Dog of Hades. Retrieved March 22, 2018.
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.harmj0y.net/blog/powershell/kerberoasting-without-mimikatz/" name="scite-5" rel="nofollow" target="_blank">
        Schroeder, W. (2016, November 1). Kerberoasting Without Mimikatz. Retrieved March 23, 2018.
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
       <a class="external text" href="https://github.com/EmpireProject/Empire/blob/master/data/module_source/credentials/Invoke-Kerberoast.ps1" name="scite-6" rel="nofollow" target="_blank">
        EmpireProject. (2016, October 31). Invoke-Kerberoast.ps1. Retrieved March 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://adsecurity.org/?p=2293" name="scite-7" rel="nofollow" target="_blank">
        Metcalf, S. (2015, December 31). Cracking Kerberos TGS Tickets Using Kerberoast – Exploiting Kerberos to Compromise the Active Directory Domain. Retrieved March 22, 2018.
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
       <a class="external text" href="https://www.secureauth.com/labs/open-source-tools/impacket" name="scite-9" rel="nofollow" target="_blank">
        SecureAuth. (n.d.).  Retrieved January 15, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://powersploit.readthedocs.io/en/latest/Recon/Invoke-Kerberoast/" name="scite-10" rel="nofollow" target="_blank">
        Schroeder, W. &amp; Hart M. (2016, October 31). Invoke-Kerberoast. Retrieved March 23, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
