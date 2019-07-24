<div class="container-fluid">
 <h1>
  Network Traffic Capture or Redirection
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An adversary may capture network traffic to and from the device to obtain credentials or other sensitive data, or redirect network traffic to flow through an adversary-controlled gateway to do the same.
   </p>
   <p>
    A malicious app could register itself as a VPN client on Android or iOS to gain access to network packets. However, on both platforms, the user must grant consent to the app to act as a VPN client, and on iOS the app requires a special entitlement that must be granted by Apple.
   </p>
   <p>
    Alternatively, if a malicious app is able to escalate operating system privileges, it may be able to use those privileges to gain access to network traffic.
   </p>
   <p>
    An adversary could redirect network traffic to an adversary-controlled gateway by establishing a VPN connection or by manipulating the device's proxy settings. For example, Skycure
    <span class="scite-citeref-number" data-reference="Skycure-Profiles" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.skycure.com/blog/malicious-profiles-the-sleeping-giant-of-ios-security/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    describes the ability to redirect network traffic by installing a malicious iOS Configuration Profile.
   </p>
   <p>
    If applications encrypt their network traffic, sensitive data may not be accessible to an adversary, depending on the point of capture.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1410
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
      : Collection, Credential Access
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
     Closely scrutinize applications that request VPN access before allowing their use.
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1009">
      Encrypt Network Traffic
     </a>
    </td>
    <td>
     This mitigation may not always be effective depending on the method used to encrypt network traffic. In some cases, an adversary may be able to capture traffic before it is encrypted.
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
     <a href="https://attack.mitre.org/software/S0288">
      KeyRaider
     </a>
    </td>
    <td>
     <p>
      Most
      <a href="https://attack.mitre.org/software/S0288">
       KeyRaider
      </a>
      samples hook SSLRead and SSLWrite functions in the itunesstored process to intercept device communication with the Apple App Store.
      <span class="scite-citeref-number" data-reference="Xiao-KeyRaider" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="http://researchcenter.paloaltonetworks.com/2015/08/keyraider-ios-malware-steals-over-225000-apple-accounts-to-create-free-app-utopia/" target="_blank">
         [2]
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
  On both Android and iOS the user must grant consent to an app to act as a VPN. Both platforms also provide visual context to the user in the top status bar when a VPN connection is in place.
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
       <a class="external text" href="https://www.skycure.com/blog/malicious-profiles-the-sleeping-giant-of-ios-security/" name="scite-1" rel="nofollow" target="_blank">
        Yair Amit. (2013, March 12). Malicious Profiles - The Sleeping Giant of iOS Security. Retrieved December 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2015/08/keyraider-ios-malware-steals-over-225000-apple-accounts-to-create-free-app-utopia/" name="scite-2" rel="nofollow" target="_blank">
        Claud Xiao. (2015, August 30). KeyRaider: iOS Malware Steals Over 225,000 Apple Accounts to Create Free App Utopia. Retrieved December 12, 2016.
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
       <a class="external text" href="https://techcrunch.com/2016/06/14/apple-will-require-https-connections-for-ios-apps-by-the-end-of-2016/" name="scite-3" rel="nofollow" target="_blank">
        Kate Conger. (2016, June 14). Apple will require HTTPS connections for iOS apps by the end of 2016. Retrieved December 19, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://developer.android.com/training/articles/security-config.html" name="scite-4" rel="nofollow" target="_blank">
        Google. (n.d.). Network Security Configuration. Retrieved December 19, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
