<div class="container-fluid">
 <h1>
  Authentication Package
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Windows Authentication Package DLLs are loaded by the Local Security Authority (LSA) process at system start. They provide support for multiple logon processes and multiple security protocols to the operating system.
    <span class="scite-citeref-number" data-reference="MSDN Authentication Packages" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://msdn.microsoft.com/library/windows/desktop/aa374733.aspx" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries can use the autostart mechanism provided by LSA Authentication Packages for persistence by placing a reference to a binary in the Windows Registry location
    <code>
     HKLM\SYSTEM\CurrentControlSet\Control\Lsa\
    </code>
    with the key value of
    <code>
     "Authentication Packages"=
     <target binary="">
     </target>
    </code>
    . The binary will then be executed by the system when the authentication packages are loaded.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1131
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
      Administrator
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
      DLL monitoring, Windows Registry, Loaded DLLs
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
     <a href="https://attack.mitre.org/software/S0143">
      Flame
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0143">
       Flame
      </a>
      can use Windows Authentication Packages for persistence.
      <span class="scite-citeref-number" data-reference="Crysys Skywiper" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.crysys.hu/publications/files/skywiper.pdf" target="_blank">
         [2]
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
  Windows 8.1, Windows Server 2012 R2, and later versions, may make LSA run as a Protected Process Light (PPL) by setting the Registry key
  <code>
   HKLM\SYSTEM\CurrentControlSet\Control\Lsa\RunAsPPL
  </code>
  , which requires all DLLs loaded by LSA to be signed by Microsoft.
  <span class="scite-citeref-number" data-reference="Graeber 2014" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="http://docplayer.net/20839173-Analysis-of-malicious-security-support-provider-dlls.html" target="_blank">
     [3]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Microsoft Configure LSA" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="https://technet.microsoft.com/en-us/library/dn408187.aspx" target="_blank">
     [4]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor the Registry for changes to the LSA Registry keys. Monitor the LSA process for DLL loads. Windows 8.1 and Windows Server 2012 R2 may generate events when unsigned DLLs try to load into the LSA by setting the Registry key
  <code>
   HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\LSASS.exe
  </code>
  with AuditLevel = 8.
  <span class="scite-citeref-number" data-reference="Graeber 2014" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="http://docplayer.net/20839173-Analysis-of-malicious-security-support-provider-dlls.html" target="_blank">
     [3]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Microsoft Configure LSA" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="https://technet.microsoft.com/en-us/library/dn408187.aspx" target="_blank">
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
       <a class="external text" href="https://msdn.microsoft.com/library/windows/desktop/aa374733.aspx" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Authentication Packages. Retrieved March 1, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.crysys.hu/publications/files/skywiper.pdf" name="scite-2" rel="nofollow" target="_blank">
        sKyWIper Analysis Team. (2012, May 31). sKyWIper (a.k.a. Flame a.k.a. Flamer):  A complex malware for targeted attacks. Retrieved September 6, 2018.
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
       <a class="external text" href="http://docplayer.net/20839173-Analysis-of-malicious-security-support-provider-dlls.html" name="scite-3" rel="nofollow" target="_blank">
        Graeber, M. (2014, October). Analysis of Malicious Security Support Provider DLLs. Retrieved March 1, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/dn408187.aspx" name="scite-4" rel="nofollow" target="_blank">
        Microsoft. (2013, July 31). Configuring Additional LSA Protection. Retrieved June 24, 2015.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
