<div class="container-fluid">
 <h1>
  Hidden Users
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Every user account in macOS has a userID associated with it. When creating a user, you can specify the userID for that account. There is a property value in
    <code>
     /Library/Preferences/com.apple.loginwindow
    </code>
    called
    <code>
     Hide500Users
    </code>
    that prevents users with userIDs 500 and lower from appearing at the login screen. By using the
    <a href="https://attack.mitre.org/techniques/T1136">
     Create Account
    </a>
    technique with a userID under 500 and enabling this property (setting it to Yes), an adversary can hide their user accounts much more easily:
    <code>
     sudo dscl . -create /Users/username UniqueID 401
    </code>
    <span class="scite-citeref-number" data-reference="Cybereason OSX Pirrit" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www2.cybereason.com/research-osx-pirrit-mac-os-x-secuirty" target="_blank">
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
      : T1147
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
      : Defense Evasion
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Platform:
      </span>
      macOS
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Permissions Required:
      </span>
      Administrator, root
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      Authentication logs, File monitoring
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
       Version
      </span>
      : 1.0
     </div>
    </div>
   </div>
  </div>
 </div>
 <h2 class="pt-3" id="mitigation">
  Mitigation
 </h2>
 <p>
  If the computer is domain joined, then group policy can help restrict the ability to create or hide users. Similarly, preventing the modification of the
  <code>
   /Library/Preferences/com.apple.loginwindow
  </code>
  <code>
   Hide500Users
  </code>
  value will force all users to be visible.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  This technique prevents the new user from showing up at the log in screen, but all of the other signs of a new user still exist. The user still gets a home directory and will appear in the authentication logs.
 </p>
 <h2 class="pt-3" id="references">
  References
 </h2>
 <div class="row">
  <div class="col">
   <ol>
    <li>
     <span class="scite-citation" id="scite-1">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.cybereason.com/research-osx-pirrit-mac-os-x-secuirty" name="scite-1" rel="nofollow" target="_blank">
        Amit Serper. (2016). Cybereason Lab Analysis OSX.Pirrit. Retrieved July 8, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
  </div>
 </div>
</div>
