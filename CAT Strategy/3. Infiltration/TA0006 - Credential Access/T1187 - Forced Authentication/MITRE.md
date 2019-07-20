<div class="container-fluid">
 <h1>
  Forced Authentication
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    The Server Message Block (SMB) protocol is commonly used in Windows networks for authentication and communication between systems for access to resources and file sharing. When a Windows system attempts to connect to an SMB resource it will automatically attempt to authenticate and send credential information for the current user to the remote system.
    <span class="scite-citeref-number" data-reference="Wikipedia Server Message Block" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://en.wikipedia.org/wiki/Server_Message_Block" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    This behavior is typical in enterprise environments so that users do not need to enter credentials to access network resources. Web Distributed Authoring and Versioning (WebDAV) is typically used by Windows systems as a backup protocol when SMB is blocked or fails. WebDAV is an extension of HTTP and will typically operate over TCP ports 80 and 443.
    <span class="scite-citeref-number" data-reference="Didier Stevens WebDAV Traffic" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://blog.didierstevens.com/2017/11/13/webdav-traffic-to-malicious-sites/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Microsoft Managing WebDAV Security" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.microsoft.com/technet/prodtechnol/WindowsServer2003/Library/IIS/4beddb35-0cba-424c-8b9b-a5832ad8e208.mspx" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries may take advantage of this behavior to gain access to user account hashes through forced SMB authentication. An adversary can send an attachment to a user through spearphishing that contains a resource link to an external server controlled by the adversary (i.e.
    <a href="https://attack.mitre.org/techniques/T1221">
     Template Injection
    </a>
    ), or place a specially crafted file on navigation path for privileged accounts (e.g. .SCF file placed on desktop) or on a publicly accessible share to be accessed by victim(s). When the user's system accesses the untrusted resource it will attempt authentication and send information including the user's hashed credentials over SMB to the adversary controlled server.
    <span class="scite-citeref-number" data-reference="GitHub Hashjacking" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://github.com/hob0/hashjacking" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    With access to the credential hash, an adversary can perform off-line
    <a href="https://attack.mitre.org/techniques/T1110">
     Brute Force
    </a>
    cracking to gain access to plaintext credentials, or reuse it for
    <a href="https://attack.mitre.org/techniques/T1075">
     Pass the Hash
    </a>
    .
    <span class="scite-citeref-number" data-reference="Cylance Redirect to SMB" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.cylance.com/content/dam/cylance/pdfs/white_papers/RedirectToSMB.pdf" target="_blank">
       [5]
      </a>
     </sup>
    </span>
   </p>
   <p>
    There are several different ways this can occur.
    <span class="scite-citeref-number" data-reference="Osanda Stealing NetNTLM Hashes" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://osandamalith.com/2017/03/24/places-of-interest-in-stealing-netntlm-hashes/" target="_blank">
       [6]
      </a>
     </sup>
    </span>
    Some specifics from in-the-wild use include:
   </p>
   <ul>
    <li>
     A spearphishing attachment containing a document with a resource that is automatically loaded when the document is opened (i.e.
     <a href="https://attack.mitre.org/techniques/T1221">
      Template Injection
     </a>
     ). The document can include, for example, a request similar to
     <code>
      file[:]//[remote address]/Normal.dotm
     </code>
     to trigger the SMB request.
     <span class="scite-citeref-number" data-reference="US-CERT APT Energy Oct 2017" id="scite-ref-7-a">
      <sup>
       <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" target="_blank">
        [7]
       </a>
      </sup>
     </span>
    </li>
    <li>
     A modified .LNK or .SCF file with the icon filename pointing to an external reference such as
     <code>
      \[remote address]\pic.png
     </code>
     that will force the system to load the resource when the icon is rendered to repeatedly gather credentials.
     <span class="scite-citeref-number" data-reference="US-CERT APT Energy Oct 2017" id="scite-ref-7-a">
      <sup>
       <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" target="_blank">
        [7]
       </a>
      </sup>
     </span>
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
      : T1187
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
      File monitoring, Network protocol analysis, Network device logs, Process use of network
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
      Teodor Cimpoesu; Sudhanshu Chauhan, @Sudhanshu_C
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
      used
      <a href="https://attack.mitre.org/techniques/T1221">
       Template Injection
      </a>
      to launch an authentication window for users to enter their credentials.
      <span class="scite-citeref-number" data-reference="Unit 42 Phishery Aug 2018" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://researchcenter.paloaltonetworks.com/2018/08/unit42-darkhydrus-uses-phishery-harvest-credentials-middle-east/" target="_blank">
         [8]
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
      has gathered hashed user credentials over SMB using spearphishing attachments with external resource links and by modifying .LNK file icon resources to collect credentials from virtualized systems.
      <span class="scite-citeref-number" data-reference="US-CERT TA18-074A" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" target="_blank">
         [9]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT APT Energy Oct 2017" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" target="_blank">
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
  Block SMB  traffic from exiting an enterprise network with egress filtering or by blocking TCP ports 139, 445 and UDP port 137. Filter or block WebDAV protocol traffic from exiting the network. If access to external resources over SMB and WebDAV is necessary, then traffic should be tightly limited with whitelisting.
  <span class="scite-citeref-number" data-reference="US-CERT SMB Security" id="scite-ref-10-a">
   <sup>
    <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www.us-cert.gov/ncas/current-activity/2017/01/16/SMB-Security-Best-Practices" target="_blank">
     [10]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="US-CERT APT Energy Oct 2017" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" target="_blank">
     [7]
    </a>
   </sup>
  </span>
 </p>
 <p>
  For internal traffic, monitor the workstation-to-workstation unusual (vs. baseline) SMB traffic. For many networks there should not be any, but it depends on how systems on the network are configured and where resources are located.
 </p>
 <p>
  Use strong passwords to increase the difficulty of credential hashes from being cracked if they are obtained.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor for SMB traffic on TCP ports 139, 445 and UDP port 137 and WebDAV traffic attempting to exit the network to unknown external systems. If attempts are detected, then investigate endpoint data sources to find the root cause.
 </p>
 <p>
  Monitor creation and modification of .LNK, .SCF, or any other files on systems and within virtual environments that contain resources that point to external network resources as these could be used to gather credentials when the files are rendered.
  <span class="scite-citeref-number" data-reference="US-CERT APT Energy Oct 2017" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" target="_blank">
     [7]
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
       <a class="external text" href="https://en.wikipedia.org/wiki/Server_Message_Block" name="scite-1" rel="nofollow" target="_blank">
        Wikipedia. (2017, December 16). Server Message Block. Retrieved December 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.didierstevens.com/2017/11/13/webdav-traffic-to-malicious-sites/" name="scite-2" rel="nofollow" target="_blank">
        Stevens, D. (2017, November 13). WebDAV Traffic To Malicious Sites. Retrieved December 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.microsoft.com/technet/prodtechnol/WindowsServer2003/Library/IIS/4beddb35-0cba-424c-8b9b-a5832ad8e208.mspx" name="scite-3" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Managing WebDAV Security (IIS 6.0). Retrieved December 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/hob0/hashjacking" name="scite-4" rel="nofollow" target="_blank">
        Dunning, J. (2016, August 1). Hashjacking. Retrieved December 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cylance.com/content/dam/cylance/pdfs/white_papers/RedirectToSMB.pdf" name="scite-5" rel="nofollow" target="_blank">
        Cylance. (2015, April 13). Redirect to SMB. Retrieved December 21, 2017.
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
       <a class="external text" href="https://osandamalith.com/2017/03/24/places-of-interest-in-stealing-netntlm-hashes/" name="scite-6" rel="nofollow" target="_blank">
        Malith, O. (2017, March 24). Places of Interest in Stealing NetNTLM Hashes. Retrieved January 26, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" name="scite-7" rel="nofollow" target="_blank">
        US-CERT. (2017, October 20). Alert (TA17-293A): Advanced Persistent Threat Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved November 2, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/08/unit42-darkhydrus-uses-phishery-harvest-credentials-middle-east/" name="scite-8" rel="nofollow" target="_blank">
        Falcone, R. (2018, August 07). DarkHydrus Uses Phishery to Harvest Credentials in the Middle East. Retrieved August 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" name="scite-9" rel="nofollow" target="_blank">
        US-CERT. (2018, March 16). Alert (TA18-074A): Russian Government Cyber Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/current-activity/2017/01/16/SMB-Security-Best-Practices" name="scite-10" rel="nofollow" target="_blank">
        US-CERT. (2017, March 16). SMB Security Best Practices. Retrieved December 21, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
