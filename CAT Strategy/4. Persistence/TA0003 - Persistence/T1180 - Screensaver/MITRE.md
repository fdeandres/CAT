<div class="container-fluid">
 <h1>
  Screensaver
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Screensavers are programs that execute after a configurable time of user inactivity and consist of Portable Executable (PE) files with a .scr file extension.
    <span class="scite-citeref-number" data-reference="Wikipedia Screensaver" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://en.wikipedia.org/wiki/Screensaver" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    The Windows screensaver application scrnsave.exe is located in
    <code>
     C:\Windows\System32\
    </code>
    along with screensavers included with base Windows installations. The following screensaver settings are stored in the Registry (
    <code>
     HKCU\Control Panel\Desktop\
    </code>
    ) and could be manipulated to achieve persistence:
   </p>
   <ul>
    <li>
     <code>
      SCRNSAVE.exe
     </code>
     - set to malicious PE path
    </li>
    <li>
     <code>
      ScreenSaveActive
     </code>
     - set to '1' to enable the screensaver
    </li>
    <li>
     <code>
      ScreenSaverIsSecure
     </code>
     - set to '0' to not require a password to unlock
    </li>
    <li>
     <code>
      ScreenSaverTimeout
     </code>
     - sets user inactivity timeout before screensaver is executed
    </li>
   </ul>
   <p>
    Adversaries can use screensaver settings to maintain persistence by setting the screensaver to run malware after a certain timeframe of user inactivity.
    <span class="scite-citeref-number" data-reference="ESET Gazer Aug 2017" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf" target="_blank">
       [2]
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
      : T1180
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
      Process monitoring, Process command-line parameters, Windows Registry, File monitoring
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
      Bartosz Jerzman
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
     <a href="https://attack.mitre.org/software/S0168">
      Gazer
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0168">
       Gazer
      </a>
      can establish persistence through the system screensaver by configuring it to execute the malware.
      <span class="scite-citeref-number" data-reference="ESET Gazer Aug 2017" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf" target="_blank">
         [2]
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
  Block .scr files from being executed from non-standard locations. Set Group Policy to force users to have a dedicated screensaver where local changes should not override the settings to prevent changes. Use Group Policy to disable screensavers if they are unnecessary.
  <span class="scite-citeref-number" data-reference="TechNet Screensaver GP" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="https://technet.microsoft.com/library/cc938799.aspx" target="_blank">
     [3]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor process execution and command-line parameters of .scr files. Monitor changes to screensaver configuration changes in the Registry that may not correlate with typical user behavior.
 </p>
 <p>
  Tools such as Sysinternals Autoruns can be used to detect changes to the screensaver binary path in the Registry. Suspicious paths and PE files may indicate outliers among legitimate screensavers in a network and should be investigated.
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
       <a class="external text" href="https://en.wikipedia.org/wiki/Screensaver" name="scite-1" rel="nofollow" target="_blank">
        Wikipedia. (2017, November 22). Screensaver. Retrieved December 5, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf" name="scite-2" rel="nofollow" target="_blank">
        ESET. (2017, August). Gazing at Gazer: Turla’s new second stage backdoor. Retrieved September 14, 2017.
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
       <a class="external text" href="https://technet.microsoft.com/library/cc938799.aspx" name="scite-3" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Customizing the Desktop. Retrieved December 5, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
