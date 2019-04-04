<div class="container-fluid">
 <h1>
  Brute Force
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries may use brute force techniques to attempt access to accounts when passwords are unknown or when password hashes are obtained.
   </p>
   <p>
    <a href="https://attack.mitre.org/techniques/T1003">
     Credential Dumping
    </a>
    to obtain password hashes may only get an adversary so far when
    <a href="https://attack.mitre.org/techniques/T1075">
     Pass the Hash
    </a>
    is not an option. Techniques to systematically guess the passwords used to compute hashes are available, or the adversary may use a pre-computed rainbow table. Cracking hashes is usually done on adversary-controlled systems outside of the target network.
    <span class="scite-citeref-number" data-reference="Wikipedia Password cracking" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://en.wikipedia.org/wiki/Password_cracking" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries may attempt to brute force logins without knowledge of passwords or hashes during an operation either with zero knowledge or by attempting a list of known or possible passwords. This is a riskier option because it could cause numerous authentication failures and account lockouts, depending on the organization's login failure policies.
    <span class="scite-citeref-number" data-reference="Cylance Cleaver" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    A related technique called password spraying uses one password, or a small list of passwords, that matches the complexity policy of the domain and may be a commonly used password. Logins are attempted with that password and many different accounts on a network to avoid account lockouts that would normally occur when brute forcing a single account with many passwords.
    <span class="scite-citeref-number" data-reference="BlackHillsInfosec Password Spraying" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="http://www.blackhillsinfosec.com/?p=4645" target="_blank">
       [3]
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
      : T1110
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
      Authentication logs
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
       Contributors:
      </span>
      John Strand
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
      has been known to brute force password hashes to be able to leverage plain text credentials.
      <span class="scite-citeref-number" data-reference="APT3 Adversary Emulation Plan" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://attack.mitre.org/docs/APT3_Adversary_Emulation_Plan.pdf" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0220">
      Chaos
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0220">
       Chaos
      </a>
      conducts brute force attacks against SSH services to gain initial access.
      <span class="scite-citeref-number" data-reference="Chaos Stolen Backdoor" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="http://gosecure.net/2018/02/14/chaos-stolen-backdoor-rising/" target="_blank">
         [5]
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
      dropped and executed tools used for password cracking, including Hydra.
      <span class="scite-citeref-number" data-reference="US-CERT TA18-074A" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" target="_blank">
         [6]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT APT Energy Oct 2017" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" target="_blank">
         [7]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Kali Hydra" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://tools.kali.org/password-attacks/hydra" target="_blank">
         [8]
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
      malware attempts to connect to Windows shares for lateral movement by using a generated list of usernames, which center around permutations of the username Administrator, and weak passwords.
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" target="_blank">
         [9]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster RATs" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-RAT-and-Staging-Report.pdf" target="_blank">
         [10]
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
      used a tool called BruteForcer to perform a brute force attack.
      <span class="scite-citeref-number" data-reference="Symantec Leafminer July 2018" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://www.symantec.com/blogs/threat-intelligence/leafminer-espionage-middle-east" target="_blank">
         [11]
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
      uses a list of known credentials gathered through credential dumping to guess passwords to accounts as it spreads throughout a network.
      <span class="scite-citeref-number" data-reference="Cylance Cleaver" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf" target="_blank">
         [2]
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
      has used brute force techniques to obtain credentials.
      <span class="scite-citeref-number" data-reference="FireEye APT34 Webinar Dec 2017" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://www.brighttalk.com/webcast/10703/296317/apt34-new-targeted-attack-in-the-middle-east" target="_blank">
         [12]
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
      may attempt to connect to systems within a victim's network using
      <code>
       net use
      </code>
      commands and a predefined list or collection of passwords.
      <span class="scite-citeref-number" data-reference="Kaspersky Turla" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://securelist.com/the-epic-turla-operation/65545/" target="_blank">
         [13]
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
  Set account lockout policies after a certain number of failed login attempts to prevent passwords from being guessed. Use multifactor authentication. Follow best practices for mitigating access to
  <a href="https://attack.mitre.org/techniques/T1078">
   Valid Accounts
  </a>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  It is difficult to detect when hashes are cracked, since this is generally done outside the scope of the target network.
 </p>
 <p>
  Monitor authentication logs for system and application login failures of
  <a href="https://attack.mitre.org/techniques/T1078">
   Valid Accounts
  </a>
  . If authentication failures are high, then there may be a brute force attempt to gain access to a system using legitimate credentials.
 </p>
 <p>
  Also monitor for many failed authentication attempts across various accounts that may result from password spraying attempts.
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
       <a class="external text" href="https://en.wikipedia.org/wiki/Password_cracking" name="scite-1" rel="nofollow" target="_blank">
        Wikipedia. (n.d.). Password cracking. Retrieved December 23, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf" name="scite-2" rel="nofollow" target="_blank">
        Cylance. (2014, December). Operation Cleaver. Retrieved September 14, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.blackhillsinfosec.com/?p=4645" name="scite-3" rel="nofollow" target="_blank">
        Thyer, J. (2015, October 30). Password Spraying &amp; Other Fun with RPCCLIENT. Retrieved April 25, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://attack.mitre.org/docs/APT3_Adversary_Emulation_Plan.pdf" name="scite-4" rel="nofollow" target="_blank">
        Korban, C, et al. (2017, September). APT3 Adversary Emulation Plan. Retrieved January 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="http://gosecure.net/2018/02/14/chaos-stolen-backdoor-rising/" name="scite-5" rel="nofollow" target="_blank">
        Sebastian Feldmann. (2018, February 14). Chaos: a Stolen Backdoor Rising Again. Retrieved March 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" name="scite-6" rel="nofollow" target="_blank">
        US-CERT. (2018, March 16). Alert (TA18-074A): Russian Government Cyber Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" name="scite-7" rel="nofollow" target="_blank">
        US-CERT. (2017, October 20). Alert (TA17-293A): Advanced Persistent Threat Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved November 2, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="8.5">
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://tools.kali.org/password-attacks/hydra" name="scite-8" rel="nofollow" target="_blank">
        Kali. (2014, February 18). THC-Hydra. Retrieved November 2, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" name="scite-9" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Unraveling the Long Thread of the Sony Attack. Retrieved February 25, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-RAT-and-Staging-Report.pdf" name="scite-10" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Remote Administration Tools &amp; Content Staging Malware Report. Retrieved March 16, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/leafminer-espionage-middle-east" name="scite-11" rel="nofollow" target="_blank">
        Symantec Security Response. (2018, July 25). Leafminer: New Espionage Campaigns Targeting Middle Eastern Regions. Retrieved August 28, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.brighttalk.com/webcast/10703/296317/apt34-new-targeted-attack-in-the-middle-east" name="scite-12" rel="nofollow" target="_blank">
        Davis, S. and Caban, D. (2017, December 19). APT34 - New Targeted Attack in the Middle East. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/the-epic-turla-operation/65545/" name="scite-13" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2014, August 7). The Epic Turla Operation: Solving some of the mysteries of Snake/Uroburos. Retrieved December 11, 2014.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
