<div class="container-fluid">
 <h1>
  DNSCalc
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    DNS Calc is a technique in which the octets of an IP address are used to calculate the port  for command and control servers from an initial DNS request.
    <span class="scite-citeref-number" data-reference="CrowdstrikeNumberedPanda" id="scite-ref-1-a">
     <sup>
      [1]
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="FireEyeDarwinsAPTGroup" id="scite-ref-2-a">
     <sup>
      [2]
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Rapid7G20Espionage" id="scite-ref-3-a">
     <sup>
      [3]
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
      : T1324
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
 No
 <br/>
 <br/>
 <b>
  Explanation:
 </b>
 There are not currently available tools that provide the ability to conduct this calculation to detect this type of activity.
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
 This technique assists the adversary in bypassing egress filtering designed to prevent unauthorized communication.  It has been used by APT12, but not otherwise widely reported.  Some botnets are hardcoded to be able to use this technique.
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
       Adam Meyers. (2013, March 29). Whois Numbered Panda. Retrieved March 6, 2017.
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       Ned Moran, Mike Oppenheim. (2014, September 3). Darwin’s Favorite APT Group. Retrieved March 6, 2017.
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
       nex. (2013, August 26). Upcoming G20 Summit Fuels Espionage Operations. Retrieved March 6, 2017.
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
