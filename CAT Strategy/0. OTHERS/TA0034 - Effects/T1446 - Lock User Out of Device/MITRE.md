<div class="container-fluid">
 <h1>
  Lock User Out of Device
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An adversary may seek to lock the legitimate user out of the device, for example until a ransom is paid.
   </p>
   <p>
    On Android versions prior to 7, apps can abuse Device Administrator access to reset the device lock passcode to lock the user out of the device.
   </p>
   <p>
    On iOS devices, this technique does not work because mobile device management servers can only remove the screen lock passcode, they cannot set a new passcode. However, on jailbroken devices, malware has been demonstrated that can lock the user out of the device
    <span class="scite-citeref-number" data-reference="Xiao-KeyRaider" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://researchcenter.paloaltonetworks.com/2015/08/keyraider-ios-malware-steals-over-225000-apple-accounts-to-create-free-app-utopia/" target="_blank">
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
      : T1446
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
     <a href="https://attack.mitre.org/mitigations/M1005">
      Application Vetting
     </a>
    </td>
    <td>
     It is rare for applications to utilize Device Administrator access. App vetting can detect apps that do so, and those apps should be closely scrutinized. Maggi and Zanero4 describe a static analysis approach that can be used to identify ransomware apps including apps that abuse Device Administrator access.
     <span class="scite-citeref-number" data-reference="Maggi-Ransomware" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
      <sup>
       <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.blackhat.com/docs/eu-16/materials/eu-16-Maggi-Pocket-Sized-Badness-Why-Ransomware-Comes-As-A-Plot-Twist-In-The-Cat-Mouse-Game.pdf" target="_blank">
        [4]
       </a>
      </sup>
     </span>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1007">
      Caution with Device Administrator Access
     </a>
    </td>
    <td>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1010">
      Deploy Compromised Device Detection Method
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
     <a href="https://attack.mitre.org/software/S0323">
      Charger
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0323">
       Charger
      </a>
      locks the device if it is granted admin permissions, displaying a message demanding a "ransom" payment.
      <span class="scite-citeref-number" data-reference="CheckPoint-Charger" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="http://blog.checkpoint.com/2017/01/24/charger-malware/" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0288">
      KeyRaider
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0288">
       KeyRaider
      </a>
      has built-in functionality to lock victims out of devices and hold them for ransom.
      <span class="scite-citeref-number" data-reference="Xiao-KeyRaider" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="http://researchcenter.paloaltonetworks.com/2015/08/keyraider-ios-malware-steals-over-225000-apple-accounts-to-create-free-app-utopia/" target="_blank">
         [1]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
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
      can remotely lock infected Android devices and ask for a ransom.
      <span class="scite-citeref-number" data-reference="PaloAlto-Xbot" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="http://researchcenter.paloaltonetworks.com/2016/02/new-android-trojan-xbot-phishes-credit-cards-and-bank-accounts-encrypts-devices-for-ransom/" target="_blank">
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
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2015/08/keyraider-ios-malware-steals-over-225000-apple-accounts-to-create-free-app-utopia/" name="scite-1" rel="nofollow" target="_blank">
        Claud Xiao. (2015, August 30). KeyRaider: iOS Malware Steals Over 225,000 Apple Accounts to Create Free App Utopia. Retrieved December 12, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.checkpoint.com/2017/01/24/charger-malware/" name="scite-2" rel="nofollow" target="_blank">
        Oren Koriat and Andrey Polkovnichenko. (2017, January 24). Charger Malware Calls and Raises the Risk on Google Play. Retrieved January 24, 2017.
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
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/02/new-android-trojan-xbot-phishes-credit-cards-and-bank-accounts-encrypts-devices-for-ransom/" name="scite-3" rel="nofollow" target="_blank">
        Cong Zheng, Claud Xiao and Zhi Xu. (2016, February 18). New Android Trojan “Xbot” Phishes Credit Cards and Bank Accounts, Encrypts Devices for Ransom. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.blackhat.com/docs/eu-16/materials/eu-16-Maggi-Pocket-Sized-Badness-Why-Ransomware-Comes-As-A-Plot-Twist-In-The-Cat-Mouse-Game.pdf" name="scite-4" rel="nofollow" target="_blank">
        Federico Maggi and Stefano Zanero. (2016). Pocket-Sized Badness - Why Ransomware Comes as a Plot Twist in the Cat-Mouse Game. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
