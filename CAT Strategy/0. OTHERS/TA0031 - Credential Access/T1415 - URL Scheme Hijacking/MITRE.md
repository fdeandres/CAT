<div class="container-fluid">
 <h1>
  URL Scheme Hijacking
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An iOS application may be able to maliciously claim a URL scheme, allowing it to intercept calls that are meant for a different application
    <span class="scite-citeref-number" data-reference="FireEye-Masque2" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.fireeye.com/blog/threat-research/2015/02/ios_masque_attackre.html" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Dhanjani-URLScheme" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="http://www.dhanjani.com/blog/2010/11/insecure-handling-of-url-schemes-in-apples-ios.html" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    . This technique, for example, could be used to capture OAuth authorization codes
    <span class="scite-citeref-number" data-reference="IETF-PKCE" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://tools.ietf.org/html/rfc7636" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    or to phish user credentials
    <span class="scite-citeref-number" data-reference="MobileIron-XARA" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.mobileiron.com/en/smartwork-blog/ios-url-scheme-hijacking-xara-attack-analysis-and-countermeasures" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    .
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1415
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
      : Credential Access
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Platform:
      </span>
      iOS
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
      <a href="https://pages.nist.gov/mobile-threat-catalogue/authentication-threats/AUT-10.html" target="_blank">
       AUT-10
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
      : 1.1
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
     <a href="https://attack.mitre.org/mitigations/M1005">
      Application Vetting
     </a>
    </td>
    <td>
     Check for potential malicious definitions of URL schemes when vetting applications. Also, when examining apps for potential vulnerabilities, encourage use of universal links as an alternative to URL schemes. When examining apps that use OAuth, encourage use of best practices.
     <span class="scite-citeref-number" data-reference="Apple-UniversalLinks" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
      <sup>
       <a aria-describedby="qtip-4" data-hasqtip="4" href="https://developer.apple.com/library/content/documentation/General/Conceptual/AppSearch/UniversalLinks.html" target="_blank">
        [5]
       </a>
      </sup>
     </span>
     <span class="scite-citeref-number" data-reference="IETF-OAuthNativeApps" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
      <sup>
       <a aria-describedby="qtip-5" data-hasqtip="5" href="https://tools.ietf.org/html/rfc8252" target="_blank">
        [6]
       </a>
      </sup>
     </span>
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
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2015/02/ios_masque_attackre.html" name="scite-1" rel="nofollow" target="_blank">
        Hui Xue, Tao Wei, Yulong Zhang, Song Jin, Zhaofeng Chen. (2015, February 19). IOS MASQUE ATTACK REVIVED: BYPASSING PROMPT FOR TRUST AND APP URL SCHEME HIJACKING. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.dhanjani.com/blog/2010/11/insecure-handling-of-url-schemes-in-apples-ios.html" name="scite-2" rel="nofollow" target="_blank">
        Nitesh Dhanjani. (2010, November 8). Insecure Handling of URL Schemes in Apple’s iOS. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://tools.ietf.org/html/rfc7636" name="scite-3" rel="nofollow" target="_blank">
        N. Sakimura, J. Bradley, and N. Agarwal. (2015, September). IETF RFC 7636: Proof Key for Code Exchange by OAuth Public Clients. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="4.0">
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.mobileiron.com/en/smartwork-blog/ios-url-scheme-hijacking-xara-attack-analysis-and-countermeasures" name="scite-4" rel="nofollow" target="_blank">
        Michael T. Raggo. (2015, October 1). iOS URL Scheme Hijacking (XARA) Attack Analysis and Countermeasures. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://developer.apple.com/library/content/documentation/General/Conceptual/AppSearch/UniversalLinks.html" name="scite-5" rel="nofollow" target="_blank">
        Apple. (n.d.). Support Universal Links. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://tools.ietf.org/html/rfc8252" name="scite-6" rel="nofollow" target="_blank">
        W. Denniss and J. Bradley. (2017, October). IETF RFC 8252: OAuth 2.0 for Native Apps. Retrieved November 30, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
