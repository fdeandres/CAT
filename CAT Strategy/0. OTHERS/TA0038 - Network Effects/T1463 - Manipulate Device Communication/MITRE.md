<div class="container-fluid">
 <h1>
  Manipulate Device Communication
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    If network traffic between the mobile device and a remote server is not securely protected, then an attacker positioned on the network may be able to manipulate network communication without being detected. For example, FireEye researchers found in 2014 that 68% of the top 1,000 free applications in the Google Play Store had at least one Transport Layer Security (TLS) implementation vulnerability potentially opening the applications' network traffic to man-in-the-middle attacks
    <span class="scite-citeref-number" data-reference="FireEye-SSL" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.fireeye.com/blog/threat-research/2014/08/ssl-vulnerabilities-who-listens-when-android-applications-talk.html" target="_blank">
       [1]
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
      : T1463
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Tactic Type:
      </span>
      Without Adversary Device Access
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Tactic
      </span>
      : Network Effects
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
      <a href="https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-1.html" target="_blank">
       APP-1
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
     Application vetting techniques can scan for use of cleartext communication, insecure TrustManager implementations, and other potential network communication weaknesses. The Google Play Store now automatically assesses submitted applications for insecure TrustManager implementations.
     <span class="scite-citeref-number" data-reference="Google-TrustManager" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
      <sup>
       <a aria-describedby="qtip-1" data-hasqtip="1" href="https://support.google.com/faqs/answer/6346016?hl=en" target="_blank">
        [2]
       </a>
      </sup>
     </span>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1009">
      Encrypt Network Traffic
     </a>
    </td>
    <td>
     App developers should be advised to use the Android Network Security Configuration feature and the iOS App Transport Security feature to gain some level of assurance that app network traffic is protected.
     <span class="scite-citeref-number" data-reference="Google-TrustManager" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
      <sup>
       <a aria-describedby="qtip-1" data-hasqtip="1" href="https://support.google.com/faqs/answer/6346016?hl=en" target="_blank">
        [2]
       </a>
      </sup>
     </span>
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
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2014/08/ssl-vulnerabilities-who-listens-when-android-applications-talk.html" name="scite-1" rel="nofollow" target="_blank">
        Adrian Mettler, Yulong Zhang, Vishwanath Raman. (2014, August 20). SSL VULNERABILITIES: WHO LISTENS WHEN ANDROID APPLICATIONS TALK?. Retrieved December 24, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://support.google.com/faqs/answer/6346016?hl=en" name="scite-2" rel="nofollow" target="_blank">
        Google. (n.d.). How to fix apps containing an unsafe implementation of TrustManager. Retrieved December 24, 2016.
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
