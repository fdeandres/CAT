<div class="container-fluid">
 <h1>
  User Interface Spoofing
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    User Interface Spoofing can be used to trick users into providing sensitive information, such as account credentials, bank account information, or Personally Identifiable Information (PII) to an unintended entity.
   </p>
   <h3>
    Impersonate User Interface of Legitimate App or Device Function
   </h3>
   <p>
    On both Android and iOS, an adversary could impersonate the user interface of a legitimate app or device function to trick a user into entering sensitive information. The constrained display size of mobile devices (compared to traditional PC displays) may impair the ability to provide the user with contextual information (for example, displaying a full web site address) that may alert the user to a potential issue.
    <span class="scite-citeref-number" data-reference="Felt-PhishingOnMobileDevices" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://w2spconf.com/2011/papers/felt-mobilephishing.pdf" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    As described by PRE-ATT&amp;CK (
    <a href="https://attack.mitre.org/techniques/T1397">
     Spearphishing for Information
    </a>
    ), it is also possible for an adversary to carry out this form of the technique without a direct adversary presence on the mobile devices, e.g. through a spoofed web page.
   </p>
   <h3>
    Impersonate Identity of Legitimate App
   </h3>
   <p>
    On both Android and iOS, a malicious app could impersonate the identity of another app (e.g. use the same app name and/or icon) and somehow get installed on the device (e.g. using
    <a href="https://attack.mitre.org/techniques/T1475">
     Deliver Malicious App via Authorized App Store
    </a>
    or
    <a href="https://attack.mitre.org/techniques/T1476">
     Deliver Malicious App via Other Means
    </a>
    ). The malicious app could then prompt the user for sensitive information.
    <span class="scite-citeref-number" data-reference="eset-finance" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.welivesecurity.com/2018/09/19/fake-finance-apps-google-play-target-around-world/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <h3>
    Abuse OS Features to Interfere with Legitimate App
   </h3>
   <p>
    On older versions of Android, a malicious app could abuse mobile operating system features to interfere with a running legitimate app.
    <span class="scite-citeref-number" data-reference="Felt-PhishingOnMobileDevices" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://w2spconf.com/2011/papers/felt-mobilephishing.pdf" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Hassell-ExploitingAndroid" id="scite-ref-3-a">
     <sup>
      [3]
     </sup>
    </span>
    However, this technique appears to have been addressed starting in Android 5.0 with the deprecation of the Android's ActivityManager.getRunningTasks method and modification of its behavior
    <span class="scite-citeref-number" data-reference="Android-getRunningTasks" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://developer.android.com/reference/android/app/ActivityManager.html#getRunningTasks%28int%29" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    and further addressed in Android 5.1.1
    <span class="scite-citeref-number" data-reference="StackOverflow-getRunningAppProcesses" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="http://stackoverflow.com/questions/30619349/android-5-1-1-and-above-getrunningappprocesses-returns-my-application-packag" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    to prevent a malicious app from determining what app is currently in the foreground.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1411
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
      : Credential Access
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
      <a href="https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-31.html" target="_blank">
       APP-31
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
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1006">
      Use Recent OS Version
     </a>
    </td>
    <td>
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
      used view overlay techniques to present credential input UIs to trick users into providing their banking credentials.
      <span class="scite-citeref-number" data-reference="FireEye-AndroidOverlay" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.fireeye.com/blog/threat-research/2016/06/latest-android-overlay-malware-spreading-in-europe.html" target="_blank">
         [6]
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
      attempts to overlay itself on top of legitimate banking apps in an effort to capture user credentials.
      <a href="https://attack.mitre.org/software/S0317">
       Marcher
      </a>
      also attempts to overlay itself on top of legitimate apps such as the Google Play Store in an effort to capture user credit card information.
      <span class="scite-citeref-number" data-reference="Proofpoint-Marcher" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.proofpoint.com/us/threat-insight/post/credential-phishing-and-android-banking-trojan-combine-austrian-mobile-attacks" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0298">
      Xbot
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0298">
       Xbot
      </a>
      uses phishing pages mimicking Google Play's payment interface as well as bank login pages.
      <span class="scite-citeref-number" data-reference="PaloAlto-Xbot" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="http://researchcenter.paloaltonetworks.com/2016/02/new-android-trojan-xbot-phishes-credit-cards-and-bank-accounts-encrypts-devices-for-ransom/" target="_blank">
         [8]
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
      can prompt a fake alert dialog to phish user credentials.
      <span class="scite-citeref-number" data-reference="PaloAlto-XcodeGhost" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="http://researchcenter.paloaltonetworks.com/2015/09/update-xcodeghost-attacker-can-phish-passwords-and-open-urls-though-infected-apps/" target="_blank">
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
       <a class="external text" href="http://w2spconf.com/2011/papers/felt-mobilephishing.pdf" name="scite-1" rel="nofollow" target="_blank">
        A.P. Felt and D. Wagner. (2011, May 26). Phishing on Mobile Devices. Retrieved August 25, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2018/09/19/fake-finance-apps-google-play-target-around-world/" name="scite-2" rel="nofollow" target="_blank">
        Lukas Stefanko. (2016, July 7). Fake finance apps on Google Play target users from around the world. Retrieved September 24, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       R. Hassell. (2011, October 12-13). Exploiting Androids for Fun and Profit. Retrieved August 25, 2016.
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://developer.android.com/reference/android/app/ActivityManager.html#getRunningTasks%28int%29" name="scite-4" rel="nofollow" target="_blank">
        Android. (n.d.). ActivityManager getRunningTasks documentation. Retrieved January 19, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="http://stackoverflow.com/questions/30619349/android-5-1-1-and-above-getrunningappprocesses-returns-my-application-packag" name="scite-5" rel="nofollow" target="_blank">
        Various. (n.d.). Android 5.1.1 and above - getRunningAppProcesses() returns my application package only. Retrieved January 19, 2017.
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
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2016/06/latest-android-overlay-malware-spreading-in-europe.html" name="scite-6" rel="nofollow" target="_blank">
        Wu Zhou et al. (2016, June 28). THE LATEST ANDROID OVERLAY MALWARE SPREADING VIA SMS PHISHING IN EUROPE. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/us/threat-insight/post/credential-phishing-and-android-banking-trojan-combine-austrian-mobile-attacks" name="scite-7" rel="nofollow" target="_blank">
        Proofpoint. (2017, November 3). Credential phishing and an Android banking Trojan combine in Austrian mobile attacks. Retrieved July 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/02/new-android-trojan-xbot-phishes-credit-cards-and-bank-accounts-encrypts-devices-for-ransom/" name="scite-8" rel="nofollow" target="_blank">
        Cong Zheng, Claud Xiao and Zhi Xu. (2016, February 18). New Android Trojan “Xbot” Phishes Credit Cards and Bank Accounts, Encrypts Devices for Ransom. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2015/09/update-xcodeghost-attacker-can-phish-passwords-and-open-urls-though-infected-apps/" name="scite-9" rel="nofollow" target="_blank">
        Claud Xiao. (2015, September 18). Update: XcodeGhost Attacker Can Phish Passwords and Open URLs through Infected Apps. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
