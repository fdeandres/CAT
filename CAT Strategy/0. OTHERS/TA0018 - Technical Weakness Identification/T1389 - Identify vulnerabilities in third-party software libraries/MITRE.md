<div class="container-fluid">
 <h1>
  Identify vulnerabilities in third-party software libraries
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Many applications use third-party software libraries, often without full knowledge of the behavior of the libraries by the application developer. For example, mobile applications often incorporate advertising libraries to generate revenue for the application developer. Vulnerabilities in these third-party libraries could potentially be exploited in any application that uses the library, and even if the vulnerabilities are fixed, many applications may still use older, vulnerable versions of the library.
    <span class="scite-citeref-number" data-reference="Flexera News Vulnerabilities" id="scite-ref-1-a">
     <sup>
      [1]
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Android Security Review 2015" id="scite-ref-2-a">
     <sup>
      [2]
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Android Multidex RCE" id="scite-ref-3-a">
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
      : T1389
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
      : Technical Weakness Identification
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
 Open source software has great appeal mostly due to the time savings and that it is free.  However, using this code without assessing it's security is akin to blindly executing third party software.  Companies often do not dedicate the time to appropriately detect and scan for vulnerabilities. The mainstream mobile application stores scan applications for some known vulnerabilities. For example, Google's Android Application Security Improvement Program identifies and alerts developers to vulnerabilities present in their applications from use of the Vungle, Apache Cordova, WebView SSL, GnuTLS, and Vitamio third-party libraries. However, these scans are not likely to cover all vulnerable libraries, developers may not always act on the results, and the results may not be made available to impacted end users of the applications.
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
 Developers commonly use open source libraries such that where an adversary can easily discover known vulnerabilities and create exploits.  It is also generally easy to decompile arbitrary mobile applications to determine what libraries they use, and similarly use this information to correlate against known CVEs and exploit packages.
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
       John Lipsey. (2015, March 25). 15,435 Vulnerabilities in Close to 4,000 Applications in 2014. Retrieved April 12, 2017.
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       Google. (2016, April). Android Security 2015 Year In Review. Retrieved April 12, 2017.
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
       Ryan Welton. (2015, June 15). A Pattern for Remote Code Execution using Arbitrary File Writes and MultiDex Applications. Retrieved April 12, 2017.
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
