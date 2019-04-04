<div class="container-fluid">
 <h1>
  Time Providers
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    The Windows Time service (W32Time) enables time synchronization across and within domains.
    <span class="scite-citeref-number" data-reference="Microsoft W32Time Feb 2018" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://docs.microsoft.com/windows-server/networking/windows-time-service/windows-time-service-top" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    W32Time time providers are responsible for retrieving time stamps from hardware/network resources and outputting these values to other network clients.
    <span class="scite-citeref-number" data-reference="Microsoft TimeProvider" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://msdn.microsoft.com/library/windows/desktop/ms725475.aspx" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Time providers are implemented as dynamic-link libraries (DLLs) that are registered in the subkeys of
    <code>
     HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\W32Time\TimeProviders\
    </code>
    .
    <span class="scite-citeref-number" data-reference="Microsoft TimeProvider" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://msdn.microsoft.com/library/windows/desktop/ms725475.aspx" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    The time provider manager, directed by the service control manager, loads and starts time providers listed and enabled under this key at system startup and/or whenever parameters are changed.
    <span class="scite-citeref-number" data-reference="Microsoft TimeProvider" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://msdn.microsoft.com/library/windows/desktop/ms725475.aspx" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries may abuse this architecture to establish Persistence, specifically by registering and enabling a malicious DLL as a time provider. Administrator privileges are required for time provider registration, though execution will run in context of the Local Service account.
    <span class="scite-citeref-number" data-reference="Github W32Time Oct 2017" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://github.com/scottlundgren/w32time" target="_blank">
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
      : T1209
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
      API monitoring, Binary file metadata, DLL monitoring, File monitoring, Loaded DLLs, Process monitoring
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
       Contributors:
      </span>
      Scott Lundgren, @5twenty9, Carbon Black
      <br/>
      <br/>
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
  Identify and block potentially malicious software that may be executed as a time provider by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [4]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-5-a">
   <sup>
    <a aria-describedby="qtip-4" data-hasqtip="4" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [5]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-6-a">
   <sup>
    <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [6]
    </a>
   </sup>
  </span>
  that are capable of auditing and/or blocking unknown DLLs.
 </p>
 <p>
  Consider using Group Policy to configure and block subsequent modifications to W32Time parameters.
  <span class="scite-citeref-number" data-reference="Microsoft W32Time May 2017" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://docs.microsoft.com/windows-server/networking/windows-time-service/windows-time-service-tools-and-settings" target="_blank">
     [7]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Baseline values and monitor/analyze activity related to modifying W32Time information in the Registry, including application programming interface (API) calls such as RegCreateKeyEx and RegSetValueEx as well as execution of the W32tm.exe utility.
  <span class="scite-citeref-number" data-reference="Microsoft W32Time May 2017" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://docs.microsoft.com/windows-server/networking/windows-time-service/windows-time-service-tools-and-settings" target="_blank">
     [7]
    </a>
   </sup>
  </span>
  There is no restriction on the number of custom time providers registrations, though each may require a DLL payload written to disk.
  <span class="scite-citeref-number" data-reference="Github W32Time Oct 2017" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="https://github.com/scottlundgren/w32time" target="_blank">
     [3]
    </a>
   </sup>
  </span>
 </p>
 <p>
  The Sysinternals Autoruns tool may also be used to analyze auto-starting locations, including DLLs listed as time providers.
  <span class="scite-citeref-number" data-reference="TechNet Autoruns" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="https://technet.microsoft.com/en-us/sysinternals/bb963902" target="_blank">
     [8]
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
       <a class="external text" href="https://docs.microsoft.com/windows-server/networking/windows-time-service/windows-time-service-top" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (2018, February 1). Windows Time Service (W32Time). Retrieved March 26, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/windows/desktop/ms725475.aspx" name="scite-2" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Time Provider. Retrieved March 26, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/scottlundgren/w32time" name="scite-3" rel="nofollow" target="_blank">
        Lundgren, S. (2017, October 28). w32time. Retrieved March 26, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-4" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="5.0">
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-5" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-6" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/windows-server/networking/windows-time-service/windows-time-service-tools-and-settings" name="scite-7" rel="nofollow" target="_blank">
        Mathers, B. (2017, May 31). Windows Time Service Tools and Settings. Retrieved March 26, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/sysinternals/bb963902" name="scite-8" rel="nofollow" target="_blank">
        Russinovich, M. (2016, January 4). Autoruns for Windows v13.51. Retrieved June 6, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
