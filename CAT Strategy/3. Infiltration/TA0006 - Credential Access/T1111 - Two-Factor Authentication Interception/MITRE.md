<div class="container-fluid">
 <h1>
  Two-Factor Authentication Interception
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Use of two- or multifactor authentication is recommended and provides a higher level of security than user names and passwords alone, but organizations should be aware of techniques that could be used to intercept and bypass these security mechanisms. Adversaries may target authentication mechanisms, such as smart cards, to gain access to systems, services, and network resources.
   </p>
   <p>
    If a smart card is used for two-factor authentication (2FA), then a keylogger will need to be used to obtain the password associated with a smart card during normal use. With both an inserted card and access to the smart card password, an adversary can connect to a network resource using the infected system to proxy the authentication with the inserted hardware token.
    <span class="scite-citeref-number" data-reference="Mandiant M Trends 2011" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://dl.mandiant.com/EE/assets/PDF_MTrends_2011.pdf" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries may also employ a keylogger to similarly target other hardware tokens, such as RSA SecurID. Capturing token input (including a user's personal identification code) may provide temporary access (i.e. replay the one-time passcode until the next value rollover) as well as possibly enabling adversaries to reliably predict future authentication values (given access to both the algorithm and any seed values used to generate appended temporary codes).
    <span class="scite-citeref-number" data-reference="GCN RSA June 2011" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://gcn.com/articles/2011/06/07/rsa-confirms-tokens-used-to-hack-lockheed.aspx" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Other methods of 2FA may be intercepted and used by an adversary to authenticate. It is common for one-time codes to be sent via out-of-band communications (email, SMS). If the device and/or service is not secured, then it may be vulnerable to interception. Although primarily focused on by cyber criminals, these authentication mechanisms have been targeted by advanced actors.
    <span class="scite-citeref-number" data-reference="Operation Emmental" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="http://www.trendmicro.com/cloud-content/us/pdfs/security-intelligence/white-papers/wp-finding-holes-operation-emmental.pdf" target="_blank">
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
      : T1111
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
      Linux, Windows, macOS
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
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      API monitoring, Process monitoring, Kernel drivers
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
      John Lambert, Microsoft Threat Intelligence Center
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
     <a href="https://attack.mitre.org/software/S0018">
      Sykipot
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0018">
       Sykipot
      </a>
      is known to contain functionality that enables targeting of smart card technologies to proxy authentication for connections to restricted network resources using detected hardware tokens.
      <span class="scite-citeref-number" data-reference="Alienvault Sykipot DOD Smart Cards" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.alienvault.com/open-threat-exchange/blog/sykipot-variant-hijacks-dod-and-windows-smart-cards" target="_blank">
         [4]
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
  Remove smart cards when not in use. Protect devices and services used to transmit and receive out-of-band codes.
 </p>
 <p>
  Identify and block potentially malicious software that may be used to intercept 2FA credentials on a system by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-5-a">
   <sup>
    <a aria-describedby="qtip-4" data-hasqtip="4" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [5]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-6-a">
   <sup>
    <a aria-describedby="qtip-5" data-hasqtip="5" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [6]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [7]
    </a>
   </sup>
  </span>
  or Software Restriction Policies
  <span class="scite-citeref-number" data-reference="Corio 2008" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" target="_blank">
     [8]
    </a>
   </sup>
  </span>
  where appropriate.
  <span class="scite-citeref-number" data-reference="TechNet Applocker vs SRP" id="scite-ref-9-a">
   <sup>
    <a aria-describedby="qtip-8" data-hasqtip="8" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" target="_blank">
     [9]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Detecting use of proxied smart card connections by an adversary may be difficult because it requires the token to be inserted into a system; thus it is more likely to be in use by a legitimate user and blend in with other network behavior.
 </p>
 <p>
  Similar to
  <a href="https://attack.mitre.org/techniques/T1056">
   Input Capture
  </a>
  , keylogging activity can take various forms but can may be detected via installation of a driver, setting a hook, or usage of particular API calls associated with polling to intercept keystrokes.
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
       <a class="external text" href="https://dl.mandiant.com/EE/assets/PDF_MTrends_2011.pdf" name="scite-1" rel="nofollow" target="_blank">
        Mandiant. (2011, January 27). Mandiant M-Trends 2011. Retrieved January 10, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://gcn.com/articles/2011/06/07/rsa-confirms-tokens-used-to-hack-lockheed.aspx" name="scite-2" rel="nofollow" target="_blank">
        Jackson, William. (2011, June 7). RSA confirms its tokens used in Lockheed hack. Retrieved September 24, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.trendmicro.com/cloud-content/us/pdfs/security-intelligence/white-papers/wp-finding-holes-operation-emmental.pdf" name="scite-3" rel="nofollow" target="_blank">
        Sancho, D., Hacquebord, F., Link, R. (2014, July 22). Finding Holes Operation Emmental. Retrieved February 9, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.alienvault.com/open-threat-exchange/blog/sykipot-variant-hijacks-dod-and-windows-smart-cards" name="scite-4" rel="nofollow" target="_blank">
        Blasco, J. (2012, January 12). Sykipot variant hijacks DOD and Windows smart cards. Retrieved January 10, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-5" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="6.5">
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-6" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-7" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" name="scite-8" rel="nofollow" target="_blank">
        Corio, C., &amp; Sayana, D. P. (2008, June). Application Lockdown with Software Restriction Policies. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" name="scite-9" rel="nofollow" target="_blank">
        Microsoft. (2012, June 27). Using Software Restriction Policies and AppLocker Policies. Retrieved April 7, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
