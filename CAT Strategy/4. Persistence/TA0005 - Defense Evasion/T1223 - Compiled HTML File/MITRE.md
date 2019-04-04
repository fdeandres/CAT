<div class="container-fluid">
 <h1>
  Compiled HTML File
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Compiled HTML files (.chm) are commonly distributed as part of the Microsoft HTML Help system. CHM files are compressed compilations of various content such as HTML documents, images, and scripting/web related programming languages such VBA, JScript, Java, and ActiveX.
    <span class="scite-citeref-number" data-reference="Microsoft HTML Help May 2018" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://docs.microsoft.com/previous-versions/windows/desktop/htmlhelp/microsoft-html-help-1-4-sdk" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    CHM content is displayed using underlying components of the Internet Explorer browser
    <span class="scite-citeref-number" data-reference="Microsoft HTML Help ActiveX" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://msdn.microsoft.com/windows/desktop/ms644670" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    loaded by the HTML Help executable program (hh.exe).
    <span class="scite-citeref-number" data-reference="Microsoft HTML Help Executable Program" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://msdn.microsoft.com/windows/desktop/ms524405" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries may abuse this technology to conceal malicious code. A custom CHM file containing embedded payloads could be delivered to a victim then triggered by
    <a href="https://attack.mitre.org/techniques/T1204">
     User Execution
    </a>
    . CHM execution may also bypass application whitelisting on older and/or unpatched systems that do not account for execution of binaries through hh.exe.
    <span class="scite-citeref-number" data-reference="MsitPros CHM Aug 2017" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://msitpros.com/?p=3909" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Microsoft CVE-2017-8625 Aug 2017" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/CVE-2017-8625" target="_blank">
       [5]
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
      : T1223
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
      File monitoring, Process monitoring, Process command-line parameters
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
      Rahmat Nurfauzi, @infosecn1nja, PT Xynexis International
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
     <a href="https://attack.mitre.org/groups/G0070">
      Dark Caracal
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0070">
       Dark Caracal
      </a>
      leveraged a compiled HTML file that contained a command to download and run an executable.
      <span class="scite-citeref-number" data-reference="Lookout Dark Caracal Jan 2018" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://info.lookout.com/rs/051-ESQ-475/images/Lookout_Dark-Caracal_srr_20180118_us_v.1.0.pdf" target="_blank">
         [6]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0032">
      Lazarus Group
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0032">
       Lazarus Group
      </a>
      has used CHM files to move concealed payloads as part of.
      <span class="scite-citeref-number" data-reference="Kaspersky Lazarus Under The Hood APR 2017" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07180244/Lazarus_Under_The_Hood_PDF_final.pdf" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0049">
      OilRig
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0049">
       OilRig
      </a>
      has used a CHM payload to load and execute another malicious file once delivered to a victim.
      <span class="scite-citeref-number" data-reference="Palo Alto OilRig May 2016" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="http://researchcenter.paloaltonetworks.com/2016/05/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/" target="_blank">
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
  Consider blocking download/transfer and execution of potentially uncommon file types known to be used in adversary campaigns, such as CHM files.
  <span class="scite-citeref-number" data-reference="PaloAlto Preventing Opportunistic Attacks Apr 2016" id="scite-ref-9-a">
   <sup>
    <a aria-describedby="qtip-8" data-hasqtip="8" href="https://live.paloaltonetworks.com/t5/Ignite-2016-Blog/Breakout-Recap-Cybersecurity-Best-Practices-Part-1-Preventing/ba-p/75913" target="_blank">
     [9]
    </a>
   </sup>
  </span>
  Also consider using application whitelisting to prevent execution of hh.exe if it is not required for a given system or network to prevent potential misuse by adversaries.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor and analyze the execution and arguments of hh.exe.
  <span class="scite-citeref-number" data-reference="MsitPros CHM Aug 2017" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="https://msitpros.com/?p=3909" target="_blank">
     [4]
    </a>
   </sup>
  </span>
  Compare recent invocations of hh.exe with prior history of known good arguments to determine anomalous and potentially adversarial activity (ex: obfuscated and/or malicious commands). Non-standard process execution trees may also indicate suspicious or malicious behavior, such as if hh.exe is the parent process for suspicious processes and activity relating to other adversarial techniques.
 </p>
 <p>
  Monitor presence and use of CHM files, especially if they are not typically used within an environment.
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
       <a class="external text" href="https://docs.microsoft.com/previous-versions/windows/desktop/htmlhelp/microsoft-html-help-1-4-sdk" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (2018, May 30). Microsoft HTML Help 1.4. Retrieved October 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/windows/desktop/ms644670" name="scite-2" rel="nofollow" target="_blank">
        Microsoft. (n.d.). HTML Help ActiveX Control Overview. Retrieved October 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/windows/desktop/ms524405" name="scite-3" rel="nofollow" target="_blank">
        Microsoft. (n.d.). About the HTML Help Executable Program. Retrieved October 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://msitpros.com/?p=3909" name="scite-4" rel="nofollow" target="_blank">
        Moe, O. (2017, August 13). Bypassing Device guard UMCI using CHM – CVE-2017-8625. Retrieved October 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/CVE-2017-8625" name="scite-5" rel="nofollow" target="_blank">
        Microsoft. (2017, August 8). CVE-2017-8625 - Internet Explorer Security Feature Bypass Vulnerability. Retrieved October 3, 2018.
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
       <a class="external text" href="https://info.lookout.com/rs/051-ESQ-475/images/Lookout_Dark-Caracal_srr_20180118_us_v.1.0.pdf" name="scite-6" rel="nofollow" target="_blank">
        Blaich, A., et al. (2018, January 18). Dark Caracal: Cyber-espionage at a Global Scale. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07180244/Lazarus_Under_The_Hood_PDF_final.pdf" name="scite-7" rel="nofollow" target="_blank">
        GReAT. (2017, April 3). Lazarus Under the Hood. Retrieved October 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/05/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/" name="scite-8" rel="nofollow" target="_blank">
        Falcone, R. and Lee, B.. (2016, May 26). The OilRig Campaign: Attacks on Saudi Arabian Organizations Deliver Helminth Backdoor. Retrieved May 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://live.paloaltonetworks.com/t5/Ignite-2016-Blog/Breakout-Recap-Cybersecurity-Best-Practices-Part-1-Preventing/ba-p/75913" name="scite-9" rel="nofollow" target="_blank">
        Kiwi. (2016, April 6). Breakout Recap: Cybersecurity Best Practices Part 1 - Preventing Opportunistic Attacks. Retrieved October 3, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
