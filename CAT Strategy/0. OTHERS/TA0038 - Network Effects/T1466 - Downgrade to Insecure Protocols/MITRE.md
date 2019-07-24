<div class="container-fluid">
 <h1>
  Downgrade to Insecure Protocols
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An adversary could cause the mobile device to use less secure protocols, for example by jamming frequencies used by newer protocols such as LTE and only allowing older protocols such as GSM to communicate
    <span class="scite-citeref-number" data-reference="NIST-SP800187" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://csrc.nist.gov/publications/drafts/800-187/sp800_187_draft.pdf" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    . Use of less secure protocols may make communication easier to eavesdrop upon or manipulate.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1466
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
      : Network Effects
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
      <a href="https://pages.nist.gov/mobile-threat-catalogue/cellular-threats/CEL-3.html" target="_blank">
       CEL-3
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
     <a href="https://attack.mitre.org/mitigations/M1009">
      Encrypt Network Traffic
     </a>
    </td>
    <td>
     Application-layer encryption (e.g. use of the Transport Layer Security protocol) or a Virtual Private Network (VPN) tunnel (e.g. using the IPsec protocol) may help mitigate weaknesses in the cellular network encryption.
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
       <a class="external text" href="http://csrc.nist.gov/publications/drafts/800-187/sp800_187_draft.pdf" name="scite-1" rel="nofollow" target="_blank">
        Jeffrey Cichonski, Joshua M Franklin, Michael Bartock. (2017, December). Guide to LTE Security. Retrieved January 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://techcrunch.com/2016/06/14/apple-will-require-https-connections-for-ios-apps-by-the-end-of-2016/" name="scite-2" rel="nofollow" target="_blank">
        Kate Conger. (2016, June 14). Apple will require HTTPS connections for iOS apps by the end of 2016. Retrieved December 19, 2016.
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
       <a class="external text" href="https://developer.android.com/training/articles/security-config.html" name="scite-3" rel="nofollow" target="_blank">
        Google. (n.d.). Network Security Configuration. Retrieved December 19, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
