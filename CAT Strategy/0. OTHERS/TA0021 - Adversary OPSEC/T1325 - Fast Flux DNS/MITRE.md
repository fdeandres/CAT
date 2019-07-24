<div class="container-fluid">
 <h1>
  Fast Flux DNS
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    A technique in which a fully qualified domain name has multiple IP addresses assigned to it which are swapped with extreme frequency, using a combination of round robin IP address and short Time-To-Live (TTL) for a DNS resource record.
    <span class="scite-citeref-number" data-reference="HoneynetFastFlux" id="scite-ref-1-a">
     <sup>
      [1]
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="MisnomerFastFlux" id="scite-ref-2-a">
     <sup>
      [2]
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="MehtaFastFluxPt1" id="scite-ref-3-a">
     <sup>
      [3]
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="MehtaFastFluxPt2" id="scite-ref-4-a">
     <sup>
      [4]
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
      : T1325
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
      : Adversary Opsec
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
 <h2 class="pt-3" id="detectable">
  Detection
 </h2>
 <b>
  Detectable by Common Defenses (Yes/No/Partial):
 </b>
 Partial
 <br/>
 <br/>
 <b>
  Explanation:
 </b>
 In general, detecting usage of fast flux DNS is difficult due to web traffic load balancing that services client requests quickly.  In single flux cases only IP addresses change for static domain names.  In double flux cases, nothing is static.  Defenders such as IPS, domain registrars, and service providers are likely in the best position for detection.
 <br/>
 <br/>
 <h2 class="pt-3" id="difficulty">
  Difficulty for the Adversary
 </h2>
 <b>
  Easy for the Adversary (Yes/No):
 </b>
 Yes
 <br/>
 <br/>
 <b>
  Explanation:
 </b>
 Fast flux is generally simple for an adversary to set up and offers several advantages.  Such advantages include limited audit trails for defenders to find, ease of operation for an adversary to maintain, and support for main nodes.
 <br/>
 <br/>
 <h2 class="pt-3" id="references">
  References
 </h2>
 <div class="row">
  <div class="col">
   <ol>
    <li>
     <span class="scite-citation" id="scite-1">
      <span class="scite-citation-text">
       Jamie Riden. (2008, August 16). HOW FAST-FLUX SERVICE NETWORKS WORK. Retrieved March 6, 2017.
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       Misnomer. (2012, May 4). RESEARCH TO DETECTION – IDENTIFY FAST FLUX IN YOUR ENVIRONMENT. Retrieved March 6, 2017.
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
       Lohit Mehta. (2014, December 17). Fast Flux Networks Working and Detection, Part 1. Retrieved March 6, 2017.
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       Lohit Mehta. (2014, December 23). Fast Flux Networks Working and Detection, Part 2. Retrieved March 6, 2017.
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
