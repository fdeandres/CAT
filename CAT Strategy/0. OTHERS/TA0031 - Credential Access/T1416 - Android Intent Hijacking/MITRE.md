<div class="container-fluid">
 <h1>
  Android Intent Hijacking
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    A malicious app can register to receive intents meant for other applications and may then be able to receive sensitive values such as OAuth authorization codes
    <span class="scite-citeref-number" data-reference="IETF-PKCE" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://tools.ietf.org/html/rfc7636" target="_blank">
       [1]
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
      : T1416
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
      Android
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
     When vetting applications for potential security weaknesses, the vetting process could look for insecure use of intents. Developers should be encouraged to use techniques to ensure that the intent can only be sent to an appropriate destination (e.g., use explicit rather than implicit intents, permission checking, checking of the destination app's signing certificate, or the App Links feature added in Android 6.0). For mobile applications using OAuth, encourage use of best practice.
     <span class="scite-citeref-number" data-reference="Android-AppLinks" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
      <sup>
       <a aria-describedby="qtip-1" data-hasqtip="1" href="https://developer.android.com/training/app-links/index.html" target="_blank">
        [2]
       </a>
      </sup>
     </span>
     <span class="scite-citeref-number" data-reference="IETF-OAuthNativeApps" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
      <sup>
       <a aria-describedby="qtip-2" data-hasqtip="2" href="https://tools.ietf.org/html/rfc8252" target="_blank">
        [3]
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
       <a class="external text" href="https://tools.ietf.org/html/rfc7636" name="scite-1" rel="nofollow" target="_blank">
        N. Sakimura, J. Bradley, and N. Agarwal. (2015, September). IETF RFC 7636: Proof Key for Code Exchange by OAuth Public Clients. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://developer.android.com/training/app-links/index.html" name="scite-2" rel="nofollow" target="_blank">
        Android. (n.d.). Handling App Links. Retrieved December 21, 2016.
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
       <a class="external text" href="https://tools.ietf.org/html/rfc8252" name="scite-3" rel="nofollow" target="_blank">
        W. Denniss and J. Bradley. (2017, October). IETF RFC 8252: OAuth 2.0 for Native Apps. Retrieved November 30, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
