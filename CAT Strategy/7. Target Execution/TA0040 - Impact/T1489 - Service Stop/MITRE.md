<div class="container-fluid">
 <h1>
  Service Stop
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries may stop or disable services on a system to render those services unavailable to legitimate users. Stopping critical services can inhibit or stop response to an incident or aid in the adversary's overall objectives to cause damage to the environment.
    <span class="scite-citeref-number" data-reference="Talos Olympic Destroyer 2018" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://blog.talosintelligence.com/2018/02/olympic-destroyer.html" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Novetta Blockbuster" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries may accomplish this by disabling individual services of high importance to an organization, such as
    <code>
     MSExchangeIS
    </code>
    , which will make Exchange content inaccessible
    <span class="scite-citeref-number" data-reference="Novetta Blockbuster" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    . In some cases, adversaries may stop or disable many or all services to render systems unusable.
    <span class="scite-citeref-number" data-reference="Talos Olympic Destroyer 2018" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://blog.talosintelligence.com/2018/02/olympic-destroyer.html" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    Services may not allow for modification of their data stores while running. Adversaries may stop services in order to conduct
    <a href="https://attack.mitre.org/techniques/T1485">
     Data Destruction
    </a>
    or
    <a href="https://attack.mitre.org/techniques/T1486">
     Data Encrypted for Impact
    </a>
    on the data stores of services like Exchange and SQL Server.
    <span class="scite-citeref-number" data-reference="SecureWorks WannaCry Analysis" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.secureworks.com/research/wcry-ransomware-analysis" target="_blank">
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
      : T1489
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
      Windows
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
      Administrator, SYSTEM, User
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
      Process command-line parameters, Process monitoring, Windows Registry, API monitoring
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
      Availability
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
     <a href="https://attack.mitre.org/groups/G0032">
      Lazarus Group
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0032">
       Lazarus Group
      </a>
      has stopped the MSExchangeIS service to render Exchange contents inaccessible to users.
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster Destructive Malware" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Destructive-Malware-Report.pdf" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0365">
      Olympic Destroyer
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0365">
       Olympic Destroyer
      </a>
      uses the API call
      <code>
       ChangeServiceConfigW
      </code>
      to disable all services on the affected system.
      <span class="scite-citeref-number" data-reference="Talos Olympic Destroyer 2018" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://blog.talosintelligence.com/2018/02/olympic-destroyer.html" target="_blank">
         [1]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0366">
      WannaCry
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0366">
       WannaCry
      </a>
      attempts to kill processes associated with Exchange, Microsoft SQL Server, and MySQL to make it possible to encrypt their data stores.
      <span class="scite-citeref-number" data-reference="FireEye WannaCry 2017" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.fireeye.com/blog/threat-research/2017/05/wannacry-malware-profile.html" target="_blank">
         [5]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="SecureWorks WannaCry Analysis" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.secureworks.com/research/wcry-ransomware-analysis" target="_blank">
         [3]
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
  Ensure proper process, registry, and file permissions are in place to inhibit adversaries from disabling or interfering with critical services. Limit privileges of user accounts and groups so that only authorized administrators can interact with service changes and service configurations. Harden systems used to serve critical network, business, and communications functions. Operate intrusion detection, analysis, and response systems on a separate network from the production environment to lessen the chances that an adversary can see and interfere with critical response functions.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor processes and command-line arguments to see if critical processes are terminated or stop running.
 </p>
 <p>
  Monitor Registry edits for modifications to services and startup programs that correspond to services of high importance. Look for changes to service Registry entries that do not correlate with known software, patch cycles, etc. Service information is stored in the Registry at
  <code>
   HKLM\SYSTEM\CurrentControlSet\Services
  </code>
  .
 </p>
 <p>
  Alterations to the service binary path or the service startup type changed to disabled may be suspicious.
 </p>
 <p>
  Remote access tools with built-in features may interact directly with the Windows API to perform these functions outside of typical system utilities. For example,
  <code>
   ChangeServiceConfigW
  </code>
  may be used by an adversary to prevent services from starting.
  <span class="scite-citeref-number" data-reference="Talos Olympic Destroyer 2018" id="scite-ref-1-a">
   <sup>
    <a aria-describedby="qtip-0" data-hasqtip="0" href="https://blog.talosintelligence.com/2018/02/olympic-destroyer.html" target="_blank">
     [1]
    </a>
   </sup>
  </span>
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
       <a class="external text" href="https://blog.talosintelligence.com/2018/02/olympic-destroyer.html" name="scite-1" rel="nofollow" target="_blank">
        Mercer, W. and Rascagneres, P. (2018, February 12). Olympic Destroyer Takes Aim At Winter Olympics. Retrieved March 14, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" name="scite-2" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Unraveling the Long Thread of the Sony Attack. Retrieved February 25, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/wcry-ransomware-analysis" name="scite-3" rel="nofollow" target="_blank">
        Counter Threat Unit Research Team. (2017, May 18). WCry Ransomware Analysis. Retrieved March 26, 2019.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="4.5">
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Destructive-Malware-Report.pdf" name="scite-4" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Destructive Malware Report. Retrieved March 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/05/wannacry-malware-profile.html" name="scite-5" rel="nofollow" target="_blank">
        Berry, A., Homan, J., and Eitzman, R. (2017, May 23). WannaCry Malware Profile. Retrieved March 15, 2019.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
