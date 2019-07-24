<div class="container-fluid">
 <h1>
  Encrypt Files
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An adversary may encrypt files stored on the mobile device to prevent the user from accessing them, for example with the intent of only unlocking access to the files after a ransom is paid. Without escalated privileges, the adversary is generally limited to only encrypting files in external/shared storage locations. This technique has been demonstrated on Android. We are unaware of any demonstrated use on iOS.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1471
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
      : Effects
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
       MTC ID:
      </span>
      <a href="https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-28.html" target="_blank">
       APP-28
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
      : 2.0
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
     Maggi and Zanero describe a static analysis approach that may be able to identify ransomware apps that encrypt user files on the device.
     <span class="scite-citeref-number" data-reference="Maggi-Ransomware" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
      <sup>
       <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.blackhat.com/docs/eu-16/materials/eu-16-Maggi-Pocket-Sized-Badness-Why-Ransomware-Comes-As-A-Plot-Twist-In-The-Cat-Mouse-Game.pdf" target="_blank">
        [2]
       </a>
      </sup>
     </span>
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
     <a href="https://attack.mitre.org/software/S0298">
      Xbot
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0298">
       Xbot
      </a>
      can encrypt the victim's files in external storage (e.g., SD card) and then request a PayPal cash card as ransom.
      <span class="scite-citeref-number" data-reference="PaloAlto-Xbot" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="http://researchcenter.paloaltonetworks.com/2016/02/new-android-trojan-xbot-phishes-credit-cards-and-bank-accounts-encrypts-devices-for-ransom/" target="_blank">
         [1]
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
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/02/new-android-trojan-xbot-phishes-credit-cards-and-bank-accounts-encrypts-devices-for-ransom/" name="scite-1" rel="nofollow" target="_blank">
        Cong Zheng, Claud Xiao and Zhi Xu. (2016, February 18). New Android Trojan “Xbot” Phishes Credit Cards and Bank Accounts, Encrypts Devices for Ransom. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="2.0">
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.blackhat.com/docs/eu-16/materials/eu-16-Maggi-Pocket-Sized-Badness-Why-Ransomware-Comes-As-A-Plot-Twist-In-The-Cat-Mouse-Game.pdf" name="scite-2" rel="nofollow" target="_blank">
        Federico Maggi and Stefano Zanero. (2016). Pocket-Sized Badness - Why Ransomware Comes as a Plot Twist in the Cat-Mouse Game. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
