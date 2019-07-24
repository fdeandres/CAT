<div class="container-fluid">
 <h1>
  Lockscreen Bypass
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An adversary with physical access to a mobile device may seek to bypass the device's lockscreen.
   </p>
   <h3>
    Biometric Spoofing
   </h3>
   <p>
    If biometric authentication is used, an adversary could attempt to spoof a mobile device's biometric authentication mechanism
    <span class="scite-citeref-number" data-reference="SRLabs-Fingerprint" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://srlabs.de/bites/spoofing-fingerprints/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="SecureIDNews-Spoof" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://thehackernews.com/2016/05/android-kernal-exploit.htmlhttps://www.secureidnews.com/news-item/another-spoof-of-mobile-biometrics/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="TheSun-FaceID" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.thesun.co.uk/tech/5584082/iphone-x-face-unlock-tricked-broken/" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    .
   </p>
   <p>
    iOS partly mitigates this attack by requiring the device passcode rather than a fingerprint to unlock the device after every device restart and after 48 hours since the device was last unlocked
    <span class="scite-citeref-number" data-reference="Apple-TouchID" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://support.apple.com/en-us/HT204587" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    . Android has similar mitigations.
   </p>
   <h3>
    Device Unlock Code Guessing or Brute Force
   </h3>
   <p>
    An adversary could attempt to brute-force or otherwise guess the lockscreen passcode (typically a PIN or password), including physically observing ("shoulder surfing") the device owner's use of the lockscreen passcode.
   </p>
   <h3>
    Exploit Other Device Lockscreen Vulnerabilities
   </h3>
   <p>
    Techniques have periodically been demonstrated that exploit vulnerabilities on Android
    <span class="scite-citeref-number" data-reference="Wired-AndroidBypass" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.wired.com/2015/09/hack-brief-new-emergency-number-hack-easily-bypasses-android-lock-screens/" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    , iOS
    <span class="scite-citeref-number" data-reference="Kaspersky-iOSBypass" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://threatpost.com/ios-10-passcode-bypass-can-access-photos-contacts/122033/" target="_blank">
       [6]
      </a>
     </sup>
    </span>
    , or other mobile devices to bypass the device lockscreen. The vulnerabilities are generally patched by the device/operating system vendor once they become aware of their existence.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1461
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
      </span>
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
     Enterprises can provision policies to mobile devices to require a minimum complexity (length, etc.) for the device passcode. Enterprises can provision policies to mobile devices to cause the device to wipe all data if an incorrect passcode is entered too many times. Both policies would mitigate brute-force, guessing, or shoulder surfing of the device passcode. If desired, enterprises can provision policies to mobile devices to disallow biometric authentication. However, biometric authentication can help make "using a longer, more complex passcode far more practical because you don't need to enter it as frequently."
     <span class="scite-citeref-number" data-reference="Apple-iOSSecurityGuide" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
      <sup>
       <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.apple.com/business/docs/iOS_Security_Guide.pdf" target="_blank">
        [7]
       </a>
      </sup>
     </span>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1001">
      Security Updates
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
 <h2 class="pt-3" id="references">
  References
 </h2>
 <div class="row">
  <div class="col">
   <ol>
    <li>
     <span class="scite-citation" id="scite-1">
      <span class="scite-citation-text">
       <a class="external text" href="https://srlabs.de/bites/spoofing-fingerprints/" name="scite-1" rel="nofollow" target="_blank">
        SRLabs. (n.d.). Fingerprints are not fit for secure device unlocking. Retrieved December 23, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://thehackernews.com/2016/05/android-kernal-exploit.htmlhttps://www.secureidnews.com/news-item/another-spoof-of-mobile-biometrics/" name="scite-2" rel="nofollow" target="_blank">
        Zack Martin. (2016, March 11). Another spoof of mobile biometrics. Retrieved September 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.thesun.co.uk/tech/5584082/iphone-x-face-unlock-tricked-broken/" name="scite-3" rel="nofollow" target="_blank">
        Sean Keach. (2018, February 15). Brit mates BREAK Apple’s face unlock and vow to never buy iPhone again. Retrieved September 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://support.apple.com/en-us/HT204587" name="scite-4" rel="nofollow" target="_blank">
        Apple. (2015, November 3). About Touch ID security on iPhone and iPad. Retrieved December 23, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="5.5">
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.wired.com/2015/09/hack-brief-new-emergency-number-hack-easily-bypasses-android-lock-screens/" name="scite-5" rel="nofollow" target="_blank">
        Andy Greenberg. (2015, September 15). Hack Brief: Emergency Number Hack Bypasses Android Lock Screens. Retrieved December 23, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://threatpost.com/ios-10-passcode-bypass-can-access-photos-contacts/122033/" name="scite-6" rel="nofollow" target="_blank">
        Chris Brook. (2016, November 17). iOS 10 Passcode Bypass Can Access Photos, Contacts. Retrieved December 23, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.apple.com/business/docs/iOS_Security_Guide.pdf" name="scite-7" rel="nofollow" target="_blank">
        Apple. (2016, May). iOS Security. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
