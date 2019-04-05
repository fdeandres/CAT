<div class="container-fluid">
 <h1>
  Trusted Developer Utilities
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    There are many utilities used for software development related tasks that can be used to execute code in various forms to assist in development, debugging, and reverse engineering. These utilities may often be signed with legitimate certificates that allow them to execute on a system and proxy execution of malicious code through a trusted process that effectively bypasses application whitelisting defensive solutions.
   </p>
   <h3>
    MSBuild
   </h3>
   <p>
    MSBuild.exe (Microsoft Build Engine) is a software build platform used by Visual Studio. It takes XML formatted project files that define requirements for building various platforms and configurations.
    <span class="scite-citeref-number" data-reference="MSDN MSBuild" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://msdn.microsoft.com/library/dd393574.aspx" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries can use MSBuild to proxy execution of code through a trusted Windows utility. The inline task capability of MSBuild that was introduced in .NET version 4 allows for C# code to be inserted into the XML project file.
    <span class="scite-citeref-number" data-reference="MSDN MSBuild" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://msdn.microsoft.com/library/dd393574.aspx" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    Inline Tasks MSBuild will compile and execute the inline task. MSBuild.exe is a signed Microsoft binary, so when it is used this way it can execute arbitrary code and bypass application whitelisting defenses that are configured to allow MSBuild.exe execution.
    <span class="scite-citeref-number" data-reference="SubTee GitHub All The Things Application Whitelisting Bypass" id="scite-ref-2-a">
     <sup>
      [2]
     </sup>
    </span>
   </p>
   <h3>
    DNX
   </h3>
   <p>
    The .NET Execution Environment (DNX), dnx.exe, is a software development kit packaged with Visual Studio Enterprise. It was retired in favor of .NET Core CLI in 2016.
    <span class="scite-citeref-number" data-reference="Microsoft Migrating from DNX" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://docs.microsoft.com/en-us/dotnet/core/migration/from-dnx" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    DNX is not present on standard builds of Windows and may only be present on developer workstations using older versions of .NET Core and ASP.NET Core 1.0. The dnx.exe executable is signed by Microsoft.
   </p>
   <p>
    An adversary can use dnx.exe to proxy execution of arbitrary code to bypass application whitelist policies that do not account for DNX.
    <span class="scite-citeref-number" data-reference="engima0x3 DNX Bypass" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://enigma0x3.net/2016/11/17/bypassing-application-whitelisting-by-using-dnx-exe/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
   </p>
   <h3>
    RCSI
   </h3>
   <p>
    The rcsi.exe utility is a non-interactive command-line interface for C# that is similar to csi.exe. It was provided within an early version of the Roslyn .NET Compiler Platform but has since been deprecated for an integrated solution.
    <span class="scite-citeref-number" data-reference="Microsoft Roslyn CPT RCSI" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://blogs.msdn.microsoft.com/visualstudio/2011/10/19/introducing-the-microsoft-roslyn-ctp/" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    The rcsi.exe binary is signed by Microsoft.
    <span class="scite-citeref-number" data-reference="engima0x3 RCSI Bypass" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://enigma0x3.net/2016/11/21/bypassing-application-whitelisting-by-using-rcsi-exe/" target="_blank">
       [6]
      </a>
     </sup>
    </span>
   </p>
   <p>
    C# .csx script files can be written and executed with rcsi.exe at the command-line. An adversary can use rcsi.exe to proxy execution of arbitrary code to bypass application whitelisting policies that do not account for execution of rcsi.exe.
    <span class="scite-citeref-number" data-reference="engima0x3 RCSI Bypass" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://enigma0x3.net/2016/11/21/bypassing-application-whitelisting-by-using-rcsi-exe/" target="_blank">
       [6]
      </a>
     </sup>
    </span>
   </p>
   <h3>
    WinDbg/CDB
   </h3>
   <p>
    WinDbg is a Microsoft Windows kernel and user-mode debugging utility. The Microsoft Console Debugger (CDB) cdb.exe is also user-mode debugger. Both utilities are included in Windows software development kits and can be used as standalone tools.
    <span class="scite-citeref-number" data-reference="Microsoft Debugging Tools for Windows" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/index" target="_blank">
       [7]
      </a>
     </sup>
    </span>
    They are commonly used in software development and reverse engineering and may not be found on typical Windows systems. Both WinDbg.exe and cdb.exe binaries are signed by Microsoft.
   </p>
   <p>
    An adversary can use WinDbg.exe and cdb.exe to proxy execution of arbitrary code to bypass application whitelist policies that do not account for execution of those utilities.
    <span class="scite-citeref-number" data-reference="Exploit Monday WinDbg" id="scite-ref-8-a">
     <sup>
      <a aria-describedby="qtip-7" data-hasqtip="7" href="http://www.exploit-monday.com/2016/08/windbg-cdb-shellcode-runner.html" target="_blank">
       [8]
      </a>
     </sup>
    </span>
   </p>
   <p>
    It is likely possible to use other debuggers for similar purposes, such as the kernel-mode debugger kd.exe, which is also signed by Microsoft.
   </p>
   <h3>
    Tracker
   </h3>
   <p>
    The file tracker utility, tracker.exe, is included with the .NET framework as part of MSBuild. It is used for logging calls to the Windows file system.
    <span class="scite-citeref-number" data-reference="Microsoft Docs File Tracking" id="scite-ref-9-a">
     <sup>
      <a aria-describedby="qtip-8" data-hasqtip="8" href="https://docs.microsoft.com/visualstudio/msbuild/file-tracking" target="_blank">
       [9]
      </a>
     </sup>
    </span>
   </p>
   <p>
    An adversary can use tracker.exe to proxy execution of an arbitrary DLL into another process. Since tracker.exe is also signed it can be used to bypass application whitelisting solutions.
    <span class="scite-citeref-number" data-reference="Twitter SubTee Tracker.exe" id="scite-ref-10-a">
     <sup>
      <a aria-describedby="qtip-9" data-hasqtip="9" href="https://twitter.com/subTee/status/793151392185589760" target="_blank">
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
      : T1127
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
      : Defense Evasion, Execution
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
      User
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
      Process monitoring
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Supports Remote:
      </span>
      No
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Defense Bypassed:
      </span>
      Application whitelisting
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
       Contributors:
      </span>
      Casey Smith; Matthew Demaske, Adaptforward
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
     <a href="https://attack.mitre.org/software/S0013">
      PlugX
     </a>
    </td>
    <td>
     <p>
      A version of
      <a href="https://attack.mitre.org/software/S0013">
       PlugX
      </a>
      loads as shellcode within a .NET Framework project using msbuild.exe, presumably to bypass application whitelisting techniques.
      <span class="scite-citeref-number" data-reference="Palo Alto PlugX June 2017" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://researchcenter.paloaltonetworks.com/2017/06/unit42-paranoid-plugx/" target="_blank">
         [11]
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
  MSBuild.exe, dnx.exe, rcsi.exe, WinDbg.exe, cdb.exe, and tracker.exe may not be necessary within a given environment and should be removed if not used.
 </p>
 <p>
  Use application whitelisting configured to block execution of MSBuild.exe, dnx.exe, rcsi.exe, WinDbg.exe, and cdb.exe if they are not required for a given system or network to prevent potential misuse by adversaries.
  <span class="scite-citeref-number" data-reference="Microsoft GitHub Device Guard CI Policies" id="scite-ref-12-a">
   <sup>
    <a aria-describedby="qtip-11" data-hasqtip="11" href="https://github.com/Microsoft/windows-itpro-docs/blob/master/windows/device-security/device-guard/deploy-code-integrity-policies-steps.md" target="_blank">
     [12]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Exploit Monday Mitigate Device Guard Bypases" id="scite-ref-13-a">
   <sup>
    <a aria-describedby="qtip-12" data-hasqtip="12" href="http://www.exploit-monday.com/2016/09/using-device-guard-to-mitigate-against.html" target="_blank">
     [13]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="GitHub mattifestation DeviceGuardBypass" id="scite-ref-14-a">
   <sup>
    <a aria-describedby="qtip-13" data-hasqtip="13" href="https://github.com/mattifestation/DeviceGuardBypassMitigationRules" target="_blank">
     [14]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="SubTee MSBuild" id="scite-ref-15-a">
   <sup>
    [15]
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  The presence of these or other utilities that enable proxy execution that are typically used for development, debugging, and reverse engineering on a system that is not used for these purposes may be suspicious.
 </p>
 <p>
  Use process monitoring to monitor the execution and arguments of MSBuild.exe, dnx.exe, rcsi.exe, WinDbg.exe, cdb.exe, and tracker.exe. Compare recent invocations of those binaries with prior history of known good arguments and executed binaries to determine anomalous and potentially adversarial activity. It is likely that these utilities will be used by software developers or for other software development related tasks, so if it exists and is used outside of that context, then the event may be suspicious. Command arguments used before and after invocation of the utilities may also be useful in determining the origin and purpose of the binary being executed.
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
       <a class="external text" href="https://msdn.microsoft.com/library/dd393574.aspx" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (n.d.). MSBuild1. Retrieved November 30, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       [ Smith, C. (2016, August 17). Includes 5 Known Application Whitelisting/ Application Control Bypass Techniques in One File. Retrieved June 30, 2017.
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/en-us/dotnet/core/migration/from-dnx" name="scite-3" rel="nofollow" target="_blank">
        Knezevic, Z., Wenzel, M. Latham, L. (2016, June 20). Migrating from DNX to .NET Core CLI (project.json). Retrieved June 28, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://enigma0x3.net/2016/11/17/bypassing-application-whitelisting-by-using-dnx-exe/" name="scite-4" rel="nofollow" target="_blank">
        Nelson, M. (2017, November 17). Bypassing Application Whitelisting By Using dnx.exe. Retrieved May 25, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://blogs.msdn.microsoft.com/visualstudio/2011/10/19/introducing-the-microsoft-roslyn-ctp/" name="scite-5" rel="nofollow" target="_blank">
        Osenkov, K. (2011, October 19). Introducing the Microsoft “Roslyn” CTP. Retrieved June 28, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://enigma0x3.net/2016/11/21/bypassing-application-whitelisting-by-using-rcsi-exe/" name="scite-6" rel="nofollow" target="_blank">
        Nelson, M. (2016, November 21). Bypassing Application Whitelisting By Using rcsi.exe. Retrieved May 26, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/index" name="scite-7" rel="nofollow" target="_blank">
        Marshall, D. (2017, May 23). Debugging Tools for Windows (WinDbg, KD, CDB, NTSD). Retrieved June 29, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.exploit-monday.com/2016/08/windbg-cdb-shellcode-runner.html" name="scite-8" rel="nofollow" target="_blank">
        Graeber, M. (2016, August 15). Bypassing Application Whitelisting by using WinDbg/CDB as a Shellcode Runner. Retrieved May 26, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="9.5">
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/visualstudio/msbuild/file-tracking" name="scite-9" rel="nofollow" target="_blank">
        B, M., Brown, K., Cai, S., Hogenson, G., Warren, G. (2016, November 4). File Tracking. Retrieved November 1, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://twitter.com/subTee/status/793151392185589760" name="scite-10" rel="nofollow" target="_blank">
        Smith, C. (2016, October 31). SubTee Twitter Status. Retrieved November 1, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/06/unit42-paranoid-plugx/" name="scite-11" rel="nofollow" target="_blank">
        Lancaster, T. and Idrizovic, E.. (2017, June 27). Paranoid PlugX. Retrieved July 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/Microsoft/windows-itpro-docs/blob/master/windows/device-security/device-guard/deploy-code-integrity-policies-steps.md" name="scite-12" rel="nofollow" target="_blank">
        Microsoft. (2017, June 16). Deploy code integrity policies: steps. Retrieved June 28, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.exploit-monday.com/2016/09/using-device-guard-to-mitigate-against.html" name="scite-13" rel="nofollow" target="_blank">
        Graeber, M. (2016, September 8). Using Device Guard to Mitigate Against Device Guard Bypasses. Retrieved September 13, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/mattifestation/DeviceGuardBypassMitigationRules" name="scite-14" rel="nofollow" target="_blank">
        Graeber, M. (2016, November 13). DeviceGuardBypassMitigationRules. Retrieved November 30, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       [ Smith, C. (2016, September 13). Bypassing Application Whitelisting using MSBuild.exe - Device Guard Example and Mitigations. Retrieved September 13, 2016.
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
