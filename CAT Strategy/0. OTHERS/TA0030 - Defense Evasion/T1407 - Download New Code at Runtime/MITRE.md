<div class="container-fluid">
 <h1>
  Download New Code at Runtime
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An app could download and execute dynamic code (not included in the original application package) after installation to evade static analysis techniques (and potentially dynamic analysis techniques) used for application vetting or application store review.
    <span class="scite-citeref-number" data-reference="Poeplau-ExecuteThis" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.internetsociety.org/sites/default/files/10_5_0.pdf" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    On Android, dynamic code could include native code, Dalvik code, or JavaScript code that uses the Android WebView's JavascriptInterface capability.
    <span class="scite-citeref-number" data-reference="Bromium-AndroidRCE" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://labs.bromium.com/2014/07/31/remote-code-execution-on-android-devices/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    On iOS, techniques also exist for executing dynamic code downloaded after application installation.
    <span class="scite-citeref-number" data-reference="FireEye-JSPatch" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.fireeye.com/blog/threat-research/2016/01/hot_or_not_the_bene.html" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Wang" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.usenix.org/conference/usenixsecurity13/technical-sessions/presentation/wang_tielei" target="_blank">
       [4]
      </a>
     </sup>
    </span>
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1407
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
      : Defense Evasion
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
      <a href="https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-20.html" target="_blank">
       APP-20
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
     Application vetting techniques could (either statically or dynamically) look for indications that the application downloads and executes new code at runtime (e.g., on Android use of DexClassLoader, System.load, or the WebView JavaScriptInterface capability, or on iOS use of JSPatch or similar capabilities). Unfortunately, this is only a partial mitigation, as additional scrutiny would still need to be applied to applications that use these techniques, as the techniques are often used without malicious intent, and because applications may employ other techniques such as to hide their use of these techniques.
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
     <a href="https://attack.mitre.org/software/S0293">
      BrainTest
     </a>
    </td>
    <td>
     <p>
      Original samples of
      <a href="https://attack.mitre.org/software/S0293">
       BrainTest
      </a>
      download their exploit packs for rooting from a remote server after installation.
      <span class="scite-citeref-number" data-reference="Lookout-BrainTest" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://blog.lookout.com/blog/2016/01/06/brain-test-re-emerges/" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0325">
      Judy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0325">
       Judy
      </a>
      bypasses Google Play's protections by downloading a malicious payload at runtime after installation.
      <span class="scite-citeref-number" data-reference="CheckPoint-Judy" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://blog.checkpoint.com/2017/05/25/judy-malware-possibly-largest-malware-campaign-found-google-play/" target="_blank">
         [6]
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
      has the ability to dynamically download and execute new code at runtime.
      <span class="scite-citeref-number" data-reference="TrendMicro-RCSAndroid" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="http://blog.trendmicro.com/trendlabs-security-intelligence/hacking-team-rcsandroid-spying-tool-listens-to-calls-roots-devices-to-get-in/" target="_blank">
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
      downloads additional components (APKs, JAR files) from different C&amp;C servers and stores them dynamically into the device’s memory, allowing the adversary to execute additional malicious APKs without having to embed them straight into the initial sample.
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
     <a href="https://attack.mitre.org/software/S0327">
      Skygofree
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0327">
       Skygofree
      </a>
      can download executable code from the C2 server after the implant starts or after a specific command.
      <span class="scite-citeref-number" data-reference="Kaspersky-Skygofree" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://securelist.com/skygofree-following-in-the-footsteps-of-hackingteam/83603/" target="_blank">
         [9]
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
      downloads and executes root exploits from a remote server.
      <span class="scite-citeref-number" data-reference="PaloAlto-SpyDealer" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://researchcenter.paloaltonetworks.com/2017/07/unit42-spydealer-android-trojan-spying-40-apps/" target="_blank">
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
      attempts to extend its capabilities via dynamic updating of its code.
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
 <h2 class="pt-3" id="references">
  References
 </h2>
 <div class="row">
  <div class="col">
   <ol>
    <li>
     <span class="scite-citation" id="scite-1">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.internetsociety.org/sites/default/files/10_5_0.pdf" name="scite-1" rel="nofollow" target="_blank">
        Sebastian Poeplau, Yanick Fratantonio, Antonio Bianchi, Christopher Kruegel, Giovanni Vigna. (2014, February). Execute This! Analyzing Unsafe and Malicious Dynamic Code Loading in Android Applications. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://labs.bromium.com/2014/07/31/remote-code-execution-on-android-devices/" name="scite-2" rel="nofollow" target="_blank">
        Tom Sutcliffe. (2014, July 31). Remote code execution on Android devices. Retrieved December 9, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2016/01/hot_or_not_the_bene.html" name="scite-3" rel="nofollow" target="_blank">
        Jing Xie, Zhaofeng Chen, Jimmy Su. (2016, January 27). HOT OR NOT? THE BENEFITS AND RISKS OF IOS REMOTE HOT PATCHING. Retrieved December 9, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.usenix.org/conference/usenixsecurity13/technical-sessions/presentation/wang_tielei" name="scite-4" rel="nofollow" target="_blank">
        Tielei Wang, Kangjie Lu, Long Lu, Simon Chung, and Wenke Lee. (2013, August). Jekyll on iOS: When Benign Apps Become Evil. Retrieved December 9, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.lookout.com/blog/2016/01/06/brain-test-re-emerges/" name="scite-5" rel="nofollow" target="_blank">
        Chris Dehghanpoor. (2016, January 6). Brain Test re-emerges: 13 apps found in Google Play  Read more: Brain Test re-emerges: 13 apps found in Google Play. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.checkpoint.com/2017/05/25/judy-malware-possibly-largest-malware-campaign-found-google-play/" name="scite-6" rel="nofollow" target="_blank">
        CheckPoint. (2017, May 25). The Judy Malware: Possibly the largest malware campaign found on Google Play. Retrieved September 18, 2018.
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
       <a class="external text" href="http://blog.trendmicro.com/trendlabs-security-intelligence/hacking-team-rcsandroid-spying-tool-listens-to-calls-roots-devices-to-get-in/" name="scite-7" rel="nofollow" target="_blank">
        Veo Zhang. (2015, July 21). Hacking Team RCSAndroid Spying Tool Listens to Calls; Roots Devices to Get In. Retrieved December 22, 2016.
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
       <a class="external text" href="https://securelist.com/skygofree-following-in-the-footsteps-of-hackingteam/83603/" name="scite-9" rel="nofollow" target="_blank">
        Nikita Buchka and Alexey Firsh. (2018, January 16). Skygofree: Following in the footsteps of HackingTeam. Retrieved September 24, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/07/unit42-spydealer-android-trojan-spying-40-apps/" name="scite-10" rel="nofollow" target="_blank">
        Wenjun Hu, Cong Zheng and Zhi Xu. (2017, July 6). SpyDealer: Android Trojan Spying on More Than 40 Apps. Retrieved September 18, 2018.
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
