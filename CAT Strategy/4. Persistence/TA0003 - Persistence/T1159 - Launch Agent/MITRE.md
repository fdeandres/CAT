<div class="container-fluid">
 <h1>
  Launch Agent
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Per Apple’s developer documentation, when a user logs in, a per-user launchd process is started which loads the parameters for each launch-on-demand user agent from the property list (plist) files found in
    <code>
     /System/Library/LaunchAgents
    </code>
    ,
    <code>
     /Library/LaunchAgents
    </code>
    , and
    <code>
     $HOME/Library/LaunchAgents
    </code>
    <span class="scite-citeref-number" data-reference="AppleDocs Launch Agent Daemons" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/CreatingLaunchdJobs.html" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="OSX Keydnap malware" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.welivesecurity.com/2016/07/06/new-osxkeydnap-malware-hungry-credentials/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Antiquated Mac Malware" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://blog.malwarebytes.com/threat-analysis/2017/01/new-mac-backdoor-using-antiquated-code/" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    . These launch agents have property list files which point to the executables that will be launched
    <span class="scite-citeref-number" data-reference="OSX.Dok Malware" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://blog.malwarebytes.com/threat-analysis/2017/04/new-osx-dok-malware-intercepts-web-traffic/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    .
   </p>
   <p>
    Adversaries may install a new launch agent that can be configured to execute at login by using launchd or launchctl to load a plist into the appropriate directories
    <span class="scite-citeref-number" data-reference="Sofacy Komplex Trojan" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://researchcenter.paloaltonetworks.com/2016/09/unit42-sofacys-komplex-os-x-trojan/" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Methods of Mac Malware Persistence" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.virusbulletin.com/uploads/pdf/conference/vb2014/VB2014-Wardle.pdf" target="_blank">
       [6]
      </a>
     </sup>
    </span>
    . The agent name may be disguised by using a name from a related operating system or benign software. Launch Agents are created with user level privileges and are executed with the privileges of the user when they log in
    <span class="scite-citeref-number" data-reference="OSX Malware Detection" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.synack.com/wp-content/uploads/2016/03/RSA_OSX_Malware.pdf" target="_blank">
       [7]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="OceanLotus for OS X" id="scite-ref-8-a">
     <sup>
      <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.alienvault.com/blogs/labs-research/oceanlotus-for-os-x-an-application-bundle-pretending-to-be-an-adobe-flash-update" target="_blank">
       [8]
      </a>
     </sup>
    </span>
    . They can be set up to execute when a specific user logs in (in the specific user’s directory structure) or when any user logs in (which requires administrator privileges).
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1159
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
      : Persistence
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Platform:
      </span>
      macOS
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Permissions Required:
      </span>
      User, Administrator
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
      File monitoring, Process monitoring
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
     <a href="https://attack.mitre.org/software/S0274">
      Calisto
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0274">
       Calisto
      </a>
      adds a .plist file to the
      <code>
       /Library/LaunchAgents
      </code>
      folder to maintain persistence.
      <span class="scite-citeref-number" data-reference="Securelist Calisto July 2018" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://securelist.com/calisto-trojan-for-macos/86543/" target="_blank">
         [9]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0235">
      CrossRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0235">
       CrossRAT
      </a>
      creates a Launch Agent on macOS.
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0281">
      Dok
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0281">
       Dok
      </a>
      persists via a Launch Agent.
      <span class="scite-citeref-number" data-reference="objsee mac malware 2017" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://objective-see.com/blog/blog_0x25.html" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0277">
      FruitFly
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0277">
       FruitFly
      </a>
      persists via a Launch Agent.
      <span class="scite-citeref-number" data-reference="objsee mac malware 2017" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://objective-see.com/blog/blog_0x25.html" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0276">
      Keydnap
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0276">
       Keydnap
      </a>
      uses a Launch Agent to persist.
      <span class="scite-citeref-number" data-reference="synack 2016 review" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://www.synack.com/2017/01/01/mac-malware-2016/" target="_blank">
         [11]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0162">
      Komplex
     </a>
    </td>
    <td>
     <p>
      The
      <a href="https://attack.mitre.org/software/S0162">
       Komplex
      </a>
      trojan creates a persistent launch agent called with
      <code>
       $HOME/Library/LaunchAgents/com.apple.updates.plist
      </code>
      with
      <code>
       launchctl load -w ~/Library/LaunchAgents/com.apple.updates.plist
      </code>
      .
      <span class="scite-citeref-number" data-reference="Sofacy Komplex Trojan" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://researchcenter.paloaltonetworks.com/2016/09/unit42-sofacys-komplex-os-x-trojan/" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0282">
      MacSpy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0282">
       MacSpy
      </a>
      persists via a Launch Agent.
      <span class="scite-citeref-number" data-reference="objsee mac malware 2017" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://objective-see.com/blog/blog_0x25.html" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0279">
      Proton
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0279">
       Proton
      </a>
      persists via a Launch Agent.
      <span class="scite-citeref-number" data-reference="objsee mac malware 2017" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://objective-see.com/blog/blog_0x25.html" target="_blank">
         [10]
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
  Restrict user's abilities to create Launch Agents with group policy.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor Launch Agent creation through additional plist files and utilities such as Objective-See’s  KnockKnock application. Launch Agents also require files on disk for persistence which can also be monitored via other file monitoring applications.
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
       <a class="external text" href="https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/CreatingLaunchdJobs.html" name="scite-1" rel="nofollow" target="_blank">
        Apple. (n.d.). Creating Launch Daemons and Agents. Retrieved July 10, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2016/07/06/new-osxkeydnap-malware-hungry-credentials/" name="scite-2" rel="nofollow" target="_blank">
        Marc-Etienne M.Leveille. (2016, July 6). New OSX/Keydnap malware is hungry for credentials. Retrieved July 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.malwarebytes.com/threat-analysis/2017/01/new-mac-backdoor-using-antiquated-code/" name="scite-3" rel="nofollow" target="_blank">
        Thomas Reed. (2017, January 18). New Mac backdoor using antiquated code. Retrieved July 5, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.malwarebytes.com/threat-analysis/2017/04/new-osx-dok-malware-intercepts-web-traffic/" name="scite-4" rel="nofollow" target="_blank">
        Thomas Reed. (2017, July 7). New OSX.Dok malware intercepts web traffic. Retrieved July 10, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2016/09/unit42-sofacys-komplex-os-x-trojan/" name="scite-5" rel="nofollow" target="_blank">
        Dani Creus, Tyler Halfpop, Robert Falcone. (2016, September 26). Sofacy's 'Komplex' OS X Trojan. Retrieved July 8, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.virusbulletin.com/uploads/pdf/conference/vb2014/VB2014-Wardle.pdf" name="scite-6" rel="nofollow" target="_blank">
        Patrick Wardle. (2014, September). Methods of Malware Persistence on Mac OS X. Retrieved July 5, 2017.
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
       <a class="external text" href="https://www.synack.com/wp-content/uploads/2016/03/RSA_OSX_Malware.pdf" name="scite-7" rel="nofollow" target="_blank">
        Patrick Wardle. (2016, February 29). Let's Play Doctor: Practical OS X Malware Detection &amp; Analysis. Retrieved July 10, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.alienvault.com/blogs/labs-research/oceanlotus-for-os-x-an-application-bundle-pretending-to-be-an-adobe-flash-update" name="scite-8" rel="nofollow" target="_blank">
        Eddie Lee. (2016, February 17). OceanLotus for OS X - an Application Bundle Pretending to be an Adobe Flash Update. Retrieved July 5, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/calisto-trojan-for-macos/86543/" name="scite-9" rel="nofollow" target="_blank">
        Kuzin, M., Zelensky S. (2018, July 20). Calisto Trojan for macOS. Retrieved September 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://objective-see.com/blog/blog_0x25.html" name="scite-10" rel="nofollow" target="_blank">
        Patrick Wardle. (n.d.). Mac Malware of 2017. Retrieved September 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.synack.com/2017/01/01/mac-malware-2016/" name="scite-11" rel="nofollow" target="_blank">
        Patrick Wardle. (2017, January 1). Mac Malware of 2016. Retrieved September 21, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
