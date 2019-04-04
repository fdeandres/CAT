<div class="container-fluid">
 <h1>
  Credentials in Registry
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    The Windows Registry stores configuration information that can be used by the system or other programs. Adversaries may query the Registry looking for credentials and passwords that have been stored for use by other programs or services. Sometimes these credentials are used for automatic logons.
   </p>
   <p>
    Example commands to find Registry keys related to password information:
    <span class="scite-citeref-number" data-reference="Pentestlab Stored Credentials" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://pentestlab.blog/2017/04/19/stored-credentials/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <ul>
    <li>
     Local Machine Hive:
     <code>
      reg query HKLM /f password /t REG_SZ /s
     </code>
    </li>
    <li>
     Current User Hive:
     <code>
      reg query HKCU /f password /t REG_SZ /s
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
      : T1214
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
      : Credential Access
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
      Windows Registry, Process command-line parameters, Process monitoring
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
      Sudhanshu Chauhan, @Sudhanshu_C
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
     <a href="https://attack.mitre.org/software/S0194">
      PowerSploit
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0194">
       PowerSploit
      </a>
      has several modules that search the Windows Registry for stored credentials:
      <code>
       Get-UnattendedInstallFile
      </code>
      ,
      <code>
       Get-Webconfig
      </code>
      ,
      <code>
       Get-ApplicationHost
      </code>
      ,
      <code>
       Get-SiteListPassword
      </code>
      ,
      <code>
       Get-CachedGPPPassword
      </code>
      , and
      <code>
       Get-RegistryAutoLogon
      </code>
      .
      <span class="scite-citeref-number" data-reference="Pentestlab Stored Credentials" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://pentestlab.blog/2017/04/19/stored-credentials/" target="_blank">
         [1]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0075">
      Reg
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0075">
       Reg
      </a>
      may be used to find credentials in the Windows Registry.
      <span class="scite-citeref-number" data-reference="Pentestlab Stored Credentials" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://pentestlab.blog/2017/04/19/stored-credentials/" target="_blank">
         [1]
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
  Do not store credentials within the Registry. Proactively search for credentials within Registry keys and attempt to remediate the risk. If necessary software must store credentials, then ensure those accounts have limited permissions so they cannot be abused if obtained by an adversary.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor processes for applications that can be used to query the Registry, such as
  <a href="https://attack.mitre.org/software/S0075">
   Reg
  </a>
  , and collect command parameters that may indicate credentials are being searched. Correlate activity with related suspicious behavior that may indicate an active intrusion to reduce false positives.
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
       <a class="external text" href="https://pentestlab.blog/2017/04/19/stored-credentials/" name="scite-1" rel="nofollow" target="_blank">
        netbiosX. (2017, April 19). Stored Credentials. Retrieved April 6, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
  </div>
 </div>
</div>
