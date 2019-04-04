<div class="container-fluid">
 <h1>
  Uncommonly Used Port
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries may conduct C2 communications over a non-standard port to bypass proxies and firewalls that have been improperly configured.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1065
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
      : Command And Control
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
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      Netflow/Enclave netflow, Process use of network, Process monitoring
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Requires Network:
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
     <a href="https://attack.mitre.org/groups/G0022">
      APT3
     </a>
    </td>
    <td>
     <p>
      An
      <a href="https://attack.mitre.org/groups/G0022">
       APT3
      </a>
      downloader establishes SOCKS5 connections to two separate IP addresses over TCP port 1913 and TCP port 81.
      <span class="scite-citeref-number" data-reference="FireEye Operation Double Tap" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.fireeye.com/blog/threat-research/2014/11/operation_doubletap.html" target="_blank">
         [1]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0239">
      Bankshot
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0239">
       Bankshot
      </a>
      binds and listens on port 1058.
      <span class="scite-citeref-number" data-reference="US-CERT Bankshot Dec 2017" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-B_WHITE.PDF" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0078">
      Gorgon Group
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0078">
       Gorgon Group
      </a>
      has used a variant of NanoCore RAT that communicates with its C2 server over port 6666.
      <span class="scite-citeref-number" data-reference="Unit 42 Gorgon Group Aug 2018" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://researchcenter.paloaltonetworks.com/2018/08/unit42-gorgon-group-slithering-nation-state-cybercrime/" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0237">
      GravityRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0237">
       GravityRAT
      </a>
      uses port 46769 for C2.
      <span class="scite-citeref-number" data-reference="Talos GravityRAT" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://blog.talosintelligence.com/2018/04/gravityrat-two-year-evolution-of-apt.html" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0043">
      Group5
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0043">
       Group5
      </a>
      C2 servers communicated with malware over TCP 8081, 8282, and 8083.
      <span class="scite-citeref-number" data-reference="Citizen Lab Group5" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://citizenlab.org/2016/08/group5-syria/" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0259">
      InnaputRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0259">
       InnaputRAT
      </a>
      uses port 52100 and 5876 for C2 communications.
      <span class="scite-citeref-number" data-reference="ASERT InnaputRAT April 2018" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://asert.arbornetworks.com/innaput-actors-utilize-remote-access-trojan-since-2016-presumably-targeting-victim-files/" target="_blank">
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
      Some
      <a href="https://attack.mitre.org/groups/G0032">
       Lazarus Group
      </a>
      malware uses a list of ordered port numbers to choose a port for C2 traffic, which includes uncommonly used ports such as 995, 1816, 465, 1521, 3306, and many others.
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" target="_blank">
         [7]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster RATs" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-RAT-and-Staging-Report.pdf" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0059">
      Magic Hound
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0059">
       Magic Hound
      </a>
      malware has communicated with its C2 server over ports 4443 and 3543.
      <span class="scite-citeref-number" data-reference="Unit 42 Magic Hound Feb 2017" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://researchcenter.paloaltonetworks.com/2017/02/unit42-magic-hound-campaign-attacks-saudi-targets/" target="_blank">
         [9]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0079">
      MobileOrder
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0079">
       MobileOrder
      </a>
      communicates with its C2 server over TCP port 3728.
      <span class="scite-citeref-number" data-reference="Scarlet Mimic Jan 2016" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="http://researchcenter.paloaltonetworks.com/2016/01/scarlet-mimic-years-long-espionage-targets-minority-activists/" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0012">
      PoisonIvy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0012">
       PoisonIvy
      </a>
      opens a backdoor on TCP ports 6868 and 7777.
      <span class="scite-citeref-number" data-reference="Symantec Darkmoon Aug 2005" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://www.symantec.com/security_response/writeup.jsp?docid=2005-081910-3934-99" target="_blank">
         [11]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0223">
      POWERSTATS
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0223">
       POWERSTATS
      </a>
      has used ports 8060 and 8888 for C2.
      <span class="scite-citeref-number" data-reference="Unit 42 MuddyWater Nov 2017" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-muddying-the-water-targeted-attacks-in-the-middle-east/" target="_blank">
         [12]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0153">
      RedLeaves
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0153">
       RedLeaves
      </a>
      can use port 995 for C2.
      <span class="scite-citeref-number" data-reference="PWC Cloud Hopper Technical Annex April 2017" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" target="_blank">
         [13]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0125">
      Remsec
     </a>
    </td>
    <td>
     <p>
      A
      <a href="https://attack.mitre.org/software/S0125">
       Remsec
      </a>
      module has a default C2 port of 13000.
      <span class="scite-citeref-number" data-reference="Kaspersky ProjectSauron Technical Analysis" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://securelist.com/files/2016/07/The-ProjectSauron-APT_Technical_Analysis_KL.pdf" target="_blank">
         [14]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0266">
      TrickBot
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0266">
       TrickBot
      </a>
      uses ports 447 and 8082 for C2 communications.
      <span class="scite-citeref-number" data-reference="S2 Grupo TrickBot June 2017" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://www.securityartwork.es/wp-content/uploads/2017/07/Trickbot-report-S2-Grupo.pdf" target="_blank">
         [15]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Fidelis TrickBot Oct 2016" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="https://www.fidelissecurity.com/threatgeek/2016/10/trickbot-we-missed-you-dyre" target="_blank">
         [16]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Trend Micro Totbrick Oct 2016" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://www.trendmicro.com/vinfo/us/threat-encyclopedia/malware/tspy_trickload.n" target="_blank">
         [17]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0263">
      TYPEFRAME
     </a>
    </td>
    <td>
     <p>
      A
      <a href="https://attack.mitre.org/software/S0263">
       TYPEFRAME
      </a>
      variant can use port 127 for communications.
      <span class="scite-citeref-number" data-reference="US-CERT TYPEFRAME June 2018" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-165A" target="_blank">
         [18]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0180">
      Volgmer
     </a>
    </td>
    <td>
     <p>
      Some
      <a href="https://attack.mitre.org/software/S0180">
       Volgmer
      </a>
      variants use port 8088 for C2.
      <span class="scite-citeref-number" data-reference="US-CERT Volgmer Nov 2017" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="https://www.us-cert.gov/ncas/alerts/TA17-318B" target="_blank">
         [19]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT Volgmer 2 Nov 2017" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-D_WHITE_S508C.PDF" target="_blank">
         [20]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Symantec Volgmer Aug 2014" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="https://www.symantec.com/security-center/writeup/2014-081811-3237-99?tabid=2" target="_blank">
         [21]
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
  Properly configure firewalls and proxies to limit outgoing traffic to only necessary ports.
 </p>
 <p>
  Network intrusion detection and prevention systems that use network signatures to identify traffic for specific adversary malware can be used to mitigate activity at the network level. Signatures are often for unique indicators within protocols and may be based on the specific protocol used by a particular adversary or tool, and will likely be different across various malware families and versions. Adversaries will likely change tool C2 signatures over time or construct protocols in such a way as to avoid detection by common defensive tools.
  <span class="scite-citeref-number" data-reference="University of Birmingham C2" id="scite-ref-22-a">
   <sup>
    <a aria-describedby="qtip-21" data-hasqtip="21" href="https://arxiv.org/ftp/arxiv/papers/1408/1408.1136.pdf" target="_blank">
     [22]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Analyze network data for uncommon data flows (e.g., a client sending significantly more data than it receives from a server). Processes utilizing the network that do not normally have network communication or have never been seen before are suspicious. Analyze packet contents to detect communications that do not follow the expected protocol behavior for the port that is being used.
  <span class="scite-citeref-number" data-reference="University of Birmingham C2" id="scite-ref-22-a">
   <sup>
    <a aria-describedby="qtip-21" data-hasqtip="21" href="https://arxiv.org/ftp/arxiv/papers/1408/1408.1136.pdf" target="_blank">
     [22]
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
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2014/11/operation_doubletap.html" name="scite-1" rel="nofollow" target="_blank">
        Moran, N., et al. (2014, November 21). Operation Double Tap. Retrieved January 14, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-B_WHITE.PDF" name="scite-2" rel="nofollow" target="_blank">
        US-CERT. (2017, December 13). Malware Analysis Report (MAR) - 10135536-B. Retrieved July 17, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/08/unit42-gorgon-group-slithering-nation-state-cybercrime/" name="scite-3" rel="nofollow" target="_blank">
        Falcone, R., et al. (2018, August 02). The Gorgon Group: Slithering Between Nation State and Cybercrime. Retrieved August 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/04/gravityrat-two-year-evolution-of-apt.html" name="scite-4" rel="nofollow" target="_blank">
        Mercer, W., Rascagneres, P. (2018, April 26). GravityRAT - The Two-Year Evolution Of An APT Targeting India. Retrieved May 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://citizenlab.org/2016/08/group5-syria/" name="scite-5" rel="nofollow" target="_blank">
        Scott-Railton, J., et al. (2016, August 2). Group5: Syria and the Iranian Connection. Retrieved September 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://asert.arbornetworks.com/innaput-actors-utilize-remote-access-trojan-since-2016-presumably-targeting-victim-files/" name="scite-6" rel="nofollow" target="_blank">
        ASERT Team. (2018, April 04). Innaput Actors Utilize Remote Access Trojan Since 2016, Presumably Targeting Victim Files. Retrieved July 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" name="scite-7" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Unraveling the Long Thread of the Sony Attack. Retrieved February 25, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-RAT-and-Staging-Report.pdf" name="scite-8" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Remote Administration Tools &amp; Content Staging Malware Report. Retrieved March 16, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/02/unit42-magic-hound-campaign-attacks-saudi-targets/" name="scite-9" rel="nofollow" target="_blank">
        Lee, B. and Falcone, R. (2017, February 15). Magic Hound Campaign Attacks Saudi Targets. Retrieved December 27, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/01/scarlet-mimic-years-long-espionage-targets-minority-activists/" name="scite-10" rel="nofollow" target="_blank">
        Falcone, R. and Miller-Osborn, J.. (2016, January 24). Scarlet Mimic: Years-Long Espionage Campaign Targets Minority Activists. Retrieved February 10, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2005-081910-3934-99" name="scite-11" rel="nofollow" target="_blank">
        Hayashi, K. (2005, August 18). Backdoor.Darkmoon. Retrieved February 23, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="12.0">
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-muddying-the-water-targeted-attacks-in-the-middle-east/" name="scite-12" rel="nofollow" target="_blank">
        Lancaster, T.. (2017, November 14). Muddying the Water: Targeted Attacks in the Middle East. Retrieved March 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" name="scite-13" rel="nofollow" target="_blank">
        PwC and BAE Systems. (2017, April). Operation Cloud Hopper: Technical Annex. Retrieved April 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/files/2016/07/The-ProjectSauron-APT_Technical_Analysis_KL.pdf" name="scite-14" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research &amp; Analysis Team. (2016, August 9). The ProjectSauron APT. Technical Analysis. Retrieved August 17, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.securityartwork.es/wp-content/uploads/2017/07/Trickbot-report-S2-Grupo.pdf" name="scite-15" rel="nofollow" target="_blank">
        Salinas, M., Holguin, J. (2017, June). Evolution of Trickbot. Retrieved July 31, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fidelissecurity.com/threatgeek/2016/10/trickbot-we-missed-you-dyre" name="scite-16" rel="nofollow" target="_blank">
        Reaves, J. (2016, October 15). TrickBot: We Missed you, Dyre. Retrieved August 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.trendmicro.com/vinfo/us/threat-encyclopedia/malware/tspy_trickload.n" name="scite-17" rel="nofollow" target="_blank">
        Antazo, F. (2016, October 31). TSPY_TRICKLOAD.N. Retrieved September 14, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-165A" name="scite-18" rel="nofollow" target="_blank">
        US-CERT. (2018, June 14). MAR-10135536-12 – North Korean Trojan: TYPEFRAME. Retrieved July 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA17-318B" name="scite-19" rel="nofollow" target="_blank">
        US-CERT. (2017, November 22). Alert (TA17-318B): HIDDEN COBRA – North Korean Trojan: Volgmer. Retrieved December 7, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-D_WHITE_S508C.PDF" name="scite-20" rel="nofollow" target="_blank">
        US-CERT. (2017, November 01). Malware Analysis Report (MAR) - 10135536-D. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security-center/writeup/2014-081811-3237-99?tabid=2" name="scite-21" rel="nofollow" target="_blank">
        Yagi, J. (2014, August 24). Trojan.Volgmer. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="https://arxiv.org/ftp/arxiv/papers/1408/1408.1136.pdf" name="scite-22" rel="nofollow" target="_blank">
        Gardiner, J.,  Cova, M., Nagaraja, S. (2014, February). Command &amp; Control Understanding, Denying and Detecting. Retrieved April 20, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
