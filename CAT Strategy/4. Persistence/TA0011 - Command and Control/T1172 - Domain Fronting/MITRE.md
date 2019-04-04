<div class="container-fluid">
 <h1>
  Domain Fronting
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Domain fronting takes advantage of routing schemes in Content Delivery Networks (CDNs) and other services which host multiple domains to obfuscate the intended destination of HTTPS traffic or traffic tunneled through HTTPS.
    <span class="scite-citeref-number" data-reference="Fifield Blocking Resistent Communication through domain fronting 2015" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://www.icir.org/vern/papers/meek-PETS-2015.pdf" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    The technique involves using different domain names in the SNI field of the TLS header and the Host field of the HTTP header. If both domains are served from the same CDN, then the CDN may route to the address specified in the HTTP header after unwrapping the TLS header. A variation of the the technique, "domainless" fronting, utilizes a SNI field that is left blank; this may allow the fronting to work even when the CDN attempts to validate that the SNI and HTTP Host fields match (if the blank SNI fields are ignored).
   </p>
   <p>
    For example, if domain-x and domain-y are customers of the same CDN, it is possible to place domain-x in the TLS header and domain-y in the HTTP header. Traffic will appear to be going to domain-x, however the CDN may route it to domain-y.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1172
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
      : Command And Control
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
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      SSL/TLS inspection, Packet capture
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Requires Network:
      </span>
      Yes
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
       Contributors:
      </span>
      Matt Kelly, @breakersall
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
     <a href="https://attack.mitre.org/groups/G0016">
      APT29
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0016">
       APT29
      </a>
      has used the meek domain fronting plugin for Tor to hide the destination of C2 traffic.
      <span class="scite-citeref-number" data-reference="Mandiant No Easy Breach" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="http://www.slideshare.net/MatthewDunwoody1/no-easy-breach-derby-con-2016" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0175">
      meek
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0175">
       meek
      </a>
      uses Domain Fronting to disguise the destination of network traffic as another server that is hosted in the same Content Delivery Network (CDN) as the intended desitnation.
     </p>
    </td>
   </tr>
  </tbody>
 </table>
 <h2 class="pt-3" id="mitigation">
  Mitigation
 </h2>
 <p>
  If it is possible to inspect HTTPS traffic, the captures can be analyzed for connections that appear to be Domain Fronting.
 </p>
 <p>
  In order to use domain fronting, attackers will likely need to deploy additional tools to compromised systems.
  <span class="scite-citeref-number" data-reference="FireEye APT29 Domain Fronting With TOR March 2017" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.fireeye.com/blog/threat-research/2017/03/apt29_domain_frontin.html" target="_blank">
     [3]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Mandiant No Easy Breach" id="scite-ref-2-a">
   <sup>
    <a aria-describedby="qtip-1" data-hasqtip="1" href="http://www.slideshare.net/MatthewDunwoody1/no-easy-breach-derby-con-2016" target="_blank">
     [2]
    </a>
   </sup>
  </span>
  It may be possible to detect or prevent the installation of these tools with Host-based solutions.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  If SSL inspection is in place or the traffic is not encrypted, the Host field of the HTTP header can be checked if it matches the HTTPS SNI or against a blacklist or whitelist of domain names.
  <span class="scite-citeref-number" data-reference="Fifield Blocking Resistent Communication through domain fronting 2015" id="scite-ref-1-a">
   <sup>
    <a aria-describedby="qtip-0" data-hasqtip="0" href="http://www.icir.org/vern/papers/meek-PETS-2015.pdf" target="_blank">
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
       <a class="external text" href="http://www.icir.org/vern/papers/meek-PETS-2015.pdf" name="scite-1" rel="nofollow" target="_blank">
        David Fifield, Chang Lan, Rod Hynes, Percy Wegmann, and Vern Paxson. (2015). Blocking-resistant communication through domain fronting. Retrieved November 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.slideshare.net/MatthewDunwoody1/no-easy-breach-derby-con-2016" name="scite-2" rel="nofollow" target="_blank">
        Dunwoody, M. and Carr, N.. (2016, September 27). No Easy Breach DerbyCon 2016. Retrieved October 4, 2016.
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
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/03/apt29_domain_frontin.html" name="scite-3" rel="nofollow" target="_blank">
        Matthew Dunwoody. (2017, March 27). APT29 Domain Fronting With TOR. Retrieved November 20, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
