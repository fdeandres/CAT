<div class="container-fluid">
 <h1>
  Data from Information Repositories
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries may leverage information repositories to mine valuable information. Information repositories are tools that allow for storage of information, typically to facilitate collaboration or information sharing between users, and can store a wide variety of data that may aid adversaries in further objectives, or direct access to the target information.
   </p>
   <p>
    The following is a brief list of example information that may hold potential value to an adversary and may also be found on an information repository:
   </p>
   <ul>
    <li>
     Policies, procedures, and standards
    </li>
    <li>
     Physical / logical network diagrams
    </li>
    <li>
     System architecture diagrams
    </li>
    <li>
     Technical system documentation
    </li>
    <li>
     Testing / development credentials
    </li>
    <li>
     Work / project schedules
    </li>
    <li>
     Source code snippets
    </li>
    <li>
     Links to network shares and other internal resources
    </li>
   </ul>
   <p>
    Specific common information repositories include:
   </p>
   <h3>
    Microsoft SharePoint
   </h3>
   <p>
    Found in many enterprise networks and often used to store and share significant amounts of documentation.
   </p>
   <h3>
    Atlassian Confluence
   </h3>
   <p>
    Often found in development environments alongside Atlassian JIRA, Confluence is generally used to store development-related documentation.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1213
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
      : Collection
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Platform:
      </span>
      Linux, Windows, macOS
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
      Application logs, Authentication logs, Data loss prevention, Third-party application logs
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
      Milos Stojadinovic
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
      has collected information from Microsoft SharePoint services within target networks.
      <span class="scite-citeref-number" data-reference="RSAC 2015 Abu Dhabi Stefano Maccaglia" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://paper.seebug.org/papers/APT/APT_CyberCriminal_Campagin/2015/2015.11.04_Evolving_Threats/cct-w08_evolving-threats-dissection-of-a-cyber-espionage-attack.pdf" target="_blank">
         [1]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0004">
      Ke3chang
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0004">
       Ke3chang
      </a>
      used a SharePoint enumeration and data dumping tool known as spwebmember.
      <span class="scite-citeref-number" data-reference="NCC Group APT15 Alive and Strong" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0227">
      spwebmember
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0227">
       spwebmember
      </a>
      is used to enumerate and dump information from Microsoft SharePoint.
      <span class="scite-citeref-number" data-reference="NCC Group APT15 Alive and Strong" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/" target="_blank">
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
  To mitigate adversary access to information repositories for collection:
 </p>
 <ul>
  <li>
   Develop and publish policies that define acceptable information to be stored
  </li>
  <li>
   Appropriate implementation of access control mechanisms that include both authentication and appropriate authorization
  </li>
  <li>
   Enforce the principle of least-privilege
  </li>
  <li>
   Periodic privilege review of accounts
  </li>
  <li>
   Mitigate access to
   <a href="https://attack.mitre.org/techniques/T1078">
    Valid Accounts
   </a>
   that may be used to access repositories
  </li>
 </ul>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  As information repositories generally have a considerably large user base, detection of malicious use can be non-trivial. At minimum, access to information repositories performed by privileged users (for example, Active Directory Domain, Enterprise, or Schema Administrators) should be closely monitored and alerted upon, as these types of accounts should not generally used to access information repositories. If the capability exists, it may be of value to monitor and alert on users that are retrieving and viewing a large number of documents and pages; this behavior may be indicative of programmatic means being used to retrieve all data within the repository. In environments with high-maturity, it may be possible to leverage User-Behavioral Analytics (UBA) platforms to detect and alert on user based anomalies.
 </p>
 <p>
  The user access logging within Microsoft's SharePoint can be configured to report access to certain pages and documents.
  <span class="scite-citeref-number" data-reference="Microsoft SharePoint Logging" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="https://support.office.com/en-us/article/configure-audit-settings-for-a-site-collection-a9920c97-38c0-44f2-8bcb-4cf1e2ae22d2" target="_blank">
     [3]
    </a>
   </sup>
  </span>
  The user user access logging within Atlassian's Confluence can also be configured to report access to certain pages and documents through AccessLogFilter.
  <span class="scite-citeref-number" data-reference="Atlassian Confluence Logging" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="https://confluence.atlassian.com/confkb/how-to-enable-user-access-logging-182943.html" target="_blank">
     [4]
    </a>
   </sup>
  </span>
  Additional log storage and analysis infrastructure will likely be required for more robust detection capabilities.
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
       <a class="external text" href="https://paper.seebug.org/papers/APT/APT_CyberCriminal_Campagin/2015/2015.11.04_Evolving_Threats/cct-w08_evolving-threats-dissection-of-a-cyber-espionage-attack.pdf" name="scite-1" rel="nofollow" target="_blank">
        Maccaglia, S. (2015, November 4). Evolving Threats: dissection of a CyberEspionage attack. Retrieved April 4, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/" name="scite-2" rel="nofollow" target="_blank">
        Smallridge, R. (2018, March 10). APT15 is alive and strong: An analysis of RoyalCli and RoyalDNS. Retrieved April 4, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="3.0">
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://support.office.com/en-us/article/configure-audit-settings-for-a-site-collection-a9920c97-38c0-44f2-8bcb-4cf1e2ae22d2" name="scite-3" rel="nofollow" target="_blank">
        Microsoft. (2017, July 19). Configure audit settings for a site collection. Retrieved April 4, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://confluence.atlassian.com/confkb/how-to-enable-user-access-logging-182943.html" name="scite-4" rel="nofollow" target="_blank">
        Atlassian. (2018, January 9). How to Enable User Access Logging. Retrieved April 4, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
