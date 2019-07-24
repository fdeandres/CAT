<div class="container-fluid">
 <h1>
  Data Hiding
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Certain types of traffic (e.g., DNS tunneling, header inject) allow for user-defined fields. These fields can then be used to hide data. In addition to hiding data in network protocols, steganography techniques can be used to hide data in images or other file formats. Detection can be difficult unless a particular signature is already known.
    <span class="scite-citeref-number" data-reference="BotnetsDNSC2" id="scite-ref-1-a">
     <sup>
      [1]
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="HAMMERTOSS2015" id="scite-ref-2-a">
     <sup>
      [2]
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="DNS-Tunnel" id="scite-ref-3-a">
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
      : T1320
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
 Yes
 <br/>
 <br/>
 <b>
  Explanation:
 </b>
 Unless defender is dissecting protocols or performing network signature analysis on any protocol deviations/patterns, this technique is largely undetected.
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
 This technique requires a more advanced protocol understanding and testing to insert covert communication into legitimate protocol fields.
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
       Christian J. Dietrich,  Christian Rossow, Felix C. Freiling, Herbert Bos, Maarten van Steen, Norbert Pohlmann. (2011). On Botnets that use DNS for Command and Control. Retrieved March 6, 2017.
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       FireEye. (2015, July). HAMMERTOSS: Stealthy Tactics Define a Russian Cyber Threat Group. Retrieved March 6, 2017.
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
       Alexey Shulmi and Sergey Yunakovsky. (2017, April 28). Use of DNS Tunneling for C&amp;C Communications. Retrieved May 9, 2017.
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
