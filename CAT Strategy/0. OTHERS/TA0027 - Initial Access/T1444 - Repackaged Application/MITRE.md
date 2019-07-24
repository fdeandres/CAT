<div class="container-fluid">
 <h1>
  Repackaged Application
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An adversary could download a legitimate app, disassemble it, add malicious code, and then reassemble the app
    <span class="scite-citeref-number" data-reference="Zhou" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://ieeexplore.ieee.org/document/6234407" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    . The app would appear to be the original app but contain additional malicious functionality. The adversary could then publish this app to app stores or use another delivery technique.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1444
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
      : Initial Access
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
      <a href="https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-14.html" target="_blank">
       APP-14
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
     <a href="https://attack.mitre.org/mitigations/M1011">
      User Guidance
     </a>
    </td>
    <td>
     Users should be encouraged to only install apps from authorized app stores, which are less likely to contain malicious repackaged apps.
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
     <a href="https://attack.mitre.org/software/S0320">
      DroidJack
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0320">
       DroidJack
      </a>
      included code from the legitimate Pokemon GO app in order to appear identical to the user, but it also included additional malicious code.
      <span class="scite-citeref-number" data-reference="Proofpoint-Droidjack" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.proofpoint.com/us/threat-insight/post/droidjack-uses-side-load-backdoored-pokemon-go-android-app" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0314">
      X-Agent for Android
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0314">
       X-Agent for Android
      </a>
      was placed in a repackaged version of an application used by Ukrainian artillery forces.
      <span class="scite-citeref-number" data-reference="CrowdStrike-Android" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.crowdstrike.com/wp-content/brochures/FancyBearTracksUkrainianArtillery.pdf" target="_blank">
         [3]
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
  An EMM/MDM or mobile threat protection solution can identify the presence of unwanted, known insecure, or malicious apps on devices.
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
       <a class="external text" href="http://ieeexplore.ieee.org/document/6234407" name="scite-1" rel="nofollow" target="_blank">
        Yajin Zhou and Xuxian Jiang. (2012, May). Dissecting Android Malware: Characterization and Evolution. Retrieved December 9, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/us/threat-insight/post/droidjack-uses-side-load-backdoored-pokemon-go-android-app" name="scite-2" rel="nofollow" target="_blank">
        Proofpoint. (2016, July 7). DroidJack Uses Side-Load…It's Super Effective! Backdoored Pokemon GO Android App Found. Retrieved January 20, 2017.
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
       <a class="external text" href="https://www.crowdstrike.com/wp-content/brochures/FancyBearTracksUkrainianArtillery.pdf" name="scite-3" rel="nofollow" target="_blank">
        CrowdStrike Global Intelligence Team. (2016). Use of Fancy Bear Android Malware in Tracking of Ukrainian FIeld Artillery Units. Retrieved February 6, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
