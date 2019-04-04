<div class="container-fluid">
 <h1>
  Office Application Startup
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Microsoft Office is a fairly common application suite on Windows-based operating systems within an enterprise network. There are multiple mechanisms that can be used with Office for persistence when an Office-based application is started.
   </p>
   <h3>
    Office Template Macros
   </h3>
   <p>
    Microsoft Office contains templates that are part of common Office applications and are used to customize styles. The base templates within the application are used each time an application starts.
    <span class="scite-citeref-number" data-reference="Microsoft Change Normal Template" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://support.office.com/article/Change-the-Normal-template-Normal-dotm-06de294b-d216-47f6-ab77-ccb5166f98ea" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Office Visual Basic for Applications (VBA) macros
    <span class="scite-citeref-number" data-reference="MSDN VBA in Office" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://msdn.microsoft.com/en-us/vba/office-shared-vba/articles/getting-started-with-vba-in-office" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    can inserted into the base templated and used to execute code when the respective Office application starts in order to obtain persistence. Examples for both Word and Excel have been discovered and published. By default, Word has a Normal.dotm template created that can be modified to include a malicious macro. Excel does not have a template file created by default, but one can be added that will automatically be loaded.
    <span class="scite-citeref-number" data-reference="enigma0x3 normal.dotm" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://enigma0x3.net/2014/01/23/maintaining-access-with-normal-dotm/comment-page-1/" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Hexacorn Office Template Macros" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="http://www.hexacorn.com/blog/2017/04/19/beyond-good-ol-run-key-part-62/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Word Normal.dotm location:
    <code>
     C:\Users(username)\AppData\Roaming\Microsoft\Templates\Normal.dotm
    </code>
   </p>
   <p>
    Excel Personal.xlsb location:
    <code>
     C:\Users(username)\AppData\Roaming\Microsoft\Excel\XLSTART\PERSONAL.XLSB
    </code>
   </p>
   <p>
    An adversary may need to enable macros to execute unrestricted depending on the system or enterprise security policy on use of macros.
   </p>
   <h3>
    Office Test
   </h3>
   <p>
    A Registry location was found that when a DLL reference was placed within it the corresponding DLL pointed to by the binary path would be executed every time an Office application is started
    <span class="scite-citeref-number" data-reference="Hexacorn Office Test" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="http://www.hexacorn.com/blog/2014/04/16/beyond-good-ol-run-key-part-10/" target="_blank">
       [5]
      </a>
     </sup>
    </span>
   </p>
   <p>
    <code>
     HKEY_CURRENT_USER\Software\Microsoft\Office test\Special\Perf
    </code>
   </p>
   <h3>
    Add-ins
   </h3>
   <p>
    Office add-ins can be used to add functionality to Office programs.
    <span class="scite-citeref-number" data-reference="Microsoft Office Add-ins" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://support.office.com/article/Add-or-remove-add-ins-0af570c4-5cf3-4fa9-9b88-403625a0b460" target="_blank">
       [6]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Add-ins can also be used to obtain persistence because they can be set to execute code when an Office application starts. There are different types of add-ins that can be used by the various Office products; including Word/Excel add-in Libraries (WLL/XLL), VBA add-ins, Office Component Object Model (COM) add-ins, automation add-ins, VBA Editor (VBE), and Visual Studio Tools for Office (VSTO) add-ins.
    <span class="scite-citeref-number" data-reference="MRWLabs Office Persistence Add-ins" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="https://labs.mwrinfosecurity.com/blog/add-in-opportunities-for-office-persistence/" target="_blank">
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
      : T1137
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
      User, Administrator
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
      Process monitoring, Process command-line parameters, Windows Registry, File monitoring
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
      Loic Jaquemet; Ricardo Dias
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
     <a href="https://attack.mitre.org/groups/G0007">
      APT28
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0007">
       APT28
      </a>
      has used the Office Test persistence mechanism within Microsoft Office by adding the Registry key
      <code>
       HKCU\Software\Microsoft\Office test\Special\Perf
      </code>
      to execute code.
      <span class="scite-citeref-number" data-reference="Palo Alto Office Test Sofacy" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://researchcenter.paloaltonetworks.com/2016/07/unit42-technical-walkthrough-office-test-persistence-method-used-in-recent-sofacy-attacks/" target="_blank">
         [8]
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
  Follow Office macro security best practices suitable for your environment. Disable Office VBA macros from executing. Even setting to disable with notification could enable unsuspecting users to execute potentially malicious macros.
  <span class="scite-citeref-number" data-reference="TechNet Office Macro Security" id="scite-ref-9-a">
   <sup>
    <a aria-describedby="qtip-8" data-hasqtip="8" href="https://blogs.technet.microsoft.com/mmpc/2016/03/22/new-feature-in-office-2016-can-block-macros-and-help-prevent-infection/" target="_blank">
     [9]
    </a>
   </sup>
  </span>
 </p>
 <p>
  For the Office Test method, create the Registry key used to execute it and set the permissions to "Read Control" to prevent easy access to the key without administrator permissions or requiring Privilege Escalation.
  <span class="scite-citeref-number" data-reference="Palo Alto Office Test Sofacy" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="https://researchcenter.paloaltonetworks.com/2016/07/unit42-technical-walkthrough-office-test-persistence-method-used-in-recent-sofacy-attacks/" target="_blank">
     [8]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Disable Office add-ins. If they are required, follow best practices for securing them by requiring them to be signed and disabling user notification for allowing add-ins. For some add-ins types (WLL, VBA) additional mitigation is likely required as disabling add-ins in the Office Trust Center does not disable WLL nor does it prevent VBA code from executing.
  <span class="scite-citeref-number" data-reference="MRWLabs Office Persistence Add-ins" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://labs.mwrinfosecurity.com/blog/add-in-opportunities-for-office-persistence/" target="_blank">
     [7]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Many Office-related persistence mechanisms require changes to the Registry and for binaries, files, or scripts to be written to disk or existing files modified to include malicious scripts. Collect events related to Registry key creation and modification for keys that could be used for Office-based persistence. Modification to base templated, like Normal.dotm, should also be investigated since the base templates should likely not contain VBA macros. Changes to the Office macro security settings should also be investigated.
 </p>
 <p>
  Monitor and validate the Office trusted locations on the file system and audit the Registry entries relevant for enabling add-ins.
  <span class="scite-citeref-number" data-reference="MRWLabs Office Persistence Add-ins" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://labs.mwrinfosecurity.com/blog/add-in-opportunities-for-office-persistence/" target="_blank">
     [7]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Non-standard process execution trees may also indicate suspicious or malicious behavior. Collect process execution information including process IDs (PID) and parent process IDs (PPID) and look for abnormal chains of activity resulting from Office processes. If winword.exe is the parent process for suspicious processes and activity relating to other adversarial techniques, then it could indicate that the application was used maliciously.
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
       <a class="external text" href="https://support.office.com/article/Change-the-Normal-template-Normal-dotm-06de294b-d216-47f6-ab77-ccb5166f98ea" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Change the Normal template (Normal.dotm). Retrieved July 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/en-us/vba/office-shared-vba/articles/getting-started-with-vba-in-office" name="scite-2" rel="nofollow" target="_blank">
        Austin, J. (2017, June 6). Getting Started with VBA in Office. Retrieved July 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://enigma0x3.net/2014/01/23/maintaining-access-with-normal-dotm/comment-page-1/" name="scite-3" rel="nofollow" target="_blank">
        Nelson, M. (2014, January 23). Maintaining Access with normal.dotm. Retrieved July 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.hexacorn.com/blog/2017/04/19/beyond-good-ol-run-key-part-62/" name="scite-4" rel="nofollow" target="_blank">
        Hexacorn. (2017, April 17). Beyond good ol’ Run key, Part 62. Retrieved July 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.hexacorn.com/blog/2014/04/16/beyond-good-ol-run-key-part-10/" name="scite-5" rel="nofollow" target="_blank">
        Hexacorn. (2014, April 16). Beyond good ol’ Run key, Part 10. Retrieved July 3, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="6.5">
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://support.office.com/article/Add-or-remove-add-ins-0af570c4-5cf3-4fa9-9b88-403625a0b460" name="scite-6" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Add or remove add-ins. Retrieved July 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://labs.mwrinfosecurity.com/blog/add-in-opportunities-for-office-persistence/" name="scite-7" rel="nofollow" target="_blank">
        Knowles, W. (2017, April 21). Add-In Opportunities for Office Persistence. Retrieved July 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2016/07/unit42-technical-walkthrough-office-test-persistence-method-used-in-recent-sofacy-attacks/" name="scite-8" rel="nofollow" target="_blank">
        Falcone, R. (2016, July 20). Technical Walkthrough: Office Test Persistence Method Used In Recent Sofacy Attacks. Retrieved July 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://blogs.technet.microsoft.com/mmpc/2016/03/22/new-feature-in-office-2016-can-block-macros-and-help-prevent-infection/" name="scite-9" rel="nofollow" target="_blank">
        Microsoft Malware Protection Center. (2016, March 22). New feature in Office 2016 can block macros and help prevent infection. Retrieved July 3, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
