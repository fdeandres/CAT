<div class="container-fluid">
 <h1>
  Access Sensitive Data or Credentials in Files
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An adversary could attempt to read files that contain sensitive data or credentials (e.g., private keys, passwords, access tokens). This technique requires either escalated privileges or for the targeted app to have stored the data in an insecure manner (e.g., with insecure file permissions or in an insecure location such as an external storage directory).
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1409
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
       MTC ID:
      </span>
      <a href="https://pages.nist.gov/mobile-threat-catalogue/authentication-threats/AUT-0.html" target="_blank">
       AUT-0
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
     Ensure that applications do not store sensitive data or credentials insecurely (e.g., with insecure file permissions or in an insecure location such as external data storage).
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
     <a href="https://attack.mitre.org/mitigations/M1008">
      Use Device Provided Credential Storage
     </a>
    </td>
    <td>
     Android and iOS provide hardware-backed capabilities to store credentials in an isolated location where they are less likely to be compromised even in the case of a successful privilege escalation attack against the operating system.
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1006">
      Use Recent OS Version
     </a>
    </td>
    <td>
     Android 7 provides stronger default file permissions over application internal data storage directories, decreasing the likelihood that insecure file permissions can be exploited.
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
     <a href="https://attack.mitre.org/software/S0290">
      Gooligan
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0290">
       Gooligan
      </a>
      steals authentication tokens that can be used to access data from multiple Google applications.
      <span class="scite-citeref-number" data-reference="Gooligan Citation" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="http://blog.checkpoint.com/2016/11/30/1-million-google-accounts-breached-gooligan/" target="_blank">
         [1]
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
      accesses sensitive data in files, such as messages stored by the WhatsApp, Facebook, and Twitter applications. It also has the ability to access arbitrary filenames and retrieve directory listings.
      <span class="scite-citeref-number" data-reference="Lookout-PegasusAndroid" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://blog.lookout.com/blog/2017/04/03/pegasus-android/" target="_blank">
         [2]
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
      accesses sensitive data in files, such as saving Skype calls by reading them out of the Skype database files.
      <span class="scite-citeref-number" data-reference="Lookout-Pegasus" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://info.lookout.com/rs/051-ESQ-475/images/lookout-pegasus-technical-analysis.pdf" target="_blank">
         [3]
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
      can collect passwords for Wi-Fi networks and online accounts, including Skype, Facebook, Twitter, Google, WhatsApp, Mail, and LinkedIn.
      <span class="scite-citeref-number" data-reference="TrendMicro-RCSAndroid" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="http://blog.trendmicro.com/trendlabs-security-intelligence/hacking-team-rcsandroid-spying-tool-listens-to-calls-roots-devices-to-get-in/" target="_blank">
         [4]
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
      has a capability to obtain files from other installed applications.
      <span class="scite-citeref-number" data-reference="Kaspersky-Skygofree" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://securelist.com/skygofree-following-in-the-footsteps-of-hackingteam/83603/" target="_blank">
         [5]
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
      exfiltrates data from over 40 apps such as WeChat, Facebook, WhatsApp, Skype, and others.
      <span class="scite-citeref-number" data-reference="PaloAlto-SpyDealer" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://researchcenter.paloaltonetworks.com/2017/07/unit42-spydealer-android-trojan-spying-40-apps/" target="_blank">
         [6]
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
      can copy files from the device to the C2 server.
      <span class="scite-citeref-number" data-reference="Zscaler-SpyNote" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.zscaler.com/blogs/research/spynote-rat-posing-netflix-app" target="_blank">
         [7]
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
      exfiltrated data, including sensitive letters/documents, stored photos, and stored audio files.
      <span class="scite-citeref-number" data-reference="Lookout-StealthMango" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://info.lookout.com/rs/051-ESQ-475/images/lookout-stealth-mango-srr-us.pdf" target="_blank">
         [8]
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
      accesses databases from WhatsApp, Viber, Skype, and Line. It also accesses browser history, pictures, and videos.
      <span class="scite-citeref-number" data-reference="Lookout-StealthMango" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://info.lookout.com/rs/051-ESQ-475/images/lookout-stealth-mango-srr-us.pdf" target="_blank">
         [8]
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
       <a class="external text" href="http://blog.checkpoint.com/2016/11/30/1-million-google-accounts-breached-gooligan/" name="scite-1" rel="nofollow" target="_blank">
        Check Point Research Team. (2016, November 30). More Than 1 Million Google Accounts Breached by Gooligan. Retrieved December 12, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.lookout.com/blog/2017/04/03/pegasus-android/" name="scite-2" rel="nofollow" target="_blank">
        Mike Murray. (2017, April 3). Pegasus for Android: the other side of the story emerges. Retrieved April 16, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://info.lookout.com/rs/051-ESQ-475/images/lookout-pegasus-technical-analysis.pdf" name="scite-3" rel="nofollow" target="_blank">
        Lookout. (2016). Technical Analysis of Pegasus Spyware. Retrieved December 12, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.trendmicro.com/trendlabs-security-intelligence/hacking-team-rcsandroid-spying-tool-listens-to-calls-roots-devices-to-get-in/" name="scite-4" rel="nofollow" target="_blank">
        Veo Zhang. (2015, July 21). Hacking Team RCSAndroid Spying Tool Listens to Calls; Roots Devices to Get In. Retrieved December 22, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="5.0">
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/skygofree-following-in-the-footsteps-of-hackingteam/83603/" name="scite-5" rel="nofollow" target="_blank">
        Nikita Buchka and Alexey Firsh. (2018, January 16). Skygofree: Following in the footsteps of HackingTeam. Retrieved September 24, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/07/unit42-spydealer-android-trojan-spying-40-apps/" name="scite-6" rel="nofollow" target="_blank">
        Wenjun Hu, Cong Zheng and Zhi Xu. (2017, July 6). SpyDealer: Android Trojan Spying on More Than 40 Apps. Retrieved September 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.zscaler.com/blogs/research/spynote-rat-posing-netflix-app" name="scite-7" rel="nofollow" target="_blank">
        Shivang Desai. (2017, January 23). SpyNote RAT posing as Netflix app. Retrieved January 26, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://info.lookout.com/rs/051-ESQ-475/images/lookout-stealth-mango-srr-us.pdf" name="scite-8" rel="nofollow" target="_blank">
        Lookout. (n.d.). Stealth Mango &amp; Tangelo. Retrieved September 27, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
