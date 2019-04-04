<div class="container-fluid">
 <h1>
  Execution through Module Load
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    The Windows module loader can be instructed to load DLLs from arbitrary local paths and arbitrary Universal Naming Convention (UNC) network paths. This functionality resides in NTDLL.dll and is part of the Windows Native API which is called from functions like CreateProcess(), LoadLibrary(), etc. of the Win32 API.
    <span class="scite-citeref-number" data-reference="Wikipedia Windows Library Files" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://en.wikipedia.org/wiki/Microsoft_Windows_library_files" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    The module loader can load DLLs:
   </p>
   <ul>
    <li>
     <p>
      via specification of the (fully-qualified or relative) DLL pathname in the IMPORT directory;
     </p>
    </li>
    <li>
     <p>
      via EXPORT forwarded to another DLL, specified with (fully-qualified or relative) pathname (but without extension);
     </p>
    </li>
    <li>
     <p>
      via an NTFS junction or symlink program.exe.local with the fully-qualified or relative pathname of a directory containing the DLLs specified in the IMPORT directory or forwarded EXPORTs;
     </p>
    </li>
    <li>
     <p>
      via
      <code>
       <file loadfrom="fully-qualified or relative pathname" name="filename.extension">
       </file>
      </code>
      in an embedded or external "application manifest". The file name refers to an entry in the IMPORT directory or a forwarded EXPORT.
     </p>
    </li>
   </ul>
   <p>
    Adversaries can use this functionality as a way to execute arbitrary code on a system.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1129
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
      : Execution
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
      API monitoring, DLL monitoring, File monitoring, Process monitoring
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
      Stefan Kanthak
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
     <a href="https://attack.mitre.org/software/S0203">
      Hydraq
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0203">
       Hydraq
      </a>
      creates a backdoor through which remote attackers can load and call DLL functions.
      <span class="scite-citeref-number" data-reference="Symantec Trojan.Hydraq Jan 2010" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.symantec.com/connect/blogs/trojanhydraq-incident" target="_blank">
         [2]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Symantec Hydraq Jan 2010" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.symantec.com/security_response/writeup.jsp?docid=2010-011114-1830-99" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0196">
      PUNCHBUGGY
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0196">
       PUNCHBUGGY
      </a>
      can load a DLL using the LoadLibrary API.
      <span class="scite-citeref-number" data-reference="FireEye Know Your Enemy FIN8 Aug 2016" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" target="_blank">
         [4]
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
  Directly mitigating module loads and API calls related to module loads will likely have unintended side effects, such as preventing legitimate software from operating properly. Efforts should be focused on preventing adversary tools from running earlier in the chain of activity and on identifying and correlated subsequent behavior to determine if it is the result of malicious activity.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitoring DLL module loads may generate a significant amount of data and may not be directly useful for defense unless collected under specific circumstances, since benign use of Windows modules load functions are common and may be difficult to distinguish from malicious behavior. Legitimate software will likely only need to load routine, bundled DLL modules or Windows system DLLs such that deviation from known module loads may be suspicious. Limiting DLL module loads to
  <code>
   %SystemRoot%
  </code>
  and
  <code>
   %ProgramFiles%
  </code>
  directories will protect against module loads from unsafe paths.
 </p>
 <p>
  Correlation of other events with behavior surrounding module loads using API monitoring and suspicious DLLs written to disk will provide additional context to an event that may assist in determining if it is due to malicious behavior.
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
       <a class="external text" href="https://en.wikipedia.org/wiki/Microsoft_Windows_library_files" name="scite-1" rel="nofollow" target="_blank">
        Wikipedia. (2017, January 31). Microsoft Windows library files. Retrieved February 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/connect/blogs/trojanhydraq-incident" name="scite-2" rel="nofollow" target="_blank">
        Symantec Security Response. (2010, January 18). The Trojan.Hydraq Incident. Retrieved February 20, 2018.
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
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2010-011114-1830-99" name="scite-3" rel="nofollow" target="_blank">
        Lelli, A. (2010, January 11). Trojan.Hydraq. Retrieved February 20, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" name="scite-4" rel="nofollow" target="_blank">
        Elovitz, S. &amp; Ahl, I. (2016, August 18). Know Your Enemy:  New Financially-Motivated &amp; Spear-Phishing Group. Retrieved February 26, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
