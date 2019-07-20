<div class="container-fluid">
 <h1>
  InstallUtil
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    InstallUtil is a command-line utility that allows for installation and uninstallation of resources by executing specific installer components specified in .NET binaries.
    <span class="scite-citeref-number" data-reference="MSDN InstallUtil" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://msdn.microsoft.com/en-us/library/50614e95.aspx" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    InstallUtil is located in the .NET directories on a Windows system:
    <code>
     C:\Windows\Microsoft.NET\Framework\v
     <version>
      \InstallUtil.exe
     </version>
    </code>
    and
    <code>
     C:\Windows\Microsoft.NET\Framework64\v
     <version>
      \InstallUtil.exe
     </version>
    </code>
    . InstallUtil.exe is digitally signed by Microsoft.
   </p>
   <p>
    Adversaries may use InstallUtil to proxy execution of code through a trusted Windows utility. InstallUtil may also be used to bypass process whitelisting through use of attributes within the binary that execute the class decorated with the attribute
    <code>
     [System.ComponentModel.RunInstaller(true)]
    </code>
    .
    <span class="scite-citeref-number" data-reference="SubTee GitHub All The Things Application Whitelisting Bypass" id="scite-ref-2-a">
     <sup>
      [2]
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
      : T1118
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
      Process whitelisting, Digital Certificate Validation
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
      Casey Smith; Travis Smith, Tripwire
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
 <h2 class="pt-3" id="mitigation">
  Mitigation
 </h2>
 <p>
  InstallUtil may not be necessary within a given environment. Use application whitelisting configured to block execution of InstallUtil.exe if it is not required for a given system or network to prevent potential misuse by adversaries.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Use process monitoring to monitor the execution and arguments of InstallUtil.exe. Compare recent invocations of InstallUtil.exe with prior history of known good arguments and executed binaries to determine anomalous and potentially adversarial activity. Command arguments used before and after the InstallUtil.exe invocation may also be useful in determining the origin and purpose of the binary being executed.
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
       <a class="external text" href="https://msdn.microsoft.com/en-us/library/50614e95.aspx" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Installutil.exe (Installer Tool). Retrieved July 1, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="2.0">
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       Smith, C. (2016, August 17). Includes 5 Known Application Whitelisting/ Application Control Bypass Techniques in One File. Retrieved June 30, 2017.
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
