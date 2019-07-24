<div class="container-fluid">
 <h1>
  Premium SMS Toll Fraud
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    A malicious app could use standard Android APIs to send SMS messages. SMS messages could potentially be sent to premium numbers that charge the device owner and generate revenue for an adversary
    <span class="scite-citeref-number" data-reference="Lookout-SMS" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://blog.lookout.com/10-organizations-build-60-of-russian-toll-fraud-malware" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    .
   </p>
   <p>
    On iOS, apps cannot send SMS messages.
   </p>
   <p>
    On Android, apps must hold the SEND_SMS permission to send SMS messages. Additionally, Android version 4.2 and above has mitigations against this threat by requiring user consent before allowing SMS messages to be sent to premium numbers
    <span class="scite-citeref-number" data-reference="AndroidSecurity2014" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://static.googleusercontent.com/media/source.android.com/en//security/reports/Google_Android_Security_2014_Report_Final.pdf" target="_blank">
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
      : T1448
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
      : Effects
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
     Starting with Android 4.2 the user must provide consent before applications can send SMS messages to premium numbers.
     <span class="scite-citeref-number" data-reference="AndroidSecurity2014" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
      <sup>
       <a aria-describedby="qtip-1" data-hasqtip="1" href="https://static.googleusercontent.com/media/source.android.com/en//security/reports/Google_Android_Security_2014_Report_Final.pdf" target="_blank">
        [2]
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
     <a href="https://attack.mitre.org/software/S0303">
      MazarBOT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0303">
       MazarBOT
      </a>
      can send messages to premium-rate numbers.
      <span class="scite-citeref-number" data-reference="Tripwire-MazarBOT" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.tripwire.com/state-of-security/security-data-protection/android-malware-sms/" target="_blank">
         [3]
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
      has the capability to send messages to premium SMS messages.
      <span class="scite-citeref-number" data-reference="Lookout-EnterpriseApps" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://blog.lookout.com/blog/2016/05/25/spoofed-apps/" target="_blank">
         [4]
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
      tricks the user into sending SMS messages to premium services and then deletes those messages.
      <span class="scite-citeref-number" data-reference="Wandera-RedDrop" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.wandera.com/reddrop-malware/" target="_blank">
         [5]
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
  Starting with Android 4.2 the user is prompted and must provide consent before applications can send SMS messages to premium numbers.
  <span class="scite-citeref-number" data-reference="AndroidSecurity2014" id="scite-ref-2-a">
   <sup>
    <a aria-describedby="qtip-1" data-hasqtip="1" href="https://static.googleusercontent.com/media/source.android.com/en//security/reports/Google_Android_Security_2014_Report_Final.pdf" target="_blank">
     [2]
    </a>
   </sup>
  </span>
 </p>
 <p>
  On Android 6.0 and up, the user can view which applications have permission to send SMS messages through the device settings screen, and the user can choose to revoke the permissions.
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
       <a class="external text" href="https://blog.lookout.com/10-organizations-build-60-of-russian-toll-fraud-malware" name="scite-1" rel="nofollow" target="_blank">
        Ryan Sammy. (2013, August 2). 10 Organizations Build 60% of Russian Toll Fraud Malware. Retrieved December 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://static.googleusercontent.com/media/source.android.com/en//security/reports/Google_Android_Security_2014_Report_Final.pdf" name="scite-2" rel="nofollow" target="_blank">
        Google. (2014). Android Security 2014 Year in Review. Retrieved December 12, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.tripwire.com/state-of-security/security-data-protection/android-malware-sms/" name="scite-3" rel="nofollow" target="_blank">
        Graham Cluley. (2016, February 16). Android users warned of malware attack spreading via SMS. Retrieved December 23, 2016.
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
       <a class="external text" href="https://blog.lookout.com/blog/2016/05/25/spoofed-apps/" name="scite-4" rel="nofollow" target="_blank">
        Lookout. (2016, May 25). 5 active mobile threats spoofing enterprise apps. Retrieved December 19, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.wandera.com/reddrop-malware/" name="scite-5" rel="nofollow" target="_blank">
        Nell Campbell. (2018, February 27). RedDrop: the blackmailing mobile malware family lurking in app stores. Retrieved September 18, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
