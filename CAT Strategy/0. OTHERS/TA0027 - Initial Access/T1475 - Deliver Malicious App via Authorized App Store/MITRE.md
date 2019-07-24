<div class="container-fluid">
 <h1>
  Deliver Malicious App via Authorized App Store
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Malicious applications are a common attack vector used by adversaries to gain a presence on mobile devices. Mobile devices often are configured to allow application installation only from an authorized app store (e.g., Google Play Store or Apple App Store). An adversary may seek to place a malicious application in an authorized app store, enabling the application to be installed onto targeted devices.
   </p>
   <p>
    App stores typically require developer registration and use vetting techniques to identify malicious applications. Adversaries may use these techniques against app store defenses:
   </p>
   <ul>
    <li>
     <a href="https://attack.mitre.org/techniques/T1407">
      Download New Code at Runtime
     </a>
    </li>
    <li>
     <a href="https://attack.mitre.org/techniques/T1406">
      Obfuscated Files or Information
     </a>
    </li>
    <li>
     PRE-ATT&amp;CK:
     <a href="https://attack.mitre.org/techniques/T1391">
      Choose pre-compromised mobile app developer account credentials or signing keys
     </a>
    </li>
    <li>
     PRE-ATT&amp;CK:
     <a href="https://attack.mitre.org/techniques/T1393">
      Test ability to evade automated mobile application security analysis performed by app stores
     </a>
    </li>
   </ul>
   <p>
    Adversaries may also seek to evade vetting by placing code in a malicious application to detect whether it is running in an app analysis environment and, if so, avoid performing malicious actions while under analysis.
    <span class="scite-citeref-number" data-reference="Petsas" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://dl.acm.org/citation.cfm?id=2592796" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Oberheide-Bouncer" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://jon.oberheide.org/files/summercon12-bouncer.pdf" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Percoco-Bouncer" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://media.blackhat.com/bh-us-12/Briefings/Percoco/BH_US_12_Percoco_Adventures_in_Bouncerland_WP.pdf" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Wang" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.usenix.org/conference/usenixsecurity13/technical-sessions/presentation/wang_tielei" target="_blank">
       [4]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries may also use fake identities, payment cards, etc., to create developer accounts to publish malicious applications to app stores.
    <span class="scite-citeref-number" data-reference="Oberheide-Bouncer" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://jon.oberheide.org/files/summercon12-bouncer.pdf" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries may also use control of a target's Google account to use the Google Play Store's remote installation capability to install apps onto the Android devices associated with the Google account.
    <span class="scite-citeref-number" data-reference="Oberheide-RemoteInstall" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://jon.oberheide.org/blog/2010/06/25/remote-kill-and-install-on-google-android/" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Konoth" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="http://www.vvdveen.com/publications/BAndroid.pdf" target="_blank">
       [6]
      </a>
     </sup>
    </span>
    (Only applications that are available for download through the Google Play Store can be remotely installed using this technique.)
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1475
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
      <a href="https://pages.nist.gov/mobile-threat-catalogue/ecosystem-threats/ECO-4.html" target="_blank">
       ECO-4
      </a>
      ,
      <a href="https://pages.nist.gov/mobile-threat-catalogue/ecosystem-threats/ECO-16.html" target="_blank">
       ECO-16
      </a>
      ,
      <a href="https://pages.nist.gov/mobile-threat-catalogue/ecosystem-threats/ECO-17.html" target="_blank">
       ECO-17
      </a>
      ,
      <a href="https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-20.html" target="_blank">
       APP-20
      </a>
      ,
      <a href="https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-21.html" target="_blank">
       APP-21
      </a>
      ,
      <a href="https://pages.nist.gov/mobile-threat-catalogue/ecosystem-threats/ECO-22.html" target="_blank">
       ECO-22
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
     App store operators and enterprises could assess reputational characteristics of the app, including the popularity of the app or other apps from the same developer and whether or not security issues have been found in other apps from the same developer.
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1011">
      User Guidance
     </a>
    </td>
    <td>
     Encourage developers to protect their account credentials and enable multi-factor authentication if available. Encourage developers to protect their signing keys.
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
     <a href="https://attack.mitre.org/software/S0316">
      Pegasus for Android
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0316">
       Pegasus for Android
      </a>
      attempts to detect whether it is running in an emulator rather than a real device.
      <span class="scite-citeref-number" data-reference="Lookout-PegasusAndroid" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://blog.lookout.com/blog/2017/04/03/pegasus-android/" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0287">
      ZergHelper
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0287">
       ZergHelper
      </a>
      apparently evaded Apple's app review process by performing different behaviors for users from different physical locations (e.g. performing differently for users in China versus outside of China), which could have bypassed the review process depending on the country from which it was performed.
      <span class="scite-citeref-number" data-reference="Xiao-ZergHelper" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="http://researchcenter.paloaltonetworks.com/2016/02/pirated-ios-app-stores-client-successfully-evaded-apple-ios-code-review/" target="_blank">
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
   An EMM/MDM or mobile threat defense solution can identify the presence of unwanted or known insecure or malicious apps on devices.
  </li>
  <li>
   Developers can scan (or have a third party scan on their behalf) the app stores for presence of unauthorized apps that were submitted using the developer's identity.
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
       <a class="external text" href="http://dl.acm.org/citation.cfm?id=2592796" name="scite-1" rel="nofollow" target="_blank">
        Thanasis Petsas, Giannis Voyatzis, Elias Athanasopoulos, Michalis Polychronakis, Sotiris Ioannidis. (2014, April). Rage Against the Virtual Machine: Hindering Dynamic Analysis of Android Malware. Retrieved December 12, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://jon.oberheide.org/files/summercon12-bouncer.pdf" name="scite-2" rel="nofollow" target="_blank">
        Jon Oberheide and Charlie Miller. (2012). Dissecting the Android Bouncer. Retrieved December 12, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://media.blackhat.com/bh-us-12/Briefings/Percoco/BH_US_12_Percoco_Adventures_in_Bouncerland_WP.pdf" name="scite-3" rel="nofollow" target="_blank">
        Nicholas J. Percoco and Sean Schulte. (2012). Adventures in BouncerLand. Retrieved December 12, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.usenix.org/conference/usenixsecurity13/technical-sessions/presentation/wang_tielei" name="scite-4" rel="nofollow" target="_blank">
        Tielei Wang, Kangjie Lu, Long Lu, Simon Chung, and Wenke Lee. (2013, August). Jekyll on iOS: When Benign Apps Become Evil. Retrieved December 9, 2016.
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
       <a class="external text" href="https://jon.oberheide.org/blog/2010/06/25/remote-kill-and-install-on-google-android/" name="scite-5" rel="nofollow" target="_blank">
        Jon Oberheide. (2010, June 25). Remote Kill and Install on Google Android. Retrieved December 12, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.vvdveen.com/publications/BAndroid.pdf" name="scite-6" rel="nofollow" target="_blank">
        Radhesh Krishnan Konoth, Victor van der Veen, and Herbert Bos. (n.d.). How Anywhere Computing Just Killed Your Phone-Based Two-Factor Authentication. Retrieved December 12, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.lookout.com/blog/2017/04/03/pegasus-android/" name="scite-7" rel="nofollow" target="_blank">
        Mike Murray. (2017, April 3). Pegasus for Android: the other side of the story emerges. Retrieved April 16, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/02/pirated-ios-app-stores-client-successfully-evaded-apple-ios-code-review/" name="scite-8" rel="nofollow" target="_blank">
        Claud Xiao. (2016, February 21). Pirated iOS App Store’s Client Successfully Evaded Apple iOS Code Review. Retrieved December 12, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
