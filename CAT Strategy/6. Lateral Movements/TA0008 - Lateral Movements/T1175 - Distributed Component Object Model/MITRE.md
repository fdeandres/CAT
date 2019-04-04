<div class="container-fluid">
 <h1>
  Distributed Component Object Model
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Windows Distributed Component Object Model (DCOM) is transparent middleware that extends the functionality of Component Object Model (COM)
    <span class="scite-citeref-number" data-reference="Microsoft COM" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://msdn.microsoft.com/library/windows/desktop/ms680573.aspx" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    beyond a local computer using remote procedure call (RPC) technology. COM is a component of the Windows application programming interface (API) that enables interaction between software objects. Through COM, a client object can call methods of server objects, which are typically Dynamic Link Libraries (DLL) or executables (EXE).
   </p>
   <p>
    Permissions to interact with local and remote server COM objects are specified by access control lists (ACL) in the Registry.
    <span class="scite-citeref-number" data-reference="Microsoft COM ACL" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://docs.microsoft.com/en-us/windows/desktop/com/dcom-security-enhancements-in-windows-xp-service-pack-2-and-windows-server-2003-service-pack-1" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Microsoft Process Wide Com Keys" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://msdn.microsoft.com/en-us/library/windows/desktop/ms687317(v=vs.85).aspx" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Microsoft System Wide Com Keys" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://msdn.microsoft.com/en-us/library/windows/desktop/ms694331(v=vs.85).aspx" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    By default, only Administrators may remotely activate and launch COM objects through DCOM.
   </p>
   <p>
    Adversaries may use DCOM for lateral movement. Through DCOM, adversaries operating in the context of an appropriately privileged user can remotely obtain arbitrary and even direct shellcode execution through Office applications
    <span class="scite-citeref-number" data-reference="Enigma Outlook DCOM Lateral Movement Nov 2017" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://enigma0x3.net/2017/11/16/lateral-movement-using-outlooks-createobject-method-and-dotnettojscript/" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    as well as other Windows objects that contain insecure methods.
    <span class="scite-citeref-number" data-reference="Enigma MMC20 COM Jan 2017" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://enigma0x3.net/2017/01/05/lateral-movement-using-the-mmc20-application-com-object/" target="_blank">
       [6]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Enigma DCOM Lateral Movement Jan 2017" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="https://enigma0x3.net/2017/01/23/lateral-movement-via-dcom-round-2/" target="_blank">
       [7]
      </a>
     </sup>
    </span>
    DCOM can also execute macros in existing documents
    <span class="scite-citeref-number" data-reference="Enigma Excel DCOM Sept 2017" id="scite-ref-8-a">
     <sup>
      <a aria-describedby="qtip-7" data-hasqtip="7" href="https://enigma0x3.net/2017/09/11/lateral-movement-using-excel-application-and-dcom/" target="_blank">
       [8]
      </a>
     </sup>
    </span>
    and may also invoke
    <a href="https://attack.mitre.org/techniques/T1173">
     Dynamic Data Exchange
    </a>
    (DDE) execution directly through a COM created instance of a Microsoft Office application
    <span class="scite-citeref-number" data-reference="Cyberreason DCOM DDE Lateral Movement Nov 2017" id="scite-ref-9-a">
     <sup>
      <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.cybereason.com/blog/leveraging-excel-dde-for-lateral-movement-via-dcom" target="_blank">
       [9]
      </a>
     </sup>
    </span>
    , bypassing the need for a malicious document.
   </p>
   <p>
    DCOM may also expose functionalities that can be leveraged during other areas of the adversary chain of activity such as Privilege Escalation and Persistence.
    <span class="scite-citeref-number" data-reference="ProjectZero File Write EoP Apr 2018" id="scite-ref-10-a">
     <sup>
      <a aria-describedby="qtip-9" data-hasqtip="9" href="https://googleprojectzero.blogspot.com/2018/04/windows-exploitation-tricks-exploiting.html" target="_blank">
       [10]
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
      : T1175
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
      : Lateral Movement
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
      API monitoring, Authentication logs, DLL monitoring, Packet capture, Process monitoring, Windows Registry, Windows event logs
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
     <a href="https://attack.mitre.org/software/S0154">
      Cobalt Strike
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0154">
       Cobalt Strike
      </a>
      can deliver "beacon" payloads for lateral movement by leveraging remote COM execution.
      <span class="scite-citeref-number" data-reference="Cobalt Strike DCOM Jan 2017" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://blog.cobaltstrike.com/2017/01/24/scripting-matt-nelsons-mmc20-application-lateral-movement-technique/" target="_blank">
         [11]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0223">
      POWERSTATS
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0223">
       POWERSTATS
      </a>
      can use DCOM (targeting the 127.0.0.1 loopback address) to execute additional payloads on compromised hosts.
      <span class="scite-citeref-number" data-reference="FireEye MuddyWater Mar 2018" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html" target="_blank">
         [12]
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
  Modify Registry settings (directly or using Dcomcnfg.exe) in
  <code>
   HKEY_LOCAL_MACHINE\SOFTWARE\Classes\AppID{AppID_GUID}
  </code>
  associated with the process-wide security of individual COM applications.
  <span class="scite-citeref-number" data-reference="Microsoft Process Wide Com Keys" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="https://msdn.microsoft.com/en-us/library/windows/desktop/ms687317(v=vs.85).aspx" target="_blank">
     [3]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Modify Registry settings (directly or using Dcomcnfg.exe) in
  <code>
   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Ole
  </code>
  associated with system-wide security defaults for all COM applications that do no set their own process-wide security.
  <span class="scite-citeref-number" data-reference="Microsoft System Wide Com Keys" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="https://msdn.microsoft.com/en-us/library/windows/desktop/ms694331(v=vs.85).aspx" target="_blank">
     [4]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Microsoft COM ACL" id="scite-ref-2-a">
   <sup>
    <a aria-describedby="qtip-1" data-hasqtip="1" href="https://docs.microsoft.com/en-us/windows/desktop/com/dcom-security-enhancements-in-windows-xp-service-pack-2-and-windows-server-2003-service-pack-1" target="_blank">
     [2]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Consider disabling DCOM through Dcomcnfg.exe.
  <span class="scite-citeref-number" data-reference="Microsoft Disable DCOM" id="scite-ref-13-a">
   <sup>
    <a aria-describedby="qtip-12" data-hasqtip="12" href="https://technet.microsoft.com/library/cc771387.aspx" target="_blank">
     [13]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Enable Windows firewall, which prevents DCOM instantiation by default.
 </p>
 <p>
  Ensure all COM alerts and Protected View are enabled.
  <span class="scite-citeref-number" data-reference="Microsoft Protected View" id="scite-ref-14-a">
   <sup>
    <a aria-describedby="qtip-13" data-hasqtip="13" href="https://support.office.com/en-us/article/What-is-Protected-View-d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653" target="_blank">
     [14]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor for COM objects loading DLLs and other modules not typically associated with the application.
  <span class="scite-citeref-number" data-reference="Enigma Outlook DCOM Lateral Movement Nov 2017" id="scite-ref-5-a">
   <sup>
    <a aria-describedby="qtip-4" data-hasqtip="4" href="https://enigma0x3.net/2017/11/16/lateral-movement-using-outlooks-createobject-method-and-dotnettojscript/" target="_blank">
     [5]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Monitor for spawning of processes associated with COM objects, especially those invoked by a user different than the one currently logged on.
 </p>
 <p>
  Monitor for influx of Distributed Computing Environment/Remote Procedure Call (DCE/RPC) traffic.
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
       <a class="external text" href="https://msdn.microsoft.com/library/windows/desktop/ms680573.aspx" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Component Object Model (COM). Retrieved November 22, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/en-us/windows/desktop/com/dcom-security-enhancements-in-windows-xp-service-pack-2-and-windows-server-2003-service-pack-1" name="scite-2" rel="nofollow" target="_blank">
        Microsoft. (n.d.). DCOM Security Enhancements in Windows XP Service Pack 2 and Windows Server 2003 Service Pack 1. Retrieved November 22, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/en-us/library/windows/desktop/ms687317(v=vs.85).aspx" name="scite-3" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Setting Process-Wide Security Through the Registry. Retrieved November 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/en-us/library/windows/desktop/ms694331(v=vs.85).aspx" name="scite-4" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Registry Values for System-Wide Security. Retrieved November 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://enigma0x3.net/2017/11/16/lateral-movement-using-outlooks-createobject-method-and-dotnettojscript/" name="scite-5" rel="nofollow" target="_blank">
        Nelson, M. (2017, November 16). Lateral Movement using Outlook's CreateObject Method and DotNetToJScript. Retrieved November 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://enigma0x3.net/2017/01/05/lateral-movement-using-the-mmc20-application-com-object/" name="scite-6" rel="nofollow" target="_blank">
        Nelson, M. (2017, January 5). Lateral Movement using the MMC20 Application COM Object. Retrieved November 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://enigma0x3.net/2017/01/23/lateral-movement-via-dcom-round-2/" name="scite-7" rel="nofollow" target="_blank">
        Nelson, M. (2017, January 23). Lateral Movement via DCOM: Round 2. Retrieved November 21, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="8.0">
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://enigma0x3.net/2017/09/11/lateral-movement-using-excel-application-and-dcom/" name="scite-8" rel="nofollow" target="_blank">
        Nelson, M. (2017, September 11). Lateral Movement using Excel.Application and DCOM. Retrieved November 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cybereason.com/blog/leveraging-excel-dde-for-lateral-movement-via-dcom" name="scite-9" rel="nofollow" target="_blank">
        Tsukerman, P. (2017, November 8). Leveraging Excel DDE for lateral movement via DCOM. Retrieved November 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://googleprojectzero.blogspot.com/2018/04/windows-exploitation-tricks-exploiting.html" name="scite-10" rel="nofollow" target="_blank">
        Forshaw, J. (2018, April 18). Windows Exploitation Tricks: Exploiting Arbitrary File Writes for Local Elevation of Privilege. Retrieved May 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.cobaltstrike.com/2017/01/24/scripting-matt-nelsons-mmc20-application-lateral-movement-technique/" name="scite-11" rel="nofollow" target="_blank">
        Mudge, R. (2017, January 24). Scripting Matt Nelson’s MMC20.Application Lateral Movement Technique. Retrieved November 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html" name="scite-12" rel="nofollow" target="_blank">
        Singh, S. et al.. (2018, March 13). Iranian Threat Group Updates Tactics, Techniques and Procedures in Spear Phishing Campaign. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/library/cc771387.aspx" name="scite-13" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Enable or Disable DCOM. Retrieved November 22, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://support.office.com/en-us/article/What-is-Protected-View-d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653" name="scite-14" rel="nofollow" target="_blank">
        Microsoft. (n.d.). What is Protected View?. Retrieved November 22, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
