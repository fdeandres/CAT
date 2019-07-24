<div class="container-fluid">
 <h1>
  System Information Discovery
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An adversary may attempt to get detailed information about the operating system and hardware, including version, patches, and architecture.
   </p>
   <p>
    On Android, much of this information is programmatically accessible to applications through the android.os.Build class
    <span class="scite-citeref-number" data-reference="Android-Build" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://zeltser.com/third-party-keyboards-security/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    .
   </p>
   <p>
    On iOS, techniques exist for applications to programmatically access this information
    <span class="scite-citeref-number" data-reference="StackOverflow-iOSVersion" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="http://stackoverflow.com/questions/7848766/how-can-we-programmatically-detect-which-ios-version-is-device-running-on" target="_blank">
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
      : T1426
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
     <a href="https://attack.mitre.org/software/S0310">
      ANDROIDOS_ANSERVER.A
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0310">
       ANDROIDOS_ANSERVER.A
      </a>
      gathers the device OS version.
      <span class="scite-citeref-number" data-reference="TrendMicro-Anserver2" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.trendmicro.com/vinfo/us/threat-encyclopedia/malware/ANDROIDOS_ANSERVER.A" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
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
      samples search to find the Apple account's username, password and device's GUID in data being transferred.
      <span class="scite-citeref-number" data-reference="Xiao-KeyRaider" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="http://researchcenter.paloaltonetworks.com/2015/08/keyraider-ios-malware-steals-over-225000-apple-accounts-to-create-free-app-utopia/" target="_blank">
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
      monitors the victim for status and disables other access to the phone by other jailbreaking software.
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
     <a href="https://attack.mitre.org/software/S0313">
      RuMMS
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0313">
       RuMMS
      </a>
      gathers device model and operating system version information and transmits it to a command and control server.
      <span class="scite-citeref-number" data-reference="FireEye-RuMMS" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.fireeye.com/blog/threat-research/2016/04/rumms-android-malware.html" target="_blank">
         [6]
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
       <a class="external text" href="https://zeltser.com/third-party-keyboards-security/" name="scite-1" rel="nofollow" target="_blank">
        Android. (n.d.). Build. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://stackoverflow.com/questions/7848766/how-can-we-programmatically-detect-which-ios-version-is-device-running-on" name="scite-2" rel="nofollow" target="_blank">
        Stack Overflow. (n.d.). How can we programmatically detect which iOS version is device running on?. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.trendmicro.com/vinfo/us/threat-encyclopedia/malware/ANDROIDOS_ANSERVER.A" name="scite-3" rel="nofollow" target="_blank">
        Karl Dominguez. (2011, September 27). ANDROIDOS_ANSERVER.A. Retrieved November 30, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="4.0">
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2015/08/keyraider-ios-malware-steals-over-225000-apple-accounts-to-create-free-app-utopia/" name="scite-4" rel="nofollow" target="_blank">
        Claud Xiao. (2015, August 30). KeyRaider: iOS Malware Steals Over 225,000 Apple Accounts to Create Free App Utopia. Retrieved December 12, 2016.
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
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2016/04/rumms-android-malware.html" name="scite-6" rel="nofollow" target="_blank">
        Wu Zhou, Deyu Hu, Jimmy Su, Yong Kang. (2016, April 26). RUMMS: THE LATEST FAMILY OF ANDROID MALWARE ATTACKING USERS IN RUSSIA VIA SMS PHISHING. Retrieved February 6, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
