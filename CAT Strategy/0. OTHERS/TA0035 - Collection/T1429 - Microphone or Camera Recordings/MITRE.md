<div class="container-fluid">
 <h1>
  Microphone or Camera Recordings
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An adversary could use a malicious or exploited application to surreptitiously record activities using the device microphone and/or camera through use of standard operating system APIs.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1429
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
      : Collection
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
      <a href="https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-19.html" target="_blank">
       APP-19
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
     On Android, applications must request the RECORD_AUDIO permission to access the microphone and the CAMERA permission to access the camera. Extra scrutiny could be given to applications that request these permissions. On iOS, calls to the relevant APIs could be detected during the vetting process.
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
     <a href="https://attack.mitre.org/software/S0292">
      AndroRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0292">
       AndroRAT
      </a>
      gathers audio from the microphone.
      <span class="scite-citeref-number" data-reference="Lookout-EnterpriseApps" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://blog.lookout.com/blog/2016/05/25/spoofed-apps/" target="_blank">
         [1]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0301">
      Dendroid
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0301">
       Dendroid
      </a>
      can take pictures using the phone’s camera as well as record audio and video.
      <span class="scite-citeref-number" data-reference="Lookout-Dendroid" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://blog.lookout.com/blog/2014/03/06/dendroid/" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0320">
      DroidJack
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0320">
       DroidJack
      </a>
      performs call recording and video capturing.
      <span class="scite-citeref-number" data-reference="Zscaler-SuperMarioRun" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.zscaler.com/blogs/research/super-mario-run-malware-2-–-droidjack-rat" target="_blank">
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
      has the ability to record audio and take pictures using the device camera.
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
      has the ability to record audio.
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
     <a href="https://attack.mitre.org/software/S0295">
      RCSAndroid
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0295">
       RCSAndroid
      </a>
      can record using the microphone as well as capture photos using the front and back cameras.
      <span class="scite-citeref-number" data-reference="TrendMicro-RCSAndroid" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="http://blog.trendmicro.com/trendlabs-security-intelligence/hacking-team-rcsandroid-spying-tool-listens-to-calls-roots-devices-to-get-in/" target="_blank">
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
      exfiltrates locally saved files (including photos) as well as live recordings of the device's surroundings.
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
     <a href="https://attack.mitre.org/software/S0327">
      Skygofree
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0327">
       Skygofree
      </a>
      can record audio via the microphone when an infected device is in a specified location as well as record a video or capture a photo.
      <span class="scite-citeref-number" data-reference="Kaspersky-Skygofree" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://securelist.com/skygofree-following-in-the-footsteps-of-hackingteam/83603/" target="_blank">
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
      can record phone calls and surrounding audio and video, as well as take photos via front and rear cameras.
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
     <a href="https://attack.mitre.org/software/S0305">
      SpyNote RAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0305">
       SpyNote RAT
      </a>
      can activate the victim's microphone.
      <span class="scite-citeref-number" data-reference="Zscaler-SpyNote" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www.zscaler.com/blogs/research/spynote-rat-posing-netflix-app" target="_blank">
         [10]
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
      can record from the camera or microphone as well as take photos from the front and back cameras.
      <span class="scite-citeref-number" data-reference="Lookout-StealthMango" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://info.lookout.com/rs/051-ESQ-475/images/lookout-stealth-mango-srr-us.pdf" target="_blank">
         [11]
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
      contains functionality to record calls as well as the victim device's environment.
      <span class="scite-citeref-number" data-reference="Lookout-StealthMango" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://info.lookout.com/rs/051-ESQ-475/images/lookout-stealth-mango-srr-us.pdf" target="_blank">
         [11]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0318">
      XLoader
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0318">
       XLoader
      </a>
      covertly records phone calls.
      <span class="scite-citeref-number" data-reference="TrendMicro-XLoader" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://blog.trendmicro.com/trendlabs-security-intelligence/xloader-android-spyware-and-banking-trojan-distributed-via-dns-spoofing/" target="_blank">
         [12]
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
  On both Android (6.0 and up) and iOS, the user can view which applications have permission to use the microphone or the camera through the device settings screen, and the user can choose to revoke the permissions.
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
       <a class="external text" href="https://blog.lookout.com/blog/2016/05/25/spoofed-apps/" name="scite-1" rel="nofollow" target="_blank">
        Lookout. (2016, May 25). 5 active mobile threats spoofing enterprise apps. Retrieved December 19, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.lookout.com/blog/2014/03/06/dendroid/" name="scite-2" rel="nofollow" target="_blank">
        Marc Rogers. (2014, March 6). Dendroid malware can take over your camera, record audio, and sneak into Google Play. Retrieved December 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.zscaler.com/blogs/research/super-mario-run-malware-2-–-droidjack-rat" name="scite-3" rel="nofollow" target="_blank">
        Viral Gandhi. (2017, January 12). Super Mario Run Malware #2 – DroidJack RAT. Retrieved January 20, 2017.
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
       <a class="external text" href="http://blog.trendmicro.com/trendlabs-security-intelligence/hacking-team-rcsandroid-spying-tool-listens-to-calls-roots-devices-to-get-in/" name="scite-6" rel="nofollow" target="_blank">
        Veo Zhang. (2015, July 21). Hacking Team RCSAndroid Spying Tool Listens to Calls; Roots Devices to Get In. Retrieved December 22, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="7.0">
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
       <a class="external text" href="https://securelist.com/skygofree-following-in-the-footsteps-of-hackingteam/83603/" name="scite-8" rel="nofollow" target="_blank">
        Nikita Buchka and Alexey Firsh. (2018, January 16). Skygofree: Following in the footsteps of HackingTeam. Retrieved September 24, 2018.
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
       <a class="external text" href="https://www.zscaler.com/blogs/research/spynote-rat-posing-netflix-app" name="scite-10" rel="nofollow" target="_blank">
        Shivang Desai. (2017, January 23). SpyNote RAT posing as Netflix app. Retrieved January 26, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://info.lookout.com/rs/051-ESQ-475/images/lookout-stealth-mango-srr-us.pdf" name="scite-11" rel="nofollow" target="_blank">
        Lookout. (n.d.). Stealth Mango &amp; Tangelo. Retrieved September 27, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/xloader-android-spyware-and-banking-trojan-distributed-via-dns-spoofing/" name="scite-12" rel="nofollow" target="_blank">
        Lorin Wu. (2018, April 19). XLoader Android Spyware and Banking Trojan Distributed via DNS Spoofing. Retrieved July 6, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
