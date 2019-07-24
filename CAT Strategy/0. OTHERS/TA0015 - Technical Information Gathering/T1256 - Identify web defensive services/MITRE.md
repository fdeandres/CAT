<div class="container-fluid">
 <h1>
  Identify web defensive services
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An adversary can attempt to identify web defensive services as
    <a href="https://www.cloudflare.com">
     CloudFlare
    </a>
    ,
    <a href="https://github.com/jjxtra/Windows-IP-Ban-Service">
     IPBan
    </a>
    , and
    <a href="https://www.snort.org">
     Snort
    </a>
    . This may be done by passively detecting services, like
    <a href="https://www.cloudflare.com">
     CloudFlare
    </a>
    routing, or actively, such as by purposefully tripping security defenses.
    <span class="scite-citeref-number" data-reference="NMAP WAF NSE" id="scite-ref-1-a">
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
      : T1256
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
      : Technical Information Gathering
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
 Yes
 <br/>
 <br/>
 <b>
  Explanation:
 </b>
 Active service detection may trigger an alert.  Passive service enumeration is not detected.
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
 Adversary can passively detect services (e.g., [https://www.cloudflare.com/ CloudFlare] routing) or actively detect services (e.g., by purposefully tripping security defenses)
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
       Paulino Calderon. (n.d.). http-waf-detect. Retrieved April 2, 2017.
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
  </div>
 </div>
</div>
