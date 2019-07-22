<div class="container-fluid">
 <h1>
  Pass the Ticket
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Pass the ticket (PtT) is a method of authenticating to a system using Kerberos tickets without having access to an account's password. Kerberos authentication can be used as the first step to lateral movement to a remote system.
   </p>
   <p>
    In this technique, valid Kerberos tickets for
    <a href="https://attack.mitre.org/techniques/T1078">
     Valid Accounts
    </a>
    are captured by
    <a href="https://attack.mitre.org/techniques/T1003">
     Credential Dumping
    </a>
    . A user's service tickets or ticket granting ticket (TGT) may be obtained, depending on the level of access. A service ticket allows for access to a particular resource, whereas a TGT can be used to request service tickets from the Ticket Granting Service (TGS) to access any resource the user has privileges to access.
    <span class="scite-citeref-number" data-reference="ADSecurity AD Kerberos Attacks" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://adsecurity.org/?p=556" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="GentilKiwi Pass the Ticket" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="http://blog.gentilkiwi.com/securite/mimikatz/pass-the-ticket-kerberos" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Silver Tickets can be obtained for services that use Kerberos as an authentication mechanism and are used to generate tickets to access that particular resource and the system that hosts the resource (e.g., SharePoint).
    <span class="scite-citeref-number" data-reference="ADSecurity AD Kerberos Attacks" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://adsecurity.org/?p=556" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Golden Tickets can be obtained for the domain using the Key Distribution Service account KRBTGT account NTLM hash, which enables generation of TGTs for any account in Active Directory.
    <span class="scite-citeref-number" data-reference="Campbell 2014" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="http://defcon.org/images/defcon-22/dc-22-presentations/Campbell/DEFCON-22-Christopher-Campbell-The-Secret-Life-of-Krbtgt.pdf" target="_blank">
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
      : T1097
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
      Requires Microsoft Windows as a target system and Kerberos authentication enabled.
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
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Contributors:
      </span>
      Ryan Becwar; Vincent Le Toux
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
     <a href="https://attack.mitre.org/groups/G0016">
      APT29
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0016">
       APT29
      </a>
      used Kerberos ticket attacks for lateral movement.
      <span class="scite-citeref-number" data-reference="Mandiant No Easy Breach" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="http://www.slideshare.net/MatthewDunwoody1/no-easy-breach-derby-con-2016" target="_blank">
         [4]
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
      successfully gained remote access by using pass the ticket.
      <span class="scite-citeref-number" data-reference="Cybereason Cobalt Kitty 2017" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://cdn2.hubspot.net/hubfs/3354902/Cybereason%20Labs%20Analysis%20Operation%20Cobalt%20Kitty.pdf" target="_blank">
         [5]
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
      has created forged Kerberos Ticket Granting Ticket (TGT) and Ticket Granting Service (TGS) tickets to maintain administrative access.
      <span class="scite-citeref-number" data-reference="Secureworks BRONZE BUTLER Oct 2017" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.secureworks.com/research/bronze-butler-targets-japanese-businesses" target="_blank">
         [6]
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
      can leverage its implementation of
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      to obtain and use Silver and Golden Tickets.
      <span class="scite-citeref-number" data-reference="Github PowerShell Empire" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://github.com/PowerShellEmpire/Empire" target="_blank">
         [7]
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
      has used
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      to generate Kerberos golden tickets.
      <span class="scite-citeref-number" data-reference="NCC Group APT15 Alive and Strong" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0002">
      Mimikatz
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      ’s
      <code>
       LSADUMP::DCSync
      </code>
      ,
      <code>
       KERBEROS::Golden
      </code>
      , and
      <code>
       KERBEROS::PTT
      </code>
      modules implement the three steps required to extract the krbtgt account hash and create/use Kerberos tickets.
      <span class="scite-citeref-number" data-reference="Adsecurity Mimikatz Guide" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://adsecurity.org/?page_id=1821" target="_blank">
         [9]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="AdSecurity Kerberos GT Aug 2015" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://adsecurity.org/?p=1640" target="_blank">
         [10]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Harmj0y DCSync Sept 2015" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="http://www.harmj0y.net/blog/redteaming/mimikatz-and-dcsync-and-extrasids-oh-my/" target="_blank">
         [11]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="NCSC Joint Report Public Tools" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://s3.eu-west-1.amazonaws.com/ncsc-content/files/Joint%20report%20on%20publicly%20available%20hacking%20tools%20%28NCSC%29.pdf" target="_blank">
         [12]
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
      Some
      <a href="https://attack.mitre.org/software/S0053">
       SeaDuke
      </a>
      samples have a module to use pass the ticket with Kerberos for authentication.
      <span class="scite-citeref-number" data-reference="Symantec Seaduke 2015" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="http://www.symantec.com/connect/blogs/forkmeiamfamous-seaduke-latest-weapon-duke-armory" target="_blank">
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
  Monitor domains for unusual credential logons. Limit credential overlap across systems to prevent the damage of credential compromise. Ensure that local administrator accounts have complex, unique passwords. Do not allow a user to be a local administrator for multiple systems. Limit domain admin account permissions to domain controllers and limited servers. Delegate other admin functions to separate accounts.
  <span class="scite-citeref-number" data-reference="ADSecurity AD Kerberos Attacks" id="scite-ref-1-a">
   <sup>
    <a aria-describedby="qtip-0" data-hasqtip="0" href="https://adsecurity.org/?p=556" target="_blank">
     [1]
    </a>
   </sup>
  </span>
 </p>
 <p>
  For containing the impact of a previously generated golden ticket, reset the built-in KRBTGT account password twice, which will invalidate any existing golden tickets that have been created with the KRBTGT hash and other Kerberos tickets derived from it.
  <span class="scite-citeref-number" data-reference="CERT-EU Golden Ticket Protection" id="scite-ref-14-a">
   <sup>
    <a aria-describedby="qtip-13" data-hasqtip="13" href="https://cert.europa.eu/static/WhitePapers/UPDATED%20-%20CERT-EU_Security_Whitepaper_2014-007_Kerberos_Golden_Ticket_Protection_v1_4.pdf" target="_blank">
     [14]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Attempt to identify and block unknown or malicious software that could be used to obtain Kerberos tickets and use them to authenticate by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-15-a">
   <sup>
    <a aria-describedby="qtip-14" data-hasqtip="14" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [15]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-16-a">
   <sup>
    <a aria-describedby="qtip-15" data-hasqtip="15" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [16]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-17-a">
   <sup>
    <a aria-describedby="qtip-16" data-hasqtip="16" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [17]
    </a>
   </sup>
  </span>
  or Software Restriction Policies
  <span class="scite-citeref-number" data-reference="Corio 2008" id="scite-ref-18-a">
   <sup>
    <a aria-describedby="qtip-17" data-hasqtip="17" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" target="_blank">
     [18]
    </a>
   </sup>
  </span>
  where appropriate.
  <span class="scite-citeref-number" data-reference="TechNet Applocker vs SRP" id="scite-ref-19-a">
   <sup>
    <a aria-describedby="qtip-18" data-hasqtip="18" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" target="_blank">
     [19]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Audit all Kerberos authentication and credential use events and review for discrepancies. Unusual remote authentication events that correlate with other suspicious activity (such as writing and executing binaries) may indicate malicious activity.
 </p>
 <p>
  Event ID 4769 is generated on the Domain Controller when using a golden ticket after the KRBTGT password has been reset twice, as mentioned in the mitigation section. The status code 0x1F indicates the action has failed due to "Integrity check on decrypted field failed" and indicates misuse by a previously invalidated golden ticket.
  <span class="scite-citeref-number" data-reference="CERT-EU Golden Ticket Protection" id="scite-ref-14-a">
   <sup>
    <a aria-describedby="qtip-13" data-hasqtip="13" href="https://cert.europa.eu/static/WhitePapers/UPDATED%20-%20CERT-EU_Security_Whitepaper_2014-007_Kerberos_Golden_Ticket_Protection_v1_4.pdf" target="_blank">
     [14]
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
       <a class="external text" href="https://adsecurity.org/?p=556" name="scite-1" rel="nofollow" target="_blank">
        Metcalf, S. (2014, November 22). Mimikatz and Active Directory Kerberos Attacks. Retrieved June 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.gentilkiwi.com/securite/mimikatz/pass-the-ticket-kerberos" name="scite-2" rel="nofollow" target="_blank">
        Deply, B. (2014, January 13). Pass the ticket. Retrieved June 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="http://defcon.org/images/defcon-22/dc-22-presentations/Campbell/DEFCON-22-Christopher-Campbell-The-Secret-Life-of-Krbtgt.pdf" name="scite-3" rel="nofollow" target="_blank">
        Campbell, C. (2014). The Secret Life of Krbtgt. Retrieved December 4, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.slideshare.net/MatthewDunwoody1/no-easy-breach-derby-con-2016" name="scite-4" rel="nofollow" target="_blank">
        Dunwoody, M. and Carr, N.. (2016, September 27). No Easy Breach DerbyCon 2016. Retrieved October 4, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://cdn2.hubspot.net/hubfs/3354902/Cybereason%20Labs%20Analysis%20Operation%20Cobalt%20Kitty.pdf" name="scite-5" rel="nofollow" target="_blank">
        Dahan, A. (2017). Operation Cobalt Kitty. Retrieved December 27, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/bronze-butler-targets-japanese-businesses" name="scite-6" rel="nofollow" target="_blank">
        Counter Threat Unit Research Team. (2017, October 12). BRONZE BUTLER Targets Japanese Enterprises. Retrieved January 4, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellEmpire/Empire" name="scite-7" rel="nofollow" target="_blank">
        Schroeder, W., Warner, J., Nelson, M. (n.d.). Github PowerShellEmpire. Retrieved April 28, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/" name="scite-8" rel="nofollow" target="_blank">
        Smallridge, R. (2018, March 10). APT15 is alive and strong: An analysis of RoyalCli and RoyalDNS. Retrieved April 4, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://adsecurity.org/?page_id=1821" name="scite-9" rel="nofollow" target="_blank">
        Metcalf, S. (2015, November 13). Unofficial Guide to Mimikatz &amp; Command Reference. Retrieved December 23, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://adsecurity.org/?p=1640" name="scite-10" rel="nofollow" target="_blank">
        Metcalf, S. (2015, August 7). Kerberos Golden Tickets are Now More Golden. Retrieved December 1, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="11.5">
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.harmj0y.net/blog/redteaming/mimikatz-and-dcsync-and-extrasids-oh-my/" name="scite-11" rel="nofollow" target="_blank">
        Schroeder, W. (2015, September 22). Mimikatz and DCSync and ExtraSids, Oh My. Retrieved December 4, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://s3.eu-west-1.amazonaws.com/ncsc-content/files/Joint%20report%20on%20publicly%20available%20hacking%20tools%20%28NCSC%29.pdf" name="scite-12" rel="nofollow" target="_blank">
        The Australian Cyber Security Centre (ACSC), the Canadian Centre for Cyber Security (CCCS), the New Zealand National Cyber Security Centre (NZ NCSC), CERT New Zealand, the UK National Cyber Security Centre (UK NCSC) and the US National Cybersecurity and Communications Integration Center (NCCIC). (2018, October 11). Joint report on publicly available hacking tools. Retrieved March 11, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/connect/blogs/forkmeiamfamous-seaduke-latest-weapon-duke-armory" name="scite-13" rel="nofollow" target="_blank">
        Symantec Security Response. (2015, July 13). “Forkmeiamfamous”: Seaduke, latest weapon in the Duke armory. Retrieved July 22, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://cert.europa.eu/static/WhitePapers/UPDATED%20-%20CERT-EU_Security_Whitepaper_2014-007_Kerberos_Golden_Ticket_Protection_v1_4.pdf" name="scite-14" rel="nofollow" target="_blank">
        Abolins, D., Boldea, C., Socha, K., Soria-Machado, M. (2016, April 26). Kerberos Golden Ticket Protection. Retrieved July 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-15" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-16" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-17" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" name="scite-18" rel="nofollow" target="_blank">
        Corio, C., &amp; Sayana, D. P. (2008, June). Application Lockdown with Software Restriction Policies. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" name="scite-19" rel="nofollow" target="_blank">
        Microsoft. (2012, June 27). Using Software Restriction Policies and AppLocker Policies. Retrieved April 7, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
