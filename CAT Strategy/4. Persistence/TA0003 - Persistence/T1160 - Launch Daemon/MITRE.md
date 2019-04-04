<div class="container-fluid">
 <h1>
  Launch Daemon
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Per Apple’s developer documentation, when macOS and OS X boot up, launchd is run to finish system initialization. This process loads the parameters for each launch-on-demand system-level daemon from the property list (plist) files found in
    <code>
     /System/Library/LaunchDaemons
    </code>
    and
    <code>
     /Library/LaunchDaemons
    </code>
    <span class="scite-citeref-number" data-reference="AppleDocs Launch Agent Daemons" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/CreatingLaunchdJobs.html" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    . These LaunchDaemons have property list files which point to the executables that will be launched
    <span class="scite-citeref-number" data-reference="Methods of Mac Malware Persistence" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.virusbulletin.com/uploads/pdf/conference/vb2014/VB2014-Wardle.pdf" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    .
   </p>
   <p>
    Adversaries may install a new launch daemon that can be configured to execute at startup by using launchd or launchctl to load a plist into the appropriate directories
    <span class="scite-citeref-number" data-reference="OSX Malware Detection" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.synack.com/wp-content/uploads/2016/03/RSA_OSX_Malware.pdf" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    . The daemon name may be disguised by using a name from a related operating system or benign software
    <span class="scite-citeref-number" data-reference="WireLurker" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.paloaltonetworks.com/content/dam/pan/en_US/assets/pdf/reports/Unit_42/unit42-wirelurker.pdf" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    . Launch Daemons may be created with administrator privileges, but are executed under root privileges, so an adversary may also use a service to escalate privileges from administrator to root.
   </p>
   <p>
    The plist file permissions must be root:wheel, but the script or program that it points to has no such requirement. So, it is possible for poor configurations to allow an adversary to modify a current Launch Daemon’s executable and gain persistence or Privilege Escalation.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1160
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
      : Persistence, Privilege Escalation
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
      Administrator
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Effective Permissions:
      </span>
      root
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      Process monitoring, File monitoring
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
 <h2 class="pt-3" id="mitigation">
  Mitigation
 </h2>
 <p>
  Limit privileges of user accounts and remediate Privilege Escalation vectors so only authorized administrators can create new Launch Daemons.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor Launch Daemon creation through additional plist files and utilities such as Objective-See's Knock Knock application.
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
       <a class="external text" href="https://www.virusbulletin.com/uploads/pdf/conference/vb2014/VB2014-Wardle.pdf" name="scite-2" rel="nofollow" target="_blank">
        Patrick Wardle. (2014, September). Methods of Malware Persistence on Mac OS X. Retrieved July 5, 2017.
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
       <a class="external text" href="https://www.synack.com/wp-content/uploads/2016/03/RSA_OSX_Malware.pdf" name="scite-3" rel="nofollow" target="_blank">
        Patrick Wardle. (2016, February 29). Let's Play Doctor: Practical OS X Malware Detection &amp; Analysis. Retrieved July 10, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.paloaltonetworks.com/content/dam/pan/en_US/assets/pdf/reports/Unit_42/unit42-wirelurker.pdf" name="scite-4" rel="nofollow" target="_blank">
        Claud Xiao. (n.d.). WireLurker: A New Era in iOS and OS X Malware. Retrieved July 10, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
