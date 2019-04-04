<div class="container-fluid">
 <h1>
  Image File Execution Options Injection
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Image File Execution Options (IFEO) enable a developer to attach a debugger to an application. When a process is created, a debugger present in an application’s IFEO will be prepended to the application’s name, effectively launching the new process under the debugger (e.g., "C:\dbg\ntsd.exe -g  notepad.exe").
    <span class="scite-citeref-number" data-reference="Microsoft Dev Blog IFEO Mar 2010" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://blogs.msdn.microsoft.com/mithuns/2010/03/24/image-file-execution-options-ifeo/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    IFEOs can be set directly via the Registry or in Global Flags via the GFlags tool.
    <span class="scite-citeref-number" data-reference="Microsoft GFlags Mar 2017" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://docs.microsoft.com/windows-hardware/drivers/debugger/gflags-overview" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    IFEOs are represented as
    <code>
     Debugger
    </code>
    values in the Registry under
    <code>
     HKLM\SOFTWARE{\Wow6432Node}\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\
     <executable>
     </executable>
    </code>
    where
    <code>
     <executable>
     </executable>
    </code>
    is the binary on which the debugger is attached.
    <span class="scite-citeref-number" data-reference="Microsoft Dev Blog IFEO Mar 2010" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://blogs.msdn.microsoft.com/mithuns/2010/03/24/image-file-execution-options-ifeo/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    IFEOs can also enable an arbitrary monitor program to be launched when a specified program silently exits (i.e. is prematurely terminated by itself or a second, non kernel-mode process).
    <span class="scite-citeref-number" data-reference="Microsoft Silent Process Exit NOV 2017" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://docs.microsoft.com/windows-hardware/drivers/debugger/registry-entries-for-silent-process-exit" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Oddvar Moe IFEO APR 2018" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://oddvar.moe/2018/04/10/persistence-using-globalflags-in-image-file-execution-options-hidden-from-autoruns-exe/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    Similar to debuggers, silent exit monitoring can be enabled through GFlags and/or by directly modifying IEFO and silent process exit Registry values in
    <code>
     HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit\
    </code>
    .
    <span class="scite-citeref-number" data-reference="Microsoft Silent Process Exit NOV 2017" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://docs.microsoft.com/windows-hardware/drivers/debugger/registry-entries-for-silent-process-exit" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Oddvar Moe IFEO APR 2018" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://oddvar.moe/2018/04/10/persistence-using-globalflags-in-image-file-execution-options-hidden-from-autoruns-exe/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
   </p>
   <p>
    An example where the evil.exe process is started when notepad.exe exits:
    <span class="scite-citeref-number" data-reference="Oddvar Moe IFEO APR 2018" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://oddvar.moe/2018/04/10/persistence-using-globalflags-in-image-file-execution-options-hidden-from-autoruns-exe/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
   </p>
   <ul>
    <li>
     <code>
      reg add "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\notepad.exe" /v GlobalFlag /t REG_DWORD /d 512
     </code>
    </li>
    <li>
     <code>
      reg add "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit\notepad.exe" /v ReportingMode /t REG_DWORD /d 1
     </code>
    </li>
    <li>
     <code>
      reg add "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit\notepad.exe" /v MonitorProcess /d "C:\temp\evil.exe"
     </code>
    </li>
   </ul>
   <p>
    Similar to
    <a href="https://attack.mitre.org/techniques/T1055">
     Process Injection
    </a>
    , these values may be abused to obtain persistence and privilege escalation by causing a malicious executable to be loaded and run in the context of separate processes on the computer.
    <span class="scite-citeref-number" data-reference="Endgame Process Injection July 2017" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    Installing IFEO mechanisms may also provide Persistence via continuous invocation.
   </p>
   <p>
    Malware may also use IFEO for Defense Evasion by registering invalid debuggers that redirect and effectively disable various system and security applications.
    <span class="scite-citeref-number" data-reference="FSecure Hupigon" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.f-secure.com/v-descs/backdoor_w32_hupigon_emv.shtml" target="_blank">
       [6]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Symantec Ushedix June 2008" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.symantec.com/security_response/writeup.jsp?docid=2008-062807-2501-99&amp;tabid=2" target="_blank">
       [7]
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
      : T1183
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
      : Privilege Escalation, Persistence, Defense Evasion
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
      Process monitoring, Windows Registry, Windows event logs
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
      Autoruns Analysis
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
      Oddvar Moe, @oddvarmoe
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
  This type of attack technique cannot be easily mitigated with preventive controls since it is based on the abuse of operating system design features. For example, mitigating all IFEO will likely have unintended side effects, such as preventing legitimate software (i.e., security products) from operating properly.
  <span class="scite-citeref-number" data-reference="Microsoft IFEOorMalware July 2015" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="https://answers.microsoft.com/windows/forum/windows_10-security/part-of-windows-10-or-really-malware/af715663-a34a-423c-850d-2a46f369a54c" target="_blank">
     [8]
    </a>
   </sup>
  </span>
  Efforts should be focused on preventing adversary tools from running earlier in the chain of activity and on identifying subsequent malicious behavior.
 </p>
 <p>
  Identify and block potentially malicious software that may be executed through IFEO by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-9-a">
   <sup>
    <a aria-describedby="qtip-8" data-hasqtip="8" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [9]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-10-a">
   <sup>
    <a aria-describedby="qtip-9" data-hasqtip="9" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [10]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-11-a">
   <sup>
    <a aria-describedby="qtip-10" data-hasqtip="10" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [11]
    </a>
   </sup>
  </span>
  that are capable of auditing and/or blocking unknown executables.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor for common processes spawned under abnormal parents and/or with creation flags indicative of debugging such as
  <code>
   DEBUG_PROCESS
  </code>
  and
  <code>
   DEBUG_ONLY_THIS_PROCESS
  </code>
  .
  <span class="scite-citeref-number" data-reference="Microsoft Dev Blog IFEO Mar 2010" id="scite-ref-1-a">
   <sup>
    <a aria-describedby="qtip-0" data-hasqtip="0" href="https://blogs.msdn.microsoft.com/mithuns/2010/03/24/image-file-execution-options-ifeo/" target="_blank">
     [1]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Monitor Registry values associated with IFEOs, as well as silent process exit monitoring, for modifications that do not correlate with known software, patch cycles, etc. Monitor and analyze application programming interface (API) calls that are indicative of Registry edits such as RegCreateKeyEx and RegSetValueEx.
  <span class="scite-citeref-number" data-reference="Endgame Process Injection July 2017" id="scite-ref-5-a">
   <sup>
    <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process" target="_blank">
     [5]
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
       <a class="external text" href="https://blogs.msdn.microsoft.com/mithuns/2010/03/24/image-file-execution-options-ifeo/" name="scite-1" rel="nofollow" target="_blank">
        Shanbhag, M. (2010, March 24). Image File Execution Options (IFEO). Retrieved December 18, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/windows-hardware/drivers/debugger/gflags-overview" name="scite-2" rel="nofollow" target="_blank">
        Microsoft. (2017, May 23). GFlags Overview. Retrieved December 18, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/windows-hardware/drivers/debugger/registry-entries-for-silent-process-exit" name="scite-3" rel="nofollow" target="_blank">
        Marshall, D. &amp; Griffin, S. (2017, November 28). Monitoring Silent Process Exit. Retrieved June 27, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://oddvar.moe/2018/04/10/persistence-using-globalflags-in-image-file-execution-options-hidden-from-autoruns-exe/" name="scite-4" rel="nofollow" target="_blank">
        Moe, O. (2018, April 10). Persistence using GlobalFlags in Image File Execution Options - Hidden from Autoruns.exe. Retrieved June 27, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process" name="scite-5" rel="nofollow" target="_blank">
        Hosseini, A. (2017, July 18). Ten Process Injection Techniques: A Technical Survey Of Common And Trending Process Injection Techniques. Retrieved December 7, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.f-secure.com/v-descs/backdoor_w32_hupigon_emv.shtml" name="scite-6" rel="nofollow" target="_blank">
        FSecure. (n.d.). Backdoor - W32/Hupigon.EMV - Threat Description. Retrieved December 18, 2017.
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
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2008-062807-2501-99&amp;tabid=2" name="scite-7" rel="nofollow" target="_blank">
        Symantec. (2008, June 28). Trojan.Ushedix. Retrieved December 18, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://answers.microsoft.com/windows/forum/windows_10-security/part-of-windows-10-or-really-malware/af715663-a34a-423c-850d-2a46f369a54c" name="scite-8" rel="nofollow" target="_blank">
        Microsoft. (2015, July 30). Part of Windows 10 or really Malware?. Retrieved December 18, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-9" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-10" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-11" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
