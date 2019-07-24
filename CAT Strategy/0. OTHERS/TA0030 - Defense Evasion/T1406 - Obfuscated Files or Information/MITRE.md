<div class="container-fluid">
 <h1>
  Obfuscated Files or Information
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An app could contain malicious code in obfuscated or encrypted form, then deobfuscate or decrypt the code at runtime to evade many app vetting techniques.
    <span class="scite-citeref-number" data-reference="Rastogi" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://pages.cs.wisc.edu/~vrastogi/static/papers/rcj13b.pdf" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Zhou" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="http://ieeexplore.ieee.org/document/6234407" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="TrendMicro-Obad" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="http://blog.trendmicro.com/trendlabs-security-intelligence/cybercriminals-improve-android-malware-stealth-routines-with-obad/" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Xiao-iOS" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="http://www.slideshare.net/Shakacon/fruit-vs-zombies-defeat-nonjailbroken-ios-malware-by-claud-xiao" target="_blank">
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
      : T1406
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
      : Defense Evasion
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
      <a href="https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-21.html" target="_blank">
       APP-21
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
      : 2.0
     </div>
    </div>
   </div>
  </div>
 </div>
 <h2 class="pt-3" id="mitigations">
  Mitigations
 </h2>
 <table class="table table-bordered table-light mt-2">
  <thead>
   <tr>
    <th scope="col">
     Mitigation
    </th>
    <th scope="col">
     Description
    </th>
   </tr>
  </thead>
  <tbody class="bg-white">
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1005">
      Application Vetting
     </a>
    </td>
    <td>
     Application vetting techniques may be able to alert to the presence of obfuscated or encrypted code in applications, and such applications could have extra scrutiny applied. Unfortunately, this mitigation is likely impractical, as many legitimate applications apply code obfuscation or encryption to resist adversary techniques such as Repackaged Application. Dynamic analysis when used in application vetting may in some cases be able to identify malicious code in obfuscated or encrypted form by detecting the code at execution time (after it is deobfuscated or decrypted). Some application vetting techniques apply reputation analysis of the application developer and can alert to potentially suspicious applications without actual examination of application code.
    </td>
   </tr>
  </tbody>
 </table>
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
     <a href="https://attack.mitre.org/software/S0293">
      BrainTest
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0293">
       BrainTest
      </a>
      stores a secondary Android app package (APK) in its assets directory in encrypted form, and decrypts the payload at runtime.
      <span class="scite-citeref-number" data-reference="Lookout-BrainTest" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://blog.lookout.com/blog/2016/01/06/brain-test-re-emerges/" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0323">
      Charger
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0323">
       Charger
      </a>
      encodes strings into binary arrays to make it difficult to inspect them. It also loads code from encrypted resources dynamically and includes meaningless commands that mask the actual commands passing through.
      <span class="scite-citeref-number" data-reference="CheckPoint-Charger" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="http://blog.checkpoint.com/2017/01/24/charger-malware/" target="_blank">
         [6]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0286">
      OBAD
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0286">
       OBAD
      </a>
      contains encrypted code along with an obfuscated decryption routine to make it difficult to analyze.
      <span class="scite-citeref-number" data-reference="TrendMicro-Obad" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="http://blog.trendmicro.com/trendlabs-security-intelligence/cybercriminals-improve-android-malware-stealth-routines-with-obad/" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0326">
      RedDrop
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0326">
       RedDrop
      </a>
      contains malicious embedded files, which are compiled to initiate the malicious functionality.
      <span class="scite-citeref-number" data-reference="Wandera-RedDrop" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.wandera.com/reddrop-malware/" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0312">
      WireLurker
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0312">
       WireLurker
      </a>
      obfuscates its payload through complex code structure, multiple component versions, file hiding, code obfuscation and customized encryption to thwart anti-reversing.
      <span class="scite-citeref-number" data-reference="PaloAlto-WireLurker" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://researchcenter.paloaltonetworks.com/2014/11/wirelurker-new-era-os-x-ios-malware/" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0318">
      XLoader
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0318">
       XLoader
      </a>
      loads an encrypted DEX code payload.
      <span class="scite-citeref-number" data-reference="TrendMicro-XLoader" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://blog.trendmicro.com/trendlabs-security-intelligence/xloader-android-spyware-and-banking-trojan-distributed-via-dns-spoofing/" target="_blank">
         [9]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
  </tbody>
 </table>
 <h2 class="pt-3" id="references">
  References
 </h2>
 <div class="row">
  <div class="col">
   <ol>
    <li>
     <span class="scite-citation" id="scite-1">
      <span class="scite-citation-text">
       <a class="external text" href="http://pages.cs.wisc.edu/~vrastogi/static/papers/rcj13b.pdf" name="scite-1" rel="nofollow" target="_blank">
        Vaibhav Rastogi, Yan Chen, and Xuxian Jiang. (2013, May). DroidChameleon: Evaluating Android Anti-malware against Transformation Attacks. Retrieved December 9, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://ieeexplore.ieee.org/document/6234407" name="scite-2" rel="nofollow" target="_blank">
        Yajin Zhou and Xuxian Jiang. (2012, May). Dissecting Android Malware: Characterization and Evolution. Retrieved December 9, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.trendmicro.com/trendlabs-security-intelligence/cybercriminals-improve-android-malware-stealth-routines-with-obad/" name="scite-3" rel="nofollow" target="_blank">
        Veo Zhang. (2013, June 13). Cybercriminals Improve Android Malware Stealth Routines with OBAD. Retrieved December 9, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.slideshare.net/Shakacon/fruit-vs-zombies-defeat-nonjailbroken-ios-malware-by-claud-xiao" name="scite-4" rel="nofollow" target="_blank">
        Claud Xiao. (2016, July). Fruit vs Zombies: Defeat Non-jailbroken iOS Malware. Retrieved December 9, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.lookout.com/blog/2016/01/06/brain-test-re-emerges/" name="scite-5" rel="nofollow" target="_blank">
        Chris Dehghanpoor. (2016, January 6). Brain Test re-emerges: 13 apps found in Google Play  Read more: Brain Test re-emerges: 13 apps found in Google Play. Retrieved December 21, 2016.
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
       <a class="external text" href="http://blog.checkpoint.com/2017/01/24/charger-malware/" name="scite-6" rel="nofollow" target="_blank">
        Oren Koriat and Andrey Polkovnichenko. (2017, January 24). Charger Malware Calls and Raises the Risk on Google Play. Retrieved January 24, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.wandera.com/reddrop-malware/" name="scite-7" rel="nofollow" target="_blank">
        Nell Campbell. (2018, February 27). RedDrop: the blackmailing mobile malware family lurking in app stores. Retrieved September 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2014/11/wirelurker-new-era-os-x-ios-malware/" name="scite-8" rel="nofollow" target="_blank">
        Claud Xiao. (2014, November 5). WireLurker: A New Era in OS X and iOS Malware. Retrieved January 24, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/xloader-android-spyware-and-banking-trojan-distributed-via-dns-spoofing/" name="scite-9" rel="nofollow" target="_blank">
        Lorin Wu. (2018, April 19). XLoader Android Spyware and Banking Trojan Distributed via DNS Spoofing. Retrieved July 6, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
