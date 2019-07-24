<div class="container-fluid">
 <h1>
  Install Insecure or Malicious Configuration
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An adversary could attempt to install insecure or malicious configuration settings on the mobile device, through means such as phishing emails or text messages either directly containing the configuration settings as an attachment, or containing a web link to the configuration settings. The device user may be tricked into installing the configuration settings through social engineering techniques
    <span class="scite-citeref-number" data-reference="Symantec-iOSProfile" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.symantec.com/connect/blogs/malicious-profiles-sleeping-giant-ios-security" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    .
   </p>
   <p>
    For example, an unwanted Certification Authority (CA) certificate could be placed in the device's trusted certificate store, increasing the device's susceptibility to man-in-the-middle network attacks seeking to eavesdrop on or manipulate the device's network communication (
    <a href="https://attack.mitre.org/techniques/T1439">
     Eavesdrop on Insecure Network Communication
    </a>
    and
    <a href="https://attack.mitre.org/techniques/T1463">
     Manipulate Device Communication
    </a>
    ).
   </p>
   <p>
    On iOS, malicious Configuration Profiles could contain unwanted Certification Authority (CA) certificates or other insecure settings such as unwanted proxy server or VPN settings to route the device's network traffic through an adversary's system. The device could also potentially be enrolled into a malicious Mobile Device Management (MDM) system
    <span class="scite-citeref-number" data-reference="Talos-MDM" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://blog.talosintelligence.com/2018/07/Mobile-Malware-Campaign-uses-Malicious-MDM.html" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    .
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1478
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
      : Defense Evasion, Initial Access
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
      <a href="https://pages.nist.gov/mobile-threat-catalogue/stack-threats/STA-7.html" target="_blank">
       STA-7
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
     <a href="https://attack.mitre.org/mitigations/M1006">
      Use Recent OS Version
     </a>
    </td>
    <td>
     iOS 10.3 and higher add an additional step for users to install new trusted CA certificates to make it more difficult to trick users into installing them. On Android, apps that target compatibility with Android 7 and higher (API Level 24) default to only trusting CA certificates that are bundled with the operating system, not CA certificates that are added by the user or administrator, hence decreasing their susceptibility to successful man-in-the-middle attack.
     <span class="scite-citeref-number" data-reference="Symantec-iOSProfile2" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
      <sup>
       <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.symantec.com/connect/blogs/apple-ios-103-finally-battles-malicious-profiles" target="_blank">
        [3]
       </a>
      </sup>
     </span>
     <span class="scite-citeref-number" data-reference="Android-TrustedCA" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
      <sup>
       <a aria-describedby="qtip-3" data-hasqtip="3" href="https://android-developers.googleblog.com/2016/07/changes-to-trusted-certificate.html" target="_blank">
        [4]
       </a>
      </sup>
     </span>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1011">
      User Guidance
     </a>
    </td>
    <td>
     Typically, insecure or malicious configuration settings are not installed without the user's consent. Users should be advised not to install unexpected configuration settings (CA certificates, iOS Configuration Profiles, Mobile Device Management server provisioning).
    </td>
   </tr>
  </tbody>
 </table>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  On Android, the user can view trusted CA certificates through the device settings and look for unexpected certificates. A mobile security product could similarly examine the trusted CA certificate store for anomalies.
 </p>
 <p>
  On iOS, the user can view installed Configuration Profiles through the device settings and look for unexpected profiles. A Mobile Device Management (MDM) system could use the iOS MDM APIs to examine the list of installed Configuration Profiles for anomalies.
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
       <a class="external text" href="https://www.symantec.com/connect/blogs/malicious-profiles-sleeping-giant-ios-security" name="scite-1" rel="nofollow" target="_blank">
        Yair Amit. (2013, March 12). Malicious Profiles – The Sleeping Giant of iOS Security. Retrieved September 24, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/07/Mobile-Malware-Campaign-uses-Malicious-MDM.html" name="scite-2" rel="nofollow" target="_blank">
        Warren Mercer, Paul Rascagneres, Andrew Williams. (2018, July 12). Advanced Mobile Malware Campaign in India uses Malicious MDM. Retrieved September 24, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="3.0">
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/connect/blogs/apple-ios-103-finally-battles-malicious-profiles" name="scite-3" rel="nofollow" target="_blank">
        Brian Duckering. (2017, March 27). Apple iOS 10.3 Finally Battles Malicious Profiles. Retrieved September 24, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://android-developers.googleblog.com/2016/07/changes-to-trusted-certificate.html" name="scite-4" rel="nofollow" target="_blank">
        Chad Brubaker. (2016, July 7). Changes to Trusted Certificate Authorities in Android Nougat. Retrieved September 24, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
