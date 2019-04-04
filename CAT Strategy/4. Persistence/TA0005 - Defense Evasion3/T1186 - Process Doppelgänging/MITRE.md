<div class="container-fluid">
 <h1>
  Process Doppelgänging
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Windows Transactional NTFS (TxF) was introduced in Vista as a method to perform safe file operations.
    <span class="scite-citeref-number" data-reference="Microsoft TxF" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://msdn.microsoft.com/library/windows/desktop/bb968806.aspx" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    To ensure data integrity, TxF enables only one transacted handle to write to a file at a given time. Until the write handle transaction is terminated, all other handles are isolated from the writer and may only read the committed version of the file that existed at the time the handle was opened.
    <span class="scite-citeref-number" data-reference="Microsoft Basic TxF Concepts" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://msdn.microsoft.com/library/windows/desktop/dd979526.aspx" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    To avoid corruption, TxF performs an automatic rollback if the system or application fails during a write transaction.
    <span class="scite-citeref-number" data-reference="Microsoft Where to use TxF" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://msdn.microsoft.com/library/windows/desktop/aa365738.aspx" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Although deprecated, the TxF application programming interface (API) is still enabled as of Windows 10.
    <span class="scite-citeref-number" data-reference="BlackHat Process Doppelgänging Dec 2017" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.blackhat.com/docs/eu-17/materials/eu-17-Liberman-Lost-In-Transaction-Process-Doppelganging.pdf" target="_blank">
       [4]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries may leverage TxF to a perform a file-less variation of
    <a href="https://attack.mitre.org/techniques/T1055">
     Process Injection
    </a>
    called Process Doppelgänging. Similar to
    <a href="https://attack.mitre.org/techniques/T1093">
     Process Hollowing
    </a>
    , Process Doppelgänging involves replacing the memory of a legitimate process, enabling the veiled execution of malicious code that may evade defenses and detection. Process Doppelgänging's use of TxF also avoids the use of highly-monitored API functions such as NtUnmapViewOfSection, VirtualProtectEx, and SetThreadContext.
    <span class="scite-citeref-number" data-reference="BlackHat Process Doppelgänging Dec 2017" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.blackhat.com/docs/eu-17/materials/eu-17-Liberman-Lost-In-Transaction-Process-Doppelganging.pdf" target="_blank">
       [4]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Process Doppelgänging is implemented in 4 steps
    <span class="scite-citeref-number" data-reference="BlackHat Process Doppelgänging Dec 2017" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.blackhat.com/docs/eu-17/materials/eu-17-Liberman-Lost-In-Transaction-Process-Doppelganging.pdf" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    :
   </p>
   <ul>
    <li>
     Transact – Create a TxF transaction using a legitimate executable then overwrite the file with malicious code. These changes will be isolated and only visible within the context of the transaction.
    </li>
    <li>
     Load – Create a shared section of memory and load the malicious executable.
    </li>
    <li>
     Rollback – Undo changes to original executable, effectively removing malicious code from the file system.
    </li>
    <li>
     Animate – Create a process from the tainted section of memory and initiate execution.
    </li>
   </ul>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1186
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
      : Defense Evasion
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
      Administrator, SYSTEM, User
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
      API monitoring, Process monitoring
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
      Process whitelisting, Anti-virus, Whitelisting by file name or path, Signature-based detection
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
     <a href="https://attack.mitre.org/software/S0242">
      SynAck
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0242">
       SynAck
      </a>
      abuses NTFS transactions to launch and conceal malicious processes.
      <span class="scite-citeref-number" data-reference="SecureList SynAck Doppelgänging May 2018" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://securelist.com/synack-targeted-ransomware-uses-the-doppelganging-technique/85431/" target="_blank">
         [5]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Kaspersky Lab SynAck May 2018" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://usa.kaspersky.com/about/press-releases/2018_synack-doppelganging" target="_blank">
         [6]
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
  This type of attack technique cannot be easily mitigated with preventive controls or patched since it is based on the abuse of operating system design features. For example, mitigating specific API calls will likely have unintended side effects, such as preventing legitimate process-loading mechanisms from operating properly. Efforts should be focused on preventing adversary tools from running earlier in the chain of activity and on identifying subsequent malicious behavior.
 </p>
 <p>
  Although Process Doppelgänging may be used to evade certain types of defenses, it is still good practice to identify potentially malicious software that may be used to perform adversarial actions and audit and/or block it by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [7]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [8]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-9-a">
   <sup>
    <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [9]
    </a>
   </sup>
  </span>
  or Software Restriction Policies
  <span class="scite-citeref-number" data-reference="Corio 2008" id="scite-ref-10-a">
   <sup>
    <a aria-describedby="qtip-9" data-hasqtip="9" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" target="_blank">
     [10]
    </a>
   </sup>
  </span>
  where appropriate.
  <span class="scite-citeref-number" data-reference="TechNet Applocker vs SRP" id="scite-ref-11-a">
   <sup>
    <a aria-describedby="qtip-10" data-hasqtip="10" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" target="_blank">
     [11]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor and analyze calls to CreateTranscation, CreateFileTransacted, RollbackTransaction, and other rarely used functions indicative of TxF activity. Process Doppelgänging also invokes an outdated and undocumented implementation of the Windows process loader via calls to NtCreateProcessEx and NtCreateThreadEx as well as API calls used to modify memory within another process, such as WriteProcessMemory.
  <span class="scite-citeref-number" data-reference="BlackHat Process Doppelgänging Dec 2017" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.blackhat.com/docs/eu-17/materials/eu-17-Liberman-Lost-In-Transaction-Process-Doppelganging.pdf" target="_blank">
     [4]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="hasherezade Process Doppelgänging Dec 2017" id="scite-ref-12-a">
   <sup>
    <a aria-describedby="qtip-11" data-hasqtip="11" href="https://hshrzd.wordpress.com/2017/12/18/process-doppelganging-a-new-way-to-impersonate-a-process/" target="_blank">
     [12]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Scan file objects reported during the PsSetCreateProcessNotifyRoutine,
  <span class="scite-citeref-number" data-reference="Microsoft PsSetCreateProcessNotifyRoutine routine" id="scite-ref-13-a">
   <sup>
    <a aria-describedby="qtip-12" data-hasqtip="12" href="https://msdn.microsoft.com/library/windows/hardware/ff559951.aspx" target="_blank">
     [13]
    </a>
   </sup>
  </span>
  which triggers a callback whenever a process is created or deleted, specifically looking for file objects with enabled write access.
  <span class="scite-citeref-number" data-reference="BlackHat Process Doppelgänging Dec 2017" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.blackhat.com/docs/eu-17/materials/eu-17-Liberman-Lost-In-Transaction-Process-Doppelganging.pdf" target="_blank">
     [4]
    </a>
   </sup>
  </span>
  Also consider comparing file objects loaded in memory to the corresponding file on disk.
  <span class="scite-citeref-number" data-reference="hasherezade Process Doppelgänging Dec 2017" id="scite-ref-12-a">
   <sup>
    <a aria-describedby="qtip-11" data-hasqtip="11" href="https://hshrzd.wordpress.com/2017/12/18/process-doppelganging-a-new-way-to-impersonate-a-process/" target="_blank">
     [12]
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
       <a class="external text" href="https://msdn.microsoft.com/library/windows/desktop/bb968806.aspx" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Transactional NTFS (TxF). Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/windows/desktop/dd979526.aspx" name="scite-2" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Basic TxF Concepts. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/windows/desktop/aa365738.aspx" name="scite-3" rel="nofollow" target="_blank">
        Microsoft. (n.d.). When to Use Transactional NTFS. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.blackhat.com/docs/eu-17/materials/eu-17-Liberman-Lost-In-Transaction-Process-Doppelganging.pdf" name="scite-4" rel="nofollow" target="_blank">
        Liberman, T. &amp; Kogan, E. (2017, December 7). Lost in Transaction: Process Doppelgänging. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/synack-targeted-ransomware-uses-the-doppelganging-technique/85431/" name="scite-5" rel="nofollow" target="_blank">
        Ivanov, A. et al.. (2018, May 7). SynAck targeted ransomware uses the Doppelgänging technique. Retrieved May 22, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://usa.kaspersky.com/about/press-releases/2018_synack-doppelganging" name="scite-6" rel="nofollow" target="_blank">
        Bettencourt, J. (2018, May 7). Kaspersky Lab finds new variant of SynAck ransomware using sophisticated Doppelgänging technique. Retrieved May 24, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-7" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="8.5">
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-8" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-9" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" name="scite-10" rel="nofollow" target="_blank">
        Corio, C., &amp; Sayana, D. P. (2008, June). Application Lockdown with Software Restriction Policies. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" name="scite-11" rel="nofollow" target="_blank">
        Microsoft. (2012, June 27). Using Software Restriction Policies and AppLocker Policies. Retrieved April 7, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://hshrzd.wordpress.com/2017/12/18/process-doppelganging-a-new-way-to-impersonate-a-process/" name="scite-12" rel="nofollow" target="_blank">
        hasherezade. (2017, December 18). Process Doppelgänging – a new way to impersonate a process. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/windows/hardware/ff559951.aspx" name="scite-13" rel="nofollow" target="_blank">
        Microsoft. (n.d.). PsSetCreateProcessNotifyRoutine routine. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
