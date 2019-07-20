<div class="container-fluid">
 <h1>
  Rc.common
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    During the boot process, macOS executes
    <code>
     source /etc/rc.common
    </code>
    , which is a shell script containing various utility functions. This file also defines routines for processing command-line arguments and for gathering system settings, and is thus recommended to include in the start of Startup Item Scripts
    <span class="scite-citeref-number" data-reference="Startup Items" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/StartupItems.html" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    . In macOS and OS X, this is now a deprecated technique in favor of launch agents and launch daemons, but is currently still used.
   </p>
   <p>
    Adversaries can use the rc.common file as a way to hide code for persistence that will execute on each reboot as the root user
    <span class="scite-citeref-number" data-reference="Methods of Mac Malware Persistence" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.virusbulletin.com/uploads/pdf/conference/vb2014/VB2014-Wardle.pdf" target="_blank">
       [2]
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
      : T1163
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
      : Persistence
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
      File monitoring, Process monitoring
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
     <a href="https://attack.mitre.org/software/S0278">
      iKitten
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0278">
       iKitten
      </a>
      adds an entry to the rc.common file for persistence.
      <span class="scite-citeref-number" data-reference="objsee mac malware 2017" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://objective-see.com/blog/blog_0x25.html" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
  </tbody>
 </table>
 <h2 class="pt-3" id="mitigation">
  Mitigation
 </h2>
 <p>
  Limit privileges of user accounts so only authorized users can edit the rc.common file.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  The
  <code>
   /etc/rc.common
  </code>
  file can be monitored to detect changes from the company policy. Monitor process execution resulting from the rc.common script for unusual or unknown applications or behavior.
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
       <a class="external text" href="https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/StartupItems.html" name="scite-1" rel="nofollow" target="_blank">
        Apple. (2016, September 13). Startup Items. Retrieved July 11, 2017.
       </a>
      </span>
     </span>
    </li>
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
  <div class="col">
   <ol start="3.5">
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://objective-see.com/blog/blog_0x25.html" name="scite-3" rel="nofollow" target="_blank">
        Patrick Wardle. (n.d.). Mac Malware of 2017. Retrieved September 21, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
