<div class="container-fluid">
 <h1>
  Group Policy Modification
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries may modify Group Policy Objects (GPOs) to subvert the intended discretionary access controls for a domain, usually with the intention of escalating privileges on the domain.
   </p>
   <p>
    Group policy allows for centralized management of user and computer settings in Active Directory (AD). GPOs are containers for group policy settings made up of files stored within a predicable network path
    <code>
     \&lt;DOMAIN&gt;\SYSVOL\&lt;DOMAIN&gt;\Policies\
    </code>
    .
    <span class="scite-citeref-number" data-reference="TechNet Group Policy Basics" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://blogs.technet.microsoft.com/musings_of_a_technical_tam/2012/02/13/group-policy-basics-part-1-understanding-the-structure-of-a-group-policy-object/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="ADSecurity GPO Persistence 2016" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://adsecurity.org/?p=2716" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Like other objects in AD, GPOs have access controls associated with them. By default all user accounts in the domain have permission to read GPOs. It is possible to delegate GPO access control permissions, e.g. write access, to specific users or groups in the domain.
   </p>
   <p>
    Malicious GPO modifications can be used to implement
    <a href="https://attack.mitre.org/techniques/T1053">
     Scheduled Task
    </a>
    ,
    <a href="https://attack.mitre.org/techniques/T1089">
     Disabling Security Tools
    </a>
    ,
    <a href="https://attack.mitre.org/techniques/T1105">
     Remote File Copy
    </a>
    ,
    <a href="https://attack.mitre.org/techniques/T1136">
     Create Account
    </a>
    ,
    <a href="https://attack.mitre.org/techniques/T1035">
     Service Execution
    </a>
    and more.
    <span class="scite-citeref-number" data-reference="ADSecurity GPO Persistence 2016" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://adsecurity.org/?p=2716" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Wald0 Guide to GPOs" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://wald0.com/?p=179" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Harmj0y Abusing GPO Permissions" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="http://www.harmj0y.net/blog/redteaming/abusing-gpo-permissions/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Mandiant M Trends 2016" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.fireeye.com/content/dam/fireeye-www/current-threats/pdfs/rpt-mtrends-2016.pdf" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Microsoft Hacking Team Breach" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.microsoft.com/security/blog/2016/06/01/hacking-team-breach-a-cyber-jurassic-park/" target="_blank">
       [6]
      </a>
     </sup>
    </span>
    Since GPOs can control so many user and machine settings in the AD environment, there are a great number of potential attacks that can stem from this GPO abuse.
    <span class="scite-citeref-number" data-reference="Wald0 Guide to GPOs" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://wald0.com/?p=179" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    Publicly available scripts such as
    <code>
     New-GPOImmediateTask
    </code>
    can be leveraged to automate the creation of a malicious
    <a href="https://attack.mitre.org/techniques/T1053">
     Scheduled Task
    </a>
    by modifying GPO settings, in this case modifying
    <code>
     &lt;GPO_PATH&gt;\Machine\Preferences\ScheduledTasks\ScheduledTasks.xml
    </code>
    .
    <span class="scite-citeref-number" data-reference="Wald0 Guide to GPOs" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://wald0.com/?p=179" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Harmj0y Abusing GPO Permissions" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="http://www.harmj0y.net/blog/redteaming/abusing-gpo-permissions/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    In some cases an adversary might modify specific user rights like SeEnableDelegationPrivilege, set in
    <code>
     &lt;GPO_PATH&gt;\MACHINE\Microsoft\Windows NT\SecEdit\GptTmpl.inf
    </code>
    , to achieve a subtle AD backdoor with complete control of the domain because the user account under the adversary's control would then be able to modify GPOs.
    <span class="scite-citeref-number" data-reference="Harmj0y SeEnableDelegationPrivilege Right" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="http://www.harmj0y.net/blog/activedirectory/the-most-dangerous-user-right-you-probably-have-never-heard-of/" target="_blank">
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
      : T1484
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
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Permissions Required:
      </span>
      Administrator, User
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
      Windows event logs
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
      System access controls, File system access controls
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
      Itamar Mizrahi; Tristan Bennett, Seamless Intelligence
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
     <a href="https://attack.mitre.org/software/S0363">
      Empire
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0363">
       Empire
      </a>
      can use
      <code>
       New-GPOImmediateTask
      </code>
      to modify a GPO that will install and execute a malicious
      <a href="https://attack.mitre.org/techniques/T1053">
       Scheduled Task
      </a>
      .
      <span class="scite-citeref-number" data-reference="Github PowerShell Empire" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://github.com/PowerShellEmpire/Empire" target="_blank">
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
  Identify and correct GPO permissions abuse opportunities (ex: GPO modification privileges) using auditing tools such as Bloodhound (version 1.5.1 and later)
  <span class="scite-citeref-number" data-reference="GitHub Bloodhound" id="scite-ref-9-a">
   <sup>
    <a aria-describedby="qtip-8" data-hasqtip="8" href="https://github.com/BloodHoundAD/BloodHound" target="_blank">
     [9]
    </a>
   </sup>
  </span>
  .
 </p>
 <p>
  Consider implementing WMI and security filtering to further tailor which users and computers a GPO will apply to.
  <span class="scite-citeref-number" data-reference="Wald0 Guide to GPOs" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="https://wald0.com/?p=179" target="_blank">
     [3]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Microsoft WMI Filters" id="scite-ref-10-a">
   <sup>
    <a aria-describedby="qtip-9" data-hasqtip="9" href="https://blogs.technet.microsoft.com/askds/2008/09/11/fun-with-wmi-filters-in-group-policy/" target="_blank">
     [10]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Microsoft GPO Security Filtering" id="scite-ref-11-a">
   <sup>
    <a aria-describedby="qtip-10" data-hasqtip="10" href="https://docs.microsoft.com/en-us/previous-versions/windows/desktop/Policy/filtering-the-scope-of-a-gpo" target="_blank">
     [11]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  It is possible to detect GPO modifications by monitoring directory service changes using Windows event logs. Several events may be logged for such GPO modifications, including:
  <em>
   Event ID 5136 - A directory service object was modified
  </em>
  Event ID 5137 - A directory service object was created
  <em>
   Event ID 5138 - A directory service object was undeleted
  </em>
  Event ID 5139 - A directory service object was moved* Event ID 5141 - A directory service object was deleted
 </p>
 <p>
  GPO abuse will often be accompanied by some other behavior such as
  <a href="https://attack.mitre.org/techniques/T1053">
   Scheduled Task
  </a>
  , which will have events associated with it to detect. Subsequent permission value modifications, like those to SeEnableDelegationPrivilege, can also be searched for in events associated with privileges assigned to new logons (Event ID 4672) and assignment of user rights (Event ID 4704).
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
       <a class="external text" href="https://blogs.technet.microsoft.com/musings_of_a_technical_tam/2012/02/13/group-policy-basics-part-1-understanding-the-structure-of-a-group-policy-object/" name="scite-1" rel="nofollow" target="_blank">
        srachui. (2012, February 13). Group Policy Basics – Part 1: Understanding the Structure of a Group Policy Object. Retrieved March 5, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://adsecurity.org/?p=2716" name="scite-2" rel="nofollow" target="_blank">
        Metcalf, S. (2016, March 14). Sneaky Active Directory Persistence #17: Group Policy. Retrieved March 5, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://wald0.com/?p=179" name="scite-3" rel="nofollow" target="_blank">
        Robbins, A. (2018, April 2). A Red Teamer’s Guide to GPOs and OUs. Retrieved March 5, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.harmj0y.net/blog/redteaming/abusing-gpo-permissions/" name="scite-4" rel="nofollow" target="_blank">
        Schroeder, W. (2016, March 17). Abusing GPO Permissions. Retrieved March 5, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/content/dam/fireeye-www/current-threats/pdfs/rpt-mtrends-2016.pdf" name="scite-5" rel="nofollow" target="_blank">
        Mandiant. (2016, February 25). Mandiant M-Trends 2016. Retrieved March 5, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.microsoft.com/security/blog/2016/06/01/hacking-team-breach-a-cyber-jurassic-park/" name="scite-6" rel="nofollow" target="_blank">
        Microsoft Secure Team. (2016, June 1). Hacking Team Breach: A Cyber Jurassic Park. Retrieved March 5, 2019.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="7.5">
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.harmj0y.net/blog/activedirectory/the-most-dangerous-user-right-you-probably-have-never-heard-of/" name="scite-7" rel="nofollow" target="_blank">
        Schroeder, W. (2017, January 10). The Most Dangerous User Right You (Probably) Have Never Heard Of. Retrieved March 5, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellEmpire/Empire" name="scite-8" rel="nofollow" target="_blank">
        Schroeder, W., Warner, J., Nelson, M. (n.d.). Github PowerShellEmpire. Retrieved April 28, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/BloodHoundAD/BloodHound" name="scite-9" rel="nofollow" target="_blank">
        Robbins, A., Vazarkar, R., and Schroeder, W. (2016, April 17). Bloodhound: Six Degrees of Domain Admin. Retrieved March 5, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://blogs.technet.microsoft.com/askds/2008/09/11/fun-with-wmi-filters-in-group-policy/" name="scite-10" rel="nofollow" target="_blank">
        Microsoft. (2008, September 11). Fun with WMI Filters in Group Policy. Retrieved March 13, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/en-us/previous-versions/windows/desktop/Policy/filtering-the-scope-of-a-gpo" name="scite-11" rel="nofollow" target="_blank">
        Microsoft. (2018, May 30). Filtering the Scope of a GPO. Retrieved March 13, 2019.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
