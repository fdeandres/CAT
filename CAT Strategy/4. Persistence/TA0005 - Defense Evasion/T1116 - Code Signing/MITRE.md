<div class="container-fluid">
 <h1>
  Code Signing
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Code signing provides a level of authenticity on a binary from the developer and a guarantee that the binary has not been tampered with.
    <span class="scite-citeref-number" data-reference="Wikipedia Code Signing" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://en.wikipedia.org/wiki/Code_signing" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    However, adversaries are known to use code signing certificates to masquerade malware and tools as legitimate binaries
    <span class="scite-citeref-number" data-reference="Janicab" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="http://www.thesafemac.com/new-signed-malware-called-janicab/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    . The certificates used during an operation may be created, forged, or stolen by the adversary.
    <span class="scite-citeref-number" data-reference="Securelist Digital Certificates" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://securelist.com/why-you-shouldnt-completely-trust-files-signed-with-digital-certificates/68593/" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Symantec Digital Certificates" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="http://www.symantec.com/connect/blogs/how-attackers-steal-private-keys-digital-certificates" target="_blank">
       [4]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Code signing to verify software on first run can be used on modern Windows and macOS/OS X systems. It is not used on Linux due to the decentralized nature of the platform.
    <span class="scite-citeref-number" data-reference="Wikipedia Code Signing" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://en.wikipedia.org/wiki/Code_signing" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Code signing certificates may be used to bypass security policies that require signed code to execute on a system.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1116
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
      macOS, Windows
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
      Binary file metadata
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
      Windows User Account Control
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
     <a href="https://attack.mitre.org/groups/G0067">
      APT37
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0067">
       APT37
      </a>
      has signed its malware with an invalid digital certificates listed as "Tencent Technology (Shenzhen) Company Limited."
      <span class="scite-citeref-number" data-reference="Securelist ScarCruft Jun 2016" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://securelist.com/operation-daybreak/75100/" target="_blank">
         [5]
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
      is sometimes signed with an invalid Authenticode certificate in an apparent effort to make it look more legitimate.
      <span class="scite-citeref-number" data-reference="TrendMicro Patchwork Dec 2017" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" target="_blank">
         [6]
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
      samples were digitally signed with a certificate originally used by Hacking Team that was later leaked and subsequently revoked.
      <span class="scite-citeref-number" data-reference="Palo Alto menuPass Feb 2017" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="http://researchcenter.paloaltonetworks.com/2017/02/unit42-menupass-returns-new-malware-new-attacks-japanese-academics-organizations/" target="_blank">
         [7]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="JPCERT ChChes Feb 2017" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="http://blog.jpcert.or.jp/2017/02/chches-malware--93d6.html" target="_blank">
         [8]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PWC Cloud Hopper Technical Annex April 2017" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" target="_blank">
         [9]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0052">
      CopyKittens
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0052">
       CopyKittens
      </a>
      digitally signed an executable with a stolen certificate from legitimate company AI Squared.
      <span class="scite-citeref-number" data-reference="ClearSky Wilted Tulip July 2017" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="http://www.clearskysec.com/wp-content/uploads/2017/07/Operation_Wilted_Tulip.pdf" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0012">
      Darkhotel
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0012">
       Darkhotel
      </a>
      has used code-signing certificates on its malware that are either forged due to weak keys or stolen.
      <span class="scite-citeref-number" data-reference="Kaspersky Darkhotel" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://securelist.com/files/2014/11/darkhotel_kl_07.11.pdf" target="_blank">
         [11]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0187">
      Daserf
     </a>
    </td>
    <td>
     <p>
      Some
      <a href="https://attack.mitre.org/software/S0187">
       Daserf
      </a>
      samples were signed with a stolen digital certificate.
      <span class="scite-citeref-number" data-reference="Symantec Tick Apr 2016" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://www.symantec.com/connect/blogs/tick-cyberespionage-group-zeros-japan" target="_blank">
         [12]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0091">
      Epic
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0010">
       Turla
      </a>
      has used valid digital certificates from Sysprint AG to sign its
      <a href="https://attack.mitre.org/software/S0091">
       Epic
      </a>
      dropper.
      <span class="scite-citeref-number" data-reference="Kaspersky Turla" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://securelist.com/the-epic-turla-operation/65545/" target="_blank">
         [13]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0046">
      FIN7
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0046">
       FIN7
      </a>
      has signed
      <a href="https://attack.mitre.org/software/S0030">
       Carbanak
      </a>
      payloads with legally purchased code signing certificates.
      <a href="https://attack.mitre.org/groups/G0046">
       FIN7
      </a>
      has also digitally signed their phishing documents, backdoors and other staging tools to bypass security controls.
      <span class="scite-citeref-number" data-reference="FireEye CARBANAK June 2017" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://www.fireeye.com/blog/threat-research/2017/06/behind-the-carbanak-backdoor.html" target="_blank">
         [14]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye FIN7 Aug 2018" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://www.fireeye.com/blog/threat-research/2018/08/fin7-pursuing-an-enigmatic-and-evasive-global-criminal-operation.html" target="_blank">
         [15]
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
      versions are signed with various valid certificates; one was likely faked and issued by Comodo for "Solid Loop Ltd," and another was issued for "Ultimate Computer Support Ltd."
      <span class="scite-citeref-number" data-reference="ESET Gazer Aug 2017" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf" target="_blank">
         [16]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Securelist WhiteBear Aug 2017" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://securelist.com/introducing-whitebear/81638/" target="_blank">
         [17]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0170">
      Helminth
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0170">
       Helminth
      </a>
      samples have been signed with legitimate, compromised code signing certificates owned by software company AI Squared.
      <span class="scite-citeref-number" data-reference="ClearSky OilRig Jan 2017" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="http://www.clearskysec.com/oilrig/" target="_blank">
         [18]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0072">
      Honeybee
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0072">
       Honeybee
      </a>
      uses a dropper called MaoCheng that harvests a stolen digital signature from Adobe Systems.
      <span class="scite-citeref-number" data-reference="McAfee Honeybee" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="https://securingtomorrow.mcafee.com/mcafee-labs/mcafee-uncovers-operation-honeybee-malicious-document-campaign-targeting-humanitarian-aid-groups/" target="_blank">
         [19]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0163">
      Janicab
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0163">
       Janicab
      </a>
      used a valid AppleDeveloperID to sign the code to get past security restrictions.
      <span class="scite-citeref-number" data-reference="Janicab" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="http://www.thesafemac.com/new-signed-malware-called-janicab/" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0065">
      Leviathan
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0065">
       Leviathan
      </a>
      has used stolen code signing certificates used to sign malware.
      <span class="scite-citeref-number" data-reference="FireEye Periscope March 2018" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" target="_blank">
         [20]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0021">
      Molerats
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0021">
       Molerats
      </a>
      has used forged Microsoft code-signing certificates on malware.
      <span class="scite-citeref-number" data-reference="FireEye Operation Molerats" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="https://www.fireeye.com/blog/threat-research/2013/08/operation-molerats-middle-east-cyber-attacks-using-poison-ivy.html" target="_blank">
         [21]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0210">
      Nerex
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0210">
       Nerex
      </a>
      drops a signed Microsoft DLL to disk.
      <span class="scite-citeref-number" data-reference="Symantec Nerex May 2012" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051515-3445-99" target="_blank">
         [22]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0198">
      NETWIRE
     </a>
    </td>
    <td>
     <p>
      The
      <a href="https://attack.mitre.org/software/S0198">
       NETWIRE
      </a>
      client has been signed by fake and invalid digital certificates.
      <span class="scite-citeref-number" data-reference="McAfee Netwire Mar 2015" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="https://securingtomorrow.mcafee.com/mcafee-labs/netwire-rat-behind-recent-targeted-attacks/" target="_blank">
         [23]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0262">
      QuasarRAT
     </a>
    </td>
    <td>
     <p>
      A
      <a href="https://attack.mitre.org/software/S0262">
       QuasarRAT
      </a>
      .dll file is digitally signed by a certificate from AirVPN.
      <span class="scite-citeref-number" data-reference="Volexity Patchwork June 2018" id="scite-ref-24-a" onclick="scrollToRef('scite-24')">
       <sup>
        <a aria-describedby="qtip-23" data-hasqtip="23" href="https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/" target="_blank">
         [24]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0019">
      Regin
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0019">
       Regin
      </a>
      stage 1 modules for 64-bit systems have been found to be signed with fake certificates masquerading as originating from Microsoft Corporation and Broadcom Corporation.
      <span class="scite-citeref-number" data-reference="Kaspersky Regin" id="scite-ref-25-a" onclick="scrollToRef('scite-25')">
       <sup>
        <a aria-describedby="qtip-24" data-hasqtip="24" href="https://securelist.com/files/2014/11/Kaspersky_Lab_whitepaper_Regin_platform_eng.pdf" target="_blank">
         [25]
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
      samples have been signed with a code-signing certificates.
      <span class="scite-citeref-number" data-reference="ESET RTM Feb 2017" id="scite-ref-26-a" onclick="scrollToRef('scite-26')">
       <sup>
        <a aria-describedby="qtip-25" data-hasqtip="25" href="https://www.welivesecurity.com/wp-content/uploads/2017/02/Read-The-Manual.pdf" target="_blank">
         [26]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0195">
      SDelete
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0195">
       SDelete
      </a>
      is digitally signed by Microsoft.
      <span class="scite-citeref-number" data-reference="Microsoft SDelete July 2016" id="scite-ref-27-a" onclick="scrollToRef('scite-27')">
       <sup>
        <a aria-describedby="qtip-26" data-hasqtip="26" href="https://docs.microsoft.com/en-us/sysinternals/downloads/sdelete" target="_blank">
         [27]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0039">
      Suckfly
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0039">
       Suckfly
      </a>
      has used stolen certificates to sign its malware.
      <span class="scite-citeref-number" data-reference="Symantec Suckfly March 2016" id="scite-ref-28-a" onclick="scrollToRef('scite-28')">
       <sup>
        <a aria-describedby="qtip-27" data-hasqtip="27" href="http://www.symantec.com/connect/blogs/suckfly-revealing-secret-life-your-code-signing-certificates" target="_blank">
         [28]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0044">
      Winnti Group
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0044">
       Winnti Group
      </a>
      used stolen certificates to sign its malware.
      <span class="scite-citeref-number" data-reference="Kaspersky Winnti April 2013" id="scite-ref-29-a" onclick="scrollToRef('scite-29')">
       <sup>
        <a aria-describedby="qtip-28" data-hasqtip="28" href="https://securelist.com/winnti-more-than-just-a-game/37029/" target="_blank">
         [29]
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
  Process whitelisting and trusted publishers to verify authenticity of software can help prevent signed malicious or untrusted code from executing on a system.
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-30-a">
   <sup>
    <a aria-describedby="qtip-29" data-hasqtip="29" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [30]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="TechNet Trusted Publishers" id="scite-ref-31-a">
   <sup>
    <a aria-describedby="qtip-30" data-hasqtip="30" href="https://technet.microsoft.com/en-us/library/cc733026.aspx" target="_blank">
     [31]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Securelist Digital Certificates" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="https://securelist.com/why-you-shouldnt-completely-trust-files-signed-with-digital-certificates/68593/" target="_blank">
     [3]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Collect and analyze signing certificate metadata on software that executes within the environment to look for unusual certificate characteristics and outliers.
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
       <a class="external text" href="https://en.wikipedia.org/wiki/Code_signing" name="scite-1" rel="nofollow" target="_blank">
        Wikipedia. (2015, November 10). Code Signing. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.thesafemac.com/new-signed-malware-called-janicab/" name="scite-2" rel="nofollow" target="_blank">
        Thomas. (2013, July 15). New signed malware called Janicab. Retrieved July 17, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/why-you-shouldnt-completely-trust-files-signed-with-digital-certificates/68593/" name="scite-3" rel="nofollow" target="_blank">
        Ladikov, A. (2015, January 29). Why You Shouldn’t Completely Trust Files Signed with Digital Certificates. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/connect/blogs/how-attackers-steal-private-keys-digital-certificates" name="scite-4" rel="nofollow" target="_blank">
        Shinotsuka, H. (2013, February 22). How Attackers Steal Private Keys from Digital Certificates. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/operation-daybreak/75100/" name="scite-5" rel="nofollow" target="_blank">
        Raiu, C., and Ivanov, A. (2016, June 17). Operation Daybreak. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf" name="scite-6" rel="nofollow" target="_blank">
        Lunghi, D., et al. (2017, December). Untangling the Patchwork Cyberespionage Group. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2017/02/unit42-menupass-returns-new-malware-new-attacks-japanese-academics-organizations/" name="scite-7" rel="nofollow" target="_blank">
        Miller-Osborn, J. and Grunzweig, J.. (2017, February 16). menuPass Returns with New Malware and New Attacks Against Japanese Academics and Organizations. Retrieved March 1, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2017/02/chches-malware--93d6.html" name="scite-8" rel="nofollow" target="_blank">
        Nakamura, Y.. (2017, February 17). ChChes - Malware that Communicates with C&amp;C Servers Using Cookie Headers. Retrieved March 1, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" name="scite-9" rel="nofollow" target="_blank">
        PwC and BAE Systems. (2017, April). Operation Cloud Hopper: Technical Annex. Retrieved April 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.clearskysec.com/wp-content/uploads/2017/07/Operation_Wilted_Tulip.pdf" name="scite-10" rel="nofollow" target="_blank">
        ClearSky Cyber Security and Trend Micro. (2017, July). Operation Wilted Tulip: Exposing a cyber espionage apparatus. Retrieved August 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/files/2014/11/darkhotel_kl_07.11.pdf" name="scite-11" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2014, November). The Darkhotel APT A Story of Unusual Hospitality. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/connect/blogs/tick-cyberespionage-group-zeros-japan" name="scite-12" rel="nofollow" target="_blank">
        DiMaggio, J. (2016, April 28). Tick cyberespionage group zeros in on Japan. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/the-epic-turla-operation/65545/" name="scite-13" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2014, August 7). The Epic Turla Operation: Solving some of the mysteries of Snake/Uroburos. Retrieved December 11, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/06/behind-the-carbanak-backdoor.html" name="scite-14" rel="nofollow" target="_blank">
        Bennett, J., Vengerik, B. (2017, June 12). Behind the CARBANAK Backdoor. Retrieved June 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/08/fin7-pursuing-an-enigmatic-and-evasive-global-criminal-operation.html" name="scite-15" rel="nofollow" target="_blank">
        Carr, N., et al. (2018, August 01). On the Hunt for FIN7: Pursuing an Enigmatic and Evasive Global Criminal Operation. Retrieved August 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf" name="scite-16" rel="nofollow" target="_blank">
        ESET. (2017, August). Gazing at Gazer: Turla’s new second stage backdoor. Retrieved September 14, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="17.5">
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/introducing-whitebear/81638/" name="scite-17" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research &amp; Analysis Team. (2017, August 30). Introducing WhiteBear. Retrieved September 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.clearskysec.com/oilrig/" name="scite-18" rel="nofollow" target="_blank">
        ClearSky Cybersecurity. (2017, January 5). Iranian Threat Agent OilRig Delivers Digitally Signed Malware, Impersonates University of Oxford. Retrieved May 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/mcafee-uncovers-operation-honeybee-malicious-document-campaign-targeting-humanitarian-aid-groups/" name="scite-19" rel="nofollow" target="_blank">
        Sherstobitoff, R. (2018, March 02). McAfee Uncovers Operation Honeybee, a Malicious Document Campaign Targeting Humanitarian Aid Groups. Retrieved May 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" name="scite-20" rel="nofollow" target="_blank">
        FireEye. (2018, March 16). Suspected Chinese Cyber Espionage Group (TEMP.Periscope) Targeting U.S. Engineering and Maritime Industries. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2013/08/operation-molerats-middle-east-cyber-attacks-using-poison-ivy.html" name="scite-21" rel="nofollow" target="_blank">
        Villeneuve, N., Haq, H., Moran, N. (2013, August 23). OPERATION MOLERATS: MIDDLE EAST CYBER ATTACKS USING POISON IVY. Retrieved April 1, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2012-051515-3445-99" name="scite-22" rel="nofollow" target="_blank">
        Ladley, F. (2012, May 15). Backdoor.Nerex. Retrieved February 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-23">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/netwire-rat-behind-recent-targeted-attacks/" name="scite-23" rel="nofollow" target="_blank">
        McAfee. (2015, March 2). Netwire RAT Behind Recent Targeted Attacks. Retrieved February 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-24">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/" name="scite-24" rel="nofollow" target="_blank">
        Meltzer, M, et al. (2018, June 07). Patchwork APT Group Targets US Think Tanks. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-25">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/files/2014/11/Kaspersky_Lab_whitepaper_Regin_platform_eng.pdf" name="scite-25" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2014, November 24). THE REGIN PLATFORM NATION-STATE OWNAGE OF GSM NETWORKS. Retrieved December 1, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-26">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2017/02/Read-The-Manual.pdf" name="scite-26" rel="nofollow" target="_blank">
        Faou, M. and Boutin, J.. (2017, February). Read The Manual: A Guide to the RTM Banking Trojan. Retrieved March 9, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-27">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/en-us/sysinternals/downloads/sdelete" name="scite-27" rel="nofollow" target="_blank">
        Russinovich, M. (2016, July 4). SDelete v2.0. Retrieved February 8, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-28">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/connect/blogs/suckfly-revealing-secret-life-your-code-signing-certificates" name="scite-28" rel="nofollow" target="_blank">
        DiMaggio, J.. (2016, March 15). Suckfly: Revealing the secret life of your code signing certificates. Retrieved August 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-29">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/winnti-more-than-just-a-game/37029/" name="scite-29" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2013, April 11). Winnti. More than just a game. Retrieved February 8, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-30">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-30" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-31">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/cc733026.aspx" name="scite-31" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Manage Trusted Publishers. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
