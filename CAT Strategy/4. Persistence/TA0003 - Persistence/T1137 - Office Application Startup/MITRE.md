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
    Add-ins can also be used to obtain persistence because they can be set to execute code when an Office application starts. There are different types of add-ins that can be used by the various Office products; including Word/Excel add-in Libraries (WLL/XLL), VBA add-ins, Office Component Object Model (COM) add-ins, automation add-ins, VBA Editor (VBE), Visual Studio Tools for Office (VSTO) add-ins, and Outlook add-ins.
    <span class="scite-citeref-number" data-reference="MRWLabs Office Persistence Add-ins" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="https://labs.mwrinfosecurity.com/blog/add-in-opportunities-for-office-persistence/" target="_blank">
       [7]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="FireEye Mail CDS 2018" id="scite-ref-8-a">
     <sup>
      <a aria-describedby="qtip-7" data-hasqtip="7" href="https://summit.fireeye.com/content/dam/fireeye-www/summit/cds-2018/presentations/cds18-technical-s03-youve-got-mail.pdf" target="_blank">
       [8]
      </a>
     </sup>
    </span>
   </p>
   <h3>
    Outlook Rules, Forms, and Home Page
   </h3>
   <p>
    A variety of features have been discovered in Outlook that can be abused to obtain persistence, such as Outlook rules, forms, and Home Page.
    <span class="scite-citeref-number" data-reference="SensePost Ruler GitHub" id="scite-ref-9-a">
     <sup>
      <a aria-describedby="qtip-8" data-hasqtip="8" href="https://github.com/sensepost/ruler" target="_blank">
       [9]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Outlook rules allow a user to define automated behavior to manage email messages. A benign rule might, for example, automatically move an email to a particular folder in Outlook if it contains specific words from a specific sender. Malicious Outlook rules can be created that can trigger code execution when an adversary sends a specifically crafted email to that user.
    <span class="scite-citeref-number" data-reference="SilentBreak Outlook Rules" id="scite-ref-10-a">
     <sup>
      <a aria-describedby="qtip-9" data-hasqtip="9" href="https://silentbreaksecurity.com/malicious-outlook-rules/" target="_blank">
       [10]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Outlook forms are used as templates for presentation and functionality in Outlook messages. Custom Outlook Forms can be created that will execute code when a specifically crafted email is sent by an adversary utilizing the same custom Outlook form.
    <span class="scite-citeref-number" data-reference="SensePost Outlook Forms" id="scite-ref-11-a">
     <sup>
      <a aria-describedby="qtip-10" data-hasqtip="10" href="https://sensepost.com/blog/2017/outlook-forms-and-shells/" target="_blank">
       [11]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Outlook Home Page is a legacy feature used to customize the presentation of Outlook folders. This feature allows for an internal or external URL to be loaded and presented whenever a folder is opened. A malicious HTML page can be crafted that will execute code when loaded by Outlook Home Page.
    <span class="scite-citeref-number" data-reference="SensePost Outlook Home Page" id="scite-ref-12-a">
     <sup>
      <a aria-describedby="qtip-11" data-hasqtip="11" href="https://sensepost.com/blog/2017/outlook-home-page-another-ruler-vector/" target="_blank">
       [12]
      </a>
     </sup>
    </span>
   </p>
   <p>
    To abuse these features, an adversary requires prior access to the user’s Outlook mailbox, either via an Exchange/OWA server or via the client application. Once malicious rules, forms, or Home Pages have been added to the user’s mailbox, they will be loaded when Outlook is started. Malicious Home Pages will execute when the right Outlook folder is loaded/reloaded while malicious rules and forms will execute when an adversary sends a specifically crafted email to the user.
    <span class="scite-citeref-number" data-reference="SilentBreak Outlook Rules" id="scite-ref-10-a">
     <sup>
      <a aria-describedby="qtip-9" data-hasqtip="9" href="https://silentbreaksecurity.com/malicious-outlook-rules/" target="_blank">
       [10]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="SensePost Outlook Forms" id="scite-ref-11-a">
     <sup>
      <a aria-describedby="qtip-10" data-hasqtip="10" href="https://sensepost.com/blog/2017/outlook-forms-and-shells/" target="_blank">
       [11]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="SensePost Outlook Home Page" id="scite-ref-12-a">
     <sup>
      <a aria-describedby="qtip-11" data-hasqtip="11" href="https://sensepost.com/blog/2017/outlook-home-page-another-ruler-vector/" target="_blank">
       [12]
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
       System Requirements:
      </span>
      Office Test technique: Office 2007, 2010, 2013, 2015 and 2016; Add-ins: some require administrator permissions
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
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Contributors:
      </span>
      Praetorian; Nick Carr, FireEye; Loic Jaquemet; Ricardo Dias
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Version
      </span>
      : 1.1
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
      <span class="scite-citeref-number" data-reference="Palo Alto Office Test Sofacy" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://researchcenter.paloaltonetworks.com/2016/07/unit42-technical-walkthrough-office-test-persistence-method-used-in-recent-sofacy-attacks/" target="_blank">
         [13]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0050">
      APT32
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0050">
       APT32
      </a>
      installed a backdoor macro in Microsoft Outlook for persistence.
      <span class="scite-citeref-number" data-reference="Cybereason Oceanlotus May 2017" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://www.cybereason.com/blog/operation-cobalt-kitty-apt" target="_blank">
         [14]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Cybereason Cobalt Kitty 2017" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://cdn2.hubspot.net/hubfs/3354902/Cybereason%20Labs%20Analysis%20Operation%20Cobalt%20Kitty.pdf" target="_blank">
         [15]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0358">
      Ruler
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0358">
       Ruler
      </a>
      can be used to automate the abuse of Outlook Rules, Forms, and Home Pages to establish persistence.
      <span class="scite-citeref-number" data-reference="SensePost Ruler GitHub" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://github.com/sensepost/ruler" target="_blank">
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
  Follow Office macro security best practices suitable for your environment. Disable Office VBA macros from executing. Even setting to disable with notification could enable unsuspecting users to execute potentially malicious macros.
  <span class="scite-citeref-number" data-reference="TechNet Office Macro Security" id="scite-ref-16-a">
   <sup>
    <a aria-describedby="qtip-15" data-hasqtip="15" href="https://blogs.technet.microsoft.com/mmpc/2016/03/22/new-feature-in-office-2016-can-block-macros-and-help-prevent-infection/" target="_blank">
     [16]
    </a>
   </sup>
  </span>
 </p>
 <p>
  For the Office Test method, create the Registry key used to execute it and set the permissions to "Read Control" to prevent easy access to the key without administrator permissions or requiring Privilege Escalation.
  <span class="scite-citeref-number" data-reference="Palo Alto Office Test Sofacy" id="scite-ref-13-a">
   <sup>
    <a aria-describedby="qtip-12" data-hasqtip="12" href="https://researchcenter.paloaltonetworks.com/2016/07/unit42-technical-walkthrough-office-test-persistence-method-used-in-recent-sofacy-attacks/" target="_blank">
     [13]
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
 <p>
  For the Outlook methods, blocking macros may be ineffective as the Visual Basic engine used for these features is separate from the macro scripting engine.
  <span class="scite-citeref-number" data-reference="SensePost Outlook Forms" id="scite-ref-11-a">
   <sup>
    <a aria-describedby="qtip-10" data-hasqtip="10" href="https://sensepost.com/blog/2017/outlook-forms-and-shells/" target="_blank">
     [11]
    </a>
   </sup>
  </span>
  Microsoft has released patches to try to address each issue. Ensure KB3191938 which blocks Outlook Visual Basic and displays a malicious code warning, KB4011091 which disables custom forms by default, and KB4011162 which removes the legacy Home Page feature, are applied to systems.
  <span class="scite-citeref-number" data-reference="SensePost Outlook Home Page" id="scite-ref-12-a">
   <sup>
    <a aria-describedby="qtip-11" data-hasqtip="11" href="https://sensepost.com/blog/2017/outlook-home-page-another-ruler-vector/" target="_blank">
     [12]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Many Office-related persistence mechanisms require changes to the Registry and for binaries, files, or scripts to be written to disk or existing files modified to include malicious scripts. Collect events related to Registry key creation and modification for keys that could be used for Office-based persistence.
  <span class="scite-citeref-number" data-reference="CrowdStrike Outlook Forms" id="scite-ref-17-a">
   <sup>
    <a aria-describedby="qtip-16" data-hasqtip="16" href="https://malware.news/t/using-outlook-forms-for-lateral-movement-and-persistence/13746" target="_blank">
     [17]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Outlook Today Home Page" id="scite-ref-18-a">
   <sup>
    <a aria-describedby="qtip-17" data-hasqtip="17" href="https://medium.com/@bwtech789/outlook-today-homepage-persistence-33ea9b505943" target="_blank">
     [18]
    </a>
   </sup>
  </span>
  Modification to base templated, like Normal.dotm, should also be investigated since the base templates should likely not contain VBA macros. Changes to the Office macro security settings should also be investigated.
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
 <p>
  For the Outlook rules and forms methods, Microsoft has released a PowerShell script to safely gather mail forwarding rules and custom forms in your mail environment as well as steps to interpret the output.
  <span class="scite-citeref-number" data-reference="Microsoft Detect Outlook Forms" id="scite-ref-19-a">
   <sup>
    <a aria-describedby="qtip-18" data-hasqtip="18" href="https://docs.microsoft.com/en-us/office365/securitycompliance/detect-and-remediate-outlook-rules-forms-attack" target="_blank">
     [19]
    </a>
   </sup>
  </span>
  SensePost, whose tool
  <a href="https://attack.mitre.org/software/S0358">
   Ruler
  </a>
  can be used to carry out malicious rules, forms, and Home Page attacks, has released a tool to detect Ruler usage.
  <span class="scite-citeref-number" data-reference="SensePost NotRuler" id="scite-ref-20-a">
   <sup>
    <a aria-describedby="qtip-19" data-hasqtip="19" href="https://github.com/sensepost/notruler" target="_blank">
     [20]
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
       <a class="external text" href="https://summit.fireeye.com/content/dam/fireeye-www/summit/cds-2018/presentations/cds18-technical-s03-youve-got-mail.pdf" name="scite-8" rel="nofollow" target="_blank">
        Caban, D. and Hirani, M. (2018, October 3). You’ve Got Mail! Enterprise Email Compromise. Retrieved April 22, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/sensepost/ruler" name="scite-9" rel="nofollow" target="_blank">
        SensePost. (2016, August 18). Ruler: A tool to abuse Exchange services. Retrieved February 4, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://silentbreaksecurity.com/malicious-outlook-rules/" name="scite-10" rel="nofollow" target="_blank">
        Landers, N. (2015, December 4). Malicious Outlook Rules. Retrieved February 4, 2019.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="11.0">
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://sensepost.com/blog/2017/outlook-forms-and-shells/" name="scite-11" rel="nofollow" target="_blank">
        Stalmans, E. (2017, April 28). Outlook Forms and Shells. Retrieved February 4, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://sensepost.com/blog/2017/outlook-home-page-another-ruler-vector/" name="scite-12" rel="nofollow" target="_blank">
        Stalmans, E. (2017, October 11). Outlook Home Page – Another Ruler Vector. Retrieved February 4, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2016/07/unit42-technical-walkthrough-office-test-persistence-method-used-in-recent-sofacy-attacks/" name="scite-13" rel="nofollow" target="_blank">
        Falcone, R. (2016, July 20). Technical Walkthrough: Office Test Persistence Method Used In Recent Sofacy Attacks. Retrieved July 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cybereason.com/blog/operation-cobalt-kitty-apt" name="scite-14" rel="nofollow" target="_blank">
        Dahan, A. (2017, May 24). OPERATION COBALT KITTY: A LARGE-SCALE APT IN ASIA CARRIED OUT BY THE OCEANLOTUS GROUP. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://cdn2.hubspot.net/hubfs/3354902/Cybereason%20Labs%20Analysis%20Operation%20Cobalt%20Kitty.pdf" name="scite-15" rel="nofollow" target="_blank">
        Dahan, A. (2017). Operation Cobalt Kitty. Retrieved December 27, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://blogs.technet.microsoft.com/mmpc/2016/03/22/new-feature-in-office-2016-can-block-macros-and-help-prevent-infection/" name="scite-16" rel="nofollow" target="_blank">
        Microsoft Malware Protection Center. (2016, March 22). New feature in Office 2016 can block macros and help prevent infection. Retrieved July 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://malware.news/t/using-outlook-forms-for-lateral-movement-and-persistence/13746" name="scite-17" rel="nofollow" target="_blank">
        Parisi, T., et al. (2017, July). Using Outlook Forms for Lateral Movement and Persistence. Retrieved February 5, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://medium.com/@bwtech789/outlook-today-homepage-persistence-33ea9b505943" name="scite-18" rel="nofollow" target="_blank">
        Soutcast. (2018, September 14). Outlook Today Homepage Persistence. Retrieved February 5, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/en-us/office365/securitycompliance/detect-and-remediate-outlook-rules-forms-attack" name="scite-19" rel="nofollow" target="_blank">
        Fox, C., Vangel, D. (2018, April 22). Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365. Retrieved February 4, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/sensepost/notruler" name="scite-20" rel="nofollow" target="_blank">
        SensePost. (2017, September 21). NotRuler - The opposite of Ruler, provides blue teams with the ability to detect Ruler usage against Exchange. Retrieved February 4, 2019.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
