<div class="container-fluid">
 <h1>
  Modify OS Kernel or Boot Partition
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    If an adversary can escalate privileges, he or she may be able to use those privileges to place malicious code in the device kernel or other boot partition components, where the code may evade detection, may persist after device resets, and may not be removable by the device user. In some cases (e.g., the Samsung Knox warranty bit as described under Detection), the attack may be detected but could result in the device being placed in a state that no longer allows certain functionality.
   </p>
   <p>
    Many Android devices provide the ability to unlock the bootloader for development purposes, but doing so introduces the potential ability for others to maliciously update the kernel or other boot partition code.
   </p>
   <p>
    If the bootloader is not unlocked, it may still be possible to exploit device vulnerabilities to update the code.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1398
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
      : Defense Evasion, Persistence
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
      <a href="https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-26.html" target="_blank">
       APP-26
      </a>
      ,
      <a href="https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-27.html" target="_blank">
       APP-27
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
     <a href="https://attack.mitre.org/mitigations/M1002">
      Attestation
     </a>
    </td>
    <td>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1003">
      Lock Bootloader
     </a>
    </td>
    <td>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1001">
      Security Updates
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
     <a href="https://attack.mitre.org/software/S0285">
      OldBoot
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0285">
       OldBoot
      </a>
      uses escalated privileges to modify the init script on the device's boot partition to maintain persistence.
      <span class="scite-citeref-number" data-reference="HackerNews-OldBoot" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="http://thehackernews.com/2014/01/first-widely-distributed-android.html" target="_blank">
         [1]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
  </tbody>
 </table>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  The Android SafetyNet API's remote attestation capability could potentially be used to identify and respond to compromised devices. Samsung KNOX also provides a remote attestation capability on supported Samsung Android devices.
 </p>
 <p>
  Samsung KNOX devices include a non-reversible Knox warranty bit fuse that is triggered "if a non-Knox kernel has been loaded on the device"
  <span class="scite-citeref-number" data-reference="Samsung-KnoxWarrantyBit" id="scite-ref-2-a">
   <sup>
    <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www2.samsungknox.com/en/faq/what-knox-warranty-bit-and-how-it-triggered" target="_blank">
     [2]
    </a>
   </sup>
  </span>
  . If triggered, enterprise Knox container services will no longer be available on the device.
 </p>
 <p>
  As described in the iOS Security Guide
  <span class="scite-citeref-number" data-reference="Apple-iOSSecurityGuide" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.apple.com/business/docs/iOS_Security_Guide.pdf" target="_blank">
     [3]
    </a>
   </sup>
  </span>
  , iOS devices will fail to boot or fail to allow device activation if unauthorized modifications are detected.
 </p>
 <p>
  Many enterprise applications perform their own checks to detect and respond to compromised devices. These checks are not foolproof but can detect common signs of compromise.
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
       <a class="external text" href="http://thehackernews.com/2014/01/first-widely-distributed-android.html" name="scite-1" rel="nofollow" target="_blank">
        Sudhir K Bansal. (2014, January 28). First widely distributed Android bootkit Malware infects more than 350,000 Devices. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.samsungknox.com/en/faq/what-knox-warranty-bit-and-how-it-triggered" name="scite-2" rel="nofollow" target="_blank">
        Samsung. (n.d.). What is a Knox Warranty Bit and how is it triggered?. Retrieved December 21, 2016.
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
       <a class="external text" href="https://www.apple.com/business/docs/iOS_Security_Guide.pdf" name="scite-3" rel="nofollow" target="_blank">
        Apple. (2016, May). iOS Security. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
