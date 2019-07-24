<div class="container-fluid">
 <h1>
  Obtain Apple iOS enterprise distribution key pair and certificate
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    The adversary can obtain an Apple iOS enterprise distribution key pair and certificate and use it to distribute malicious apps directly to Apple iOS devices without the need to publish the apps to the Apple App Store (where the apps could potentially be detected).
    <span class="scite-citeref-number" data-reference="Apple Developer Enterprise Porgram Apps" id="scite-ref-1-a">
     <sup>
      [1]
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Fruit vs Zombies" id="scite-ref-2-a">
     <sup>
      [2]
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="WIRELURKER" id="scite-ref-3-a">
     <sup>
      [3]
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Sideloading Change" id="scite-ref-4-a">
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
      : T1392
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
      : Persona Development
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
 Starting in iOS 9, Apple has changed the user interface when installing apps to better indicate to users the potential implications of installing apps signed by an enterprise distribution key rather than from Apple's App Store and to make it more difficult for users to inadvertently install these apps. Additionally, enterprise management controls are available that can be imposed to prevent installing these apps. Also, enterprise mobility management / mobile device management (EMM/MDM) systems can be used to scan for the presence of undesired apps on enterprise mobile devices.
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
 Apple requires a DUNS number, corporate documentation, and $299 to obtain an enterprise distribution certificate. Additionally, Apple revokes certificates if they discover malicious use.  However, the enrollment information could be falsified to Apple by an adversary, or an adversary could steal an existing enterprise distribution certificate (and the corresponding private key) from a business that already possesses one.
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
       Apple Inc.. (2016). Distributing Apple Developer Enterprise Program Apps. Retrieved April 12, 2017.
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       Claud Xiao. (2016). Fruit vs Zombies: Defeat Non-jailbroken iOS Malware. Retrieved April 12, 2017.
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
       Claud Xiao. (2014). WIRELURKER:  A New Era in iOS and OS X Malware. Retrieved April 12, 2017.
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       David Richardson. (2015, September 10). Change to sideloading apps in iOS 9 is a security win. Retrieved April 12, 2017.
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
