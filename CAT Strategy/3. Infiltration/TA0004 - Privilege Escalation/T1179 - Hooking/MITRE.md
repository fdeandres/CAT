<div class="container-fluid">
 <h1>
  Hooking
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Windows processes often leverage application programming interface (API) functions to perform tasks that require reusable system resources. Windows API functions are typically stored in dynamic-link libraries (DLLs) as exported functions. Hooking involves redirecting calls to these functions and can be implemented via:
   </p>
   <ul>
    <li>
     <strong>
      Hooks procedures
     </strong>
     , which intercept and execute designated code in response to events such as messages, keystrokes, and mouse inputs.
     <span class="scite-citeref-number" data-reference="Microsoft Hook Overview" id="scite-ref-1-a">
      <sup>
       <a aria-describedby="qtip-0" data-hasqtip="0" href="https://msdn.microsoft.com/library/windows/desktop/ms644959.aspx" target="_blank">
        [1]
       </a>
      </sup>
     </span>
     <span class="scite-citeref-number" data-reference="Endgame Process Injection July 2017" id="scite-ref-2-a">
      <sup>
       <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process" target="_blank">
        [2]
       </a>
      </sup>
     </span>
    </li>
    <li>
     <strong>
      Import address table (IAT) hooking
     </strong>
     , which use modifications to a process’s IAT, where pointers to imported API functions are stored.
     <span class="scite-citeref-number" data-reference="Endgame Process Injection July 2017" id="scite-ref-2-a">
      <sup>
       <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process" target="_blank">
        [2]
       </a>
      </sup>
     </span>
     <span class="scite-citeref-number" data-reference="Adlice Software IAT Hooks Oct 2014" id="scite-ref-3-a">
      <sup>
       <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.adlice.com/userland-rootkits-part-1-iat-hooks/" target="_blank">
        [3]
       </a>
      </sup>
     </span>
     <span class="scite-citeref-number" data-reference="MWRInfoSecurity Dynamic Hooking 2015" id="scite-ref-4-a">
      <sup>
       <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.mwrinfosecurity.com/our-thinking/dynamic-hooking-techniques-user-mode/" target="_blank">
        [4]
       </a>
      </sup>
     </span>
    </li>
    <li>
     <strong>
      Inline hooking
     </strong>
     , which overwrites the first bytes in an API function to redirect code flow.
     <span class="scite-citeref-number" data-reference="Endgame Process Injection July 2017" id="scite-ref-2-a">
      <sup>
       <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process" target="_blank">
        [2]
       </a>
      </sup>
     </span>
     <span class="scite-citeref-number" data-reference="HighTech Bridge Inline Hooking Sept 2011" id="scite-ref-5-a">
      <sup>
       <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.exploit-db.com/docs/17802.pdf" target="_blank">
        [5]
       </a>
      </sup>
     </span>
     <span class="scite-citeref-number" data-reference="MWRInfoSecurity Dynamic Hooking 2015" id="scite-ref-4-a">
      <sup>
       <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.mwrinfosecurity.com/our-thinking/dynamic-hooking-techniques-user-mode/" target="_blank">
        [4]
       </a>
      </sup>
     </span>
    </li>
   </ul>
   <p>
    Similar to
    <a href="https://attack.mitre.org/techniques/T1055">
     Process Injection
    </a>
    , adversaries may use hooking to load and execute malicious code within the context of another process, masking the execution while also allowing access to the process's memory and possibly elevated privileges. Installing hooking mechanisms may also provide Persistence via continuous invocation when the functions are called through normal use.
   </p>
   <p>
    Malicious hooking mechanisms may also capture API calls that include parameters that reveal user authentication credentials for Credential Access.
    <span class="scite-citeref-number" data-reference="Microsoft TrojanSpy:Win32/Ursnif.gen!I Sept 2017" id="scite-ref-6-a">
     <sup>
      [6]
     </sup>
    </span>
   </p>
   <p>
    Hooking is commonly utilized by
    <a href="https://attack.mitre.org/techniques/T1014">
     Rootkit
    </a>
    s to conceal files, processes, Registry keys, and other objects in order to hide malware and associated behaviors.
    <span class="scite-citeref-number" data-reference="Symantec Windows Rootkits" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.symantec.com/avcenter/reference/windows.rootkit.overview.pdf" target="_blank">
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
      : T1179
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
      : Persistence, Privilege Escalation, Credential Access
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
      API monitoring, Binary file metadata, DLL monitoring, Loaded DLLs, Process monitoring, Windows event logs
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
     <a href="https://attack.mitre.org/software/S0182">
      FinFisher
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0182">
       FinFisher
      </a>
      hooks processes by modifying IAT pointers to CreateWindowEx.
      <span class="scite-citeref-number" data-reference="FinFisher Citation" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="http://www.finfisher.com/FinFisher/index.html" target="_blank">
         [8]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Endgame Process Injection July 2017" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0068">
      PLATINUM
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0068">
       PLATINUM
      </a>
      is capable of using Windows hook interfaces for information gathering such as credential access.
      <span class="scite-citeref-number" data-reference="Microsoft PLATINUM April 2016" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" target="_blank">
         [9]
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
  This type of attack technique cannot be easily mitigated with preventive controls since it is based on the abuse of operating system design features. For example, mitigating all hooking will likely have unintended side effects, such as preventing legitimate software (i.e., security products) from operating properly. Efforts should be focused on preventing adversary tools from running earlier in the chain of activity and on identifying subsequent malicious behavior.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor for calls to the SetWindowsHookEx and SetWinEventHook functions, which install a hook procedure.
  <span class="scite-citeref-number" data-reference="Microsoft Hook Overview" id="scite-ref-1-a">
   <sup>
    <a aria-describedby="qtip-0" data-hasqtip="0" href="https://msdn.microsoft.com/library/windows/desktop/ms644959.aspx" target="_blank">
     [1]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Volatility Detecting Hooks Sept 2012" id="scite-ref-10-a">
   <sup>
    <a aria-describedby="qtip-9" data-hasqtip="9" href="https://volatility-labs.blogspot.com/2012/09/movp-31-detecting-malware-hooks-in.html" target="_blank">
     [10]
    </a>
   </sup>
  </span>
  Also consider analyzing hook chains (which hold pointers to hook procedures for each type of hook) using tools
  <span class="scite-citeref-number" data-reference="Volatility Detecting Hooks Sept 2012" id="scite-ref-10-a">
   <sup>
    <a aria-describedby="qtip-9" data-hasqtip="9" href="https://volatility-labs.blogspot.com/2012/09/movp-31-detecting-malware-hooks-in.html" target="_blank">
     [10]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="PreKageo Winhook Jul 2011" id="scite-ref-11-a">
   <sup>
    <a aria-describedby="qtip-10" data-hasqtip="10" href="https://github.com/prekageo/winhook" target="_blank">
     [11]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Jay GetHooks Sept 2011" id="scite-ref-12-a">
   <sup>
    <a aria-describedby="qtip-11" data-hasqtip="11" href="https://github.com/jay/gethooks" target="_blank">
     [12]
    </a>
   </sup>
  </span>
  or by programmatically examining internal kernel structures.
  <span class="scite-citeref-number" data-reference="Zairon Hooking Dec 2006" id="scite-ref-13-a">
   <sup>
    <a aria-describedby="qtip-12" data-hasqtip="12" href="https://zairon.wordpress.com/2006/12/06/any-application-defined-hook-procedure-on-my-machine/" target="_blank">
     [13]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="EyeofRa Detecting Hooking June 2017" id="scite-ref-14-a">
   <sup>
    <a aria-describedby="qtip-13" data-hasqtip="13" href="https://eyeofrablog.wordpress.com/2017/06/27/windows-keylogger-part-2-defense-against-user-land/" target="_blank">
     [14]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Rootkits detectors
  <span class="scite-citeref-number" data-reference="GMER Rootkits" id="scite-ref-15-a">
   <sup>
    <a aria-describedby="qtip-14" data-hasqtip="14" href="http://www.gmer.net/" target="_blank">
     [15]
    </a>
   </sup>
  </span>
  can also be used to monitor for various flavors of hooking activity.
 </p>
 <p>
  Verify integrity of live processes by comparing code in memory to that of corresponding static binaries, specifically checking for jumps and other instructions that redirect code flow. Also consider taking snapshots of newly started processes
  <span class="scite-citeref-number" data-reference="Microsoft Process Snapshot" id="scite-ref-16-a">
   <sup>
    <a aria-describedby="qtip-15" data-hasqtip="15" href="https://msdn.microsoft.com/library/windows/desktop/ms686701.aspx" target="_blank">
     [16]
    </a>
   </sup>
  </span>
  to compare the in-memory IAT to the real addresses of the referenced functions.
  <span class="scite-citeref-number" data-reference="StackExchange Hooks Jul 2012" id="scite-ref-17-a">
   <sup>
    <a aria-describedby="qtip-16" data-hasqtip="16" href="https://security.stackexchange.com/questions/17904/what-are-the-methods-to-find-hooked-functions-and-apis" target="_blank">
     [17]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Adlice Software IAT Hooks Oct 2014" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.adlice.com/userland-rootkits-part-1-iat-hooks/" target="_blank">
     [3]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Analyze process behavior to determine if a process is performing actions it usually does not, such as opening network connections, reading files, or other suspicious actions that could relate to post-compromise behavior.
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
       <a class="external text" href="https://msdn.microsoft.com/library/windows/desktop/ms644959.aspx" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Hooks Overview. Retrieved December 12, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process" name="scite-2" rel="nofollow" target="_blank">
        Hosseini, A. (2017, July 18). Ten Process Injection Techniques: A Technical Survey Of Common And Trending Process Injection Techniques. Retrieved December 7, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.adlice.com/userland-rootkits-part-1-iat-hooks/" name="scite-3" rel="nofollow" target="_blank">
        Tigzy. (2014, October 15). Userland Rootkits: Part 1, IAT hooks. Retrieved December 12, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.mwrinfosecurity.com/our-thinking/dynamic-hooking-techniques-user-mode/" name="scite-4" rel="nofollow" target="_blank">
        Hillman, M. (2015, August 8). Dynamic Hooking Techniques: User Mode. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.exploit-db.com/docs/17802.pdf" name="scite-5" rel="nofollow" target="_blank">
        Mariani, B. (2011, September 6). Inline Hooking in Windows. Retrieved December 12, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       Microsoft. (2017, September 15). TrojanSpy:Win32/Ursnif.gen!I. Retrieved December 18, 2017.
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/avcenter/reference/windows.rootkit.overview.pdf" name="scite-7" rel="nofollow" target="_blank">
        Symantec. (n.d.). Windows Rootkit Overview. Retrieved December 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.finfisher.com/FinFisher/index.html" name="scite-8" rel="nofollow" target="_blank">
        FinFisher. (n.d.). Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" name="scite-9" rel="nofollow" target="_blank">
        Windows Defender Advanced Threat Hunting Team. (2016, April 29). PLATINUM: Targeted attacks in South and Southeast Asia. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="10.5">
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://volatility-labs.blogspot.com/2012/09/movp-31-detecting-malware-hooks-in.html" name="scite-10" rel="nofollow" target="_blank">
        Volatility Labs. (2012, September 24). MoVP 3.1 Detecting Malware Hooks in the Windows GUI Subsystem. Retrieved December 12, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/prekageo/winhook" name="scite-11" rel="nofollow" target="_blank">
        Prekas, G. (2011, July 11). Winhook. Retrieved December 12, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/jay/gethooks" name="scite-12" rel="nofollow" target="_blank">
        Satiro, J. (2011, September 14). GetHooks. Retrieved December 12, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://zairon.wordpress.com/2006/12/06/any-application-defined-hook-procedure-on-my-machine/" name="scite-13" rel="nofollow" target="_blank">
        Felici, M. (2006, December 6). Any application-defined hook procedure on my machine?. Retrieved December 12, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://eyeofrablog.wordpress.com/2017/06/27/windows-keylogger-part-2-defense-against-user-land/" name="scite-14" rel="nofollow" target="_blank">
        Eye of Ra. (2017, June 27). Windows Keylogger Part 2: Defense against user-land. Retrieved December 12, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.gmer.net/" name="scite-15" rel="nofollow" target="_blank">
        GMER. (n.d.). GMER. Retrieved December 12, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/windows/desktop/ms686701.aspx" name="scite-16" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Taking a Snapshot and Viewing Processes. Retrieved December 12, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://security.stackexchange.com/questions/17904/what-are-the-methods-to-find-hooked-functions-and-apis" name="scite-17" rel="nofollow" target="_blank">
        Stack Exchange - Security. (2012, July 31). What are the methods to find hooked functions and APIs?. Retrieved December 12, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
