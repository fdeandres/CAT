<div class="container-fluid">
 <h1>
  Install Root Certificate
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Root certificates are used in public key cryptography to identify a root certificate authority (CA). When a root certificate is installed, the system or application will trust certificates in the root's chain of trust that have been signed by the root certificate.
    <span class="scite-citeref-number" data-reference="Wikipedia Root Certificate" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://en.wikipedia.org/wiki/Root_certificate" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    Certificates are commonly used for establishing secure TLS/SSL communications within a web browser. When a user attempts to browse a website that presents a certificate that is not trusted an error message will be displayed to warn the user of the security risk. Depending on the security settings, the browser may not allow the user to establish a connection to the website.
   </p>
   <p>
    Installation of a root certificate on a compromised system would give an adversary a way to degrade the security of that system. Adversaries have used this technique to avoid security warnings prompting users when compromised systems connect over HTTPS to adversary controlled web servers that spoof legitimate websites in order to collect login credentials.
    <span class="scite-citeref-number" data-reference="Operation Emmental" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="http://www.trendmicro.com/cloud-content/us/pdfs/security-intelligence/white-papers/wp-finding-holes-operation-emmental.pdf" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Atypical root certificates have also been pre-installed on systems by the manufacturer or in the software supply chain and were used in conjunction with malware/adware to provide a man-in-the-middle capability for intercepting information transmitted over secure TLS/SSL communications.
    <span class="scite-citeref-number" data-reference="Kaspersky Superfish" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.kaspersky.com/blog/lenovo-pc-with-adware-superfish-preinstalled/7712/" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Root certificates (and their associated chains) can also be cloned and reinstalled. Cloned certificate chains will carry many of the same metadata characteristics of the source and can be used to sign malicious code that may then bypass signature validation tools (ex: Sysinternals, antivirus, etc.) used to block execution and/or uncover artifacts of Persistence.
    <span class="scite-citeref-number" data-reference="SpectorOps Code Signing Dec 2017" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://posts.specterops.io/code-signing-certificate-cloning-attacks-and-defenses-6f98657fc6ec" target="_blank">
       [4]
      </a>
     </sup>
    </span>
   </p>
   <p>
    In macOS, the Ay MaMi malware uses
    <code>
     /usr/bin/security add-trusted-cert -d -r trustRoot -k /Library/Keychains/System.keychain /path/to/malicious/cert
    </code>
    to install a malicious certificate as a trusted root certificate into the system keychain.
    <span class="scite-citeref-number" data-reference="objective-see ay mami 2018" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://objective-see.com/blog/blog_0x26.html" target="_blank">
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
      : T1130
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
      Linux, Windows, macOS
      <br/>
      <br/>
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
      SSL/TLS inspection, Digital certificate logs
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
      Digital Certificate Validation
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
       Contributors:
      </span>
      Itzik Kotler, SafeBreach; Travis Smith, Tripwire; Red Canary; Matt Graeber, @mattifestation, SpecterOps
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
     <a href="https://attack.mitre.org/software/S0160">
      certutil
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0160">
       certutil
      </a>
      can be used to install browser root certificates as a precursor to performing man-in-the-middle between connections to banking websites. Example command:
      <code>
       certutil -addstore -f -user ROOT ProgramData\cert512121.der
      </code>
      .
      <span class="scite-citeref-number" data-reference="Palo Alto Retefe" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://researchcenter.paloaltonetworks.com/2015/08/retefe-banking-trojan-targets-sweden-switzerland-and-japan/" target="_blank">
         [6]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0281">
      Dok
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0281">
       Dok
      </a>
      installs a root certificate to aid in man-in-the-middle actions.
      <span class="scite-citeref-number" data-reference="objsee mac malware 2017" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://objective-see.com/blog/blog_0x25.html" target="_blank">
         [7]
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
      can add a certificate to the Windows store.
      <span class="scite-citeref-number" data-reference="ESET RTM Feb 2017" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.welivesecurity.com/wp-content/uploads/2017/02/Read-The-Manual.pdf" target="_blank">
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
  HTTP Public Key Pinning (HPKP) is one method to mitigate potential man-in-the-middle situations where and adversary uses a mis-issued or fraudulent certificate to intercept encrypted communications by enforcing use of an expected certificate.
  <span class="scite-citeref-number" data-reference="Wikipedia HPKP" id="scite-ref-9-a">
   <sup>
    <a aria-describedby="qtip-8" data-hasqtip="8" href="https://en.wikipedia.org/wiki/HTTP_Public_Key_Pinning" target="_blank">
     [9]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Windows Group Policy can be used to manage root certificates and the
  <code>
   Flags
  </code>
  value of
  <code>
   HKLM\SOFTWARE\Policies\Microsoft\SystemCertificates\Root\ProtectedRoots
  </code>
  can be set to 1 to prevent non-administrator users from making further root installations into their own HKCU certificate store.
  <span class="scite-citeref-number" data-reference="SpectorOps Code Signing Dec 2017" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="https://posts.specterops.io/code-signing-certificate-cloning-attacks-and-defenses-6f98657fc6ec" target="_blank">
     [4]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  A system's root certificates are unlikely to change frequently. Monitor new certificates installed on a system that could be due to malicious activity.
  <span class="scite-citeref-number" data-reference="SpectorOps Code Signing Dec 2017" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="https://posts.specterops.io/code-signing-certificate-cloning-attacks-and-defenses-6f98657fc6ec" target="_blank">
     [4]
    </a>
   </sup>
  </span>
  Check pre-installed certificates on new systems to ensure unnecessary or suspicious certificates are not present. Microsoft provides a list of trustworthy root certificates online and through authroot.stl.
  <span class="scite-citeref-number" data-reference="SpectorOps Code Signing Dec 2017" id="scite-ref-4-a">
   <sup>
    <a aria-describedby="qtip-3" data-hasqtip="3" href="https://posts.specterops.io/code-signing-certificate-cloning-attacks-and-defenses-6f98657fc6ec" target="_blank">
     [4]
    </a>
   </sup>
  </span>
  The Sysinternals Sigcheck utility can also be used (
  <code>
   sigcheck[64].exe -tuv
  </code>
  ) to dump the contents of the certificate store and list valid certificates not rooted to the Microsoft Certificate Trust List.
  <span class="scite-citeref-number" data-reference="Microsoft Sigcheck May 2017" id="scite-ref-10-a">
   <sup>
    <a aria-describedby="qtip-9" data-hasqtip="9" href="https://docs.microsoft.com/sysinternals/downloads/sigcheck" target="_blank">
     [10]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Installed root certificates are located in the Registry under
  <code>
   HKLM\SOFTWARE\Microsoft\EnterpriseCertificates\Root\Certificates\
  </code>
  and
  <code>
   [HKLM or HKCU]\Software[\Policies]\Microsoft\SystemCertificates\Root\Certificates\
  </code>
  . There are a subset of root certificates that are consistent across Windows systems and can be used for comparison:
  <span class="scite-citeref-number" data-reference="Tripwire AppUNBlocker" id="scite-ref-11-a">
   <sup>
    <a aria-describedby="qtip-10" data-hasqtip="10" href="https://www.tripwire.com/state-of-security/off-topic/appunblocker-bypassing-applocker/" target="_blank">
     [11]
    </a>
   </sup>
  </span>
 </p>
 <ul>
  <li>
   18F7C1FCC3090203FD5BAA2F861A754976C8DD25
  </li>
  <li>
   245C97DF7514E7CF2DF8BE72AE957B9E04741E85
  </li>
  <li>
   3B1EFD3A66EA28B16697394703A72CA340A05BD5
  </li>
  <li>
   7F88CD7223F3C813818C994614A89C99FA3B5247
  </li>
  <li>
   8F43288AD272F3103B6FB1428485EA3014C0BCFE
  </li>
  <li>
   A43489159A520F0D93D032CCAF37E7FE20A8B419
  </li>
  <li>
   BE36A4562FB2EE05DBB3D32323ADF445084ED656
  </li>
  <li>
   CDD4EEAE6000AC7F40C3802C171E30148030C072
  </li>
 </ul>
 <h2 class="pt-3" id="references">
  References
 </h2>
 <div class="row">
  <div class="col">
   <ol>
    <li>
     <span class="scite-citation" id="scite-1">
      <span class="scite-citation-text">
       <a class="external text" href="https://en.wikipedia.org/wiki/Root_certificate" name="scite-1" rel="nofollow" target="_blank">
        Wikipedia. (2016, December 6). Root certificate. Retrieved February 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.trendmicro.com/cloud-content/us/pdfs/security-intelligence/white-papers/wp-finding-holes-operation-emmental.pdf" name="scite-2" rel="nofollow" target="_blank">
        Sancho, D., Hacquebord, F., Link, R. (2014, July 22). Finding Holes Operation Emmental. Retrieved February 9, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.kaspersky.com/blog/lenovo-pc-with-adware-superfish-preinstalled/7712/" name="scite-3" rel="nofollow" target="_blank">
        Onuma. (2015, February 24). Superfish: Adware Preinstalled on Lenovo Laptops. Retrieved February 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://posts.specterops.io/code-signing-certificate-cloning-attacks-and-defenses-6f98657fc6ec" name="scite-4" rel="nofollow" target="_blank">
        Graeber, M. (2017, December 22). Code Signing Certificate Cloning Attacks and Defenses. Retrieved April 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://objective-see.com/blog/blog_0x26.html" name="scite-5" rel="nofollow" target="_blank">
        Patrick Wardle. (2018, January 11). Ay MaMi. Retrieved March 19, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2015/08/retefe-banking-trojan-targets-sweden-switzerland-and-japan/" name="scite-6" rel="nofollow" target="_blank">
        Levene, B., Falcone, R., Grunzweig, J., Lee, B., Olson, R. (2015, August 20). Retefe Banking Trojan Targets Sweden, Switzerland and Japan. Retrieved July 3, 2017.
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
       <a class="external text" href="https://objective-see.com/blog/blog_0x25.html" name="scite-7" rel="nofollow" target="_blank">
        Patrick Wardle. (n.d.). Mac Malware of 2017. Retrieved September 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2017/02/Read-The-Manual.pdf" name="scite-8" rel="nofollow" target="_blank">
        Faou, M. and Boutin, J.. (2017, February). Read The Manual: A Guide to the RTM Banking Trojan. Retrieved March 9, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://en.wikipedia.org/wiki/HTTP_Public_Key_Pinning" name="scite-9" rel="nofollow" target="_blank">
        Wikipedia. (2017, February 28). HTTP Public Key Pinning. Retrieved March 31, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/sysinternals/downloads/sigcheck" name="scite-10" rel="nofollow" target="_blank">
        Russinovich, M. et al.. (2017, May 22). Sigcheck. Retrieved April 3, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.tripwire.com/state-of-security/off-topic/appunblocker-bypassing-applocker/" name="scite-11" rel="nofollow" target="_blank">
        Smith, T. (2016, October 27). AppUNBlocker: Bypassing AppLocker. Retrieved December 19, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
