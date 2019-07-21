<div class="container-fluid">
 <h1>
  Custom Cryptographic Protocol
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries may use a custom cryptographic protocol or algorithm to hide command and control traffic. A simple scheme, such as XOR-ing the plaintext with a fixed key, will produce a very weak ciphertext.
   </p>
   <p>
    Custom encryption schemes may vary in sophistication. Analysis and reverse engineering of malware samples may be enough to discover the algorithm and encryption key used.
   </p>
   <p>
    Some adversaries may also attempt to implement their own version of a well-known cryptographic algorithm instead of using a known implementation library, which may lead to unintentional errors.
    <span class="scite-citeref-number" data-reference="F-Secure Cosmicduke" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.f-secure.com/documents/996508/1030745/cosmicduke_whitepaper.pdf" target="_blank">
       [1]
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
      : T1024
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
      Packet capture, Netflow/Enclave netflow, Process use of network, Malware reverse engineering, Process monitoring
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
     <a href="https://attack.mitre.org/software/S0066">
      3PARA RAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0066">
       3PARA RAT
      </a>
      will use an 8-byte XOR key derived from the string HYF54&amp;%9&amp;jkMCXuiS instead if the DES decoding fails.
      <span class="scite-citeref-number" data-reference="CrowdStrike Putter Panda" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="http://cdn0.vox-cdn.com/assets/4589853/crowdstrike-intelligence-report-putter-panda.original.pdf" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0065">
      4H RAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0065">
       4H RAT
      </a>
      obfuscates C2 communication using a 1-byte XOR with the key 0xBE.
      <span class="scite-citeref-number" data-reference="CrowdStrike Putter Panda" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="http://cdn0.vox-cdn.com/assets/4589853/crowdstrike-intelligence-report-putter-panda.original.pdf" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0245">
      BADCALL
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0245">
       BADCALL
      </a>
      encrypts C2 traffic using an XOR/ADD cipher and uses a FakeTLS method.
      <span class="scite-citeref-number" data-reference="US-CERT BADCALL" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-G.PDF" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0128">
      BADNEWS
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0128">
       BADNEWS
      </a>
      encrypts C2 data with a ROR by 3 and an XOR by 0x23.
      <span class="scite-citeref-number" data-reference="Forcepoint Monsoon" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" target="_blank">
         [4]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="TrendMicro Patchwork Dec 2017" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0127">
      BBSRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0127">
       BBSRAT
      </a>
      uses a custom encryption algorithm on data sent back to the C2 server over HTTP.
      <span class="scite-citeref-number" data-reference="Palo Alto Networks BBSRAT" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="http://researchcenter.paloaltonetworks.com/2015/12/bbsrat-attacks-targeting-russian-organizations-linked-to-roaming-tiger/" target="_blank">
         [6]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0268">
      Bisonal
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0268">
       Bisonal
      </a>
      variants reported on in 2014 and 2015 used a simple XOR cipher for C2.
      <span class="scite-citeref-number" data-reference="Unit 42 Bisonal July 2018" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-bisonal-malware-used-attacks-russia-south-korea/" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0060">
      BRONZE BUTLER
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0060">
       BRONZE BUTLER
      </a>
      has used a tool called RarStar that encodes data with a custom XOR algorithm when posting it to a C2 server.
      <span class="scite-citeref-number" data-reference="Secureworks BRONZE BUTLER Oct 2017" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.secureworks.com/research/bronze-butler-targets-japanese-businesses" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0030">
      Carbanak
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0030">
       Carbanak
      </a>
      uses XOR with random keys for its communications.
      <span class="scite-citeref-number" data-reference="FireEye CARBANAK June 2017" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.fireeye.com/blog/threat-research/2017/06/behind-the-carbanak-backdoor.html" target="_blank">
         [9]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0348">
      Cardinal RAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0348">
       Cardinal RAT
      </a>
      uses a secret key with a series of XOR and addition operations to encrypt C2 traffic.
      <span class="scite-citeref-number" data-reference="PaloAlto CardinalRat Apr 2017" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://researchcenter.paloaltonetworks.com/2017/04/unit42-cardinal-rat-active-two-years/" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0144">
      ChChes
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0144">
       ChChes
      </a>
      can encrypt C2 data with a custom technique using MD5, base64-encoding, and RC4.
      <span class="scite-citeref-number" data-reference="Palo Alto menuPass Feb 2017" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="http://researchcenter.paloaltonetworks.com/2017/02/unit42-menupass-returns-new-malware-new-attacks-japanese-academics-organizations/" target="_blank">
         [11]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="JPCERT ChChes Feb 2017" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="http://blog.jpcert.or.jp/2017/02/chches-malware--93d6.html" target="_blank">
         [12]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0137">
      CORESHELL
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0137">
       CORESHELL
      </a>
      C2 messages are encrypted with custom stream ciphers using six-byte or eight-byte keys.
      <span class="scite-citeref-number" data-reference="FireEye APT28" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/rpt-apt28.pdf" target="_blank">
         [13]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0050">
      CosmicDuke
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0050">
       CosmicDuke
      </a>
      contains a custom version of the RC4 algorithm that includes a programming error.
      <span class="scite-citeref-number" data-reference="F-Secure Cosmicduke" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.f-secure.com/documents/996508/1030745/cosmicduke_whitepaper.pdf" target="_blank">
         [1]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0021">
      Derusbi
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0021">
       Derusbi
      </a>
      obfuscates C2 traffic with variable 4-byte XOR keys.
      <span class="scite-citeref-number" data-reference="Fidelis Turbo" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://www.fidelissecurity.com/sites/default/files/TA_Fidelis_Turbo_1602_0.pdf" target="_blank">
         [14]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0377">
      Ebury
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0377">
       Ebury
      </a>
      has encrypted C2 traffic using the client IP address, then encoded it as a hexadecimal string.
      <span class="scite-citeref-number" data-reference="ESET Ebury Feb 2014" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://www.welivesecurity.com/2014/02/21/an-in-depth-analysis-of-linuxebury/" target="_blank">
         [15]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0082">
      Emissary
     </a>
    </td>
    <td>
     <p>
      The C2 server response to a beacon sent by a variant of
      <a href="https://attack.mitre.org/software/S0082">
       Emissary
      </a>
      contains a 36-character GUID value that is used as an encryption key for subsequent network communications. Some variants of
      <a href="https://attack.mitre.org/software/S0082">
       Emissary
      </a>
      use various XOR operations to encrypt C2 data.
      <span class="scite-citeref-number" data-reference="Lotus Blossom Dec 2015" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="http://researchcenter.paloaltonetworks.com/2015/12/attack-on-french-diplomat-linked-to-operation-lotus-blossom/" target="_blank">
         [16]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0076">
      FakeM
     </a>
    </td>
    <td>
     <p>
      The original variant of
      <a href="https://attack.mitre.org/software/S0076">
       FakeM
      </a>
      encrypts C2 traffic using a custom encryption cipher that uses an XOR key of "YHCRA" and bit rotation between each XOR operation.
      <a href="https://attack.mitre.org/software/S0076">
       FakeM
      </a>
      has also included HTML code in C2 traffic in an apparent attempt to evade detection. Additionally, some variants of
      <a href="https://attack.mitre.org/software/S0076">
       FakeM
      </a>
      use modified SSL code for communications back to C2 servers, making SSL decryption ineffective.
      <span class="scite-citeref-number" data-reference="Scarlet Mimic Jan 2016" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="http://researchcenter.paloaltonetworks.com/2016/01/scarlet-mimic-years-long-espionage-targets-minority-activists/" target="_blank">
         [17]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0181">
      FALLCHILL
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0181">
       FALLCHILL
      </a>
      uses fake Transport Layer Security (TLS) to communicate with its C2 server, encoding data with RC4 encryption.
      <span class="scite-citeref-number" data-reference="US-CERT FALLCHILL Nov 2017" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="https://www.us-cert.gov/ncas/alerts/TA17-318A" target="_blank">
         [18]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0171">
      Felismus
     </a>
    </td>
    <td>
     <p>
      Some
      <a href="https://attack.mitre.org/software/S0171">
       Felismus
      </a>
      samples use a custom encryption method for C2 traffic using AES, base64 encoding, and multiple keys.
      <span class="scite-citeref-number" data-reference="Forcepoint Felismus Mar 2017" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="https://blogs.forcepoint.com/security-labs/playing-cat-mouse-introducing-felismus-malware" target="_blank">
         [19]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0168">
      Gazer
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0168">
       Gazer
      </a>
      uses custom encryption for C2 using 3DES and RSA.
      <span class="scite-citeref-number" data-reference="ESET Gazer Aug 2017" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf" target="_blank">
         [20]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Securelist WhiteBear Aug 2017" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="https://securelist.com/introducing-whitebear/81638/" target="_blank">
         [21]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0037">
      HAMMERTOSS
     </a>
    </td>
    <td>
     <p>
      Before being appended to image files,
      <a href="https://attack.mitre.org/software/S0037">
       HAMMERTOSS
      </a>
      commands are encrypted with a key composed of both a hard-coded value and a string contained on that day's tweet. To decrypt the commands, an investigator would need access to the intended malware sample, the day's tweet, and the image file containing the command.
      <span class="scite-citeref-number" data-reference="FireEye APT29" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-apt29-hammertoss.pdf" target="_blank">
         [22]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0246">
      HARDRAIN
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0246">
       HARDRAIN
      </a>
      uses FakeTLS to communicate with its C2 server.
      <span class="scite-citeref-number" data-reference="US-CERT HARDRAIN March 2018" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-F.pdf" target="_blank">
         [23]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0009">
      Hikit
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0009">
       Hikit
      </a>
      performs XOR encryption.
      <span class="scite-citeref-number" data-reference="Novetta-Axiom" id="scite-ref-24-a" onclick="scrollToRef('scite-24')">
       <sup>
        <a aria-describedby="qtip-23" data-hasqtip="23" href="http://www.novetta.com/wp-content/uploads/2014/11/Executive_Summary-Final_1.pdf" target="_blank">
         [24]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0068">
      httpclient
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0068">
       httpclient
      </a>
      encrypts C2 content with XOR using a single byte, 0x12.
      <span class="scite-citeref-number" data-reference="CrowdStrike Putter Panda" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="http://cdn0.vox-cdn.com/assets/4589853/crowdstrike-intelligence-report-putter-panda.original.pdf" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0203">
      Hydraq
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0203">
       Hydraq
      </a>
      C2 traffic is encrypted using bitwise NOT and XOR operations.
      <span class="scite-citeref-number" data-reference="Symantec Hydraq Jan 2010" id="scite-ref-25-a" onclick="scrollToRef('scite-25')">
       <sup>
        <a aria-describedby="qtip-24" data-hasqtip="24" href="https://www.symantec.com/security_response/writeup.jsp?docid=2010-011114-1830-99" target="_blank">
         [25]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0260">
      InvisiMole
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0260">
       InvisiMole
      </a>
      uses variations of a simple XOR encryption routine for C&amp;C communications.
      <span class="scite-citeref-number" data-reference="ESET InvisiMole June 2018" id="scite-ref-26-a" onclick="scrollToRef('scite-26')">
       <sup>
        <a aria-describedby="qtip-25" data-hasqtip="25" href="https://www.welivesecurity.com/2018/06/07/invisimole-equipped-spyware-undercover/" target="_blank">
         [26]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0271">
      KEYMARBLE
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0271">
       KEYMARBLE
      </a>
      uses a customized XOR algorithm to encrypt C2 communications.
      <span class="scite-citeref-number" data-reference="US-CERT KEYMARBLE Aug 2018" id="scite-ref-27-a" onclick="scrollToRef('scite-27')">
       <sup>
        <a aria-describedby="qtip-26" data-hasqtip="26" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-221A" target="_blank">
         [27]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0162">
      Komplex
     </a>
    </td>
    <td>
     <p>
      The
      <a href="https://attack.mitre.org/software/S0162">
       Komplex
      </a>
      C2 channel uses an 11-byte XOR algorithm to hide data.
      <span class="scite-citeref-number" data-reference="Sofacy Komplex Trojan" id="scite-ref-28-a" onclick="scrollToRef('scite-28')">
       <sup>
        <a aria-describedby="qtip-27" data-hasqtip="27" href="https://researchcenter.paloaltonetworks.com/2016/09/unit42-sofacys-komplex-os-x-trojan/" target="_blank">
         [28]
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
      Several
      <a href="https://attack.mitre.org/groups/G0032">
       Lazarus Group
      </a>
      malware families encrypt C2 traffic using custom code that uses XOR with an ADD operation and XOR with a SUB operation. Another
      <a href="https://attack.mitre.org/groups/G0032">
       Lazarus Group
      </a>
      malware sample XORs C2 traffic.
      <a href="https://attack.mitre.org/groups/G0032">
       Lazarus Group
      </a>
      malware also uses a unique form of communication encryption known as FakeTLS that mimics TLS but uses a different encryption method, evading SSL man-in-the-middle decryption attacks.
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster" id="scite-ref-29-a" onclick="scrollToRef('scite-29')">
       <sup>
        <a aria-describedby="qtip-28" data-hasqtip="28" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" target="_blank">
         [29]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster Destructive Malware" id="scite-ref-30-a" onclick="scrollToRef('scite-30')">
       <sup>
        <a aria-describedby="qtip-29" data-hasqtip="29" href="https://operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Destructive-Malware-Report.pdf" target="_blank">
         [30]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="McAfee Lazarus Resurfaces Feb 2018" id="scite-ref-31-a" onclick="scrollToRef('scite-31')">
       <sup>
        <a aria-describedby="qtip-30" data-hasqtip="30" href="https://securingtomorrow.mcafee.com/mcafee-labs/lazarus-resurfaces-targets-global-banks-bitcoin-users/" target="_blank">
         [31]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="McAfee GhostSecret" id="scite-ref-32-a" onclick="scrollToRef('scite-32')">
       <sup>
        <a aria-describedby="qtip-31" data-hasqtip="31" href="https://securingtomorrow.mcafee.com/mcafee-labs/analyzing-operation-ghostsecret-attack-seeks-to-steal-data-worldwide/" target="_blank">
         [32]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0010">
      Lurid
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0010">
       Lurid
      </a>
      performs XOR encryption.
      <span class="scite-citeref-number" data-reference="Villeneuve 2011" id="scite-ref-33-a" onclick="scrollToRef('scite-33')">
       <sup>
        <a aria-describedby="qtip-32" data-hasqtip="32" href="http://www.trendmicro.com/cloud-content/us/pdfs/security-intelligence/white-papers/wp_dissecting-lurid-apt.pdf" target="_blank">
         [33]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0256">
      Mosquito
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0256">
       Mosquito
      </a>
      uses a custom encryption algorithm, which consists of XOR and a stream that is similar to the Blum Blum Shub algorithm.
      <span class="scite-citeref-number" data-reference="ESET Turla Mosquito Jan 2018" id="scite-ref-34-a" onclick="scrollToRef('scite-34')">
       <sup>
        <a aria-describedby="qtip-33" data-hasqtip="33" href="https://www.welivesecurity.com/wp-content/uploads/2018/01/ESET_Turla_Mosquito.pdf" target="_blank">
         [34]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0254">
      PLAINTEE
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0254">
       PLAINTEE
      </a>
      encodes C2 beacons using XOR.
      <span class="scite-citeref-number" data-reference="Rancor Unit42 June 2018" id="scite-ref-35-a" onclick="scrollToRef('scite-35')">
       <sup>
        <a aria-describedby="qtip-34" data-hasqtip="34" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-rancor-targeted-attacks-south-east-asia-using-plaintee-ddkong-malware-families/" target="_blank">
         [35]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0148">
      RTM
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0148">
       RTM
      </a>
      encrypts C2 traffic with a custom RC4 variant.
      <span class="scite-citeref-number" data-reference="ESET RTM Feb 2017" id="scite-ref-36-a" onclick="scrollToRef('scite-36')">
       <sup>
        <a aria-describedby="qtip-35" data-hasqtip="35" href="https://www.welivesecurity.com/wp-content/uploads/2017/02/Read-The-Manual.pdf" target="_blank">
         [36]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0074">
      Sakula
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0074">
       Sakula
      </a>
      encodes C2 traffic with single-byte XOR keys.
      <span class="scite-citeref-number" data-reference="Dell Sakula" id="scite-ref-37-a" onclick="scrollToRef('scite-37')">
       <sup>
        <a aria-describedby="qtip-36" data-hasqtip="36" href="http://www.secureworks.com/cyber-threat-intelligence/threats/sakula-malware-family/" target="_blank">
         [37]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0060">
      Sys10
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0060">
       Sys10
      </a>
      uses an XOR 0x1 loop to encrypt its C2 domain.
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0011">
      Taidoor
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0011">
       Taidoor
      </a>
      is known to utilize encryption within network protocols.
      <span class="scite-citeref-number" data-reference="TrendMicro Taidoor" id="scite-ref-38-a" onclick="scrollToRef('scite-38')">
       <sup>
        <a aria-describedby="qtip-37" data-hasqtip="37" href="http://www.trendmicro.com/cloud-content/us/pdfs/security-intelligence/white-papers/wp_the_taidoor_campaign.pdf" target="_blank">
         [38]
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
      uses a custom crypter leveraging Microsoft’s CryptoAPI to encrypt C2 traffic.
      <span class="scite-citeref-number" data-reference="Fidelis TrickBot Oct 2016" id="scite-ref-39-a" onclick="scrollToRef('scite-39')">
       <sup>
        <a aria-describedby="qtip-38" data-hasqtip="38" href="https://www.fidelissecurity.com/threatgeek/2016/10/trickbot-we-missed-you-dyre" target="_blank">
         [39]
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
      uses a custom cryptographic protocol over the
      <a href="https://attack.mitre.org/software/S0183">
       Tor
      </a>
      circuit.
      <span class="scite-citeref-number" data-reference="SecureWorks WannaCry Analysis" id="scite-ref-40-a" onclick="scrollToRef('scite-40')">
       <sup>
        <a aria-describedby="qtip-39" data-hasqtip="39" href="https://www.secureworks.com/research/wcry-ransomware-analysis" target="_blank">
         [40]
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
  Network intrusion detection and prevention systems that use network signatures to identify traffic for specific adversary malware can be used to mitigate activity at the network level. Since the custom protocol used may not adhere to typical protocol standards, there may be opportunities to signature the traffic on a network level for detection. Signatures are often for unique indicators within protocols and may be based on the specific protocol used by a particular adversary or tool, and will likely be different across various malware families and versions. Adversaries will likely change tool C2 signatures over time or construct protocols in such a way as to avoid detection by common defensive tools.
  <span class="scite-citeref-number" data-reference="University of Birmingham C2" id="scite-ref-41-a">
   <sup>
    <a aria-describedby="qtip-40" data-hasqtip="40" href="https://arxiv.org/ftp/arxiv/papers/1408/1408.1136.pdf" target="_blank">
     [41]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  If malware uses custom encryption with symmetric keys, it may be possible to obtain the algorithm and key from samples and use them to decode network traffic to detect malware communications signatures.
  <span class="scite-citeref-number" data-reference="Fidelis DarkComet" id="scite-ref-42-a">
   <sup>
    <a aria-describedby="qtip-41" data-hasqtip="41" href="https://www.fidelissecurity.com/sites/default/files/FTA_1018_looking_at_the_sky_for_a_dark_comet.pdf" target="_blank">
     [42]
    </a>
   </sup>
  </span>
 </p>
 <p>
  In general, analyze network data for uncommon data flows (e.g., a client sending significantly more data than it receives from a server). Processes utilizing the network that do not normally have network communication or have never been seen before are suspicious. Analyze packet contents to detect when communications do not follow the expected protocol behavior for the port that is being used.
  <span class="scite-citeref-number" data-reference="University of Birmingham C2" id="scite-ref-41-a">
   <sup>
    <a aria-describedby="qtip-40" data-hasqtip="40" href="https://arxiv.org/ftp/arxiv/papers/1408/1408.1136.pdf" target="_blank">
     [41]
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
       <a class="external text" href="https://www.f-secure.com/documents/996508/1030745/cosmicduke_whitepaper.pdf" name="scite-1" rel="nofollow" target="_blank">
        F-Secure Labs. (2014, July). COSMICDUKE Cosmu with a twist of MiniDuke. Retrieved July 3, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://cdn0.vox-cdn.com/assets/4589853/crowdstrike-intelligence-report-putter-panda.original.pdf" name="scite-2" rel="nofollow" target="_blank">
        Crowdstrike Global Intelligence Team. (2014, June 9). CrowdStrike Intelligence Report: Putter Panda. Retrieved January 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-G.PDF" name="scite-3" rel="nofollow" target="_blank">
        US-CERT. (2018, February 06). Malware Analysis Report (MAR) - 10135536-G. Retrieved June 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" name="scite-4" rel="nofollow" target="_blank">
        Settle, A., et al. (2016, August 8). MONSOON - Analysis Of An APT Campaign. Retrieved September 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" name="scite-5" rel="nofollow" target="_blank">
        Lunghi, D., et al. (2017, December). Untangling the Patchwork Cyberespionage Group. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2015/12/bbsrat-attacks-targeting-russian-organizations-linked-to-roaming-tiger/" name="scite-6" rel="nofollow" target="_blank">
        Lee, B. Grunzweig, J. (2015, December 22). BBSRAT Attacks Targeting Russian Organizations Linked to Roaming Tiger. Retrieved August 19, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/07/unit42-bisonal-malware-used-attacks-russia-south-korea/" name="scite-7" rel="nofollow" target="_blank">
        Hayashi, K., Ray, V. (2018, July 31). Bisonal Malware Used in Attacks Against Russia and South Korea. Retrieved August 7, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/bronze-butler-targets-japanese-businesses" name="scite-8" rel="nofollow" target="_blank">
        Counter Threat Unit Research Team. (2017, October 12). BRONZE BUTLER Targets Japanese Enterprises. Retrieved January 4, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/06/behind-the-carbanak-backdoor.html" name="scite-9" rel="nofollow" target="_blank">
        Bennett, J., Vengerik, B. (2017, June 12). Behind the CARBANAK Backdoor. Retrieved June 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/04/unit42-cardinal-rat-active-two-years/" name="scite-10" rel="nofollow" target="_blank">
        Grunzweig, J.. (2017, April 20). Cardinal RAT Active for Over Two Years. Retrieved December 8, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2017/02/unit42-menupass-returns-new-malware-new-attacks-japanese-academics-organizations/" name="scite-11" rel="nofollow" target="_blank">
        Miller-Osborn, J. and Grunzweig, J.. (2017, February 16). menuPass Returns with New Malware and New Attacks Against Japanese Academics and Organizations. Retrieved March 1, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2017/02/chches-malware--93d6.html" name="scite-12" rel="nofollow" target="_blank">
        Nakamura, Y.. (2017, February 17). ChChes - Malware that Communicates with C&amp;C Servers Using Cookie Headers. Retrieved March 1, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/rpt-apt28.pdf" name="scite-13" rel="nofollow" target="_blank">
        FireEye. (2015). APT28: A WINDOW INTO RUSSIA’S CYBER ESPIONAGE OPERATIONS?. Retrieved August 19, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fidelissecurity.com/sites/default/files/TA_Fidelis_Turbo_1602_0.pdf" name="scite-14" rel="nofollow" target="_blank">
        Fidelis Cybersecurity. (2016, February 29). The Turbo Campaign, Featuring Derusbi for 64-bit Linux. Retrieved March 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2014/02/21/an-in-depth-analysis-of-linuxebury/" name="scite-15" rel="nofollow" target="_blank">
        M.Léveillé, M.. (2014, February 21). An In-depth Analysis of Linux/Ebury. Retrieved April 19, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2015/12/attack-on-french-diplomat-linked-to-operation-lotus-blossom/" name="scite-16" rel="nofollow" target="_blank">
        Falcone, R. and Miller-Osborn, J.. (2015, December 18). Attack on French Diplomat Linked to Operation Lotus Blossom. Retrieved February 15, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/01/scarlet-mimic-years-long-espionage-targets-minority-activists/" name="scite-17" rel="nofollow" target="_blank">
        Falcone, R. and Miller-Osborn, J.. (2016, January 24). Scarlet Mimic: Years-Long Espionage Campaign Targets Minority Activists. Retrieved February 10, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA17-318A" name="scite-18" rel="nofollow" target="_blank">
        US-CERT. (2017, November 22). Alert (TA17-318A): HIDDEN COBRA – North Korean Remote Administration Tool: FALLCHILL. Retrieved December 7, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://blogs.forcepoint.com/security-labs/playing-cat-mouse-introducing-felismus-malware" name="scite-19" rel="nofollow" target="_blank">
        Somerville, L. and Toro, A. (2017, March 30). Playing Cat &amp; Mouse: Introducing the Felismus Malware. Retrieved November 16, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf" name="scite-20" rel="nofollow" target="_blank">
        ESET. (2017, August). Gazing at Gazer: Turla’s new second stage backdoor. Retrieved September 14, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/introducing-whitebear/81638/" name="scite-21" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research &amp; Analysis Team. (2017, August 30). Introducing WhiteBear. Retrieved September 21, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="22.0">
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-apt29-hammertoss.pdf" name="scite-22" rel="nofollow" target="_blank">
        FireEye Labs. (2015, July). HAMMERTOSS: Stealthy Tactics Define a Russian Cyber Threat Group. Retrieved September 17, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-23">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/sites/default/files/publications/MAR-10135536-F.pdf" name="scite-23" rel="nofollow" target="_blank">
        US-CERT. (2018, February 05). Malware Analysis Report (MAR) - 10135536-F. Retrieved June 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-24">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.novetta.com/wp-content/uploads/2014/11/Executive_Summary-Final_1.pdf" name="scite-24" rel="nofollow" target="_blank">
        Novetta. (n.d.). Operation SMN: Axiom Threat Actor Group Report. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-25">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2010-011114-1830-99" name="scite-25" rel="nofollow" target="_blank">
        Lelli, A. (2010, January 11). Trojan.Hydraq. Retrieved February 20, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-26">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2018/06/07/invisimole-equipped-spyware-undercover/" name="scite-26" rel="nofollow" target="_blank">
        Hromcová, Z. (2018, June 07). InvisiMole: Surprisingly equipped spyware, undercover since 2013. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-27">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/analysis-reports/AR18-221A" name="scite-27" rel="nofollow" target="_blank">
        US-CERT. (2018, August 09). MAR-10135536-17 – North Korean Trojan: KEYMARBLE. Retrieved August 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-28">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2016/09/unit42-sofacys-komplex-os-x-trojan/" name="scite-28" rel="nofollow" target="_blank">
        Dani Creus, Tyler Halfpop, Robert Falcone. (2016, September 26). Sofacy's 'Komplex' OS X Trojan. Retrieved July 8, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-29">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" name="scite-29" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Unraveling the Long Thread of the Sony Attack. Retrieved February 25, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-30">
      <span class="scite-citation-text">
       <a class="external text" href="https://operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Destructive-Malware-Report.pdf" name="scite-30" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Destructive Malware Report. Retrieved March 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-31">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/lazarus-resurfaces-targets-global-banks-bitcoin-users/" name="scite-31" rel="nofollow" target="_blank">
        Sherstobitoff, R. (2018, February 12). Lazarus Resurfaces, Targets Global Banks and Bitcoin Users. Retrieved February 19, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-32">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/analyzing-operation-ghostsecret-attack-seeks-to-steal-data-worldwide/" name="scite-32" rel="nofollow" target="_blank">
        Sherstobitoff, R., Malhotra, A. (2018, April 24). Analyzing Operation GhostSecret: Attack Seeks to Steal Data Worldwide. Retrieved May 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-33">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.trendmicro.com/cloud-content/us/pdfs/security-intelligence/white-papers/wp_dissecting-lurid-apt.pdf" name="scite-33" rel="nofollow" target="_blank">
        Villeneuve, N., Sancho, D. (2011). THE “LURID” DOWNLOADER. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-34">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2018/01/ESET_Turla_Mosquito.pdf" name="scite-34" rel="nofollow" target="_blank">
        ESET, et al. (2018, January). Diplomats in Eastern Europe bitten by a Turla mosquito. Retrieved July 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-35">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-rancor-targeted-attacks-south-east-asia-using-plaintee-ddkong-malware-families/" name="scite-35" rel="nofollow" target="_blank">
        Ash, B., et al. (2018, June 26). RANCOR: Targeted Attacks in South East Asia Using PLAINTEE and DDKONG Malware Families. Retrieved July 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-36">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2017/02/Read-The-Manual.pdf" name="scite-36" rel="nofollow" target="_blank">
        Faou, M. and Boutin, J.. (2017, February). Read The Manual: A Guide to the RTM Banking Trojan. Retrieved March 9, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-37">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.secureworks.com/cyber-threat-intelligence/threats/sakula-malware-family/" name="scite-37" rel="nofollow" target="_blank">
        Dell SecureWorks Counter Threat Unit Threat Intelligence. (2015, July 30). Sakula Malware Family. Retrieved January 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-38">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.trendmicro.com/cloud-content/us/pdfs/security-intelligence/white-papers/wp_the_taidoor_campaign.pdf" name="scite-38" rel="nofollow" target="_blank">
        Trend Micro. (2012). The Taidoor Campaign. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-39">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fidelissecurity.com/threatgeek/2016/10/trickbot-we-missed-you-dyre" name="scite-39" rel="nofollow" target="_blank">
        Reaves, J. (2016, October 15). TrickBot: We Missed you, Dyre. Retrieved August 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-40">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/wcry-ransomware-analysis" name="scite-40" rel="nofollow" target="_blank">
        Counter Threat Unit Research Team. (2017, May 18). WCry Ransomware Analysis. Retrieved March 26, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-41">
      <span class="scite-citation-text">
       <a class="external text" href="https://arxiv.org/ftp/arxiv/papers/1408/1408.1136.pdf" name="scite-41" rel="nofollow" target="_blank">
        Gardiner, J.,  Cova, M., Nagaraja, S. (2014, February). Command &amp; Control Understanding, Denying and Detecting. Retrieved April 20, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-42">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fidelissecurity.com/sites/default/files/FTA_1018_looking_at_the_sky_for_a_dark_comet.pdf" name="scite-42" rel="nofollow" target="_blank">
        Fidelis Cybersecurity. (2015, August 4). Looking at the Sky for a DarkComet. Retrieved April 5, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
