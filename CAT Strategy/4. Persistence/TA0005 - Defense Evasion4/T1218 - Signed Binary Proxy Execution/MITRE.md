<div class="container-fluid">
 <h1>
  Signed Binary Proxy Execution
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Binaries signed with trusted digital certificates can execute on Windows systems protected by digital signature validation. Several Microsoft signed binaries that are default on Windows installations can be used to proxy execution of other files. This behavior may be abused by adversaries to execute malicious files that could bypass application whitelisting and signature validation on systems. This technique accounts for proxy execution methods that are not already accounted for within the existing techniques.
   </p>
   <h3>
    Mavinject.exe
   </h3>
   <p>
    Mavinject.exe is a Windows utility that allows for code execution. Mavinject can be used to input a DLL into a running process.
    <span class="scite-citeref-number" data-reference="Twitter gN3mes1s Status Update MavInject32" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://twitter.com/gn3mes1s/status/941315826107510784" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    <code>
     "C:\Program Files\Common Files\microsoft shared\ClickToRun\MavInject32.exe"
     <pid>
      /INJECTRUNNING
      <path dll="">
      </path>
     </pid>
    </code>
    <code>
     C:\Windows\system32\mavinject.exe
     <pid>
      /INJECTRUNNING
      <path dll="">
      </path>
     </pid>
    </code>
   </p>
   <h3>
    SyncAppvPublishingServer.exe
   </h3>
   <p>
    SyncAppvPublishingServer.exe can be used to run powershell scripts without executing powershell.exe.
    <span class="scite-citeref-number" data-reference="Twitter monoxgas Status Update SyncAppvPublishingServer" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://twitter.com/monoxgas/status/895045566090010624" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Several others binaries exist that may be used to perform similar behavior.
    <span class="scite-citeref-number" data-reference="GitHub Ultimate AppLocker Bypass List" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://github.com/api0cradle/UltimateAppLockerByPassList" target="_blank">
       [3]
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
      : T1218
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
      : Defense Evasion, Execution
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Platform:
      </span>
      Windows
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
      Process monitoring, Process command-line parameters
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Supports Remote:
      </span>
      No
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Defense Bypassed:
      </span>
      Application whitelisting, Digital Certificate Validation
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
 <h2 class="pt-3" id="mitigation">
  Mitigation
 </h2>
 <p>
  Certain signed binaries that can be used to execute other programs may not be necessary within a given environment. Use application whitelisting configured to block execution of these scripts if they are not required for a given system or network to prevent potential misuse by adversaries.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor processes and command-line parameters for signed binaries that may be used to proxy execution of malicious files. Correlate activity with other suspicious behavior to reduce false positives that may be due to normal benign use by users and administrators.
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
       <a class="external text" href="https://twitter.com/gn3mes1s/status/941315826107510784" name="scite-1" rel="nofollow" target="_blank">
        Giuseppe. (2017, December 14). gN3mes1s Status Update. Retrieved April 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://twitter.com/monoxgas/status/895045566090010624" name="scite-2" rel="nofollow" target="_blank">
        Landers, N. (2017, August 8). monoxgas Status Update. Retrieved April 10, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="3.5">
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/api0cradle/UltimateAppLockerByPassList" name="scite-3" rel="nofollow" target="_blank">
        Moe, O. (2018, March 1). Ultimate AppLocker Bypass List. Retrieved April 10, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
