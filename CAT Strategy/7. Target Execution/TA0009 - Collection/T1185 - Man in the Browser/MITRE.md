<div class="container-fluid">
 <h1>
  Man in the Browser
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries can take advantage of security vulnerabilities and inherent functionality in browser software to change content, modify behavior, and intercept information as part of various man in the browser techniques.
    <span class="scite-citeref-number" data-reference="Wikipedia Man in the Browser" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://en.wikipedia.org/wiki/Man-in-the-browser" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    A specific example is when an adversary injects software into a browser that allows an them to inherit cookies, HTTP sessions, and SSL client certificates of a user and use the browser as a way to pivot into an authenticated intranet.
    <span class="scite-citeref-number" data-reference="Cobalt Strike Browser Pivot" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.cobaltstrike.com/help-browser-pivoting" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="ICEBRG Chrome Extensions" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.icebrg.io/blog/malicious-chrome-extensions-enable-criminals-to-impact-over-half-a-million-users-and-global-businesses" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Browser pivoting requires the SeDebugPrivilege and a high-integrity process to execute. Browser traffic is pivoted from the adversary's browser through the user's browser by setting up an HTTP proxy which will redirect any HTTP and HTTPS traffic. This does not alter the user's traffic in any way. The proxy connection is severed as soon as the browser is closed. Whichever browser process the proxy is injected into, the adversary assumes the security context of that process. Browsers typically create a new process for each tab that is opened and permissions and certificates are separated accordingly. With these permissions, an adversary could browse to any resource on an intranet that is accessible through the browser and which the browser has sufficient permissions, such as Sharepoint or webmail. Browser pivoting also eliminates the security provided by 2-factor authentication.
    <span class="scite-citeref-number" data-reference="cobaltstrike manual" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://cobaltstrike.com/downloads/csmanual38.pdf" target="_blank">
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
      : T1185
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
      : Collection
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
      Authentication logs, Packet capture, Process monitoring, API monitoring
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
      Justin Warner, ICEBRG
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
     <a href="https://attack.mitre.org/software/S0154">
      Cobalt Strike
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0154">
       Cobalt Strike
      </a>
      can perform browser pivoting and inject into a user's browser to inherit cookies, authenticated HTTP sessions, and client SSL certificates.
      <span class="scite-citeref-number" data-reference="cobaltstrike manual" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://cobaltstrike.com/downloads/csmanual38.pdf" target="_blank">
         [4]
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
      uses web injects and browser redirection to trick the user into providing their login credentials on a fake or modified web page.
      <span class="scite-citeref-number" data-reference="Fidelis TrickBot Oct 2016" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.fidelissecurity.com/threatgeek/2016/10/trickbot-we-missed-you-dyre" target="_blank">
         [5]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="IBM TrickBot Nov 2016" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://securityintelligence.com/tricks-of-the-trade-a-deeper-look-into-trickbots-machinations/" target="_blank">
         [6]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Microsoft Totbrick Oct 2017" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.microsoft.com/en-us/wdsi/threats/malware-encyclopedia-description?Name=Trojan:Win32/Totbrick" target="_blank">
         [7]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Trend Micro Trickbot Nov 2018" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://blog.trendmicro.com/trendlabs-security-intelligence/trickbot-shows-off-new-trick-password-grabber-module/" target="_blank">
         [8]
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
  Since browser pivoting requires a high integrity process to launch from, restricting user permissions and addressing Privilege Escalation and
  <a href="https://attack.mitre.org/techniques/T1088">
   Bypass User Account Control
  </a>
  opportunities can limit the exposure to this technique.
 </p>
 <p>
  Close all browser sessions regularly and when they are no longer needed.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  This is a difficult technique to detect because adversary traffic would be masked by normal user traffic. No new processes are created and no additional software touches disk. Authentication logs can be used to audit logins to specific web applications, but determining malicious logins versus benign logins may be difficult if activity matches typical user behavior. Monitor for process injection against browser applications
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
       <a class="external text" href="https://en.wikipedia.org/wiki/Man-in-the-browser" name="scite-1" rel="nofollow" target="_blank">
        Wikipedia. (2017, October 28). Man-in-the-browser. Retrieved January 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cobaltstrike.com/help-browser-pivoting" name="scite-2" rel="nofollow" target="_blank">
        Mudge, R. (n.d.). Browser Pivoting. Retrieved January 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.icebrg.io/blog/malicious-chrome-extensions-enable-criminals-to-impact-over-half-a-million-users-and-global-businesses" name="scite-3" rel="nofollow" target="_blank">
        De Tore, M., Warner, J. (2018, January 15). MALICIOUS CHROME EXTENSIONS ENABLE CRIMINALS TO IMPACT OVER HALF A MILLION USERS AND GLOBAL BUSINESSES. Retrieved January 17, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://cobaltstrike.com/downloads/csmanual38.pdf" name="scite-4" rel="nofollow" target="_blank">
        Strategic Cyber LLC. (2017, March 14). Cobalt Strike Manual. Retrieved May 24, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="5.0">
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fidelissecurity.com/threatgeek/2016/10/trickbot-we-missed-you-dyre" name="scite-5" rel="nofollow" target="_blank">
        Reaves, J. (2016, October 15). TrickBot: We Missed you, Dyre. Retrieved August 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://securityintelligence.com/tricks-of-the-trade-a-deeper-look-into-trickbots-machinations/" name="scite-6" rel="nofollow" target="_blank">
        Keshet, L. (2016, November 09). Tricks of the Trade: A Deeper Look Into TrickBot’s Machinations. Retrieved August 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.microsoft.com/en-us/wdsi/threats/malware-encyclopedia-description?Name=Trojan:Win32/Totbrick" name="scite-7" rel="nofollow" target="_blank">
        Pornasdoro, A. (2017, October 12). Trojan:Win32/Totbrick. Retrieved September 14, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/trickbot-shows-off-new-trick-password-grabber-module/" name="scite-8" rel="nofollow" target="_blank">
        Anthony, N., Pascual, C.. (2018, November 1). Trickbot Shows Off New Trick: Password Grabber Module. Retrieved November 16, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
