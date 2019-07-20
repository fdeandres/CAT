<div class="container-fluid">
 <h1>
  LC_MAIN Hijacking
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    As of OS X 10.8, mach-O binaries introduced a new header called LC_MAIN that points to the binary’s entry point for execution. Previously, there were two headers to achieve this same effect: LC_THREAD and LC_UNIXTHREAD
    <span class="scite-citeref-number" data-reference="Prolific OSX Malware History" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://assets.documentcloud.org/documents/2459197/bit9-carbon-black-threat-research-report-2015.pdf" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    . The entry point for a binary can be hijacked so that initial execution flows to a malicious addition (either another section or a code cave) and then goes back to the initial entry point so that the victim doesn’t know anything was different
    <span class="scite-citeref-number" data-reference="Methods of Mac Malware Persistence" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.virusbulletin.com/uploads/pdf/conference/vb2014/VB2014-Wardle.pdf" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    . By modifying a binary in this way, application whitelisting can be bypassed because the file name or application path is still the same.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1149
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
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Permissions Required:
      </span>
      User, Administrator
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
      Binary file metadata, Malware reverse engineering, Process monitoring
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
       Defense Bypassed:
      </span>
      Application whitelisting, Process whitelisting, Whitelisting by file name or path
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
  Enforce valid digital signatures for signed code on all applications and only trust applications with signatures from trusted parties.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Determining the original entry point for a binary is difficult, but checksum and signature verification is very possible. Modifying the LC_MAIN entry point or adding in an additional LC_MAIN entry point invalidates the signature for the file and can be detected. Collect running process information and compare against known applications to look for suspicious behavior.
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
       <a class="external text" href="https://assets.documentcloud.org/documents/2459197/bit9-carbon-black-threat-research-report-2015.pdf" name="scite-1" rel="nofollow" target="_blank">
        Bit9 + Carbon Black Threat Research Team. (2015). 2015: The Most Prolific Year in History for OS X Malware. Retrieved July 8, 2017.
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
       <a class="external text" href="https://www.virusbulletin.com/uploads/pdf/conference/vb2014/VB2014-Wardle.pdf" name="scite-2" rel="nofollow" target="_blank">
        Patrick Wardle. (2014, September). Methods of Malware Persistence on Mac OS X. Retrieved July 5, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
