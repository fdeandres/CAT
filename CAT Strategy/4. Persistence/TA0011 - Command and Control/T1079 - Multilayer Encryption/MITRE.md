<div class="container-fluid">
 <h1>
  Multilayer Encryption
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    An adversary performs C2 communications using multiple layers of encryption, typically (but not exclusively) tunneling a custom encryption scheme within a protocol encryption scheme such as HTTPS or SMTPS.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1079
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
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      Packet capture, Process use of network, Malware reverse engineering, Process monitoring
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
     <a href="https://attack.mitre.org/software/S0087">
      Hi-Zor
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0087">
       Hi-Zor
      </a>
      encrypts C2 traffic with HTTPS and also encodes it with a single-byte XOR key.
      <span class="scite-citeref-number" data-reference="Fidelis INOCNATION" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.fidelissecurity.com/sites/default/files/FTA_1020_Fidelis_Inocnation_FINAL_0.pdf" target="_blank">
         [1]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0192">
      Pupy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0192">
       Pupy
      </a>
      can use Obfs3, a pluggable transport, to add another layer of encryption and obfuscate TLS.
      <span class="scite-citeref-number" data-reference="GitHub Pupy" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://github.com/n1nj4sec/pupy" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0018">
      Sykipot
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0018">
       Sykipot
      </a>
      communicates using HTTPS and uses a custom encryption cipher to encrypt the HTTPS message body.
      <span class="scite-citeref-number" data-reference="Blasco 2013" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="http://www.alienvault.com/open-threat-exchange/blog/new-sykipot-developments" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0183">
      Tor
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0183">
       Tor
      </a>
      encapsulates traffic in multiple layers of encryption.
      <span class="scite-citeref-number" data-reference="Dingledine Tor The Second-Generation Onion Router" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="http://www.dtic.mil/dtic/tr/fulltext/u2/a465464.pdf" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0366">
      WannaCry
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0366">
       WannaCry
      </a>
      uses
      <a href="https://attack.mitre.org/software/S0183">
       Tor
      </a>
      for command and control traffic and routes a custom cryptographic protocol over the
      <a href="https://attack.mitre.org/software/S0183">
       Tor
      </a>
      circuit.
      <span class="scite-citeref-number" data-reference="SecureWorks WannaCry Analysis" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.secureworks.com/research/wcry-ransomware-analysis" target="_blank">
         [5]
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
  Network intrusion detection and prevention systems that use network signatures to identify traffic for specific adversary malware can be used to mitigate activity at the network level. Use of encryption protocols may make typical network-based C2 detection more difficult due to a reduced ability to signature the traffic. Prior knowledge of adversary C2 infrastructure may be useful for domain and IP address blocking, but will likely not be an effective long-term solution because adversaries can change infrastructure often.
  <span class="scite-citeref-number" data-reference="University of Birmingham C2" id="scite-ref-6-a">
   <sup>
    <a aria-describedby="qtip-5" data-hasqtip="5" href="https://arxiv.org/ftp/arxiv/papers/1408/1408.1136.pdf" target="_blank">
     [6]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  If malware uses
  <a href="https://attack.mitre.org/techniques/T1032">
   Standard Cryptographic Protocol
  </a>
  , SSL/TLS inspection can be used to detect command and control traffic within some encrypted communication channels.
  <span class="scite-citeref-number" data-reference="SANS Decrypting SSL" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="http://www.sans.org/reading-room/whitepapers/analyst/finding-hidden-threats-decrypting-ssl-34840" target="_blank">
     [7]
    </a>
   </sup>
  </span>
  SSL/TLS inspection does come with certain risks that should be considered before implementing to avoid potential security issues such as incomplete certificate validation.
  <span class="scite-citeref-number" data-reference="SEI SSL Inspection Risks" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="https://insights.sei.cmu.edu/cert/2015/03/the-risks-of-ssl-inspection.html" target="_blank">
     [8]
    </a>
   </sup>
  </span>
  After SSL/TLS inspection, additional cryptographic analysis may be needed to analyze the second layer of encryption.
 </p>
 <p>
  With
  <a href="https://attack.mitre.org/techniques/T1024">
   Custom Cryptographic Protocol
  </a>
  , if malware uses encryption with symmetric keys, it may be possible to obtain the algorithm and key from samples and use them to decode network traffic to detect malware communications signatures.
  <span class="scite-citeref-number" data-reference="Fidelis DarkComet" id="scite-ref-9-a">
   <sup>
    <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.fidelissecurity.com/sites/default/files/FTA_1018_looking_at_the_sky_for_a_dark_comet.pdf" target="_blank">
     [9]
    </a>
   </sup>
  </span>
 </p>
 <p>
  In general, analyze network data for uncommon data flows (e.g., a client sending significantly more data than it receives from a server). Processes utilizing the network that do not normally have network communication or have never been seen before are suspicious. Analyze packet contents to detect communications that do not follow the expected protocol behavior for the port that is being used.
  <span class="scite-citeref-number" data-reference="University of Birmingham C2" id="scite-ref-6-a">
   <sup>
    <a aria-describedby="qtip-5" data-hasqtip="5" href="https://arxiv.org/ftp/arxiv/papers/1408/1408.1136.pdf" target="_blank">
     [6]
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
       <a class="external text" href="https://www.fidelissecurity.com/sites/default/files/FTA_1020_Fidelis_Inocnation_FINAL_0.pdf" name="scite-1" rel="nofollow" target="_blank">
        Fidelis Cybersecurity. (2015, December 16). Fidelis Threat Advisory #1020: Dissecting the Malware Involved in the INOCNATION Campaign. Retrieved March 24, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/n1nj4sec/pupy" name="scite-2" rel="nofollow" target="_blank">
        Nicolas Verdier. (n.d.). Retrieved January 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.alienvault.com/open-threat-exchange/blog/new-sykipot-developments" name="scite-3" rel="nofollow" target="_blank">
        Blasco, J. (2013, March 21). New Sykipot developments [Blog]. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.dtic.mil/dtic/tr/fulltext/u2/a465464.pdf" name="scite-4" rel="nofollow" target="_blank">
        Roger Dingledine, Nick Mathewson and Paul Syverson. (2004). Tor: The Second-Generation Onion Router. Retrieved December 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/wcry-ransomware-analysis" name="scite-5" rel="nofollow" target="_blank">
        Counter Threat Unit Research Team. (2017, May 18). WCry Ransomware Analysis. Retrieved March 26, 2019.
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
       <a class="external text" href="https://arxiv.org/ftp/arxiv/papers/1408/1408.1136.pdf" name="scite-6" rel="nofollow" target="_blank">
        Gardiner, J.,  Cova, M., Nagaraja, S. (2014, February). Command &amp; Control Understanding, Denying and Detecting. Retrieved April 20, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/analyst/finding-hidden-threats-decrypting-ssl-34840" name="scite-7" rel="nofollow" target="_blank">
        Butler, M. (2013, November). Finding Hidden Threats by Decrypting SSL. Retrieved April 5, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://insights.sei.cmu.edu/cert/2015/03/the-risks-of-ssl-inspection.html" name="scite-8" rel="nofollow" target="_blank">
        Dormann, W. (2015, March 13). The Risks of SSL Inspection. Retrieved April 5, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fidelissecurity.com/sites/default/files/FTA_1018_looking_at_the_sky_for_a_dark_comet.pdf" name="scite-9" rel="nofollow" target="_blank">
        Fidelis Cybersecurity. (2015, August 4). Looking at the Sky for a DarkComet. Retrieved April 5, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
