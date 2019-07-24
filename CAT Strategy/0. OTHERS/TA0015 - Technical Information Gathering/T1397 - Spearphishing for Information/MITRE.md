<div class="container-fluid">
 <h1>
  Spearphishing for Information
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Spearphishing for information is a specific variant of spearphishing. Spearphishing for information is different from other forms of spearphishing in that it it doesn't leverage malicious code. All forms of spearphishing are elctronically delivered social engineering targeted at a specific individual, company, or industry. Spearphishing for information is an attempt to trick targets into divulging information, frequently credentials, without involving malicious code. Spearphishing for information frequently involves masquerading as a source with a reason to collect information (such as a system administrator or a bank) and providing a user with a website link to visit. The given website often closely resembles a legitimate site in appearance and has a URL containing elements from the real site. From the fake website, information is gathered in web forms and sent to the attacker. Spearphishing for information may also try to obtain information directly through the exchange of emails, instant messengers or other electronic conversation means.
    <span class="scite-citeref-number" data-reference="ATTACKREF GRIZZLY STEPPE JAR" id="scite-ref-1-a">
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
      : T1397
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
 Partial
 <br/>
 <br/>
 <b>
  Explanation:
 </b>
 Depending on the specific method of phishing, the detections can vary. For emails, filtering based on DKIP+SPF or header analysis can help detect when the email sender is spoofed. When it comes to following links, network intrusion detection systems (NIDS), firewalls, removing links, exploding shortened links, proxy monitoring, blocking uncategorized sites, and site reputation based filtering can all provide detection opportunities.
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
 Sending emails is trivial, and, over time, an adversary can refine their technique to minimize detection by making their emails seem legitimate in structure and content.
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
       Department of Homeland Security and Federal Bureau of Investigation. (2016, December 29). GRIZZLY STEPPE – Russian Malicious Cyber Activity. Retrieved January 11, 2017.
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
  </div>
 </div>
</div>
