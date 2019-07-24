<div class="container-fluid">
 <h1>
  Obtain Device Cloud Backups
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An adversary who is able to obtain unauthorized access to or misuse authorized access to cloud backup services (e.g. Google's Android backup service or Apple's iCloud) could use that access to obtain sensitive data stored in device backups. For example, the Elcomsoft Phone Breaker product advertises the ability to retrieve iOS backup data from Apple's iCloud
    <span class="scite-citeref-number" data-reference="Elcomsoft-EPPB" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.elcomsoft.com/eppb.html" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    . Elcomsoft also describes
    <span class="scite-citeref-number" data-reference="Elcomsoft-WhatsApp" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://blog.elcomsoft.com/2017/07/extract-and-decrypt-whatsapp-backups-from-icloud/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    obtaining WhatsApp communication histories from backups stored in iCloud.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1470
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Tactic Type:
      </span>
      Without Adversary Device Access
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Tactic
      </span>
      : Remote Service Effects
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
      <a href="https://pages.nist.gov/mobile-threat-catalogue/ecosystem-threats/ECO-0.html" target="_blank">
       ECO-0
      </a>
      ,
      <a href="https://pages.nist.gov/mobile-threat-catalogue/ecosystem-threats/ECO-1.html" target="_blank">
       ECO-1
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
     <a href="https://attack.mitre.org/mitigations/M1011">
      User Guidance
     </a>
    </td>
    <td>
     Encourage users to protect their account credentials and to enable available multi-factor authentication options.
    </td>
   </tr>
  </tbody>
 </table>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Google provides the ability for users to view their account activity. Apple iCloud also provides notifications to users of account activity.
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
       <a class="external text" href="https://www.elcomsoft.com/eppb.html" name="scite-1" rel="nofollow" target="_blank">
        Elcomsoft. (n.d.). Elcomsoft Phone Breaker. Retrieved December 29, 2016.
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
       <a class="external text" href="https://blog.elcomsoft.com/2017/07/extract-and-decrypt-whatsapp-backups-from-icloud/" name="scite-2" rel="nofollow" target="_blank">
        Oleg Afonin. (2017, July 20). Extract and Decrypt WhatsApp Backups from iCloud. Retrieved July 6, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
