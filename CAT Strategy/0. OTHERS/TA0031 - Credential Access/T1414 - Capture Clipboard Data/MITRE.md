<div class="container-fluid">
 <h1>
  Capture Clipboard Data
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    A malicious app or other attack vector could capture sensitive data stored in the device clipboard, for example passwords being copy-and-pasted from a password manager app.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1414
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
      <a href="https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-35.html" target="_blank">
       APP-35
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
     <a href="https://attack.mitre.org/software/S0295">
      RCSAndroid
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0295">
       RCSAndroid
      </a>
      can monitor clipboard content.
      <span class="scite-citeref-number" data-reference="TrendMicro-RCSAndroid" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="http://blog.trendmicro.com/trendlabs-security-intelligence/hacking-team-rcsandroid-spying-tool-listens-to-calls-roots-devices-to-get-in/" target="_blank">
         [1]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0297">
      XcodeGhost
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0297">
       XcodeGhost
      </a>
      can read and write data in the user’s clipboard.
      <span class="scite-citeref-number" data-reference="PaloAlto-XcodeGhost" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="http://researchcenter.paloaltonetworks.com/2015/09/update-xcodeghost-attacker-can-phish-passwords-and-open-urls-though-infected-apps/" target="_blank">
         [2]
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
       <a class="external text" href="http://blog.trendmicro.com/trendlabs-security-intelligence/hacking-team-rcsandroid-spying-tool-listens-to-calls-roots-devices-to-get-in/" name="scite-1" rel="nofollow" target="_blank">
        Veo Zhang. (2015, July 21). Hacking Team RCSAndroid Spying Tool Listens to Calls; Roots Devices to Get In. Retrieved December 22, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="2.0">
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2015/09/update-xcodeghost-attacker-can-phish-passwords-and-open-urls-though-infected-apps/" name="scite-2" rel="nofollow" target="_blank">
        Claud Xiao. (2015, September 18). Update: XcodeGhost Attacker Can Phish Passwords and Open URLs through Infected Apps. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
