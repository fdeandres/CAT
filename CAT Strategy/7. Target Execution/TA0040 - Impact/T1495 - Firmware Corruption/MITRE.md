<div class="container-fluid">
 <h1>
  Firmware Corruption
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries may overwrite or corrupt the flash memory contents of system BIOS or other firmware in devices attached to a system in order to render them inoperable or unable to boot.
    <span class="scite-citeref-number" data-reference="Symantec Chernobyl W95.CIH" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.symantec.com/security-center/writeup/2000-122010-2655-99" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    Firmware is software that is loaded and executed from non-volatile memory on hardware devices in order to initialize and manage device functionality. These devices could include the motherboard, hard drive, or video cards.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1495
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
      : Impact
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Platform:
      </span>
      Linux, macOS, Windows
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
      Administrator, root, SYSTEM
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
      BIOS, Component firmware
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
       Impact Type:
      </span>
      Availability
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
  Prevent adversary access to privileged accounts or access necessary to perform this technique. Check the integrity of the existing BIOS and device firmware to determine if it is vulnerable to modification. Patch the BIOS and other firmware as necessary to prevent successful use of known vulnerabilities.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  System firmware manipulation may be detected.
  <span class="scite-citeref-number" data-reference="MITRE Trustworthy Firmware Measurement" id="scite-ref-2-a">
   <sup>
    <a aria-describedby="qtip-1" data-hasqtip="1" href="http://www.mitre.org/publications/project-stories/going-deep-into-the-bios-with-mitre-firmware-security-research" target="_blank">
     [2]
    </a>
   </sup>
  </span>
  Log attempts to read/write to BIOS and compare against known patching behavior.
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
       <a class="external text" href="https://www.symantec.com/security-center/writeup/2000-122010-2655-99" name="scite-1" rel="nofollow" target="_blank">
        Yamamura, M. (2002, April 25). W95.CIH. Retrieved April 12, 2019.
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
       <a class="external text" href="http://www.mitre.org/publications/project-stories/going-deep-into-the-bios-with-mitre-firmware-security-research" name="scite-2" rel="nofollow" target="_blank">
        Upham, K. (2014, March). Going Deep into the BIOS with MITRE Firmware Security Research. Retrieved January 5, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
