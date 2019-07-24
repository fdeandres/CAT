<div class="container-fluid">
 <h1>
  System Network Configuration Discovery
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    On Android, details of onboard network interfaces are accessible to apps through the java.net.NetworkInterface class
    <span class="scite-citeref-number" data-reference="NetworkInterface" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://developer.android.com/reference/java/net/NetworkInterface.html" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    . The Android TelephonyManager class can be used to gather related information such as the IMSI, IMEI, and phone number
    <span class="scite-citeref-number" data-reference="TelephonyManager" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://developer.android.com/reference/android/telephony/TelephonyManager.html" target="_blank">
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
      : T1422
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
      : Discovery
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
     Application vetting could be used to analyze applications to determine whether they access this information, including determining whether the application requests the Android ACCESS_NETWORK_STATE permission (required in order to access NetworkInterface information) or the READ_PHONE_STATE permission (required in order to access TelephonyManager information).
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1006">
      Use Recent OS Version
     </a>
    </td>
    <td>
     Starting in Android 6.0, applications can no longer access MAC addresses of network interfaces.
     <span class="scite-citeref-number" data-reference="Android60Changes" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
      <sup>
       <a aria-describedby="qtip-10" data-hasqtip="10" href="https://developer.android.com/about/versions/marshmallow/android-6.0-changes.html#behavior-hardware-id" target="_blank">
        [11]
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
     <a href="https://attack.mitre.org/software/S0315">
      DualToy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0315">
       DualToy
      </a>
      collects the connected iOS device’s information including IMEI, IMSI, ICCID, serial number and phone number.
      <span class="scite-citeref-number" data-reference="PaloAlto-DualToy" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://researchcenter.paloaltonetworks.com/2016/09/dualtoy-new-windows-trojan-sideloads-risky-apps-to-android-and-ios-devices/" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
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
      checks if the device is on Wi-Fi, a cellular network, and is roaming.
      <span class="scite-citeref-number" data-reference="Lookout-PegasusAndroid" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://blog.lookout.com/blog/2017/04/03/pegasus-android/" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0289">
      Pegasus for iOS
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0289">
       Pegasus for iOS
      </a>
      monitors the connection state and tracks which types of networks the phone is connected to, potentially to determine the bandwidth and ability to send full data across the network.
      <span class="scite-citeref-number" data-reference="Lookout-Pegasus" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://info.lookout.com/rs/051-ESQ-475/images/lookout-pegasus-technical-analysis.pdf" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0291">
      PJApps
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0291">
       PJApps
      </a>
      has the capability to collect and leak the victim's phone number, mobile device unique identifier (IMEI).
      <span class="scite-citeref-number" data-reference="Lookout-EnterpriseApps" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://blog.lookout.com/blog/2016/05/25/spoofed-apps/" target="_blank">
         [6]
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
      exfiltrates IMEI, IMSI, MNC, MCC, nearby WiFi networks, and other device and SIM related info.
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
     <a href="https://attack.mitre.org/software/S0313">
      RuMMS
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0313">
       RuMMS
      </a>
      gathers the device phone number and IMEI and transmits them to a command and control server.
      <span class="scite-citeref-number" data-reference="FireEye-RuMMS" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.fireeye.com/blog/threat-research/2016/04/rumms-android-malware.html" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0324">
      SpyDealer
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0324">
       SpyDealer
      </a>
      harvests phone number IMEI, and IMSI.
      <span class="scite-citeref-number" data-reference="PaloAlto-SpyDealer" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://researchcenter.paloaltonetworks.com/2017/07/unit42-spydealer-android-trojan-spying-40-apps/" target="_blank">
         [9]
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
      uploads information about changes in SIM card or phone numbers on the device.
      <span class="scite-citeref-number" data-reference="Lookout-StealthMango" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://info.lookout.com/rs/051-ESQ-475/images/lookout-stealth-mango-srr-us.pdf" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0329">
      Tangelo
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0329">
       Tangelo
      </a>
      contains functionality to gather cellular IDs.
      <span class="scite-citeref-number" data-reference="Lookout-StealthMango" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://info.lookout.com/rs/051-ESQ-475/images/lookout-stealth-mango-srr-us.pdf" target="_blank">
         [10]
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
       <a class="external text" href="https://developer.android.com/reference/java/net/NetworkInterface.html" name="scite-1" rel="nofollow" target="_blank">
        Android. (n.d.). NetworkInterface. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://developer.android.com/reference/android/telephony/TelephonyManager.html" name="scite-2" rel="nofollow" target="_blank">
        Android. (n.d.). TelephonyManager. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2016/09/dualtoy-new-windows-trojan-sideloads-risky-apps-to-android-and-ios-devices/" name="scite-3" rel="nofollow" target="_blank">
        Claud Xiao. (2016, September 13). DualToy: New Windows Trojan Sideloads Risky Apps to Android and iOS Devices. Retrieved January 24, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.lookout.com/blog/2017/04/03/pegasus-android/" name="scite-4" rel="nofollow" target="_blank">
        Mike Murray. (2017, April 3). Pegasus for Android: the other side of the story emerges. Retrieved April 16, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://info.lookout.com/rs/051-ESQ-475/images/lookout-pegasus-technical-analysis.pdf" name="scite-5" rel="nofollow" target="_blank">
        Lookout. (2016). Technical Analysis of Pegasus Spyware. Retrieved December 12, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.lookout.com/blog/2016/05/25/spoofed-apps/" name="scite-6" rel="nofollow" target="_blank">
        Lookout. (2016, May 25). 5 active mobile threats spoofing enterprise apps. Retrieved December 19, 2016.
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
       <a class="external text" href="https://www.wandera.com/reddrop-malware/" name="scite-7" rel="nofollow" target="_blank">
        Nell Campbell. (2018, February 27). RedDrop: the blackmailing mobile malware family lurking in app stores. Retrieved September 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2016/04/rumms-android-malware.html" name="scite-8" rel="nofollow" target="_blank">
        Wu Zhou, Deyu Hu, Jimmy Su, Yong Kang. (2016, April 26). RUMMS: THE LATEST FAMILY OF ANDROID MALWARE ATTACKING USERS IN RUSSIA VIA SMS PHISHING. Retrieved February 6, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/07/unit42-spydealer-android-trojan-spying-40-apps/" name="scite-9" rel="nofollow" target="_blank">
        Wenjun Hu, Cong Zheng and Zhi Xu. (2017, July 6). SpyDealer: Android Trojan Spying on More Than 40 Apps. Retrieved September 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://info.lookout.com/rs/051-ESQ-475/images/lookout-stealth-mango-srr-us.pdf" name="scite-10" rel="nofollow" target="_blank">
        Lookout. (n.d.). Stealth Mango &amp; Tangelo. Retrieved September 27, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://developer.android.com/about/versions/marshmallow/android-6.0-changes.html#behavior-hardware-id" name="scite-11" rel="nofollow" target="_blank">
        Android. (n.d.). Android 6.0 Changes. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
