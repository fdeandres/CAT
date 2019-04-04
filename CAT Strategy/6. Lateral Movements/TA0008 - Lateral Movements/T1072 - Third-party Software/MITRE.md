<div class="container-fluid">
 <h1>
  Third-party Software
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Third-party applications and software deployment systems may be in use in the network environment for administration purposes (e.g., SCCM, VNC, HBSS, Altiris, etc.). If an adversary gains access to these systems, then they may be able to execute code.
   </p>
   <p>
    Adversaries may gain access to and use third-party application deployment systems installed within an enterprise network. Access to a network-wide or enterprise-wide software deployment system enables an adversary to have remote code execution on all systems that are connected to such a system. The access may be used to laterally move to systems, gather information, or cause a specific effect, such as wiping the hard drives on all endpoints.
   </p>
   <p>
    The permissions required for this action vary by system configuration; local credentials may be sufficient with direct access to the deployment server, or specific domain credentials may be required. However, the system may require an administrative account to log in or to perform software deployment.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1072
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
      : Execution, Lateral Movement
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Platform:
      </span>
      Linux, macOS, Windows
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Permissions Required:
      </span>
      User, Administrator, SYSTEM
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
      File monitoring, Third-party application logs, Windows Registry, Process monitoring, Process use of network, Binary file metadata
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Supports Remote:
      </span>
      Yes
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
     <a href="https://attack.mitre.org/groups/G0028">
      Threat Group-1314
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0028">
       Threat Group-1314
      </a>
      actors used a victim's endpoint management platform, Altiris, for lateral movement.
      <span class="scite-citeref-number" data-reference="Dell TG-1314" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="http://www.secureworks.com/resources/blog/living-off-the-land/" target="_blank">
         [1]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0041">
      Wiper
     </a>
    </td>
    <td>
     <p>
      It is believed that a patch management system for an anti-virus product commonly installed among targeted companies was used to distribute the
      <a href="https://attack.mitre.org/software/S0041">
       Wiper
      </a>
      malware.
      <span class="scite-citeref-number" data-reference="Dell Wiper" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="http://www.secureworks.com/cyber-threat-intelligence/threats/wiper-malware-analysis-attacking-korean-financial-sector/" target="_blank">
         [2]
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
  Evaluate the security of third-party software that could be used to deploy or execute programs. Ensure that access to management systems for deployment systems is limited, monitored, and secure. Have a strict approval policy for use of deployment systems.
 </p>
 <p>
  Grant access to application deployment systems only to a limited number of authorized administrators. Ensure proper system and access isolation for critical network systems through use of firewalls, account privilege separation, group policy, and multifactor authentication. Verify that account credentials that may be used to access deployment systems are unique and not used throughout the enterprise network. Patch deployment systems regularly to prevent potential remote access through
  <a href="https://attack.mitre.org/techniques/T1068">
   Exploitation of Vulnerability
  </a>
  .
 </p>
 <p>
  If the application deployment system can be configured to deploy only signed binaries, then ensure that the trusted signing certificates are not co-located with the application deployment system and are instead located on a system that cannot be accessed remotely or to which remote access is tightly controlled.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Detection methods will vary depending on the type of third-party software or system and how it is typically used.
 </p>
 <p>
  The same investigation process can be applied here as with other potentially malicious activities where the distribution vector is initially unknown but the resulting activity follows a discernible pattern. Analyze the process execution trees, historical activities from the third-party application (such as what types of files are usually pushed), and the resulting activities or events from the file/binary/script pushed to systems.
 </p>
 <p>
  Often these third-party applications will have logs of their own that can be collected and correlated with other data from the environment. Audit software deployment logs and look for suspicious or unauthorized activity. A system not typically used to push software to clients that suddenly is used for such a task outside of a known admin function may be suspicious.
 </p>
 <p>
  Perform application deployment at regular times so that irregular deployment activity stands out. Monitor process activity that does not correlate to known good software. Monitor account login activity on the deployment system.
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
       <a class="external text" href="http://www.secureworks.com/resources/blog/living-off-the-land/" name="scite-1" rel="nofollow" target="_blank">
        Dell SecureWorks Counter Threat Unit Special Operations Team. (2015, May 28). Living off the Land. Retrieved January 26, 2016.
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
       <a class="external text" href="http://www.secureworks.com/cyber-threat-intelligence/threats/wiper-malware-analysis-attacking-korean-financial-sector/" name="scite-2" rel="nofollow" target="_blank">
        Dell SecureWorks. (2013, March 21). Wiper Malware Analysis Attacking Korean Financial Sector. Retrieved May 13, 2015.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
