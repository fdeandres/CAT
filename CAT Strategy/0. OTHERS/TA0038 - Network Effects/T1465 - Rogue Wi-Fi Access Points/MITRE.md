<div class="container-fluid">
 <h1>
  Rogue Wi-Fi Access Points
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An adversary could set up unauthorized Wi-Fi access points or compromise existing access points and, if the device connects to them, carry out network-based attacks such as eavesdropping on or modifying network communication
    <span class="scite-citeref-number" data-reference="NIST-SP800153" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-153.pdf" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Kaspersky-DarkHotel" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://blog.kaspersky.com/darkhotel-apt/6613/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    .
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1465
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
      <a href="https://pages.nist.gov/mobile-threat-catalogue/lan-pan-threats/LPN-0.html" target="_blank">
       LPN-0
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
     Application-layer encryption (e.g. use of the Transport Layer Security protocol) or a Virtual Private Network (VPN) tunnel (e.g. using the IPsec protocol) may help mitigate use of untrusted Wi-Fi networks.
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1012">
      Enterprise Policy
     </a>
    </td>
    <td>
     Enterprise policies could be provisioned to devices to control the Wi-Fi access points that they are allowed to connect to.
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
       <a class="external text" href="http://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-153.pdf" name="scite-1" rel="nofollow" target="_blank">
        M. Souppaya and K. Scarfone. (2012, February). NIST SP 800-153 Guidelines for Securing Wireless Local Area Networks (WLANs). Retrieved December 24, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.kaspersky.com/darkhotel-apt/6613/" name="scite-2" rel="nofollow" target="_blank">
        Alex Drozhzhin. (2014, November 10). Darkhotel: a spy campaign in luxury Asian hotels. Retrieved December 24, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="3.0">
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://techcrunch.com/2016/06/14/apple-will-require-https-connections-for-ios-apps-by-the-end-of-2016/" name="scite-3" rel="nofollow" target="_blank">
        Kate Conger. (2016, June 14). Apple will require HTTPS connections for iOS apps by the end of 2016. Retrieved December 19, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://developer.android.com/training/articles/security-config.html" name="scite-4" rel="nofollow" target="_blank">
        Google. (n.d.). Network Security Configuration. Retrieved December 19, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
