<div class="container-fluid">
 <h1>
  Securityd Memory
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    In OS X prior to El Capitan, users with root access can read plaintext keychain passwords of logged-in users because Apple’s keychain implementation allows these credentials to be cached so that users are not repeatedly prompted for passwords.
    <span class="scite-citeref-number" data-reference="OS X Keychain" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://juusosalonen.com/post/30923743427/breaking-into-the-os-x-keychain" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="External to DA, the OS X Way" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="http://www.slideshare.net/StephanBorosh/external-to-da-the-os-x-way" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    Apple’s securityd utility takes the user’s logon password, encrypts it with PBKDF2, and stores this master key in memory. Apple also uses a set of keys and algorithms to encrypt the user’s password, but once the master key is found, an attacker need only iterate over the other values to unlock the final password.
    <span class="scite-citeref-number" data-reference="OS X Keychain" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://juusosalonen.com/post/30923743427/breaking-into-the-os-x-keychain" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    If an adversary can obtain root access (allowing them to read securityd’s memory), then they can scan through memory to find the correct sequence of keys in relatively few tries to decrypt the user’s logon keychain. This provides the adversary with all the plaintext passwords for users, WiFi, mail, browsers, certificates, secure notes, etc.
    <span class="scite-citeref-number" data-reference="OS X Keychain" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://juusosalonen.com/post/30923743427/breaking-into-the-os-x-keychain" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="OSX Keydnap malware" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.welivesecurity.com/2016/07/06/new-osxkeydnap-malware-hungry-credentials/" target="_blank">
       [3]
      </a>
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
      : T1167
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
      : Credential Access
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
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Permissions Required:
      </span>
      root
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
      Process monitoring
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
       Version
      </span>
      : 1.0
     </div>
    </div>
   </div>
  </div>
 </div>
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
     <a href="https://attack.mitre.org/software/S0276">
      Keydnap
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0276">
       Keydnap
      </a>
      uses the keychaindump project to read securityd memory.
      <span class="scite-citeref-number" data-reference="synack 2016 review" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.synack.com/2017/01/01/mac-malware-2016/" target="_blank">
         [4]
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
       <a class="external text" href="http://juusosalonen.com/post/30923743427/breaking-into-the-os-x-keychain" name="scite-1" rel="nofollow" target="_blank">
        Juuso Salonen. (2012, September 5). Breaking into the OS X keychain. Retrieved July 15, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.slideshare.net/StephanBorosh/external-to-da-the-os-x-way" name="scite-2" rel="nofollow" target="_blank">
        Alex Rymdeko-Harvey, Steve Borosh. (2016, May 14). External to DA, the OS X Way. Retrieved July 3, 2017.
       </a>
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
       <a class="external text" href="https://www.welivesecurity.com/2016/07/06/new-osxkeydnap-malware-hungry-credentials/" name="scite-3" rel="nofollow" target="_blank">
        Marc-Etienne M.Leveille. (2016, July 6). New OSX/Keydnap malware is hungry for credentials. Retrieved July 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.synack.com/2017/01/01/mac-malware-2016/" name="scite-4" rel="nofollow" target="_blank">
        Patrick Wardle. (2017, January 1). Mac Malware of 2016. Retrieved September 21, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
