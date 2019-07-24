<div class="container-fluid">
 <h1>
  Dynamic DNS
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Dynamic DNS is a automated method to rapidly update the domain name system mapping of hostnames to IPs.
    <span class="scite-citeref-number" data-reference="FireEyeSupplyChain" id="scite-ref-1-a">
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
      : T1333
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
 <h2 class="pt-3" id="techniques">
  Similar Techniques by Tactic
 </h2>
 <table class="table table-bordered table-light mt-2">
  <thead>
   <tr>
    <th scope="col">
     Tactic
    </th>
    <th scope="col">
     Technique
    </th>
   </tr>
  </thead>
  <tbody class="bg-white">
   <tr>
    <td>
     <a href="https://attack.mitre.org/tactics/TA0021">
      Adversary Opsec
     </a>
    </td>
    <td>
     <a href="https://attack.mitre.org/techniques/T1311">
      Dynamic DNS
     </a>
    </td>
   </tr>
  </tbody>
 </table>
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
     <a href="https://attack.mitre.org/groups/G0006">
      APT1
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0006">
       APT1
      </a>
      used dynamic DNS to register hundreds of FQDNs.
      <span class="scite-citeref-number" data-reference="Mandiant APT1" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
  </tbody>
 </table>
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
 Defender will not know at first use what is valid or hostile traffic without more context.
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
 It is relatively easy to subscribe to dynamic DNS providers or find ways to get different IP addresses from a cloud provider.
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
       FireEye. (2014). SUPPLY CHAIN ANALYSIS: From Quartermaster to SunshopFireEye. Retrieved March 6, 2017.
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
       <a class="external text" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf" name="scite-2" rel="nofollow" target="_blank">
        Mandiant. (n.d.). APT1 Exposing One of China’s Cyber Espionage Units. Retrieved July 18, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
