<div class="container-fluid">
 <h1>
  Hypervisor
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    A type-1 hypervisor is a software layer that sits between the guest operating systems and system's hardware.
    <span class="scite-citeref-number" data-reference="Wikipedia Hypervisor" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://en.wikipedia.org/wiki/Hypervisor" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    It presents a virtual running environment to an operating system. An example of a common hypervisor is Xen.
    <span class="scite-citeref-number" data-reference="Wikipedia Xen" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="http://en.wikipedia.org/wiki/Xen" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    A type-1 hypervisor operates at a level below the operating system and could be designed with
    <a href="https://attack.mitre.org/techniques/T1014">
     Rootkit
    </a>
    functionality to hide its existence from the guest operating system.
    <span class="scite-citeref-number" data-reference="Myers 2007" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.90.8832&amp;rep=rep1&amp;type=pdf" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    A malicious hypervisor of this nature could be used to persist on systems through interruption.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1062
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
      Windows
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
      Administrator, SYSTEM
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
      System calls
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
       CAPEC ID:
      </span>
      <a href="https://capec.mitre.org/data/definitions/552.html" target="_blank">
       CAPEC-552
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
  Prevent adversary access to privileged accounts necessary to install a hypervisor.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Type-1 hypervisors may be detected by performing timing analysis. Hypervisors emulate certain CPU instructions that would normally be executed by the hardware. If an instruction takes orders of magnitude longer to execute than normal on a system that should not contain a hypervisor, one may be present.
  <span class="scite-citeref-number" data-reference="virtualization.info 2006" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="http://virtualization.info/en/news/2006/08/debunking-blue-pill-myth.html" target="_blank">
     [4]
    </a>
   </sup>
  </span>
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
       <a class="external text" href="https://en.wikipedia.org/wiki/Hypervisor" name="scite-1" rel="nofollow" target="_blank">
        Wikipedia. (2016, May 23). Hypervisor. Retrieved June 11, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://en.wikipedia.org/wiki/Xen" name="scite-2" rel="nofollow" target="_blank">
        Xen. (n.d.). In Wikipedia. Retrieved November 13, 2014.
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
       <a class="external text" href="http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.90.8832&amp;rep=rep1&amp;type=pdf" name="scite-3" rel="nofollow" target="_blank">
        Myers, M., and Youndt, S. (2007). An Introduction to Hardware-Assisted Virtual Machine (HVM) Rootkits. Retrieved November 13, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://virtualization.info/en/news/2006/08/debunking-blue-pill-myth.html" name="scite-4" rel="nofollow" target="_blank">
        virtualization.info. (Interviewer) &amp; Liguori, A. (Interviewee). (2006, August 11). Debunking Blue Pill myth [Interview transcript]. Retrieved November 13, 2014.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
