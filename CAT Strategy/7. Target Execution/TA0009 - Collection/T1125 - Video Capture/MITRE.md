<div class="container-fluid">
 <h1>
  Video Capture
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An adversary can leverage a computer's peripheral devices (e.g., integrated cameras or webcams) or applications (e.g., video call services) to capture video recordings for the purpose of gathering information. Images may also be captured from devices or applications, potentially in specified intervals, in lieu of video files.
   </p>
   <p>
    Malware or scripts may be used to interact with the devices through an available API provided by the operating system or an application to capture video or images. Video or image files may be written to disk and exfiltrated later. This technique differs from
    <a href="https://attack.mitre.org/techniques/T1113">
     Screen Capture
    </a>
    due to use of specific devices or applications for video recording rather than capturing the victim's screen.
   </p>
   <p>
    In macOS, there are a few different malware samples that record the user's webcam such as FruitFly and Proton.
    <span class="scite-citeref-number" data-reference="objective-see 2017 review" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://objective-see.com/blog/blog_0x25.html" target="_blank">
       [1]
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
      : T1125
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
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
      Windows, macOS
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Permissions Required:
      </span>
      User
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      Process monitoring, File monitoring, API monitoring
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
       Contributors:
      </span>
      Praetorian
      <br/>
      <br/>
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
     <a href="https://attack.mitre.org/software/S0234">
      Bandook
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0234">
       Bandook
      </a>
      has modules that are capable of capturing from a victim's webcam.
      <span class="scite-citeref-number" data-reference="EFF Manul Aug 2016" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.eff.org/files/2016/08/03/i-got-a-letter-from-the-government.pdf" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0021">
      Derusbi
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0021">
       Derusbi
      </a>
      is capable of capturing video.
      <span class="scite-citeref-number" data-reference="FireEye Periscope March 2018" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0152">
      EvilGrab
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0152">
       EvilGrab
      </a>
      has the capability to capture video from a victim machine.
      <span class="scite-citeref-number" data-reference="PWC Cloud Hopper Technical Annex April 2017" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0046">
      FIN7
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0046">
       FIN7
      </a>
      created a custom video recording capability that could be used to monitor operations in the victim's environment.
      <span class="scite-citeref-number" data-reference="FireEye FIN7 Aug 2018" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.fireeye.com/blog/threat-research/2018/08/fin7-pursuing-an-enigmatic-and-evasive-global-criminal-operation.html" target="_blank">
         [5]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="DOJ FIN7 Aug 2018" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.justice.gov/opa/press-release/file/1084361/download" target="_blank">
         [6]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0260">
      InvisiMole
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0260">
       InvisiMole
      </a>
      can remotely activate the victim’s webcam to capture content.
      <span class="scite-citeref-number" data-reference="ESET InvisiMole June 2018" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.welivesecurity.com/2018/06/07/invisimole-equipped-spyware-undercover/" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0283">
      jRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0283">
       jRAT
      </a>
      has the capability to access the webcam on the victim’s machine.
      <span class="scite-citeref-number" data-reference="jRAT Symantec Aug 2018" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.symantec.com/blogs/threat-intelligence/jrat-new-anti-parsing-techniques" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0265">
      Kazuar
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0265">
       Kazuar
      </a>
      captures images from the webcam.
      <span class="scite-citeref-number" data-reference="Unit 42 Kazuar May 2017" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://researchcenter.paloaltonetworks.com/2017/05/unit42-kazuar-multiplatform-espionage-backdoor-api-access/" target="_blank">
         [9]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0192">
      Pupy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0192">
       Pupy
      </a>
      can access a connected webcam and capture pictures.
      <span class="scite-citeref-number" data-reference="GitHub Pupy" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://github.com/n1nj4sec/pupy" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0262">
      QuasarRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0262">
       QuasarRAT
      </a>
      can perform webcam viewing.
      <span class="scite-citeref-number" data-reference="GitHub QuasarRAT" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://github.com/quasar/QuasarRAT" target="_blank">
         [11]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Volexity Patchwork June 2018" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/" target="_blank">
         [12]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0098">
      T9000
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0098">
       T9000
      </a>
      uses the Skype API to record audio and video calls. It writes encrypted data to
      <code>
       %APPDATA%\Intel\Skype
      </code>
      .
      <span class="scite-citeref-number" data-reference="Palo Alto T9000 Feb 2016" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="http://researchcenter.paloaltonetworks.com/2016/02/t9000-advanced-modular-backdoor-uses-complex-anti-analysis-techniques/" target="_blank">
         [13]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
  </tbody>
 </table>
 <h2 class="pt-3" id="mitigation">
  Mitigation
 </h2>
 <p>
  Mitigating this technique specifically may be difficult as it requires fine-grained API control. Efforts should be focused on preventing unwanted or unknown code from executing on a system.
 </p>
 <p>
  Identify and block potentially malicious software that may be used to capture video and images by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-14-a">
   <sup>
    <a aria-describedby="qtip-13" data-hasqtip="13" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [14]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-15-a">
   <sup>
    <a aria-describedby="qtip-14" data-hasqtip="14" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [15]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-16-a">
   <sup>
    <a aria-describedby="qtip-15" data-hasqtip="15" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [16]
    </a>
   </sup>
  </span>
  or Software Restriction Policies
  <span class="scite-citeref-number" data-reference="Corio 2008" id="scite-ref-17-a">
   <sup>
    <a aria-describedby="qtip-16" data-hasqtip="16" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" target="_blank">
     [17]
    </a>
   </sup>
  </span>
  where appropriate.
  <span class="scite-citeref-number" data-reference="TechNet Applocker vs SRP" id="scite-ref-18-a">
   <sup>
    <a aria-describedby="qtip-17" data-hasqtip="17" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" target="_blank">
     [18]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Detection of this technique may be difficult due to the various APIs that may be used. Telemetry data regarding API use may not be useful depending on how a system is normally used, but may provide context to other potentially malicious activity occurring on a system.
 </p>
 <p>
  Behavior that could indicate technique use include an unknown or unusual process accessing APIs associated with devices or software that interact with the video camera, recording devices, or recording software, and a process periodically writing files to disk that contain video or camera image data.
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
       <a class="external text" href="https://objective-see.com/blog/blog_0x25.html" name="scite-1" rel="nofollow" target="_blank">
        Patrick Wardle. (n.d.). Retrieved March 20, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.eff.org/files/2016/08/03/i-got-a-letter-from-the-government.pdf" name="scite-2" rel="nofollow" target="_blank">
        Galperin, E., Et al.. (2016, August). I Got a Letter From the Government the Other Day.... Retrieved April 25, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" name="scite-3" rel="nofollow" target="_blank">
        FireEye. (2018, March 16). Suspected Chinese Cyber Espionage Group (TEMP.Periscope) Targeting U.S. Engineering and Maritime Industries. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" name="scite-4" rel="nofollow" target="_blank">
        PwC and BAE Systems. (2017, April). Operation Cloud Hopper: Technical Annex. Retrieved April 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/08/fin7-pursuing-an-enigmatic-and-evasive-global-criminal-operation.html" name="scite-5" rel="nofollow" target="_blank">
        Carr, N., et al. (2018, August 01). On the Hunt for FIN7: Pursuing an Enigmatic and Evasive Global Criminal Operation. Retrieved August 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.justice.gov/opa/press-release/file/1084361/download" name="scite-6" rel="nofollow" target="_blank">
        Department of Justice. (2018, August 01). HOW FIN7 ATTACKED AND STOLE DATA. Retrieved August 24, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2018/06/07/invisimole-equipped-spyware-undercover/" name="scite-7" rel="nofollow" target="_blank">
        Hromcová, Z. (2018, June 07). InvisiMole: Surprisingly equipped spyware, undercover since 2013. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/jrat-new-anti-parsing-techniques" name="scite-8" rel="nofollow" target="_blank">
        Sharma, R. (2018, August 15). Revamped jRAT Uses New Anti-Parsing Techniques. Retrieved September 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/05/unit42-kazuar-multiplatform-espionage-backdoor-api-access/" name="scite-9" rel="nofollow" target="_blank">
        Levene, B, et al. (2017, May 03). Kazuar: Multiplatform Espionage Backdoor with API Access. Retrieved July 17, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="10.0">
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/n1nj4sec/pupy" name="scite-10" rel="nofollow" target="_blank">
        Nicolas Verdier. (n.d.). Retrieved January 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/quasar/QuasarRAT" name="scite-11" rel="nofollow" target="_blank">
        MaxXor. (n.d.). QuasarRAT. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/" name="scite-12" rel="nofollow" target="_blank">
        Meltzer, M, et al. (2018, June 07). Patchwork APT Group Targets US Think Tanks. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/02/t9000-advanced-modular-backdoor-uses-complex-anti-analysis-techniques/" name="scite-13" rel="nofollow" target="_blank">
        Grunzweig, J. and Miller-Osborn, J.. (2016, February 4). T9000: Advanced Modular Backdoor Uses Complex Anti-Analysis Techniques. Retrieved April 15, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-14" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-15" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-16" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" name="scite-17" rel="nofollow" target="_blank">
        Corio, C., &amp; Sayana, D. P. (2008, June). Application Lockdown with Software Restriction Policies. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" name="scite-18" rel="nofollow" target="_blank">
        Microsoft. (2012, June 27). Using Software Restriction Policies and AppLocker Policies. Retrieved April 7, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
