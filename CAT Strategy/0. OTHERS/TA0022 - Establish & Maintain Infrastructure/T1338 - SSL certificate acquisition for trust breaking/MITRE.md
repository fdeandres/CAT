<div class="container-fluid">
 <h1>
  SSL certificate acquisition for trust breaking
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Fake certificates can be acquired by legal process or coercion. Or, an adversary can trick a Certificate Authority into issuing a certificate. These fake certificates can be used as a part of Man-in-the-Middle attacks.
    <span class="scite-citeref-number" data-reference="SubvertSSL" id="scite-ref-1-a">
     <sup>
      [1]
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
      : T1338
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
      : Establish &amp; Maintain Infrastructure
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
 No
 <br/>
 <br/>
 <b>
  Explanation:
 </b>
 The certificate authority who is hacked cannot easily see they've been compromised, but [https://www.google.com Google] has caught on to this occurring in previous attacks such as DigiNotarDigiNotar2016 and [https://www.verisign.com Verisign].
 <br/>
 <br/>
 <h2 class="pt-3" id="difficulty">
  Difficulty for the Adversary
 </h2>
 <b>
  Easy for the Adversary (Yes/No):
 </b>
 No
 <br/>
 <br/>
 <b>
  Explanation:
 </b>
 One example of it occurring in the real world is the DigiNotarDigiNotar2016 case.  To be able to do this usually requires sophisticated skills and is traditionally done by a nation state to spy on its citizens.
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
       Ryan Singel. (2010, March 24). Law Enforcement Appliance Subverts SSL. Retrieved March 2, 2017.
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
  </div>
 </div>
</div>
