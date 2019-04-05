<div class="container-fluid">
 <h1>
  DCShadow
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    DCShadow is a method of manipulating Active Directory (AD) data, including objects and schemas, by registering (or reusing an inactive registration) and simulating the behavior of a Domain Controller (DC).
    <span class="scite-citeref-number" data-reference="DCShadow Blog" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.dcshadow.com/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="BlueHat DCShadow Jan 2018" id="scite-ref-2-a">
     <sup>
      [2]
     </sup>
    </span>
    Once registered, a rogue DC may be able to inject and replicate changes into AD infrastructure for any domain object, including credentials and keys.
   </p>
   <p>
    Registering a rogue DC involves creating a new server and nTDSDSA objects in the Configuration partition of the AD schema, which requires Administrator privileges (either Domain or local to the DC) or the KRBTGT hash.
    <span class="scite-citeref-number" data-reference="Adsecurity Mimikatz Guide" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://adsecurity.org/?page_id=1821" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    This technique may bypass system logging and security monitors such as security information and event management (SIEM) products (since actions taken on a rogue DC may not be reported to these sensors).
    <span class="scite-citeref-number" data-reference="DCShadow Blog" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.dcshadow.com/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    The technique may also be used to alter and delete replication and other associated metadata to obstruct forensic analysis. Adversaries may also utilize this technique to perform
    <a href="https://attack.mitre.org/techniques/T1178">
     SID-History Injection
    </a>
    and/or manipulate AD objects (such as accounts, access control lists, schemas) to establish backdoors for Persistence.
    <span class="scite-citeref-number" data-reference="DCShadow Blog" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.dcshadow.com/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="BlueHat DCShadow Jan 2018" id="scite-ref-2-a">
     <sup>
      [2]
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
      : T1207
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
       Permissions Required:
      </span>
      Administrator
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
      API monitoring, Authentication logs, Network protocol analysis, Packet capture
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
      Log analysis
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
      Vincent Le Toux
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
     <a href="https://attack.mitre.org/software/S0002">
      Mimikatz
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      ’s
      <code>
       LSADUMP::DCShadow
      </code>
      module can be used to make AD updates by temporarily setting a computer to be a DC.
      <span class="scite-citeref-number" data-reference="Deply Mimikatz" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://github.com/gentilkiwi/mimikatz" target="_blank">
         [4]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Adsecurity Mimikatz Guide" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://adsecurity.org/?page_id=1821" target="_blank">
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
  This type of attack technique cannot be easily mitigated with preventive controls since it is based on the abuse of AD design features. For example, mitigating specific AD API calls will likely have unintended side effects, such as preventing DC replication from operating properly. Efforts should be focused on preventing adversary tools from running earlier in the chain of activity and on identification of subsequent malicious behavior.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor and analyze network traffic associated with data replication (such as calls to DrsAddEntry, DrsReplicaAdd, and especially GetNCChanges) between DCs as well as to/from non DC hosts.
  <span class="scite-citeref-number" data-reference="GitHub DCSYNCMonitor" id="scite-ref-5-a">
   <sup>
    <a aria-describedby="qtip-4" data-hasqtip="4" href="https://github.com/shellster/DCSYNCMonitor" target="_blank">
     [5]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="DCShadow Blog" id="scite-ref-1-a">
   <sup>
    <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.dcshadow.com/" target="_blank">
     [1]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="BlueHat DCShadow Jan 2018" id="scite-ref-2-a">
   <sup>
    [2]
   </sup>
  </span>
  DC replication will naturally take place every 15 minutes but can be triggered by an attacker or by legitimate urgent changes (ex: passwords).
  <span class="scite-citeref-number" data-reference="BlueHat DCShadow Jan 2018" id="scite-ref-2-a">
   <sup>
    [2]
   </sup>
  </span>
  Also consider monitoring and alerting on the replication of AD objects (Audit Detailed Directory Service Replication Events 4928 and 4929).
  <span class="scite-citeref-number" data-reference="DCShadow Blog" id="scite-ref-1-a">
   <sup>
    <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.dcshadow.com/" target="_blank">
     [1]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Leverage AD directory synchronization (DirSync) to monitor changes to directory state using AD replication cookies.
  <span class="scite-citeref-number" data-reference="Microsoft DirSync" id="scite-ref-6-a">
   <sup>
    <a aria-describedby="qtip-5" data-hasqtip="5" href="https://msdn.microsoft.com/en-us/library/ms677626.aspx" target="_blank">
     [6]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="ADDSecurity DCShadow Feb 2018" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://adds-security.blogspot.fr/2018/02/detecter-dcshadow-impossible.html" target="_blank">
     [7]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Baseline and periodically analyze the Configuration partition of the AD schema and alert on creation of nTDSDSA objects.
  <span class="scite-citeref-number" data-reference="BlueHat DCShadow Jan 2018" id="scite-ref-2-a">
   <sup>
    [2]
   </sup>
  </span>
 </p>
 <p>
  Investigate usage of Kerberos Service Principal Names (SPNs), especially those associated with services (beginning with "GC/") by computers not present in the DC organizational unit (OU). The SPN associated with the Directory Replication Service (DRS) Remote Protocol interface (GUID E3514235–4B06–11D1-AB04–00C04FC2DCD2) can be set without logging.
  <span class="scite-citeref-number" data-reference="ADDSecurity DCShadow Feb 2018" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://adds-security.blogspot.fr/2018/02/detecter-dcshadow-impossible.html" target="_blank">
     [7]
    </a>
   </sup>
  </span>
  A rogue DC must authenticate as a service using these two SPNs for the replication process to successfully complete.
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
       <a class="external text" href="https://www.dcshadow.com/" name="scite-1" rel="nofollow" target="_blank">
        Delpy, B. &amp; LE TOUX, V. (n.d.). DCShadow. Retrieved March 20, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       Delpy, B. &amp; LE TOUX, V. (2018, January 24). Active Directory: What can make your million dollar SIEM go blind?. Retrieved March 20, 2018.
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://adsecurity.org/?page_id=1821" name="scite-3" rel="nofollow" target="_blank">
        Metcalf, S. (2015, November 13). Unofficial Guide to Mimikatz &amp; Command Reference. Retrieved December 23, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/gentilkiwi/mimikatz" name="scite-4" rel="nofollow" target="_blank">
        Deply, B. (n.d.). Mimikatz. Retrieved September 29, 2015.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="5.5">
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/shellster/DCSYNCMonitor" name="scite-5" rel="nofollow" target="_blank">
        Spencer S. (2018, February 22). DCSYNCMonitor. Retrieved March 30, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/en-us/library/ms677626.aspx" name="scite-6" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Polling for Changes Using the DirSync Control. Retrieved March 30, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://adds-security.blogspot.fr/2018/02/detecter-dcshadow-impossible.html" name="scite-7" rel="nofollow" target="_blank">
        Lucand,G. (2018, February 18). Detect DCShadow, impossible?. Retrieved March 30, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
