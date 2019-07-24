<div class="container-fluid">
 <h1>
  Compromise 3rd party infrastructure to support delivery
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Instead of buying, leasing, or renting infrastructure an adversary may compromise infrastructure and use it for some or all of the attack cycle.
    <span class="scite-citeref-number" data-reference="WateringHole2014" id="scite-ref-1-a">
     <sup>
      [1]
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="FireEye Operation SnowMan" id="scite-ref-2-a">
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
      : T1334
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
     <a href="https://attack.mitre.org/techniques/T1312">
      Compromise 3rd party infrastructure to support delivery
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
      comrpomised a vast set of 3rd party victim hop points as part of their network infrastructure.
      <span class="scite-citeref-number" data-reference="Mandiant APT1" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
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
      hijacked FQDNs associated with legitimate websites hosted by hop points. Mandiant considers them to be "hijacked" since they were originally registered for a legitimate reason but were used by APT1 for malicious purposes.
      <span class="scite-citeref-number" data-reference="Mandiant APT1" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0023">
      APT16
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0023">
       APT16
      </a>
      has compromised otherwise legitimate sites as staging servers for second-stage payloads.
      <span class="scite-citeref-number" data-reference="FireEye EPS Awakens Part 2" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.fireeye.com/blog/threat-research/2015/12/the-eps-awakens-part-two.html" target="_blank">
         [4]
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
 Defender will not have visibility on 3rd party sites unless target is successfully enticed to visit one.
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
 Commonly used technique currently (e.g., [https://www.wordpress.com WordPress] sites) as precursor activity to launching attack against intended target (e.g., acquiring botnet or layers of proxies for reducing attribution possibilities).
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
       Pierluigi Paganini. (2014, February 15). FireEye discovered a new watering hole attack based on 0-day exploit. Retrieved March 1, 2017.
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       Darien Kindlund, Xiaobo Chen, Mike Scott, Ned Moran, Dan Caselden. (2014, February 13). Operation SnowMan: DeputyDog Actor Compromises US Veterans of Foreign Wars Website. Retrieved March 28, 2017.
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
       <a class="external text" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf" name="scite-3" rel="nofollow" target="_blank">
        Mandiant. (n.d.). APT1 Exposing One of China’s Cyber Espionage Units. Retrieved July 18, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2015/12/the-eps-awakens-part-two.html" name="scite-4" rel="nofollow" target="_blank">
        Winters, R.. (2015, December 20). The EPS Awakens - Part 2. Retrieved January 22, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
