<div class="container-fluid">
 <h1>
  Standard Application Layer Protocol
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries may communicate using a common, standardized application layer protocol such as HTTP, HTTPS, SMTP, or DNS to avoid detection by blending in with existing traffic.
   </p>
   <p>
    In the mobile environment, the Google Cloud Messaging (GCM; two-way) and Apple Push Notification Service (APNS; one-way server-to-device) are commonly used protocols on Android and iOS respectively that would blend in with routine device traffic and are difficult for enterprises to inspect. Google reportedly responds to reports of abuse by blocking access to GCM.
    <span class="scite-citeref-number" data-reference="Kaspersky-MobileMalware" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://securelist.com/mobile-malware-evolution-2013/58335/" target="_blank">
       [1]
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
      : T1437
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
      : Command And Control, Exfiltration
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
      <a href="https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-29.html" target="_blank">
       APP-29
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
     <a href="https://attack.mitre.org/software/S0304">
      Android/Chuli.A
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0304">
       Android/Chuli.A
      </a>
      used HTTP uploads to a URL as a command and control mechanism.
      <span class="scite-citeref-number" data-reference="Kaspersky-WUC" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://securelist.com/android-trojan-found-in-targeted-attack-58/35552/" target="_blank">
         [2]
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
      exfiltrates data using standard HTTP.
      <span class="scite-citeref-number" data-reference="Wandera-RedDrop" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.wandera.com/reddrop-malware/" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0313">
      RuMMS
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0313">
       RuMMS
      </a>
      uses HTTP for command and control.
      <span class="scite-citeref-number" data-reference="FireEye-RuMMS" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.fireeye.com/blog/threat-research/2016/04/rumms-android-malware.html" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0327">
      Skygofree
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0327">
       Skygofree
      </a>
      can be controlled via HTTP, XMPP, FirebaseCloudMessaging, or GoogleCloudMessaging in older versions.
      <span class="scite-citeref-number" data-reference="Kaspersky-Skygofree" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://securelist.com/skygofree-following-in-the-footsteps-of-hackingteam/83603/" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0307">
      Trojan-SMS.AndroidOS.Agent.ao
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0307">
       Trojan-SMS.AndroidOS.Agent.ao
      </a>
      uses Google Cloud Messaging (GCM) for command and control.
      <span class="scite-citeref-number" data-reference="Kaspersky-MobileMalware" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://securelist.com/mobile-malware-evolution-2013/58335/" target="_blank">
         [1]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0306">
      Trojan-SMS.AndroidOS.FakeInst.a
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0306">
       Trojan-SMS.AndroidOS.FakeInst.a
      </a>
      uses Google Cloud Messaging (GCM) for command and control.
      <span class="scite-citeref-number" data-reference="Kaspersky-MobileMalware" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://securelist.com/mobile-malware-evolution-2013/58335/" target="_blank">
         [1]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0308">
      Trojan-SMS.AndroidOS.OpFake.a
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0308">
       Trojan-SMS.AndroidOS.OpFake.a
      </a>
      uses Google Cloud Messaging (GCM) for command and control.
      <span class="scite-citeref-number" data-reference="Kaspersky-MobileMalware" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://securelist.com/mobile-malware-evolution-2013/58335/" target="_blank">
         [1]
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
       <a class="external text" href="https://securelist.com/mobile-malware-evolution-2013/58335/" name="scite-1" rel="nofollow" target="_blank">
        Roman Unuchek and Victor Chebyshev. (2014, February 24). Mobile Malware Evolution: 2013. Retrieved December 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/android-trojan-found-in-targeted-attack-58/35552/" name="scite-2" rel="nofollow" target="_blank">
        Costin Raiu, Denis Maslennikov, Kurt Baumgartner. (2013, March 26). Android Trojan Found in Targeted Attack. Retrieved December 23, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.wandera.com/reddrop-malware/" name="scite-3" rel="nofollow" target="_blank">
        Nell Campbell. (2018, February 27). RedDrop: the blackmailing mobile malware family lurking in app stores. Retrieved September 18, 2018.
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
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2016/04/rumms-android-malware.html" name="scite-4" rel="nofollow" target="_blank">
        Wu Zhou, Deyu Hu, Jimmy Su, Yong Kang. (2016, April 26). RUMMS: THE LATEST FAMILY OF ANDROID MALWARE ATTACKING USERS IN RUSSIA VIA SMS PHISHING. Retrieved February 6, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/skygofree-following-in-the-footsteps-of-hackingteam/83603/" name="scite-5" rel="nofollow" target="_blank">
        Nikita Buchka and Alexey Firsh. (2018, January 16). Skygofree: Following in the footsteps of HackingTeam. Retrieved September 24, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
