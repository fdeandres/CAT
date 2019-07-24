<div class="container-fluid">
 <h1>
  Deliver Malicious App via Other Means
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Malicious applications are a common attack vector used by adversaries to gain a presence on mobile devices. This technique describes installing a malicious application on targeted mobile devices without involving an authorized app store (e.g., Google Play Store or Apple App Store). Adversaries may wish to avoid placing malicious applications in an authorized app store due to increased potential risk of detection or other reasons. However, mobile devices often are configured to allow application installation only from an authorized app store which would prevent this technique from working.
   </p>
   <p>
    Delivery methods for the malicious application include:
   </p>
   <ul>
    <li>
     <a href="https://attack.mitre.org/techniques/T1193">
      Spearphishing Attachment
     </a>
     - Including the mobile app package as an attachment to an email message.
    </li>
    <li>
     <a href="https://attack.mitre.org/techniques/T1192">
      Spearphishing Link
     </a>
     - Including a link to the mobile app package within an email, text message (e.g. SMS, iMessage, Hangouts, WhatsApp, etc.), web site, QR code, or other means.
    </li>
    <li>
     Third-Party App Store - Installed from a third-party app store (as opposed to an authorized app store that the device implicitly trusts as part of its default behavior), which may not apply the same level of scrutiny to apps as applied by an authorized app store.
     <span class="scite-citeref-number" data-reference="IBTimes-ThirdParty" id="scite-ref-1-a">
      <sup>
       <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.ibtimes.co.uk/danger-lurks-third-party-android-app-stores-1544861" target="_blank">
        [1]
       </a>
      </sup>
     </span>
     <span class="scite-citeref-number" data-reference="TrendMicro-RootingMalware" id="scite-ref-2-a">
      <sup>
       <a aria-describedby="qtip-1" data-hasqtip="1" href="https://blog.trendmicro.com/trendlabs-security-intelligence/user-beware-rooting-malware-found-in-3rd-party-app-stores/" target="_blank">
        [2]
       </a>
      </sup>
     </span>
     <span class="scite-citeref-number" data-reference="TrendMicro-FlappyBird" id="scite-ref-3-a">
      <sup>
       <a aria-describedby="qtip-2" data-hasqtip="2" href="https://blog.trendmicro.com/trendlabs-security-intelligence/flappy-bird-and-third-party-app-stores/" target="_blank">
        [3]
       </a>
      </sup>
     </span>
    </li>
   </ul>
   <p>
    As a prerequisite, adversaries may use this PRE-ATT&amp;CK technique:
   </p>
   <ul>
    <li>
     <a href="https://attack.mitre.org/techniques/T1392">
      Obtain Apple iOS enterprise distribution key pair and certificate
     </a>
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
      : T1476
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
      <a href="https://pages.nist.gov/mobile-threat-catalogue/authentication-threats/AUT-9.html" target="_blank">
       AUT-9
      </a>
      ,
      <a href="https://pages.nist.gov/mobile-threat-catalogue/ecosystem-threats/ECO-13.html" target="_blank">
       ECO-13
      </a>
      ,
      <a href="https://pages.nist.gov/mobile-threat-catalogue/ecosystem-threats/ECO-21.html" target="_blank">
       ECO-21
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
     <a href="https://attack.mitre.org/mitigations/M1012">
      Enterprise Policy
     </a>
    </td>
    <td>
     On iOS, the allowEnterpriseAppTrust and allowEnterpriseAppTrustModification configuration profile restrictions can be used to prevent users from installing apps signed using enterprise distribution keys.
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1011">
      User Guidance
     </a>
    </td>
    <td>
     iOS 9 and above requires explicit user consent before allowing installation of applications signed with enterprise distribution keys rather than installed from Apple's App Store. Users should be encouraged to not agree to installation of applications signed with enterprise distribution keys unless absolutely certain of the source of the application. On Android, the "Unknown Sources" setting must be enabled for users to install apps from sources other than an authorized app store (such as the Google Play Store), so users should be encouraged not to enable that setting.
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
     <a href="https://attack.mitre.org/software/S0296">
      Android Overlay Malware
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0296">
       Android Overlay Malware
      </a>
      was distributed by sending SMS messages with an embedded link to the malware.
      <span class="scite-citeref-number" data-reference="FireEye-AndroidOverlay" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.fireeye.com/blog/threat-research/2016/06/latest-android-overlay-malware-spreading-in-europe.html" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
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
      was delivered via a spearphishing message containing a malicious Android application as an attachment.
      <span class="scite-citeref-number" data-reference="Kaspersky-WUC" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://securelist.com/android-trojan-found-in-targeted-attack-58/35552/" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
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
      is delivered via a link sent by SMS or email, including instructions advising the user to modify their Android device security settings to enable apps to be installed from "Unknown Sources."
      <span class="scite-citeref-number" data-reference="Proofpoint-Marcher" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.proofpoint.com/us/threat-insight/post/credential-phishing-and-android-banking-trojan-combine-austrian-mobile-attacks" target="_blank">
         [6]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0303">
      MazarBOT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0303">
       MazarBOT
      </a>
      is delivered via an unsolicited text message containing a link to a web download URI.
      <span class="scite-citeref-number" data-reference="Tripwire-MazarBOT" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.tripwire.com/state-of-security/security-data-protection/android-malware-sms/" target="_blank">
         [7]
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
      uses ads or other links within web sites to encourage users to download the malicious apps. A complex content distribution network (CDN) and series of network redirects is used in an apparent attempt to evade malware detection techniques.
      <span class="scite-citeref-number" data-reference="Wandera-RedDrop" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.wandera.com/reddrop-malware/" target="_blank">
         [8]
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
      is delivered via an SMS message containing a link to an APK (Android application package).
      <span class="scite-citeref-number" data-reference="FireEye-RuMMS" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.fireeye.com/blog/threat-research/2016/04/rumms-android-malware.html" target="_blank">
         [9]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0311">
      YiSpecter
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0311">
       YiSpecter
      </a>
      's malicious apps were signed with iOS enterprise certificates issued by Apple to allow the apps to be installed as enterprise apps on non-jailbroken iOS devices.
      <span class="scite-citeref-number" data-reference="PaloAlto-YiSpecter" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://researchcenter.paloaltonetworks.com/2015/10/yispecter-first-ios-malware-attacks-non-jailbroken-ios-devices-by-abusing-private-apis/" target="_blank">
         [10]
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
      abuses enterprises certificate and personal certificates to sign and distribute apps.
      <span class="scite-citeref-number" data-reference="Xiao-ZergHelper" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="http://researchcenter.paloaltonetworks.com/2016/02/pirated-ios-app-stores-client-successfully-evaded-apple-ios-code-review/" target="_blank">
         [11]
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
   An EMM/MDM or mobile threat defense solution may be able to identify the presence of apps installed from sources other than an authorized app store.
  </li>
  <li>
   An EMM/MDM or mobile threat defense solution may be able to identify Android devices configured to allow apps to be installed from "Unknown Sources".
  </li>
  <li>
   Enterprise email security solutions can identify the presence of Android or iOS application packages within email messages.
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
       <a class="external text" href="https://www.ibtimes.co.uk/danger-lurks-third-party-android-app-stores-1544861" name="scite-1" rel="nofollow" target="_blank">
        A Prasad. (2016, February 19). Danger lurks in third-party Android app stores. Retrieved November 8, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/user-beware-rooting-malware-found-in-3rd-party-app-stores/" name="scite-2" rel="nofollow" target="_blank">
        Jordan Pan. (2016, February 10). User Beware: Rooting Malware Found in 3rd Party App Stores. Retrieved November 8, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/flappy-bird-and-third-party-app-stores/" name="scite-3" rel="nofollow" target="_blank">
        Veo Zhang. (2014, February 18). Flappy Bird and Third-Party App Stores. Retrieved November 8, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2016/06/latest-android-overlay-malware-spreading-in-europe.html" name="scite-4" rel="nofollow" target="_blank">
        Wu Zhou et al. (2016, June 28). THE LATEST ANDROID OVERLAY MALWARE SPREADING VIA SMS PHISHING IN EUROPE. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/android-trojan-found-in-targeted-attack-58/35552/" name="scite-5" rel="nofollow" target="_blank">
        Costin Raiu, Denis Maslennikov, Kurt Baumgartner. (2013, March 26). Android Trojan Found in Targeted Attack. Retrieved December 23, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/us/threat-insight/post/credential-phishing-and-android-banking-trojan-combine-austrian-mobile-attacks" name="scite-6" rel="nofollow" target="_blank">
        Proofpoint. (2017, November 3). Credential phishing and an Android banking Trojan combine in Austrian mobile attacks. Retrieved July 6, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="7.5">
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.tripwire.com/state-of-security/security-data-protection/android-malware-sms/" name="scite-7" rel="nofollow" target="_blank">
        Graham Cluley. (2016, February 16). Android users warned of malware attack spreading via SMS. Retrieved December 23, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.wandera.com/reddrop-malware/" name="scite-8" rel="nofollow" target="_blank">
        Nell Campbell. (2018, February 27). RedDrop: the blackmailing mobile malware family lurking in app stores. Retrieved September 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2016/04/rumms-android-malware.html" name="scite-9" rel="nofollow" target="_blank">
        Wu Zhou, Deyu Hu, Jimmy Su, Yong Kang. (2016, April 26). RUMMS: THE LATEST FAMILY OF ANDROID MALWARE ATTACKING USERS IN RUSSIA VIA SMS PHISHING. Retrieved February 6, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2015/10/yispecter-first-ios-malware-attacks-non-jailbroken-ios-devices-by-abusing-private-apis/" name="scite-10" rel="nofollow" target="_blank">
        Claud Xiao. (2015, October 4). YiSpecter: First iOS Malware That Attacks Non-jailbroken Apple iOS Devices by Abusing Private APIs. Retrieved January 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/02/pirated-ios-app-stores-client-successfully-evaded-apple-ios-code-review/" name="scite-11" rel="nofollow" target="_blank">
        Claud Xiao. (2016, February 21). Pirated iOS App Store’s Client Successfully Evaded Apple iOS Code Review. Retrieved December 12, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
