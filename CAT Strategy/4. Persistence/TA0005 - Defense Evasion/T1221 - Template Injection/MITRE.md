<div class="container-fluid">
 <h1>
  Template Injection
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Microsoft’s Open Office XML (OOXML) specification defines an XML-based format for Office documents (.docx, xlsx, .pptx) to replace older binary formats (.doc, .xls, .ppt). OOXML files are packed together ZIP archives compromised of various XML files, referred to as parts, containing properties that collectively define how a document is rendered.
    <span class="scite-citeref-number" data-reference="Microsoft Open XML July 2017" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa338205(v=office.12)" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Properties within parts may reference shared public resources accessed via online URLs. For example, template properties reference a file, serving as a pre-formatted document blueprint, that is fetched when the document is loaded.
   </p>
   <p>
    Adversaries may abuse this technology to initially conceal malicious code to be executed via documents (i.e.
    <a href="https://attack.mitre.org/techniques/T1064">
     Scripting
    </a>
    ). Template references injected into a document may enable malicious payloads to be fetched and executed when the document is loaded. These documents can be delivered via other techniques such as
    <a href="https://attack.mitre.org/techniques/T1193">
     Spearphishing Attachment
    </a>
    and/or
    <a href="https://attack.mitre.org/techniques/T1080">
     Taint Shared Content
    </a>
    and may evade static detections since no typical indicators (VBA macro, script, etc.) are present until after the malicious payload is fetched.
    <span class="scite-citeref-number" data-reference="Redxorblue Remote Template Injection" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="http://blog.redxorblue.com/2018/07/executing-macros-from-docx-with-remote.html" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    Examples have been seen in the wild where template injection was used to load malicious code containing an exploit.
    <span class="scite-citeref-number" data-reference="MalwareBytes Template Injection OCT 2017" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://blog.malwarebytes.com/threat-analysis/2017/10/decoy-microsoft-word-document-delivers-malware-through-rat/" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    This technique may also enable
    <a href="https://attack.mitre.org/techniques/T1187">
     Forced Authentication
    </a>
    by injecting a SMB/HTTPS (or other credential prompting) URL and triggering an authentication attempt.
    <span class="scite-citeref-number" data-reference="Anomali Template Injection MAR 2018" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://forum.anomali.com/t/credential-harvesting-and-malicious-file-delivery-using-microsoft-office-template-injection/2104" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Talos Template Injection July 2017" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://blog.talosintelligence.com/2017/07/template-injection.html" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="ryhanson phishery SEPT 2016" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://github.com/ryhanson/phishery" target="_blank">
       [6]
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
      : T1221
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
      Anti-virus, Email gateway, Network intrusion detection system, Web logs
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
      Static File Analysis
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
      Patrick Campbell, @pjcampbe11
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
     <a href="https://attack.mitre.org/groups/G0079">
      DarkHydrus
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0079">
       DarkHydrus
      </a>
      used an open-source tool, Phishery, to inject malicious remote template URLs into Microsoft Word documents and then sent them to victims to enable
      <a href="https://attack.mitre.org/techniques/T1187">
       Forced Authentication
      </a>
      .
      <span class="scite-citeref-number" data-reference="Unit 42 Phishery Aug 2018" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://researchcenter.paloaltonetworks.com/2018/08/unit42-darkhydrus-uses-phishery-harvest-credentials-middle-east/" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0074">
      Dragonfly 2.0
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0074">
       Dragonfly 2.0
      </a>
      has injected SMB URLs into malicious Word spearphishing attachments to initiate
      <a href="https://attack.mitre.org/techniques/T1187">
       Forced Authentication
      </a>
      .
      <span class="scite-citeref-number" data-reference="US-CERT TA18-074A" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" target="_blank">
         [8]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT APT Energy Oct 2017" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" target="_blank">
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
  Consider disabling Microsoft Office macros/active content to prevent the execution of malicious payloads in documents
  <span class="scite-citeref-number" data-reference="Microsoft Disable Macros" id="scite-ref-10-a">
   <sup>
    <a aria-describedby="qtip-9" data-hasqtip="9" href="https://support.office.com/article/enable-or-disable-macros-in-office-files-12b036fd-d140-4e74-b45e-16fed1a7e5c6" target="_blank">
     [10]
    </a>
   </sup>
  </span>
  , though this setting may not mitigate the
  <a href="https://attack.mitre.org/techniques/T1187">
   Forced Authentication
  </a>
  use for this technique.
 </p>
 <p>
  Because this technique involves user interaction on the endpoint, it's difficult to fully mitigate. However, there are potential mitigations including training users to identify social engineering techniques and spearphishing emails. Network/Host intrusion prevention systems, antivirus, and detonation chambers can be employed to prevent documents from fetching and/or executing malicious payloads.
  <span class="scite-citeref-number" data-reference="Anomali Template Injection MAR 2018" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="https://forum.anomali.com/t/credential-harvesting-and-malicious-file-delivery-using-microsoft-office-template-injection/2104" target="_blank">
     [4]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Analyze process behavior to determine if an Office application is performing actions, such as opening network connections, reading files, spawning abnormal child processes (ex:
  <a href="https://attack.mitre.org/techniques/T1086">
   PowerShell
  </a>
  ), or other suspicious actions that could relate to post-compromise behavior.
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
       <a class="external text" href="https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa338205(v=office.12)" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (2014, July 9). Introducing the Office (2007) Open XML File Formats. Retrieved July 20, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.redxorblue.com/2018/07/executing-macros-from-docx-with-remote.html" name="scite-2" rel="nofollow" target="_blank">
        Hawkins, J. (2018, July 18). Executing Macros From a DOCX With Remote Template Injection. Retrieved October 12, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.malwarebytes.com/threat-analysis/2017/10/decoy-microsoft-word-document-delivers-malware-through-rat/" name="scite-3" rel="nofollow" target="_blank">
        Segura, J. (2017, October 13). Decoy Microsoft Word document delivers malware through a RAT. Retrieved July 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://forum.anomali.com/t/credential-harvesting-and-malicious-file-delivery-using-microsoft-office-template-injection/2104" name="scite-4" rel="nofollow" target="_blank">
        Intel_Acquisition_Team. (2018, March 1). Credential Harvesting and Malicious File Delivery using Microsoft Office Template Injection. Retrieved July 20, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2017/07/template-injection.html" name="scite-5" rel="nofollow" target="_blank">
        Baird, S. et al.. (2017, July 7). Attack on Critical Infrastructure Leverages Template Injection. Retrieved July 21, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="6.0">
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/ryhanson/phishery" name="scite-6" rel="nofollow" target="_blank">
        Hanson, R. (2016, September 24). phishery. Retrieved July 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/08/unit42-darkhydrus-uses-phishery-harvest-credentials-middle-east/" name="scite-7" rel="nofollow" target="_blank">
        Falcone, R. (2018, August 07). DarkHydrus Uses Phishery to Harvest Credentials in the Middle East. Retrieved August 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" name="scite-8" rel="nofollow" target="_blank">
        US-CERT. (2018, March 16). Alert (TA18-074A): Russian Government Cyber Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" name="scite-9" rel="nofollow" target="_blank">
        US-CERT. (2017, October 20). Alert (TA17-293A): Advanced Persistent Threat Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved November 2, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://support.office.com/article/enable-or-disable-macros-in-office-files-12b036fd-d140-4e74-b45e-16fed1a7e5c6" name="scite-10" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Enable or disable macros in Office files. Retrieved September 13, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
