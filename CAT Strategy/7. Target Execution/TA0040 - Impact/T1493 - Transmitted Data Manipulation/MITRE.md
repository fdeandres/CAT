<div class="container-fluid">
 <h1>
  Transmitted Data Manipulation
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries may alter data en route to storage or other systems in order to manipulate external outcomes or hide activity.
    <span class="scite-citeref-number" data-reference="FireEye APT38 Oct 2018" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://content.fireeye.com/apt/rpt-apt38" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="DOJ Lazarus Sony 2018" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.justice.gov/opa/press-release/file/1092091/download" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    By manipulating transmitted data, adversaries may attempt to affect a business process, organizational understanding, and decision making.
   </p>
   <p>
    Manipulation may be possible over a network connection or between system processes where there is an opportunity deploy a tool that will intercept and change information. The type of modification and the impact it will have depends on the target transmission mechanism as well as the goals and objectives of the adversary. For complex systems, an adversary would likely need special expertise and possibly access to specialized software related to the system that would typically be gained through a prolonged information gathering campaign in order to have the desired impact.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1493
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
      : Impact
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Platform:
      </span>
      Linux, macOS, Windows
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Permissions Required:
      </span>
      User, Administrator, root, SYSTEM
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
      Packet capture, Network protocol analysis
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
       Impact Type:
      </span>
      Integrity
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
     <a href="https://attack.mitre.org/groups/G0082">
      APT38
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0082">
       APT38
      </a>
      has used DYEPACK to manipulate SWIFT messages en route to a printer.
      <span class="scite-citeref-number" data-reference="FireEye APT38 Oct 2018" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://content.fireeye.com/apt/rpt-apt38" target="_blank">
         [1]
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
  Identify critical business and system processes that may be targeted by adversaries and work to secure communications related to those processes against tampering. Encrypt all important data flows to reduce the impact of tailored modifications on data in transit.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Detecting the manipulation of data as at passes over a network can be difficult without the appropriate tools. In some cases integrity verification checks, such as file hashing, may be used on critical files as they transit a network. With some critical processes involving transmission of data, manual or out-of-band integrity checking may be useful for identifying manipulated data.
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
       <a class="external text" href="https://content.fireeye.com/apt/rpt-apt38" name="scite-1" rel="nofollow" target="_blank">
        FireEye. (2018, October 03). APT38: Un-usual Suspects. Retrieved November 6, 2018.
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
       <a class="external text" href="https://www.justice.gov/opa/press-release/file/1092091/download" name="scite-2" rel="nofollow" target="_blank">
        Department of Justice. (2018, September 6). Criminal Complaint - United States of America v. PARK JIN HYOK. Retrieved March 29, 2019.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
