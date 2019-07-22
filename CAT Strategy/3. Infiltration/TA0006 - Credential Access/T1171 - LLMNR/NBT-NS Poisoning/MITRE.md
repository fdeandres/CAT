<div class="container-fluid">
 <h1>
  LLMNR/NBT-NS Poisoning
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Link-Local Multicast Name Resolution (LLMNR) and NetBIOS Name Service (NBT-NS) are Microsoft Windows components that serve as alternate methods of host identification. LLMNR is based upon the Domain Name System (DNS) format and allows hosts on the same local link to perform name resolution for other hosts. NBT-NS identifies systems on a local network by their NetBIOS name.
    <span class="scite-citeref-number" data-reference="Wikipedia LLMNR" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://en.wikipedia.org/wiki/Link-Local_Multicast_Name_Resolution" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="TechNet NetBIOS" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://technet.microsoft.com/library/cc958811.aspx" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries can spoof an authoritative source for name resolution on a victim network by responding to LLMNR (UDP 5355)/NBT-NS (UDP 137) traffic as if they know the identity of the requested host, effectively poisoning the service so that the victims will communicate with the adversary controlled system. If the requested host belongs to a resource that requires identification/authentication, the username and NTLMv2 hash will then be sent to the adversary controlled system. The adversary can then collect the hash information sent over the wire through tools that monitor the ports for traffic or through
    <a href="https://attack.mitre.org/techniques/T1040">
     Network Sniffing
    </a>
    and crack the hashes offline through
    <a href="https://attack.mitre.org/techniques/T1110">
     Brute Force
    </a>
    to obtain the plaintext passwords.
   </p>
   <p>
    Several tools exist that can be used to poison name services within local networks such as NBNSpoof, Metasploit, and
    <a href="https://attack.mitre.org/software/S0174">
     Responder
    </a>
    .
    <span class="scite-citeref-number" data-reference="GitHub NBNSpoof" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://github.com/nomex/nbnspoof" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Rapid7 LLMNR Spoofer" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.rapid7.com/db/modules/auxiliary/spoof/llmnr/llmnr_response" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="GitHub Responder" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://github.com/SpiderLabs/Responder" target="_blank">
       [5]
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
      : T1171
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
      Windows Registry, Packet capture, Netflow/Enclave netflow
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
      Matthew Demaske, Adaptforward
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
     <a href="https://attack.mitre.org/software/S0192">
      Pupy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0192">
       Pupy
      </a>
      can sniff plaintext network credentials and use NBNS Spoofing to poison name services.
      <span class="scite-citeref-number" data-reference="GitHub Pupy" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://github.com/n1nj4sec/pupy" target="_blank">
         [6]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0174">
      Responder
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0174">
       Responder
      </a>
      is used to poison name services to gather hashes and credentials from systems within a local network.
      <span class="scite-citeref-number" data-reference="GitHub Responder" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://github.com/SpiderLabs/Responder" target="_blank">
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
  Disable LLMNR and NetBIOS in local computer security settings or by group policy if they are not needed within an environment.
  <span class="scite-citeref-number" data-reference="ADSecurity Windows Secure Baseline" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://adsecurity.org/?p=3299" target="_blank">
     [7]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Use host-based security software to block LLMNR/NetBIOS traffic.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor
  <code>
   HKLM\Software\Policies\Microsoft\Windows NT\DNSClient
  </code>
  for changes to the "EnableMulticast" DWORD value. A value of "0" indicates LLMNR is disabled.
  <span class="scite-citeref-number" data-reference="Sternsecurity LLMNR-NBTNS" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.sternsecurity.com/blog/local-network-attacks-llmnr-and-nbt-ns-poisoning" target="_blank">
     [8]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Monitor for traffic on ports UDP 5355 and UDP 137 if LLMNR/NetBIOS is disabled by security policy.
 </p>
 <p>
  Deploy an LLMNR/NBT-NS spoofing detection tool.
  <span class="scite-citeref-number" data-reference="GitHub Conveigh" id="scite-ref-9-a">
   <sup>
    <a aria-describedby="qtip-8" data-hasqtip="8" href="https://github.com/Kevin-Robertson/Conveigh" target="_blank">
     [9]
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
       <a class="external text" href="https://en.wikipedia.org/wiki/Link-Local_Multicast_Name_Resolution" name="scite-1" rel="nofollow" target="_blank">
        Wikipedia. (2016, July 7). Link-Local Multicast Name Resolution. Retrieved November 17, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/library/cc958811.aspx" name="scite-2" rel="nofollow" target="_blank">
        Microsoft. (n.d.). NetBIOS Name Resolution. Retrieved November 17, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/nomex/nbnspoof" name="scite-3" rel="nofollow" target="_blank">
        Nomex. (2014, February 7). NBNSpoof. Retrieved November 17, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.rapid7.com/db/modules/auxiliary/spoof/llmnr/llmnr_response" name="scite-4" rel="nofollow" target="_blank">
        Francois, R. (n.d.). LLMNR Spoofer. Retrieved November 17, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/SpiderLabs/Responder" name="scite-5" rel="nofollow" target="_blank">
        Gaffie, L. (2016, August 25). Responder. Retrieved November 17, 2017.
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
       <a class="external text" href="https://github.com/n1nj4sec/pupy" name="scite-6" rel="nofollow" target="_blank">
        Nicolas Verdier. (n.d.). Retrieved January 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://adsecurity.org/?p=3299" name="scite-7" rel="nofollow" target="_blank">
        Metcalf, S. (2016, October 21). Securing Windows Workstations: Developing a Secure Baseline. Retrieved November 17, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.sternsecurity.com/blog/local-network-attacks-llmnr-and-nbt-ns-poisoning" name="scite-8" rel="nofollow" target="_blank">
        Sternstein, J. (2013, November). Local Network Attacks: LLMNR and NBT-NS Poisoning. Retrieved November 17, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/Kevin-Robertson/Conveigh" name="scite-9" rel="nofollow" target="_blank">
        Robertson, K. (2016, August 28). Conveigh. Retrieved November 17, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
