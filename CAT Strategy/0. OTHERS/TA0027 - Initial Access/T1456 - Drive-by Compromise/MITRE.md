<div class="container-fluid">
 <h1>
  Drive-by Compromise
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    As described by
    <a href="https://attack.mitre.org/techniques/T1189">
     Drive-by Compromise
    </a>
    , a drive-by compromise is when an adversary gains access to a system through a user visiting a website over the normal course of browsing. With this technique, the user's web browser is targeted for exploitation. For example, a website may contain malicious media content intended to exploit vulnerabilities in media parsers as demonstrated by the Android Stagefright vulnerability
    <span class="scite-citeref-number" data-reference="Zimperium-Stagefright" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://blog.zimperium.com/experts-found-a-unicorn-in-the-heart-of-android/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    .
   </p>
   <p>
    (This technique was formerly known as Malicious Web Content. It has been renamed to better align with ATT&amp;CK for Enterprise.)
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1456
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Tactic Type:
      </span>
      Post-Adversary Device Access
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Tactic
      </span>
      : Initial Access
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Platform:
      </span>
      Android, iOS
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
       MTC ID:
      </span>
      <a href="https://pages.nist.gov/mobile-threat-catalogue/cellular-threats/CEL-22.html" target="_blank">
       CEL-22
      </a>
      <br/>
      <br/>
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
 <h2 class="pt-3" id="mitigations">
  Mitigations
 </h2>
 <table class="table table-bordered table-light mt-2">
  <thead>
   <tr>
    <th scope="col">
     Mitigation
    </th>
    <th scope="col">
     Description
    </th>
   </tr>
  </thead>
  <tbody class="bg-white">
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1001">
      Security Updates
     </a>
    </td>
    <td>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1006">
      Use Recent OS Version
     </a>
    </td>
    <td>
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
     <a href="https://attack.mitre.org/software/S0289">
      Pegasus for iOS
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0289">
       Pegasus for iOS
      </a>
      was distributed through a web site by exploiting vulnerabilities in the Safari web browser on iOS devices.
      <span class="scite-citeref-number" data-reference="Lookout-Pegasus" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://info.lookout.com/rs/051-ESQ-475/images/lookout-pegasus-technical-analysis.pdf" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0328">
      Stealth Mango
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0328">
       Stealth Mango
      </a>
      is delivered via a a watering hole website that mimics the third-party Android app store APKMonk. In at least one case, the watering hole URL was distributed through Facebook Messenger.
      <span class="scite-citeref-number" data-reference="Lookout-StealthMango" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://info.lookout.com/rs/051-ESQ-475/images/lookout-stealth-mango-srr-us.pdf" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
  </tbody>
 </table>
 <h2 class="pt-3" id="references">
  References
 </h2>
 <div class="row">
  <div class="col">
   <ol>
    <li>
     <span class="scite-citation" id="scite-1">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.zimperium.com/experts-found-a-unicorn-in-the-heart-of-android/" name="scite-1" rel="nofollow" target="_blank">
        Zimperium. (2015, January 27). Experts Found a Unicorn in the Heart of Android. Retrieved December 23, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://info.lookout.com/rs/051-ESQ-475/images/lookout-pegasus-technical-analysis.pdf" name="scite-2" rel="nofollow" target="_blank">
        Lookout. (2016). Technical Analysis of Pegasus Spyware. Retrieved December 12, 2016.
       </a>
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
       <a class="external text" href="https://info.lookout.com/rs/051-ESQ-475/images/lookout-stealth-mango-srr-us.pdf" name="scite-3" rel="nofollow" target="_blank">
        Lookout. (n.d.). Stealth Mango &amp; Tangelo. Retrieved September 27, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
