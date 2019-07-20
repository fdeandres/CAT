<div class="container-fluid">
 <h1>
  Indicator Blocking
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An adversary may attempt to block indicators or events typically captured by sensors from being gathered and analyzed. This could include modifying sensor settings stored in configuration files and/or Registry keys to disable or maliciously redirect event telemetry.
    <span class="scite-citeref-number" data-reference="Microsoft Lamin Sept 2017" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.microsoft.com/wdsi/threats/malware-encyclopedia-description?name=Backdoor:Win32/Lamin.A" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    In the case of network-based reporting of indicators, an adversary may block traffic associated with reporting to prevent central analysis. This may be accomplished by many means, such as stopping a local process responsible for forwarding telemetry and/or creating a host-based firewall rule to block traffic to specific hosts responsible for aggregating events, such as security information and event management (SIEM) products.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1054
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
      : Defense Evasion
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
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      Sensor health and status, Process command-line parameters, Process monitoring
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
       Defense Bypassed:
      </span>
      Anti-virus, Log analysis, Host intrusion prevention systems
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       CAPEC ID:
      </span>
      <a href="https://capec.mitre.org/data/definitions/571.html" target="_blank">
       CAPEC-571
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
  Ensure event tracers/forwarders
  <span class="scite-citeref-number" data-reference="Microsoft ETW May 2018" id="scite-ref-2-a">
   <sup>
    <a aria-describedby="qtip-1" data-hasqtip="1" href="https://docs.microsoft.com/windows/desktop/etw/event-tracing-portal" target="_blank">
     [2]
    </a>
   </sup>
  </span>
  , firewall policies, and other associated mechanisms are secured with appropriate permissions and access controls. Consider automatically relaunching forwarding mechanisms at recurring intervals (ex: temporal, on-logon, etc.) as well as applying appropriate change management to firewall rules and other related system configurations.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Detect lack of reported activity from a host sensor. Different methods of blocking may cause different disruptions in reporting. Systems may suddenly stop reporting all data or only certain kinds of data.
 </p>
 <p>
  Depending on the types of host information collected, an analyst may be able to detect the event that triggered a process to stop or connection to be blocked.
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
       <a class="external text" href="https://www.microsoft.com/wdsi/threats/malware-encyclopedia-description?name=Backdoor:Win32/Lamin.A" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (2009, May 17). Backdoor:Win32/Lamin.A. Retrieved September 6, 2018.
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
       <a class="external text" href="https://docs.microsoft.com/windows/desktop/etw/event-tracing-portal" name="scite-2" rel="nofollow" target="_blank">
        Microsoft. (2018, May 30). Event Tracing. Retrieved September 6, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
