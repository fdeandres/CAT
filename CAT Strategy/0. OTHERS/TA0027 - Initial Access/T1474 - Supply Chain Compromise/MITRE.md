<div class="container-fluid">
 <h1>
  Supply Chain Compromise
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    As further described in
    <a href="https://attack.mitre.org/techniques/T1195">
     Supply Chain Compromise
    </a>
    , supply chain compromise is the manipulation of products or product delivery mechanisms prior to receipt by a final consumer for the purpose of data or system compromise. Somewhat related, adversaries could also identify and exploit inadvertently present vulnerabilities. In many cases, it may be difficult to be certain whether exploitable functionality is due to malicious intent or simply inadvertent mistake.
   </p>
   <p>
    Related PRE-ATT&amp;CK techniques include:
   </p>
   <ul>
    <li>
     <a href="https://attack.mitre.org/techniques/T1389">
      Identify vulnerabilities in third-party software libraries
     </a>
     - Third-party libraries incorporated into mobile apps could contain malicious behavior, privacy-invasive behavior, or exploitable vulnerabilities. An adversary could deliberately insert malicious behavior or could exploit inadvertent vulnerabilities. For example, Ryan Welton of NowSecure identified exploitable remote code execution vulnerabilities in a third-party advertisement library
     <span class="scite-citeref-number" data-reference="NowSecure-RemoteCode" id="scite-ref-1-a">
      <sup>
       <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.nowsecure.com/blog/2015/06/15/a-pattern-for-remote-code-execution-using-arbitrary-file-writes-and-multidex-applications/" target="_blank">
        [1]
       </a>
      </sup>
     </span>
     . Grace et al. identified security issues in mobile advertisement libraries
     <span class="scite-citeref-number" data-reference="Grace-Advertisement" id="scite-ref-2-a">
      <sup>
       <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.nowsecure.com/blog/2015/06/15/a-pattern-for-remote-code-execution-using-arbitrary-file-writes-and-multidex-applications/" target="_blank">
        [2]
       </a>
      </sup>
     </span>
     .
    </li>
    <li>
     <a href="https://attack.mitre.org/techniques/T1394">
      Distribute malicious software development tools
     </a>
     - As demonstrated by the XcodeGhost attack
     <span class="scite-citeref-number" data-reference="PaloAlto-XcodeGhost1" id="scite-ref-3-a">
      <sup>
       <a aria-describedby="qtip-2" data-hasqtip="2" href="http://researchcenter.paloaltonetworks.com/2015/09/novel-malware-xcodeghost-modifies-xcode-infects-apple-ios-apps-and-hits-app-store/" target="_blank">
        [3]
       </a>
      </sup>
     </span>
     , app developers could be provided with modified versions of software development tools (e.g. compilers) that automatically inject malicious or exploitable code into applications.
    </li>
   </ul>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1474
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Tactic Type:
      </span>
      Post-Adversary Device Access
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Tactic
      </span>
      : Initial Access
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Platform:
      </span>
      Android, iOS
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
       MTC ID:
      </span>
      <a href="https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-6.html" target="_blank">
       APP-6
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
     <a href="https://attack.mitre.org/software/S0309">
      Adups
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0309">
       Adups
      </a>
      was pre-installed on Android devices from some vendors.
      <span class="scite-citeref-number" data-reference="NYTimes-BackDoor" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.nytimes.com/2016/11/16/us/politics/china-phones-software-security.html" target="_blank">
         [4]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="BankInfoSecurity-BackDoor" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="http://www.bankinfosecurity.com/did-chinese-spyware-linger-in-us-phones-a-9534" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0319">
      Allwinner
     </a>
    </td>
    <td>
     <p>
      A Linux kernel distributed by
      <a href="https://attack.mitre.org/software/S0319">
       Allwinner
      </a>
      reportedly contained an simple backdoor that could be used to obtain root access. It was believed to have been left in the kernel by mistake by the authors.
      <span class="scite-citeref-number" data-reference="HackerNews-Allwinner" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://thehackernews.com/2016/05/android-kernal-exploit.html" target="_blank">
         [6]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0328">
      Stealth Mango
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0328">
       Stealth Mango
      </a>
      in at least one case may have been installed using physical access to the device by a repair shop.
      <span class="scite-citeref-number" data-reference="Lookout-StealthMango" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://info.lookout.com/rs/051-ESQ-475/images/lookout-stealth-mango-srr-us.pdf" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0297">
      XcodeGhost
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0297">
       XcodeGhost
      </a>
      was injected into apps by a modified version of Xcode (Apple's software development tool).
      <span class="scite-citeref-number" data-reference="PaloAlto-XcodeGhost1" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="http://researchcenter.paloaltonetworks.com/2015/09/novel-malware-xcodeghost-modifies-xcode-infects-apple-ios-apps-and-hits-app-store/" target="_blank">
         [3]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PaloAlto-XcodeGhost" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="http://researchcenter.paloaltonetworks.com/2015/09/update-xcodeghost-attacker-can-phish-passwords-and-open-urls-though-infected-apps/" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
  </tbody>
 </table>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <ul>
  <li>
   Insecure third-party libraries could be detected by application vetting techniques. For example, Google's
   <a href="https://developer.android.com/google/play/asi">
    App Security Improvement Program
   </a>
   detects the use of third-party libraries with known vulnerabilities within Android apps submitted to the Google Play Store.
  </li>
  <li>
   Malicious software development tools could be detected by enterprises deploying integrity checking software to the computers that they use to develop code to detect presence of unauthorized, modified software development tools.
  </li>
 </ul>
 <h2 class="pt-3" id="references">
  References
 </h2>
 <div class="row">
  <div class="col">
   <ol>
    <li>
     <span class="scite-citation" id="scite-1">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.nowsecure.com/blog/2015/06/15/a-pattern-for-remote-code-execution-using-arbitrary-file-writes-and-multidex-applications/" name="scite-1" rel="nofollow" target="_blank">
        Ryan Welton. (2015, June 15). A Pattern for Remote Code Execution using Arbitrary File Writes and MultiDex Applications. Retrieved December 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.nowsecure.com/blog/2015/06/15/a-pattern-for-remote-code-execution-using-arbitrary-file-writes-and-multidex-applications/" name="scite-2" rel="nofollow" target="_blank">
        M. Grace et al. (2012, April 16-18). Unsafe exposure analysis of mobile in-app advertisements. Retrieved December 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2015/09/novel-malware-xcodeghost-modifies-xcode-infects-apple-ios-apps-and-hits-app-store/" name="scite-3" rel="nofollow" target="_blank">
        Claud Xiao. (2015, September 17). Novel Malware XcodeGhost Modifies Xcode, Infects Apple iOS Apps and Hits App Store. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.nytimes.com/2016/11/16/us/politics/china-phones-software-security.html" name="scite-4" rel="nofollow" target="_blank">
        Matt Apuzzo and Michael S. Schmidt. (2016, November 15). Secret Back Door in Some U.S. Phones Sent Data to China, Analysts Say. Retrieved February 6, 2017.
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
       <a class="external text" href="http://www.bankinfosecurity.com/did-chinese-spyware-linger-in-us-phones-a-9534" name="scite-5" rel="nofollow" target="_blank">
        Jeremy Kirk. (2016, November 16). Why Did Chinese Spyware Linger in U.S. Phones?. Retrieved February 6, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://thehackernews.com/2016/05/android-kernal-exploit.html" name="scite-6" rel="nofollow" target="_blank">
        Mohit Kumar. (2016, May 11). Kernel Backdoor found in Gadgets Powered by Popular Chinese ARM Maker. Retrieved September 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://info.lookout.com/rs/051-ESQ-475/images/lookout-stealth-mango-srr-us.pdf" name="scite-7" rel="nofollow" target="_blank">
        Lookout. (n.d.). Stealth Mango &amp; Tangelo. Retrieved September 27, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2015/09/update-xcodeghost-attacker-can-phish-passwords-and-open-urls-though-infected-apps/" name="scite-8" rel="nofollow" target="_blank">
        Claud Xiao. (2015, September 18). Update: XcodeGhost Attacker Can Phish Passwords and Open URLs through Infected Apps. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
