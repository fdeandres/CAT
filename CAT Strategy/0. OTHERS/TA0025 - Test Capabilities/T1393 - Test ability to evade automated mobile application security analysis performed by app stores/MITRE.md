<div class="container-fluid">
 <h1>
  Test ability to evade automated mobile application security analysis performed by app stores
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Many mobile devices are configured to only allow applications to be installed from the mainstream vendor app stores (e.g., Apple App Store and Google Play Store). An adversary can submit multiple code samples to these stores deliberately designed to probe the stores' security analysis capabilities, with the goal of determining effective techniques to place malicious applications in the stores that could then be delivered to targeted devices.
    <span class="scite-citeref-number" data-reference="Android Bouncer" id="scite-ref-1-a">
     <sup>
      [1]
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Adventures in BouncerLand" id="scite-ref-2-a">
     <sup>
      [2]
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Jekyll on iOS" id="scite-ref-3-a">
     <sup>
      [3]
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Fruit vs Zombies" id="scite-ref-4-a">
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
      : T1393
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
      : Test Capabilities
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
 The app store operators (e.g., Apple and Google) may detect the attempts, but it would not be observable to those being attacked.
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
 An adversary can submit code remotely using throwaway accounts, although a registration fee may need to be paid for each new account (e.g., $99 for Apple and $25 for Google Play Store).
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
       Jon Oberheide and Charlie Miller. (2012). DISSECTING THE ANDROID BOUNCER. Retrieved April 12, 2017.
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       Nicholas J. Percoco and Sean Schulte. (2012). Adventures in BouncerLand. Retrieved April 12, 2017.
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
       Tielei Wang, Kangjie Lu, Long Lu, Simon Chung, and Wenke Lee. (2013). Jekyll on iOS: When Benign Apps Become Evil. Retrieved April 12, 2017.
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       Claud Xiao. (2016). Fruit vs Zombies: Defeat Non-jailbroken iOS Malware. Retrieved April 12, 2017.
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
