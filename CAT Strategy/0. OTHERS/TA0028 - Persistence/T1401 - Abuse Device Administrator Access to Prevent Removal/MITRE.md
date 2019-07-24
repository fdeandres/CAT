<div class="container-fluid">
 <h1>
  Abuse Device Administrator Access to Prevent Removal
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    A malicious application can request Device Administrator privileges. If the user grants the privileges, the application can take steps to make its removal more difficult.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1401
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
      : Persistence
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Platform:
      </span>
      Android
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
      <a href="https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-22.html" target="_blank">
       APP-22
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
      : 1.1
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
     It is rare for applications to utilize Device Administrator access. App vetting can detect apps that do so, and those apps should be closely scrutinized. Maggi and Zanero describe a static analysis approach that can be used to identify ransomware apps including apps that abuse Device Administrator access.
     <span class="scite-citeref-number" data-reference="Maggi-Ransomware" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
      <sup>
       <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.blackhat.com/docs/eu-16/materials/eu-16-Maggi-Pocket-Sized-Badness-Why-Ransomware-Comes-As-A-Plot-Twist-In-The-Cat-Mouse-Game.pdf" target="_blank">
        [4]
       </a>
      </sup>
     </span>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1007">
      Caution with Device Administrator Access
     </a>
    </td>
    <td>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1006">
      Use Recent OS Version
     </a>
    </td>
    <td>
     Changes were made in Android 7 to help prevent use of this technique.
     <span class="scite-citeref-number" data-reference="GoogleIO2016" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
      <sup>
       <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.youtube.com/watch?v=XZzLjllizYs" target="_blank">
        [5]
       </a>
      </sup>
     </span>
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
     <a href="https://attack.mitre.org/software/S0317">
      Marcher
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0317">
       Marcher
      </a>
      requests Android Device Administrator access.
      <span class="scite-citeref-number" data-reference="Proofpoint-Marcher" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.proofpoint.com/us/threat-insight/post/credential-phishing-and-android-banking-trojan-combine-austrian-mobile-attacks" target="_blank">
         [1]
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
      abuses device administrator access to make it more difficult for users to remove the application.
      <span class="scite-citeref-number" data-reference="TrendMicro-Obad" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="http://blog.trendmicro.com/trendlabs-security-intelligence/cybercriminals-improve-android-malware-stealth-routines-with-obad/" target="_blank">
         [2]
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
      requests Android Device Administrator access.
      <span class="scite-citeref-number" data-reference="TrendMicro-XLoader" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://blog.trendmicro.com/trendlabs-security-intelligence/xloader-android-spyware-and-banking-trojan-distributed-via-dns-spoofing/" target="_blank">
         [3]
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
 <p>
  The device user can view a list of apps with Device Administrator privilege in the device settings.
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
       <a class="external text" href="https://www.proofpoint.com/us/threat-insight/post/credential-phishing-and-android-banking-trojan-combine-austrian-mobile-attacks" name="scite-1" rel="nofollow" target="_blank">
        Proofpoint. (2017, November 3). Credential phishing and an Android banking Trojan combine in Austrian mobile attacks. Retrieved July 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.trendmicro.com/trendlabs-security-intelligence/cybercriminals-improve-android-malware-stealth-routines-with-obad/" name="scite-2" rel="nofollow" target="_blank">
        Veo Zhang. (2013, June 13). Cybercriminals Improve Android Malware Stealth Routines with OBAD. Retrieved December 9, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/xloader-android-spyware-and-banking-trojan-distributed-via-dns-spoofing/" name="scite-3" rel="nofollow" target="_blank">
        Lorin Wu. (2018, April 19). XLoader Android Spyware and Banking Trojan Distributed via DNS Spoofing. Retrieved July 6, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="4.5">
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.blackhat.com/docs/eu-16/materials/eu-16-Maggi-Pocket-Sized-Badness-Why-Ransomware-Comes-As-A-Plot-Twist-In-The-Cat-Mouse-Game.pdf" name="scite-4" rel="nofollow" target="_blank">
        Federico Maggi and Stefano Zanero. (2016). Pocket-Sized Badness - Why Ransomware Comes as a Plot Twist in the Cat-Mouse Game. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.youtube.com/watch?v=XZzLjllizYs" name="scite-5" rel="nofollow" target="_blank">
        Adrian Ludwig. (2016, May 19). What's new in Android security (M and N Version). Retrieved December 9, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
