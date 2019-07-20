<div class="container-fluid">
 <h1>
  Credential Dumping
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Credential dumping is the process of obtaining account login and password information, normally in the form of a hash or a clear text password, from the operating system and software. Credentials can then be used to perform Lateral Movement and access restricted information.
   </p>
   <p>
    Several of the tools mentioned in this technique may be used by both adversaries and professional security testers. Additional custom tools likely exist as well.
   </p>
   <h3>
    Windows
   </h3>
   <h4>
    SAM (Security Accounts Manager)
   </h4>
   <p>
    The SAM is a database file that contains local accounts for the host, typically those found with the ‘net user’ command. To enumerate the SAM database, system level access is required. A number of tools can be used to retrieve the SAM file through in-memory techniques:
   </p>
   <ul>
    <li>
     pwdumpx.exe
    </li>
    <li>
     <a href="https://attack.mitre.org/software/S0008">
      gsecdump
     </a>
    </li>
    <li>
     <a href="https://attack.mitre.org/software/S0002">
      Mimikatz
     </a>
    </li>
    <li>
     secretsdump.py
    </li>
   </ul>
   <p>
    Alternatively, the SAM can be extracted from the Registry with
    <a href="https://attack.mitre.org/software/S0075">
     Reg
    </a>
    :
   </p>
   <ul>
    <li>
     <code>
      reg save HKLM\sam sam
     </code>
    </li>
    <li>
     <code>
      reg save HKLM\system system
     </code>
    </li>
   </ul>
   <p>
    Creddump7 can then be used to process the SAM database locally to retrieve hashes.
    <span class="scite-citeref-number" data-reference="GitHub Creddump7" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://github.com/Neohapsis/creddump7" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Notes:Rid 500 account is the local, in-built administrator.Rid 501 is the guest account.User accounts start with a RID of 1,000+.
   </p>
   <h4>
    Cached Credentials
   </h4>
   <p>
    The DCC2 (Domain Cached Credentials version 2) hash, used by Windows Vista and newer caches credentials when the domain controller is unavailable. The number of default cached credentials varies, and this number can be altered per system. This hash does not allow pass-the-hash style attacks. A number of tools can be used to retrieve the SAM file through in-memory techniques.
   </p>
   <ul>
    <li>
     pwdumpx.exe
    </li>
    <li>
     <a href="https://attack.mitre.org/software/S0008">
      gsecdump
     </a>
    </li>
    <li>
     <a href="https://attack.mitre.org/software/S0002">
      Mimikatz
     </a>
    </li>
   </ul>
   <p>
    Alternatively, reg.exe can be used to extract from the Registry and Creddump7 used to gather the credentials.
   </p>
   <p>
    Notes:Cached credentials for Windows Vista are derived using PBKDF2.
   </p>
   <h4>
    Local Security Authority (LSA) Secrets
   </h4>
   <p>
    With SYSTEM access to a host, the LSA secrets often allows trivial access from a local account to domain-based account credentials. The Registry is used to store the LSA secrets. When services are run under the context of local or domain users, their passwords are stored in the Registry. If auto-logon is enabled, this information will be stored in the Registry as well. A number of tools can be used to retrieve the SAM file through in-memory techniques.
   </p>
   <ul>
    <li>
     pwdumpx.exe
    </li>
    <li>
     <a href="https://attack.mitre.org/software/S0008">
      gsecdump
     </a>
    </li>
    <li>
     <a href="https://attack.mitre.org/software/S0002">
      Mimikatz
     </a>
    </li>
    <li>
     secretsdump.py
    </li>
   </ul>
   <p>
    Alternatively, reg.exe can be used to extract from the Registry and Creddump7 used to gather the credentials.
   </p>
   <p>
    Notes:The passwords extracted by his mechanism are UTF-16 encoded, which means that they are returned in plaintext.Windows 10 adds protections for LSA Secrets described in Mitigation.
   </p>
   <h4>
    NTDS from Domain Controller
   </h4>
   <p>
    Active Directory stores information about members of the domain including devices and users to verify credentials and define access rights. The Active Directory domain database is stored in the NTDS.dit file. By default the NTDS file will be located in %SystemRoot%\NTDS\Ntds.dit of a domain controller.
    <span class="scite-citeref-number" data-reference="Wikipedia Active Directory" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://en.wikipedia.org/wiki/Active_Directory" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    The following tools and techniques can be used to enumerate the NTDS file and the contents of the entire Active Directory hashes.
   </p>
   <ul>
    <li>
     Volume Shadow Copy
    </li>
    <li>
     secretsdump.py
    </li>
    <li>
     Using the in-built Windows tool, ntdsutil.exe
    </li>
    <li>
     Invoke-NinjaCopy
    </li>
   </ul>
   <h4>
    Group Policy Preference (GPP) Files
   </h4>
   <p>
    Group Policy Preferences (GPP) are tools that allowed administrators to create domain policies with embedded credentials. These policies, amongst other things, allow administrators to set local accounts.
   </p>
   <p>
    These group policies are stored in SYSVOL on a domain controller, this means that any domain user can view the SYSVOL share and decrypt the password (the AES private key was leaked on-line.
    <span class="scite-citeref-number" data-reference="Microsoft GPP Key" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://msdn.microsoft.com/library/cc422924.aspx" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="SRD GPP" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="http://blogs.technet.com/b/srd/archive/2014/05/13/ms14-025-an-update-for-group-policy-preferences.aspx" target="_blank">
       [4]
      </a>
     </sup>
    </span>
   </p>
   <p>
    The following tools and scripts can be used to gather and decrypt the password file from Group Policy Preference XML files:
   </p>
   <ul>
    <li>
     Metasploit’s post exploitation module: "post/windows/gather/credentials/gpp"
    </li>
    <li>
     Get-GPPPassword
     <span class="scite-citeref-number" data-reference="Obscuresecurity Get-GPPPassword" id="scite-ref-5-a">
      <sup>
       <a aria-describedby="qtip-4" data-hasqtip="4" href="https://obscuresecurity.blogspot.co.uk/2012/05/gpp-password-retrieval-with-powershell.html" target="_blank">
        [5]
       </a>
      </sup>
     </span>
    </li>
    <li>
     gpprefdecrypt.py
    </li>
   </ul>
   <p>
    Notes:On the SYSVOL share, the following can be used to enumerate potential XML files.dir /s * .xml
   </p>
   <h4>
    Service Principal Names (SPNs)
   </h4>
   <p>
    See
    <a href="https://attack.mitre.org/techniques/T1208">
     Kerberoasting
    </a>
    .
   </p>
   <h4>
    Plaintext Credentials
   </h4>
   <p>
    After a user logs on to a system, a variety of credentials are generated and stored in the Local Security Authority Subsystem Service (LSASS) process in memory. These credentials can be harvested by a administrative user or SYSTEM.
   </p>
   <p>
    SSPI (Security Support Provider Interface) functions as a common interface to several Security Support Providers (SSPs): A Security Support Provider is a dynamic-link library (DLL) that makes one or more security packages available to applications.
   </p>
   <p>
    The following SSPs can be used to access credentials:
   </p>
   <p>
    Msv: Interactive logons, batch logons, and service logons are done through the MSV authentication package.Wdigest: The Digest Authentication protocol is designed for use with Hypertext Transfer Protocol (HTTP) and Simple Authentication Security Layer (SASL) exchanges.
    <span class="scite-citeref-number" data-reference="TechNet Blogs Credential Protection" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://blogs.technet.microsoft.com/askpfeplat/2016/04/18/the-importance-of-kb2871997-and-kb2928120-for-credential-protection/" target="_blank">
       [6]
      </a>
     </sup>
    </span>
    Kerberos: Preferred for mutual client-server domain authentication in Windows 2000 and later.CredSSP:  Provides SSO and Network Level Authentication for Remote Desktop Services.
    <span class="scite-citeref-number" data-reference="Microsoft CredSSP" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc749211(v=ws.10)" target="_blank">
       [7]
      </a>
     </sup>
    </span>
    The following tools can be used to enumerate credentials:
   </p>
   <ul>
    <li>
     <a href="https://attack.mitre.org/software/S0005">
      Windows Credential Editor
     </a>
    </li>
    <li>
     <a href="https://attack.mitre.org/software/S0002">
      Mimikatz
     </a>
    </li>
   </ul>
   <p>
    As well as in-memory techniques, the LSASS process memory can be dumped from the target host and analyzed on a local system.
   </p>
   <p>
    For example, on the target host use procdump:
   </p>
   <ul>
    <li>
     <code>
      procdump -ma lsass.exe lsass_dump
     </code>
    </li>
   </ul>
   <p>
    Locally, mimikatz can be run:
   </p>
   <ul>
    <li>
     <code>
      sekurlsa::Minidump lsassdump.dmp
     </code>
    </li>
    <li>
     <code>
      sekurlsa::logonPasswords
     </code>
    </li>
   </ul>
   <h4>
    DCSync
   </h4>
   <p>
    DCSync is a variation on credential dumping which can be used to acquire sensitive information from a domain controller. Rather than executing recognizable malicious code, the action works by abusing the domain controller's  application programming interface (API)
    <span class="scite-citeref-number" data-reference="Microsoft DRSR Dec 2017" id="scite-ref-8-a">
     <sup>
      <a aria-describedby="qtip-7" data-hasqtip="7" href="https://msdn.microsoft.com/library/cc228086.aspx" target="_blank">
       [8]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Microsoft GetNCCChanges" id="scite-ref-9-a">
     <sup>
      <a aria-describedby="qtip-8" data-hasqtip="8" href="https://msdn.microsoft.com/library/dd207691.aspx" target="_blank">
       [9]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Samba DRSUAPI" id="scite-ref-10-a">
     <sup>
      <a aria-describedby="qtip-9" data-hasqtip="9" href="https://wiki.samba.org/index.php/DRSUAPI" target="_blank">
       [10]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Wine API samlib.dll" id="scite-ref-11-a">
     <sup>
      <a aria-describedby="qtip-10" data-hasqtip="10" href="https://source.winehq.org/WineAPI/samlib.html" target="_blank">
       [11]
      </a>
     </sup>
    </span>
    to simulate the replication process from a remote domain controller. Any members of the Administrators, Domain Admins, Enterprise Admin groups or computer accounts on the domain controller are able to run DCSync to pull password data
    <span class="scite-citeref-number" data-reference="ADSecurity Mimikatz DCSync" id="scite-ref-12-a">
     <sup>
      <a aria-describedby="qtip-11" data-hasqtip="11" href="https://adsecurity.org/?p=1729" target="_blank">
       [12]
      </a>
     </sup>
    </span>
    from Active Directory, which may include current and historical hashes of potentially useful accounts such as KRBTGT and Administrators. The hashes can then in turn be used to create a Golden Ticket for use in
    <a href="https://attack.mitre.org/techniques/T1097">
     Pass the Ticket
    </a>
    <span class="scite-citeref-number" data-reference="Harmj0y Mimikatz and DCSync" id="scite-ref-13-a">
     <sup>
      <a aria-describedby="qtip-12" data-hasqtip="12" href="http://www.harmj0y.net/blog/redteaming/mimikatz-and-dcsync-and-extrasids-oh-my/" target="_blank">
       [13]
      </a>
     </sup>
    </span>
    or change an account's password as noted in
    <a href="https://attack.mitre.org/techniques/T1098">
     Account Manipulation
    </a>
    .
    <span class="scite-citeref-number" data-reference="InsiderThreat ChangeNTLM July 2017" id="scite-ref-14-a">
     <sup>
      <a aria-describedby="qtip-13" data-hasqtip="13" href="https://blog.stealthbits.com/manipulating-user-passwords-with-mimikatz-SetNTLM-ChangeNTLM" target="_blank">
       [14]
      </a>
     </sup>
    </span>
    DCSync functionality has been included in the "lsadump" module in Mimikatz.
    <span class="scite-citeref-number" data-reference="GitHub Mimikatz lsadump Module" id="scite-ref-15-a">
     <sup>
      <a aria-describedby="qtip-14" data-hasqtip="14" href="https://github.com/gentilkiwi/mimikatz/wiki/module-~-lsadump" target="_blank">
       [15]
      </a>
     </sup>
    </span>
    Lsadump also includes NetSync, which performs DCSync over a legacy replication protocol.
    <span class="scite-citeref-number" data-reference="Microsoft NRPC Dec 2017" id="scite-ref-16-a">
     <sup>
      <a aria-describedby="qtip-15" data-hasqtip="15" href="https://msdn.microsoft.com/library/cc237008.aspx" target="_blank">
       [16]
      </a>
     </sup>
    </span>
   </p>
   <h3>
    Linux
   </h3>
   <h4>
    Proc filesystem
   </h4>
   <p>
    The /proc filesystem on Linux contains a great deal of information regarding the state of the running operating system. Processes running with root privileges can use this facility to scrape live memory of other running programs. If any of these programs store passwords in clear text or password hashes in memory, these values can then be harvested for either usage or brute force attacks, respectively. This functionality has been implemented in the
    <a href="https://attack.mitre.org/software/S0179">
     MimiPenguin
    </a>
    , an open source tool inspired by
    <a href="https://attack.mitre.org/software/S0002">
     Mimikatz
    </a>
    . The tool dumps process memory, then harvests passwords and hashes by looking for text strings and regex patterns for how given applications such as Gnome Keyring, sshd, and Apache use memory to store such authentication artifacts.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1003
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
      Windows, Linux, macOS
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
      Administrator, SYSTEM, root
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
      API monitoring, Process monitoring, PowerShell logs, Process command-line parameters
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
       CAPEC ID:
      </span>
      <a href="https://capec.mitre.org/data/definitions/567.html" target="_blank">
       CAPEC-567
      </a>
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
      </span>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Contributors:
      </span>
      Vincent Le Toux; Ed Williams, Trustwave, SpiderLabs
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
     <a href="https://attack.mitre.org/groups/G0006">
      APT1
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0006">
       APT1
      </a>
      has been known to use credential dumping.
      <span class="scite-citeref-number" data-reference="Mandiant APT1" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf" target="_blank">
         [17]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
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
      regularly deploys both publicly available and custom password retrieval tools on victims.
      <span class="scite-citeref-number" data-reference="ESET Sednit Part 2" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part-2.pdf" target="_blank">
         [18]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="DOJ GRU Indictment Jul 2018" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="https://www.justice.gov/file/1080281/download" target="_blank">
         [19]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0022">
      APT3
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0022">
       APT3
      </a>
      has used a tool to dump credentials by injecting itself into lsass.exe and triggering with the argument "dig." The group has also used a tools to dump passwords from browsers.
      <span class="scite-citeref-number" data-reference="Symantec Buckeye" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="http://www.symantec.com/connect/blogs/buckeye-cyberespionage-group-shifts-gaze-us-hong-kong" target="_blank">
         [20]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0050">
      APT32
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0050">
       APT32
      </a>
      used Mimikatz, GetPassword_x64, and  customized versions of Windows Credential Dumper, HookChangePassword, and Outlook Credential Dumper to harvest credentials.
      <span class="scite-citeref-number" data-reference="Cybereason Oceanlotus May 2017" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="https://www.cybereason.com/blog/operation-cobalt-kitty-apt" target="_blank">
         [21]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Cybereason Cobalt Kitty 2017" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="https://cdn2.hubspot.net/hubfs/3354902/Cybereason%20Labs%20Analysis%20Operation%20Cobalt%20Kitty.pdf" target="_blank">
         [22]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0064">
      APT33
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0064">
       APT33
      </a>
      has used a variety of publicly available tools like
      <a href="https://attack.mitre.org/software/S0349">
       LaZagne
      </a>
      ,
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      , Gpppassword, SniffPass, and ProcDump to dump credentials.
      <span class="scite-citeref-number" data-reference="Symantec Elfin Mar 2019" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="https://www.symantec.com/blogs/threat-intelligence/elfin-apt33-espionage" target="_blank">
         [23]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye APT33 Guardrail" id="scite-ref-24-a" onclick="scrollToRef('scite-24')">
       <sup>
        <a aria-describedby="qtip-23" data-hasqtip="23" href="https://www.fireeye.com/blog/threat-research/2018/12/overruled-containing-a-potentially-destructive-adversary.html" target="_blank">
         [24]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
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
      has used a credential stealer known as ZUMKONG that can harvest usernames and passwords stored in browsers.
      <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-25-a" onclick="scrollToRef('scite-25')">
       <sup>
        <a aria-describedby="qtip-24" data-hasqtip="24" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
         [25]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0087">
      APT39
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0087">
       APT39
      </a>
      has used Mimikatz, Ncrack, Windows Credential Editor and ProcDump to dump credentials.
      <span class="scite-citeref-number" data-reference="FireEye APT39 Jan 2019" id="scite-ref-26-a" onclick="scrollToRef('scite-26')">
       <sup>
        <a aria-describedby="qtip-25" data-hasqtip="25" href="https://www.fireeye.com/blog/threat-research/2019/01/apt39-iranian-cyber-espionage-group-focused-on-personal-information.html" target="_blank">
         [26]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0373">
      Astaroth
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0373">
       Astaroth
      </a>
      uses an external software known as NetPass to recover passwords.
      <span class="scite-citeref-number" data-reference="Cybereason Astaroth Feb 2019" id="scite-ref-27-a" onclick="scrollToRef('scite-27')">
       <sup>
        <a aria-describedby="qtip-26" data-hasqtip="26" href="https://www.cybereason.com/blog/information-stealing-malware-targeting-brazil-full-research" target="_blank">
         [27]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0001">
      Axiom
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0001">
       Axiom
      </a>
      has been known to dump credentials.
      <span class="scite-citeref-number" data-reference="Novetta-Axiom" id="scite-ref-28-a" onclick="scrollToRef('scite-28')">
       <sup>
        <a aria-describedby="qtip-27" data-hasqtip="27" href="http://www.novetta.com/wp-content/uploads/2014/11/Executive_Summary-Final_1.pdf" target="_blank">
         [28]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0344">
      Azorult
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0344">
       Azorult
      </a>
      can dump credentials from victim browsers.
      <span class="scite-citeref-number" data-reference="Unit42 Azorult Nov 2018" id="scite-ref-29-a" onclick="scrollToRef('scite-29')">
       <sup>
        <a aria-describedby="qtip-28" data-hasqtip="28" href="https://researchcenter.paloaltonetworks.com/2018/11/unit42-new-wine-old-bottle-new-azorult-variant-found-findmyname-campaign-using-fallout-exploit-kit/" target="_blank">
         [29]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0093">
      Backdoor.Oldrea
     </a>
    </td>
    <td>
     <p>
      Some
      <a href="https://attack.mitre.org/software/S0093">
       Backdoor.Oldrea
      </a>
      samples contain a publicly available Web browser password recovery tool.
      <span class="scite-citeref-number" data-reference="Symantec Dragonfly" id="scite-ref-30-a" onclick="scrollToRef('scite-30')">
       <sup>
        <a aria-describedby="qtip-29" data-hasqtip="29" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/Dragonfly_Threat_Against_Western_Energy_Suppliers.pdf" target="_blank">
         [30]
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
      has used various tools to perform credential dumping.
      <span class="scite-citeref-number" data-reference="Secureworks BRONZE BUTLER Oct 2017" id="scite-ref-31-a" onclick="scrollToRef('scite-31')">
       <sup>
        <a aria-describedby="qtip-30" data-hasqtip="30" href="https://www.secureworks.com/research/bronze-butler-targets-japanese-businesses" target="_blank">
         [31]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0119">
      Cachedump
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0119">
       Cachedump
      </a>
      can extract cached password hashes from a system’s registry.
      <span class="scite-citeref-number" data-reference="Mandiant APT1" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf" target="_blank">
         [17]
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
      obtains Windows logon password details.
      <span class="scite-citeref-number" data-reference="FireEye CARBANAK June 2017" id="scite-ref-32-a" onclick="scrollToRef('scite-32')">
       <sup>
        <a aria-describedby="qtip-31" data-hasqtip="31" href="https://www.fireeye.com/blog/threat-research/2017/06/behind-the-carbanak-backdoor.html" target="_blank">
         [32]
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
      steals credentials stored inside Internet Explorer.
      <span class="scite-citeref-number" data-reference="PWC Cloud Hopper Technical Annex April 2017" id="scite-ref-33-a" onclick="scrollToRef('scite-33')">
       <sup>
        <a aria-describedby="qtip-32" data-hasqtip="32" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" target="_blank">
         [33]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0003">
      Cleaver
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0003">
       Cleaver
      </a>
      has been known to dump credentials.
      <span class="scite-citeref-number" data-reference="Cylance Cleaver" id="scite-ref-34-a" onclick="scrollToRef('scite-34')">
       <sup>
        <a aria-describedby="qtip-33" data-hasqtip="33" href="https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf" target="_blank">
         [34]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0154">
      Cobalt Strike
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0154">
       Cobalt Strike
      </a>
      can recover hashed passwords.
      <span class="scite-citeref-number" data-reference="cobaltstrike manual" id="scite-ref-35-a" onclick="scrollToRef('scite-35')">
       <sup>
        <a aria-describedby="qtip-34" data-hasqtip="34" href="https://cobaltstrike.com/downloads/csmanual38.pdf" target="_blank">
         [35]
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
      collects user credentials, including passwords, for various programs and browsers, including popular instant messaging applications, Web browsers, and email clients. Windows account hashes, domain accounts, and LSA secrets are also collected, as are WLAN keys.
      <span class="scite-citeref-number" data-reference="F-Secure The Dukes" id="scite-ref-36-a" onclick="scrollToRef('scite-36')">
       <sup>
        <a aria-describedby="qtip-35" data-hasqtip="35" href="https://www.f-secure.com/documents/996508/1030745/dukes_whitepaper.pdf" target="_blank">
         [36]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0046">
      CozyCar
     </a>
    </td>
    <td>
     <p>
      Password stealer and NTLM stealer modules in
      <a href="https://attack.mitre.org/software/S0046">
       CozyCar
      </a>
      harvest stored credentials from the victim, including credentials used as part of Windows NTLM user authentication.
      <a href="https://attack.mitre.org/software/S0046">
       CozyCar
      </a>
      has also executed
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      for further victim penetration.
      <span class="scite-citeref-number" data-reference="F-Secure CozyDuke" id="scite-ref-37-a" onclick="scrollToRef('scite-37')">
       <sup>
        <a aria-describedby="qtip-36" data-hasqtip="36" href="https://www.f-secure.com/documents/996508/1030745/CozyDuke" target="_blank">
         [37]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0115">
      Crimson
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0115">
       Crimson
      </a>
      contains a module to steal credentials from Web browsers on the victim machine.
      <span class="scite-citeref-number" data-reference="Proofpoint Operation Transparent Tribe March 2016" id="scite-ref-38-a" onclick="scrollToRef('scite-38')">
       <sup>
        <a aria-describedby="qtip-37" data-hasqtip="37" href="https://www.proofpoint.com/sites/default/files/proofpoint-operation-transparent-tribe-threat-insight-en.pdf" target="_blank">
         [38]
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
      <a href="https://attack.mitre.org/software/S0187">
       Daserf
      </a>
      leverages
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      and
      <a href="https://attack.mitre.org/software/S0005">
       Windows Credential Editor
      </a>
      to steal credentials.
      <span class="scite-citeref-number" data-reference="Symantec Tick Apr 2016" id="scite-ref-39-a" onclick="scrollToRef('scite-39')">
       <sup>
        <a aria-describedby="qtip-38" data-hasqtip="38" href="https://www.symantec.com/connect/blogs/tick-cyberespionage-group-zeros-japan" target="_blank">
         [39]
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
      dropped and executed SecretsDump and CrackMapExec, tools that can dump password hashes.
      <span class="scite-citeref-number" data-reference="US-CERT TA18-074A" id="scite-ref-40-a" onclick="scrollToRef('scite-40')">
       <sup>
        <a aria-describedby="qtip-39" data-hasqtip="39" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" target="_blank">
         [40]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT APT Energy Oct 2017" id="scite-ref-41-a" onclick="scrollToRef('scite-41')">
       <sup>
        <a aria-describedby="qtip-40" data-hasqtip="40" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" target="_blank">
         [41]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Core Security Impacket" id="scite-ref-42-a" onclick="scrollToRef('scite-42')">
       <sup>
        <a aria-describedby="qtip-41" data-hasqtip="41" href="https://www.coresecurity.com/corelabs-research/open-source-tools/impacket" target="_blank">
         [42]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0367">
      Emotet
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0367">
       Emotet
      </a>
      has been observed dropping browser and password grabber modules including
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      .
      <span class="scite-citeref-number" data-reference="Trend Micro Emotet Jan 2019" id="scite-ref-43-a" onclick="scrollToRef('scite-43')">
       <sup>
        <a aria-describedby="qtip-42" data-hasqtip="42" href="https://documents.trendmicro.com/assets/white_papers/ExploringEmotetsActivities_Final.pdf" target="_blank">
         [43]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
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
      contains an implementation of
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      to gather credentials from memory.
      <span class="scite-citeref-number" data-reference="Github PowerShell Empire" id="scite-ref-44-a" onclick="scrollToRef('scite-44')">
       <sup>
        <a aria-describedby="qtip-43" data-hasqtip="43" href="https://github.com/PowerShellEmpire/Empire" target="_blank">
         [44]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0120">
      Fgdump
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0120">
       Fgdump
      </a>
      can dump Windows password hashes.
      <span class="scite-citeref-number" data-reference="Mandiant APT1" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf" target="_blank">
         [17]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0053">
      FIN5
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0053">
       FIN5
      </a>
      has dumped credentials from victims. Specifically, the group has used the tool GET5 Penetrator to look for remote login and hard-coded credentials.
      <span class="scite-citeref-number" data-reference="DarkReading FireEye FIN5 Oct 2015" id="scite-ref-45-a" onclick="scrollToRef('scite-45')">
       <sup>
        <a aria-describedby="qtip-44" data-hasqtip="44" href="https://www.darkreading.com/analytics/prolific-cybercrime-gang-favors-legit-login-credentials/d/d-id/1322645?" target="_blank">
         [45]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Mandiant FIN5 GrrCON Oct 2016" id="scite-ref-46-a" onclick="scrollToRef('scite-46')">
       <sup>
        <a aria-describedby="qtip-45" data-hasqtip="45" href="https://www.youtube.com/watch?v=fevGZs0EQu8" target="_blank">
         [46]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0037">
      FIN6
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0037">
       FIN6
      </a>
      has used
      <a href="https://attack.mitre.org/software/S0005">
       Windows Credential Editor
      </a>
      for credential dumping, as well as Metasploit’s
      <a href="https://attack.mitre.org/software/S0029">
       PsExec
      </a>
      NTDSGRAB module to obtain a copy of the victim's Active Directory database.
      <br/>
      <br/>
      <span class="scite-citeref-number" data-reference="FireEye FIN6 April 2016" id="scite-ref-47-a" onclick="scrollToRef('scite-47')">
       <sup>
        <a aria-describedby="qtip-46" data-hasqtip="46" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin6.pdf" target="_blank">
         [47]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye FIN6 Apr 2019" id="scite-ref-48-a" onclick="scrollToRef('scite-48')">
       <sup>
        <a aria-describedby="qtip-47" data-hasqtip="47" href="https://www.fireeye.com/blog/threat-research/2019/04/pick-six-intercepting-a-fin6-intrusion.html" target="_blank">
         [48]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0061">
      FIN8
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0061">
       FIN8
      </a>
      harvests credentials using Invoke-Mimikatz or Windows Credentials Editor (WCE).
      <span class="scite-citeref-number" data-reference="FireEye Know Your Enemy FIN8 Aug 2016" id="scite-ref-49-a" onclick="scrollToRef('scite-49')">
       <sup>
        <a aria-describedby="qtip-48" data-hasqtip="48" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" target="_blank">
         [49]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0342">
      GreyEnergy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0342">
       GreyEnergy
      </a>
      has a module for
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      to collect Windows credentials from the victim’s machine.
      <span class="scite-citeref-number" data-reference="ESET GreyEnergy Oct 2018" id="scite-ref-50-a" onclick="scrollToRef('scite-50')">
       <sup>
        <a aria-describedby="qtip-49" data-hasqtip="49" href="https://www.welivesecurity.com/wp-content/uploads/2018/10/ESET_GreyEnergy.pdf" target="_blank">
         [50]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0008">
      gsecdump
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0008">
       gsecdump
      </a>
      can dump Windows password hashes and LSA secrets.
      <span class="scite-citeref-number" data-reference="TrueSec Gsecdump" id="scite-ref-51-a" onclick="scrollToRef('scite-51')">
       <sup>
        <a aria-describedby="qtip-50" data-hasqtip="50" href="https://www.truesec.se/sakerhet/verktyg/saakerhet/gsecdump_v2.0b5" target="_blank">
         [51]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0132">
      H1N1
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0132">
       H1N1
      </a>
      dumps usernames and passwords from Firefox, Internet Explorer, and Outlook.
      <span class="scite-citeref-number" data-reference="Cisco H1N1 Part 2" id="scite-ref-52-a" onclick="scrollToRef('scite-52')">
       <sup>
        <a aria-describedby="qtip-51" data-hasqtip="51" href="http://blogs.cisco.com/security/h1n1-technical-analysis-reveals-new-capabilities-part-2" target="_blank">
         [52]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0232">
      HOMEFRY
     </a>
    </td>
    <td>
     <p>
      can perform credential dumping.
      <span class="scite-citeref-number" data-reference="FireEye Periscope March 2018" id="scite-ref-53-a" onclick="scrollToRef('scite-53')">
       <sup>
        <a aria-describedby="qtip-52" data-hasqtip="52" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" target="_blank">
         [53]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0376">
      HOPLIGHT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0376">
       HOPLIGHT
      </a>
      has the capability to harvest credentials and passwords.
      <span class="scite-citeref-number" data-reference="US-CERT HOPLIGHT Apr 2019" id="scite-ref-54-a" onclick="scrollToRef('scite-54')">
       <sup>
        <a aria-describedby="qtip-53" data-hasqtip="53" href="https://www.us-cert.gov/ncas/analysis-reports/AR19-100A" target="_blank">
         [54]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0357">
      Impacket
     </a>
    </td>
    <td>
     <p>
      SecretsDump and
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      modules within
      <a href="https://attack.mitre.org/software/S0357">
       Impacket
      </a>
      can perform credential dumping to obtain account and password information.
      <span class="scite-citeref-number" data-reference="Impacket Tools" id="scite-ref-55-a" onclick="scrollToRef('scite-55')">
       <sup>
        <a aria-describedby="qtip-54" data-hasqtip="54" href="https://www.secureauth.com/labs/open-source-tools/impacket" target="_blank">
         [55]
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
      has dumped credentials, including by using
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      .
      <span class="scite-citeref-number" data-reference="Villeneuve et al 2014" id="scite-ref-56-a" onclick="scrollToRef('scite-56')">
       <sup>
        <a aria-describedby="qtip-55" data-hasqtip="55" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/wp-operation-ke3chang.pdf" target="_blank">
         [56]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="NCC Group APT15 Alive and Strong" id="scite-ref-57-a" onclick="scrollToRef('scite-57')">
       <sup>
        <a aria-describedby="qtip-56" data-hasqtip="56" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/" target="_blank">
         [57]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0250">
      Koadic
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0250">
       Koadic
      </a>
      can gather hashed passwords by dumping SAM/SECURITY hive and gathers domain controller hashes from NTDS.
      <span class="scite-citeref-number" data-reference="Github Koadic" id="scite-ref-58-a" onclick="scrollToRef('scite-58')">
       <sup>
        <a aria-describedby="qtip-57" data-hasqtip="57" href="https://github.com/zerosum0x0/koadic" target="_blank">
         [58]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0356">
      KONNI
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0356">
       KONNI
      </a>
      can steal profiles (containing credential information) from Firefox, Chrome, and Opera.
      <span class="scite-citeref-number" data-reference="Talos Konni May 2017" id="scite-ref-59-a" onclick="scrollToRef('scite-59')">
       <sup>
        <a aria-describedby="qtip-58" data-hasqtip="58" href="https://blog.talosintelligence.com/2017/05/konni-malware-under-radar-for-years.html" target="_blank">
         [59]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0349">
      LaZagne
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0349">
       LaZagne
      </a>
      can perform credential dumping to obtain account and password information.
      <span class="scite-citeref-number" data-reference="GitHub LaZagne Dec 2018" id="scite-ref-60-a" onclick="scrollToRef('scite-60')">
       <sup>
        <a aria-describedby="qtip-59" data-hasqtip="59" href="https://github.com/AlessandroZ/LaZagne" target="_blank">
         [60]
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
      <a href="https://attack.mitre.org/groups/G0032">
       Lazarus Group
      </a>
      leveraged
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      to extract Windows Credentials of currently logged-in users and steals passwords stored in browsers.
      <span class="scite-citeref-number" data-reference="Lazarus KillDisk" id="scite-ref-61-a" onclick="scrollToRef('scite-61')">
       <sup>
        <a aria-describedby="qtip-60" data-hasqtip="60" href="https://www.welivesecurity.com/2018/04/03/lazarus-killdisk-central-american-casino/" target="_blank">
         [61]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0077">
      Leafminer
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0077">
       Leafminer
      </a>
      used several tools for retrieving login and password information.
      <span class="scite-citeref-number" data-reference="Symantec Leafminer July 2018" id="scite-ref-62-a" onclick="scrollToRef('scite-62')">
       <sup>
        <a aria-describedby="qtip-61" data-hasqtip="61" href="https://www.symantec.com/blogs/threat-intelligence/leafminer-espionage-middle-east" target="_blank">
         [62]
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
      has used publicly available tools to dump password hashes.
      <span class="scite-citeref-number" data-reference="FireEye APT40 March 2019" id="scite-ref-63-a" onclick="scrollToRef('scite-63')">
       <sup>
        <a aria-describedby="qtip-62" data-hasqtip="62" href="https://www.fireeye.com/blog/threat-research/2019/03/apt40-examining-a-china-nexus-espionage-actor.html" target="_blank">
         [63]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0121">
      Lslsass
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0121">
       Lslsass
      </a>
      can dump active logon session password hashes from the lsass process.
      <span class="scite-citeref-number" data-reference="Mandiant APT1" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf" target="_blank">
         [17]
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
      stole domain credentials from Microsoft Active Directory Domain Controller and leveraged
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      .
      <span class="scite-citeref-number" data-reference="FireEye APT35 2018" id="scite-ref-64-a" onclick="scrollToRef('scite-64')">
       <sup>
        <a aria-describedby="qtip-63" data-hasqtip="63" href="https://www.fireeye.com/content/dam/collateral/en/mtrends-2018.pdf" target="_blank">
         [64]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0167">
      Matroyshka
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0167">
       Matroyshka
      </a>
      is capable of stealing Outlook passwords.
      <span class="scite-citeref-number" data-reference="ClearSky Wilted Tulip July 2017" id="scite-ref-65-a" onclick="scrollToRef('scite-65')">
       <sup>
        <a aria-describedby="qtip-64" data-hasqtip="64" href="http://www.clearskysec.com/wp-content/uploads/2017/07/Operation_Wilted_Tulip.pdf" target="_blank">
         [65]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="CopyKittens Nov 2015" id="scite-ref-66-a" onclick="scrollToRef('scite-66')">
       <sup>
        <a aria-describedby="qtip-65" data-hasqtip="65" href="https://s3-eu-west-1.amazonaws.com/minervaresearchpublic/CopyKittens/CopyKittens.pdf" target="_blank">
         [66]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0045">
      menuPass
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0045">
       menuPass
      </a>
      has used a modified version of pentesting tools wmiexec.vbs and secretsdump.py to dump credentials.
      <span class="scite-citeref-number" data-reference="PWC Cloud Hopper Technical Annex April 2017" id="scite-ref-33-a" onclick="scrollToRef('scite-33')">
       <sup>
        <a aria-describedby="qtip-32" data-hasqtip="32" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" target="_blank">
         [33]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Github AD-Pentest-Script" id="scite-ref-67-a" onclick="scrollToRef('scite-67')">
       <sup>
        <a aria-describedby="qtip-66" data-hasqtip="66" href="https://github.com/Twi1ight/AD-Pentest-Script/blob/master/wmiexec.vbs" target="_blank">
         [67]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0002">
      Mimikatz
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      performs credential dumping to obtain account and password information useful in gaining access to additional systems and enterprise network resources. It contains functionality to acquire information about credentials in many ways, including from the LSA, SAM table, credential vault, DCSync/NetSync, and DPAPI.
      <span class="scite-citeref-number" data-reference="Deply Mimikatz" id="scite-ref-68-a" onclick="scrollToRef('scite-68')">
       <sup>
        <a aria-describedby="qtip-67" data-hasqtip="67" href="https://github.com/gentilkiwi/mimikatz" target="_blank">
         [68]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="GitHub Mimikatz lsadump Module" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://github.com/gentilkiwi/mimikatz/wiki/module-~-lsadump" target="_blank">
         [15]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Directory Services Internals DPAPI Backup Keys Oct 2015" id="scite-ref-69-a" onclick="scrollToRef('scite-69')">
       <sup>
        <a aria-describedby="qtip-68" data-hasqtip="68" href="https://www.dsinternals.com/en/retrieving-dpapi-backup-keys-from-active-directory/" target="_blank">
         [69]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="NCSC Joint Report Public Tools" id="scite-ref-70-a" onclick="scrollToRef('scite-70')">
       <sup>
        <a aria-describedby="qtip-69" data-hasqtip="69" href="https://s3.eu-west-1.amazonaws.com/ncsc-content/files/Joint%20report%20on%20publicly%20available%20hacking%20tools%20%28NCSC%29.pdf" target="_blank">
         [70]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0179">
      MimiPenguin
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0179">
       MimiPenguin
      </a>
      can dump process memory and extract clear-text credentials.
      <span class="scite-citeref-number" data-reference="MimiPenguin GitHub May 2017" id="scite-ref-71-a" onclick="scrollToRef('scite-71')">
       <sup>
        <a aria-describedby="qtip-70" data-hasqtip="70" href="https://github.com/huntergregal/mimipenguin" target="_blank">
         [71]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0080">
      Mivast
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0080">
       Mivast
      </a>
      has the capability to gather NTLM password information.
      <span class="scite-citeref-number" data-reference="Symantec Backdoor.Mivast" id="scite-ref-72-a" onclick="scrollToRef('scite-72')">
       <sup>
        <a aria-describedby="qtip-71" data-hasqtip="71" href="http://www.symantec.com/security_response/writeup.jsp?docid=2015-020623-0740-99&amp;tabid=2" target="_blank">
         [72]
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
      used the public tool BrowserPasswordDump10 to dump passwords saved in browsers on victims.
      <span class="scite-citeref-number" data-reference="DustySky" id="scite-ref-73-a" onclick="scrollToRef('scite-73')">
       <sup>
        <a aria-describedby="qtip-72" data-hasqtip="72" href="https://www.clearskysec.com/wp-content/uploads/2016/01/Operation%20DustySky_TLP_WHITE.pdf" target="_blank">
         [73]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0069">
      MuddyWater
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0069">
       MuddyWater
      </a>
      has performed credential dumping with
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      ,
      <a href="https://attack.mitre.org/software/S0349">
       LaZagne
      </a>
      , and other tools, including by dumping passwords saved in victim web browsers and email.
      <span class="scite-citeref-number" data-reference="Unit 42 MuddyWater Nov 2017" id="scite-ref-74-a" onclick="scrollToRef('scite-74')">
       <sup>
        <a aria-describedby="qtip-73" data-hasqtip="73" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-muddying-the-water-targeted-attacks-in-the-middle-east/" target="_blank">
         [74]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Symantec MuddyWater Dec 2018" id="scite-ref-75-a" onclick="scrollToRef('scite-75')">
       <sup>
        <a aria-describedby="qtip-74" data-hasqtip="74" href="https://www.symantec.com/blogs/threat-intelligence/seedworm-espionage-group" target="_blank">
         [75]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0056">
      Net Crawler
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0056">
       Net Crawler
      </a>
      uses credential dumpers such as
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      and
      <a href="https://attack.mitre.org/software/S0005">
       Windows Credential Editor
      </a>
      to extract cached credentials from Windows systems.
      <span class="scite-citeref-number" data-reference="Cylance Cleaver" id="scite-ref-34-a" onclick="scrollToRef('scite-34')">
       <sup>
        <a aria-describedby="qtip-33" data-hasqtip="33" href="https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf" target="_blank">
         [34]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0014">
      Night Dragon
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0014">
       Night Dragon
      </a>
      has dumped account hashes with
      <a href="https://attack.mitre.org/groups/G0008">
       Carbanak
      </a>
      and cracked them with Cain &amp; Abel.
      <span class="scite-citeref-number" data-reference="McAfee Night Dragon" id="scite-ref-76-a" onclick="scrollToRef('scite-76')">
       <sup>
        <a aria-describedby="qtip-75" data-hasqtip="75" href="https://securingtomorrow.mcafee.com/wp-content/uploads/2011/02/McAfee_NightDragon_wp_draft_to_customersv1-1.pdf" target="_blank">
         [76]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0368">
      NotPetya
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0368">
       NotPetya
      </a>
      contains a modified version of
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      to help gather credentials that are later used for lateral movement.
      <span class="scite-citeref-number" data-reference="Talos Nyetya June 2017" id="scite-ref-77-a" onclick="scrollToRef('scite-77')">
       <sup>
        <a aria-describedby="qtip-76" data-hasqtip="76" href="https://blog.talosintelligence.com/2017/06/worldwide-ransomware-variant.html" target="_blank">
         [77]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="US-CERT NotPetya 2017" id="scite-ref-78-a" onclick="scrollToRef('scite-78')">
       <sup>
        <a aria-describedby="qtip-77" data-hasqtip="77" href="https://www.us-cert.gov/ncas/alerts/TA17-181A" target="_blank">
         [78]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="NCSC Joint Report Public Tools" id="scite-ref-70-a" onclick="scrollToRef('scite-70')">
       <sup>
        <a aria-describedby="qtip-69" data-hasqtip="69" href="https://s3.eu-west-1.amazonaws.com/ncsc-content/files/Joint%20report%20on%20publicly%20available%20hacking%20tools%20%28NCSC%29.pdf" target="_blank">
         [70]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0049">
      OilRig
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0049">
       OilRig
      </a>
      has used credential dumping tools such as
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      and
      <a href="https://attack.mitre.org/software/S0349">
       LaZagne
      </a>
      to steal credentials to accounts logged into the compromised system and to Outlook Web Access.
      <span class="scite-citeref-number" data-reference="Unit 42 Playbook Dec 2017" id="scite-ref-79-a" onclick="scrollToRef('scite-79')">
       <sup>
        <a aria-describedby="qtip-78" data-hasqtip="78" href="https://pan-unit42.github.io/playbook_viewer/" target="_blank">
         [79]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye APT34 Webinar Dec 2017" id="scite-ref-80-a" onclick="scrollToRef('scite-80')">
       <sup>
        <a aria-describedby="qtip-79" data-hasqtip="79" href="https://www.brighttalk.com/webcast/10703/296317/apt34-new-targeted-attack-in-the-middle-east" target="_blank">
         [80]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="FireEye APT35 2018" id="scite-ref-64-a" onclick="scrollToRef('scite-64')">
       <sup>
        <a aria-describedby="qtip-63" data-hasqtip="63" href="https://www.fireeye.com/content/dam/collateral/en/mtrends-2018.pdf" target="_blank">
         [64]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0138">
      OLDBAIT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0138">
       OLDBAIT
      </a>
      collects credentials from Internet Explorer, Mozilla Firefox, Eudora, and several email clients.
      <span class="scite-citeref-number" data-reference="FireEye APT28" id="scite-ref-81-a" onclick="scrollToRef('scite-81')">
       <sup>
        <a aria-describedby="qtip-80" data-hasqtip="80" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/rpt-apt28.pdf" target="_blank">
         [81]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0365">
      Olympic Destroyer
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0365">
       Olympic Destroyer
      </a>
      contains a module that tries to obtain credentials from LSASS, similar to
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      . These credentials are used with
      <a href="https://attack.mitre.org/software/S0029">
       PsExec
      </a>
      and
      <a href="https://attack.mitre.org/techniques/T1047">
       Windows Management Instrumentation
      </a>
      to help the malware propagate itself across a network.
      <span class="scite-citeref-number" data-reference="Talos Olympic Destroyer 2018" id="scite-ref-82-a" onclick="scrollToRef('scite-82')">
       <sup>
        <a aria-describedby="qtip-81" data-hasqtip="81" href="https://blog.talosintelligence.com/2018/02/olympic-destroyer.html" target="_blank">
         [82]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0052">
      OnionDuke
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0052">
       OnionDuke
      </a>
      steals credentials from its victims.
      <span class="scite-citeref-number" data-reference="F-Secure The Dukes" id="scite-ref-36-a" onclick="scrollToRef('scite-36')">
       <sup>
        <a aria-describedby="qtip-35" data-hasqtip="35" href="https://www.f-secure.com/documents/996508/1030745/dukes_whitepaper.pdf" target="_blank">
         [36]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0040">
      Patchwork
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0040">
       Patchwork
      </a>
      dumped the login data database from
      <code>
       \AppData\Local\Google\Chrome\User Data\Default\Login Data
      </code>
      .
      <span class="scite-citeref-number" data-reference="Cymmetria Patchwork" id="scite-ref-83-a" onclick="scrollToRef('scite-83')">
       <sup>
        <a aria-describedby="qtip-82" data-hasqtip="82" href="https://s3-us-west-2.amazonaws.com/cymmetria-blog/public/Unveiling_Patchwork.pdf" target="_blank">
         [83]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0048">
      PinchDuke
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0048">
       PinchDuke
      </a>
      steals credentials from compromised hosts.
      <a href="https://attack.mitre.org/software/S0048">
       PinchDuke
      </a>
      's credential stealing functionality is believed to be based on the source code of the Pinch credential stealing malware (also known as LdPinch). Credentials targeted by
      <a href="https://attack.mitre.org/software/S0048">
       PinchDuke
      </a>
      include ones associated with The Bat!, Yahoo!, Mail.ru, Passport.Net, Google Talk, Netscape Navigator, Mozilla Firefox, Mozilla Thunderbird, Internet Explorer, Microsoft Outlook, WinInet Credential Cache, and Lightweight Directory Access Protocol (LDAP).
      <span class="scite-citeref-number" data-reference="F-Secure The Dukes" id="scite-ref-36-a" onclick="scrollToRef('scite-36')">
       <sup>
        <a aria-describedby="qtip-35" data-hasqtip="35" href="https://www.f-secure.com/documents/996508/1030745/dukes_whitepaper.pdf" target="_blank">
         [36]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0068">
      PLATINUM
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0068">
       PLATINUM
      </a>
      has used keyloggers that are also capable of dumping credentials.
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0033">
      Poseidon Group
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0033">
       Poseidon Group
      </a>
      conducts credential dumping on victims, with a focus on obtaining credentials belonging to domain and database servers.
      <span class="scite-citeref-number" data-reference="Kaspersky Poseidon Group" id="scite-ref-84-a" onclick="scrollToRef('scite-84')">
       <sup>
        <a aria-describedby="qtip-83" data-hasqtip="83" href="https://securelist.com/poseidon-group-a-targeted-attack-boutique-specializing-in-global-cyber-espionage/73673/" target="_blank">
         [84]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0378">
      PoshC2
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0378">
       PoshC2
      </a>
      contains an implementation of
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      to gather credentials from memory.
      <span class="scite-citeref-number" data-reference="GitHub PoshC2" id="scite-ref-85-a" onclick="scrollToRef('scite-85')">
       <sup>
        <a aria-describedby="qtip-84" data-hasqtip="84" href="https://github.com/nettitude/PoshC2" target="_blank">
         [85]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0194">
      PowerSploit
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0194">
       PowerSploit
      </a>
      contains a collection of Exfiltration modules that can harvest credentials from Group Policy Preferences, Windows vault credential objects, or using
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      .
      <span class="scite-citeref-number" data-reference="GitHub PowerSploit May 2012" id="scite-ref-86-a" onclick="scrollToRef('scite-86')">
       <sup>
        <a aria-describedby="qtip-85" data-hasqtip="85" href="https://github.com/PowerShellMafia/PowerSploit" target="_blank">
         [86]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PowerSploit Documentation" id="scite-ref-87-a" onclick="scrollToRef('scite-87')">
       <sup>
        <a aria-describedby="qtip-86" data-hasqtip="86" href="http://powersploit.readthedocs.io" target="_blank">
         [87]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0371">
      POWERTON
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0371">
       POWERTON
      </a>
      has the ability to dump password hashes.
      <span class="scite-citeref-number" data-reference="FireEye APT33 Guardrail" id="scite-ref-24-a" onclick="scrollToRef('scite-24')">
       <sup>
        <a aria-describedby="qtip-23" data-hasqtip="23" href="https://www.fireeye.com/blog/threat-research/2018/12/overruled-containing-a-potentially-destructive-adversary.html" target="_blank">
         [24]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0113">
      Prikormka
     </a>
    </td>
    <td>
     <p>
      A module in
      <a href="https://attack.mitre.org/software/S0113">
       Prikormka
      </a>
      collects passwords stored in applications installed on the victim.
      <span class="scite-citeref-number" data-reference="ESET Operation Groundbait" id="scite-ref-88-a" onclick="scrollToRef('scite-88')">
       <sup>
        <a aria-describedby="qtip-87" data-hasqtip="87" href="http://www.welivesecurity.com/wp-content/uploads/2016/05/Operation-Groundbait.pdf" target="_blank">
         [88]
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
      executes
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      using PowerShell and can also perform pass-the-ticket and use Lazagne for harvesting credentials.
      <span class="scite-citeref-number" data-reference="GitHub Pupy" id="scite-ref-89-a" onclick="scrollToRef('scite-89')">
       <sup>
        <a aria-describedby="qtip-88" data-hasqtip="88" href="https://github.com/n1nj4sec/pupy" target="_blank">
         [89]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0006">
      pwdump
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0006">
       pwdump
      </a>
      can be used to dump credentials.
      <span class="scite-citeref-number" data-reference="Wikipedia pwdump" id="scite-ref-90-a" onclick="scrollToRef('scite-90')">
       <sup>
        <a aria-describedby="qtip-89" data-hasqtip="89" href="https://en.wikipedia.org/wiki/Pwdump" target="_blank">
         [90]
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
      <a href="https://attack.mitre.org/software/S0262">
       QuasarRAT
      </a>
      can obtain passwords from common browsers and FTP clients.
      <span class="scite-citeref-number" data-reference="GitHub QuasarRAT" id="scite-ref-91-a" onclick="scrollToRef('scite-91')">
       <sup>
        <a aria-describedby="qtip-90" data-hasqtip="90" href="https://github.com/quasar/QuasarRAT" target="_blank">
         [91]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Volexity Patchwork June 2018" id="scite-ref-92-a" onclick="scrollToRef('scite-92')">
       <sup>
        <a aria-describedby="qtip-91" data-hasqtip="91" href="https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/" target="_blank">
         [92]
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
      can gather browser usernames and passwords.
      <span class="scite-citeref-number" data-reference="Accenture Hogfish April 2018" id="scite-ref-93-a" onclick="scrollToRef('scite-93')">
       <sup>
        <a aria-describedby="qtip-92" data-hasqtip="92" href="https://www.accenture.com/t20180423T055005Z_w_/se-en/_acnmedia/PDF-76/Accenture-Hogfish-Threat-Analysis.pdf" target="_blank">
         [93]
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
      <a href="https://attack.mitre.org/software/S0125">
       Remsec
      </a>
      can dump the SAM database.
      <span class="scite-citeref-number" data-reference="Kaspersky ProjectSauron Technical Analysis" id="scite-ref-94-a" onclick="scrollToRef('scite-94')">
       <sup>
        <a aria-describedby="qtip-93" data-hasqtip="93" href="https://securelist.com/files/2016/07/The-ProjectSauron-APT_Technical_Analysis_KL.pdf" target="_blank">
         [94]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0240">
      ROKRAT
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0240">
       ROKRAT
      </a>
      steals credentials stored in Web browsers by querying the sqlite database and leveraging the Windows Vault mechanism.
      <span class="scite-citeref-number" data-reference="Talos Group123" id="scite-ref-95-a" onclick="scrollToRef('scite-95')">
       <sup>
        <a aria-describedby="qtip-94" data-hasqtip="94" href="https://blog.talosintelligence.com/2018/01/korea-in-crosshairs.html" target="_blank">
         [95]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0054">
      Sowbug
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0054">
       Sowbug
      </a>
      has used credential dumping tools.
      <span class="scite-citeref-number" data-reference="Symantec Sowbug Nov 2017" id="scite-ref-96-a" onclick="scrollToRef('scite-96')">
       <sup>
        <a aria-describedby="qtip-95" data-hasqtip="95" href="https://www.symantec.com/connect/blogs/sowbug-cyber-espionage-group-targets-south-american-and-southeast-asian-governments" target="_blank">
         [96]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0038">
      Stealth Falcon
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0038">
       Stealth Falcon
      </a>
      malware gathers passwords from multiple sources, including Windows Credential Vault, Internet Explorer, Firefox, Chrome, and Outlook.
      <span class="scite-citeref-number" data-reference="Citizen Lab Stealth Falcon May 2016" id="scite-ref-97-a" onclick="scrollToRef('scite-97')">
       <sup>
        <a aria-describedby="qtip-96" data-hasqtip="96" href="https://citizenlab.org/2016/05/stealth-falcon/" target="_blank">
         [97]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0086">
      Stolen Pencil
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0086">
       Stolen Pencil
      </a>
      gathers credentials using
      <a href="https://attack.mitre.org/groups/G0002">
       Moafee
      </a>
      and Procdump.
      <span class="scite-citeref-number" data-reference="Netscout Stolen Pencil Dec 2018" id="scite-ref-98-a" onclick="scrollToRef('scite-98')">
       <sup>
        <a aria-describedby="qtip-97" data-hasqtip="97" href="https://asert.arbornetworks.com/stolen-pencil-campaign-targets-academia/" target="_blank">
         [98]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0041">
      Strider
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0041">
       Strider
      </a>
      has registered its persistence module on domain controllers as a Windows LSA (Local System Authority) password filter to dump credentials any time a domain, local user, or administrator logs in or changes a password.
      <span class="scite-citeref-number" data-reference="Kaspersky ProjectSauron Full Report" id="scite-ref-99-a" onclick="scrollToRef('scite-99')">
       <sup>
        <a aria-describedby="qtip-98" data-hasqtip="98" href="https://securelist.com/files/2016/07/The-ProjectSauron-APT_research_KL.pdf" target="_blank">
         [99]
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
      used a signed credential-dumping tool to obtain victim account credentials.
      <span class="scite-citeref-number" data-reference="Symantec Suckfly May 2016" id="scite-ref-100-a" onclick="scrollToRef('scite-100')">
       <sup>
        <a aria-describedby="qtip-99" data-hasqtip="99" href="http://www.symantec.com/connect/blogs/indian-organizations-targeted-suckfly-attacks" target="_blank">
         [100]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0088">
      TEMP.Veles
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0088">
       TEMP.Veles
      </a>
      has used
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      and a custom tool, SecHack, to harvest credentials.
      <span class="scite-citeref-number" data-reference="FireEye TRITON 2019" id="scite-ref-101-a" onclick="scrollToRef('scite-101')">
       <sup>
        <a aria-describedby="qtip-100" data-hasqtip="100" href="https://www.fireeye.com/blog/threat-research/2019/04/triton-actor-ttp-profile-custom-attack-tools-detections.html" target="_blank">
         [101]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0027">
      Threat Group-3390
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0027">
       Threat Group-3390
      </a>
      actors have used
      <a href="https://attack.mitre.org/software/S0008">
       gsecdump
      </a>
      and a modified version of
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      called Wrapikatz to dump credentials. They have also dumped credentials from domain controllers.
      <span class="scite-citeref-number" data-reference="Dell TG-3390" id="scite-ref-102-a" onclick="scrollToRef('scite-102')">
       <sup>
        <a aria-describedby="qtip-101" data-hasqtip="101" href="https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage" target="_blank">
         [102]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="SecureWorks BRONZE UNION June 2017" id="scite-ref-103-a" onclick="scrollToRef('scite-103')">
       <sup>
        <a aria-describedby="qtip-102" data-hasqtip="102" href="https://www.secureworks.com/research/bronze-union" target="_blank">
         [103]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0094">
      Trojan.Karagany
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0094">
       Trojan.Karagany
      </a>
      can dump passwords and save them into
      <code>
       \ProgramData\Mail\MailAg\pwds.txt
      </code>
      .
      <span class="scite-citeref-number" data-reference="Symantec Dragonfly" id="scite-ref-30-a" onclick="scrollToRef('scite-30')">
       <sup>
        <a aria-describedby="qtip-29" data-hasqtip="29" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/Dragonfly_Threat_Against_Western_Energy_Suppliers.pdf" target="_blank">
         [30]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0130">
      Unknown Logger
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0130">
       Unknown Logger
      </a>
      is capable of stealing usernames and passwords from browsers on the victim machine.
      <span class="scite-citeref-number" data-reference="Forcepoint Monsoon" id="scite-ref-104-a" onclick="scrollToRef('scite-104')">
       <sup>
        <a aria-describedby="qtip-103" data-hasqtip="103" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" target="_blank">
         [104]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0005">
      Windows Credential Editor
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0005">
       Windows Credential Editor
      </a>
      can dump credentials.
      <span class="scite-citeref-number" data-reference="Amplia WCE" id="scite-ref-105-a" onclick="scrollToRef('scite-105')">
       <sup>
        <a aria-describedby="qtip-104" data-hasqtip="104" href="http://www.ampliasecurity.com/research/wcefaq.html" target="_blank">
         [105]
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
 <h3>
  Windows
 </h3>
 <p>
  Monitor/harden access to LSASS and SAM table with tools that allow process whitelisting. Limit credential overlap across systems to prevent lateral movement opportunities using
  <a href="https://attack.mitre.org/techniques/T1078">
   Valid Accounts
  </a>
  if passwords and hashes are obtained. Ensure that local administrator accounts have complex, unique passwords across all systems on the network. Do not put user or admin domain accounts in the local administrator groups across systems unless they are tightly controlled, as this is often equivalent to having a local administrator account with the same password on all systems. Follow best practices for design and administration of an enterprise network to limit privileged account use across administrative tiers.
  <span class="scite-citeref-number" data-reference="Microsoft Securing Privileged Access" id="scite-ref-106-a">
   <sup>
    <a aria-describedby="qtip-105" data-hasqtip="105" href="https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access-reference-material#a-nameesaebmaesae-administrative-forest-design-approach" target="_blank">
     [106]
    </a>
   </sup>
  </span>
 </p>
 <p>
  On Windows 8.1 and Windows Server 2012 R2, enable Protected Process Light for LSA.
  <span class="scite-citeref-number" data-reference="Microsoft LSA" id="scite-ref-107-a">
   <sup>
    <a aria-describedby="qtip-106" data-hasqtip="106" href="https://technet.microsoft.com/en-us/library/dn408187.aspx" target="_blank">
     [107]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Identify and block potentially malicious software that may be used to dump credentials by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-108-a">
   <sup>
    <a aria-describedby="qtip-107" data-hasqtip="107" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [108]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-109-a">
   <sup>
    <a aria-describedby="qtip-108" data-hasqtip="108" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [109]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-110-a">
   <sup>
    <a aria-describedby="qtip-109" data-hasqtip="109" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [110]
    </a>
   </sup>
  </span>
  or Software Restriction Policies
  <span class="scite-citeref-number" data-reference="Corio 2008" id="scite-ref-111-a">
   <sup>
    <a aria-describedby="qtip-110" data-hasqtip="110" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" target="_blank">
     [111]
    </a>
   </sup>
  </span>
  where appropriate.
  <span class="scite-citeref-number" data-reference="TechNet Applocker vs SRP" id="scite-ref-112-a">
   <sup>
    <a aria-describedby="qtip-111" data-hasqtip="111" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" target="_blank">
     [112]
    </a>
   </sup>
  </span>
 </p>
 <p>
  With Windows 10, Microsoft implemented new protections called Credential Guard to protect the LSA secrets that can be used to obtain credentials through forms of credential dumping. It is not configured by default and has hardware and firmware system requirements.
  <span class="scite-citeref-number" data-reference="TechNet Credential Guard" id="scite-ref-113-a">
   <sup>
    <a aria-describedby="qtip-112" data-hasqtip="112" href="https://technet.microsoft.com/en-us/itpro/windows/keep-secure/credential-guard" target="_blank">
     [113]
    </a>
   </sup>
  </span>
  It also does not protect against all forms of credential dumping.
  <span class="scite-citeref-number" data-reference="GitHub SHB Credential Guard" id="scite-ref-114-a">
   <sup>
    <a aria-describedby="qtip-113" data-hasqtip="113" href="https://github.com/iadgov/Secure-Host-Baseline/tree/master/Credential%20Guard" target="_blank">
     [114]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Manage the access control list for "Replicating Directory Changes" and other permissions associated with domain controller replication.
  <span class="scite-citeref-number" data-reference="AdSecurity DCSync Sept 2015" id="scite-ref-115-a">
   <sup>
    <a aria-describedby="qtip-114" data-hasqtip="114" href="https://adsecurity.org/?p=1729" target="_blank">
     [115]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Microsoft Replication ACL" id="scite-ref-116-a">
   <sup>
    <a aria-describedby="qtip-115" data-hasqtip="115" href="https://support.microsoft.com/help/303972/how-to-grant-the-replicating-directory-changes-permission-for-the-micr" target="_blank">
     [116]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Consider disabling or restricting NTLM traffic.
  <span class="scite-citeref-number" data-reference="Microsoft Disable NTLM Nov 2012" id="scite-ref-117-a">
   <sup>
    <a aria-describedby="qtip-116" data-hasqtip="116" href="https://technet.microsoft.com/library/jj865668.aspx" target="_blank">
     [117]
    </a>
   </sup>
  </span>
 </p>
 <h3>
  Linux
 </h3>
 <p>
  Scraping the passwords from memory requires root privileges. Follow best practices in restricting access to escalated privileges to avoid hostile programs from accessing such sensitive regions of memory.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <h3>
  Windows
 </h3>
 <p>
  Common credential dumpers such as
  <a href="https://attack.mitre.org/software/S0002">
   Mimikatz
  </a>
  access the LSA Subsystem Service (LSASS) process by opening the process, locating the LSA secrets key, and decrypting the sections in memory where credential details are stored. Credential dumpers may also use methods for reflective
  <a href="https://attack.mitre.org/techniques/T1055">
   Process Injection
  </a>
  to reduce potential indicators of malicious activity.
 </p>
 <p>
  Hash dumpers open the Security Accounts Manager (SAM) on the local file system (%SystemRoot%/system32/config/SAM) or create a dump of the Registry SAM key to access stored account password hashes. Some hash dumpers will open the local file system as a device and parse to the SAM table to avoid file access defenses. Others will make an in-memory copy of the SAM table before reading hashes. Detection of compromised
  <a href="https://attack.mitre.org/techniques/T1078">
   Valid Accounts
  </a>
  in-use by adversaries may help as well.
 </p>
 <p>
  On Windows 8.1 and Windows Server 2012 R2, monitor Windows Logs for LSASS.exe creation to verify that LSASS started as a protected process.
 </p>
 <p>
  Monitor processes and command-line arguments for program execution that may be indicative of credential dumping. Remote access tools may contain built-in features or incorporate existing tools like
  <a href="https://attack.mitre.org/software/S0002">
   Mimikatz
  </a>
  .
  <a href="https://attack.mitre.org/techniques/T1086">
   PowerShell
  </a>
  scripts also exist that contain credential dumping functionality, such as PowerSploit's Invoke-Mimikatz module,
  <span class="scite-citeref-number" data-reference="Powersploit" id="scite-ref-118-a">
   <sup>
    <a aria-describedby="qtip-117" data-hasqtip="117" href="https://github.com/mattifestation/PowerSploit" target="_blank">
     [118]
    </a>
   </sup>
  </span>
  which may require additional logging features to be configured in the operating system to collect necessary information for analysis.
 </p>
 <p>
  Monitor domain controller logs for replication requests and other unscheduled activity possibly associated with DCSync.
  <span class="scite-citeref-number" data-reference="Microsoft DRSR Dec 2017" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="https://msdn.microsoft.com/library/cc228086.aspx" target="_blank">
     [8]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Microsoft GetNCCChanges" id="scite-ref-9-a">
   <sup>
    <a aria-describedby="qtip-8" data-hasqtip="8" href="https://msdn.microsoft.com/library/dd207691.aspx" target="_blank">
     [9]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Samba DRSUAPI" id="scite-ref-10-a">
   <sup>
    <a aria-describedby="qtip-9" data-hasqtip="9" href="https://wiki.samba.org/index.php/DRSUAPI" target="_blank">
     [10]
    </a>
   </sup>
  </span>
  Note: Domain controllers may not log replication requests originating from the default domain controller account.
  <span class="scite-citeref-number" data-reference="Harmj0y DCSync Sept 2015" id="scite-ref-119-a">
   <sup>
    <a aria-describedby="qtip-118" data-hasqtip="118" href="http://www.harmj0y.net/blog/redteaming/mimikatz-and-dcsync-and-extrasids-oh-my/" target="_blank">
     [119]
    </a>
   </sup>
  </span>
  . Also monitor for network protocols
  <span class="scite-citeref-number" data-reference="Microsoft DRSR Dec 2017" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="https://msdn.microsoft.com/library/cc228086.aspx" target="_blank">
     [8]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Microsoft NRPC Dec 2017" id="scite-ref-16-a">
   <sup>
    <a aria-describedby="qtip-15" data-hasqtip="15" href="https://msdn.microsoft.com/library/cc237008.aspx" target="_blank">
     [16]
    </a>
   </sup>
  </span>
  and other replication requests
  <span class="scite-citeref-number" data-reference="Microsoft SAMR" id="scite-ref-120-a">
   <sup>
    <a aria-describedby="qtip-119" data-hasqtip="119" href="https://msdn.microsoft.com/library/cc245496.aspx" target="_blank">
     [120]
    </a>
   </sup>
  </span>
  from IPs not associated with known domain controllers.
  <span class="scite-citeref-number" data-reference="AdSecurity DCSync Sept 2015" id="scite-ref-115-a">
   <sup>
    <a aria-describedby="qtip-114" data-hasqtip="114" href="https://adsecurity.org/?p=1729" target="_blank">
     [115]
    </a>
   </sup>
  </span>
 </p>
 <h3>
  Linux
 </h3>
 <p>
  To obtain the passwords and hashes stored in memory, processes must open a maps file in the /proc filesystem for the process being analyzed. This file is stored under the path
  <code>
   /proc/
   <pid>
    /maps
   </pid>
  </code>
  , where the
  <code>
   <pid>
   </pid>
  </code>
  directory is the unique pid of the program being interrogated for such authentication data. The AuditD monitoring tool, which ships stock in many Linux distributions, can be used to watch for hostile processes opening this file in the proc file system, alerting on the pid, process name, and arguments of such programs.
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
       <a class="external text" href="https://github.com/Neohapsis/creddump7" name="scite-1" rel="nofollow" target="_blank">
        Flathers, R. (2018, February 19). creddump7. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://en.wikipedia.org/wiki/Active_Directory" name="scite-2" rel="nofollow" target="_blank">
        Wikipedia. (2018, March 10). Active Directory. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/cc422924.aspx" name="scite-3" rel="nofollow" target="_blank">
        Microsoft. (n.d.). 2.2.1.1.4 Password Encryption. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://blogs.technet.com/b/srd/archive/2014/05/13/ms14-025-an-update-for-group-policy-preferences.aspx" name="scite-4" rel="nofollow" target="_blank">
        Security Research and Defense. (2014, May 13). MS14-025: An Update for Group Policy Preferences. Retrieved January 28, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://obscuresecurity.blogspot.co.uk/2012/05/gpp-password-retrieval-with-powershell.html" name="scite-5" rel="nofollow" target="_blank">
        Campbell, C. (2012, May 24). GPP Password Retrieval with PowerShell. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://blogs.technet.microsoft.com/askpfeplat/2016/04/18/the-importance-of-kb2871997-and-kb2928120-for-credential-protection/" name="scite-6" rel="nofollow" target="_blank">
        Wilson, B. (2016, April 18). The Importance of KB2871997 and KB2928120 for Credential Protection. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc749211(v=ws.10)" name="scite-7" rel="nofollow" target="_blank">
        Microsoft. (2008, July 25). Credential Security Service Provider and SSO for Terminal Services Logon. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/cc228086.aspx" name="scite-8" rel="nofollow" target="_blank">
        Microsoft. (2017, December 1). MS-DRSR Directory Replication Service (DRS) Remote Protocol. Retrieved December 4, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/dd207691.aspx" name="scite-9" rel="nofollow" target="_blank">
        Microsoft. (n.d.). IDL_DRSGetNCChanges (Opnum 3). Retrieved December 4, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://wiki.samba.org/index.php/DRSUAPI" name="scite-10" rel="nofollow" target="_blank">
        SambaWiki. (n.d.). DRSUAPI. Retrieved December 4, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://source.winehq.org/WineAPI/samlib.html" name="scite-11" rel="nofollow" target="_blank">
        Wine API. (n.d.). samlib.dll. Retrieved December 4, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://adsecurity.org/?p=1729" name="scite-12" rel="nofollow" target="_blank">
        Metcalf, S. (2015, September 25). Mimikatz DCSync Usage, Exploitation, and Detection. Retrieved August 7, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.harmj0y.net/blog/redteaming/mimikatz-and-dcsync-and-extrasids-oh-my/" name="scite-13" rel="nofollow" target="_blank">
        Schroeder, W. (2015, September 22). Mimikatz and DCSync and ExtraSids, Oh My. Retrieved August 7, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.stealthbits.com/manipulating-user-passwords-with-mimikatz-SetNTLM-ChangeNTLM" name="scite-14" rel="nofollow" target="_blank">
        Warren, J. (2017, July 11). Manipulating User Passwords with Mimikatz. Retrieved December 4, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/gentilkiwi/mimikatz/wiki/module-~-lsadump" name="scite-15" rel="nofollow" target="_blank">
        Deply, B., Le Toux, V. (2016, June 5). module ~ lsadump. Retrieved August 7, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/cc237008.aspx" name="scite-16" rel="nofollow" target="_blank">
        Microsoft. (2017, December 1). MS-NRPC - Netlogon Remote Protocol. Retrieved December 6, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf" name="scite-17" rel="nofollow" target="_blank">
        Mandiant. (n.d.). APT1 Exposing One of China’s Cyber Espionage Units. Retrieved July 18, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part-2.pdf" name="scite-18" rel="nofollow" target="_blank">
        ESET. (2016, October). En Route with Sednit - Part 2: Observing the Comings and Goings. Retrieved November 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.justice.gov/file/1080281/download" name="scite-19" rel="nofollow" target="_blank">
        Mueller, R. (2018, July 13). Indictment - United States of America vs. VIKTOR BORISOVICH NETYKSHO, et al. Retrieved September 13, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/connect/blogs/buckeye-cyberespionage-group-shifts-gaze-us-hong-kong" name="scite-20" rel="nofollow" target="_blank">
        Symantec Security Response. (2016, September 6). Buckeye cyberespionage group shifts gaze from US to Hong Kong. Retrieved September 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cybereason.com/blog/operation-cobalt-kitty-apt" name="scite-21" rel="nofollow" target="_blank">
        Dahan, A. (2017, May 24). OPERATION COBALT KITTY: A LARGE-SCALE APT IN ASIA CARRIED OUT BY THE OCEANLOTUS GROUP. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="https://cdn2.hubspot.net/hubfs/3354902/Cybereason%20Labs%20Analysis%20Operation%20Cobalt%20Kitty.pdf" name="scite-22" rel="nofollow" target="_blank">
        Dahan, A. (2017). Operation Cobalt Kitty. Retrieved December 27, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-23">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/elfin-apt33-espionage" name="scite-23" rel="nofollow" target="_blank">
        Security Response attack Investigation Team. (2019, March 27). Elfin: Relentless Espionage Group Targets Multiple Organizations in Saudi Arabia and U.S.. Retrieved April 10, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-24">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/12/overruled-containing-a-potentially-destructive-adversary.html" name="scite-24" rel="nofollow" target="_blank">
        Ackerman, G., et al. (2018, December 21). OVERRULED: Containing a Potentially Destructive Adversary. Retrieved January 17, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-25">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" name="scite-25" rel="nofollow" target="_blank">
        FireEye. (2018, February 20). APT37 (Reaper): The Overlooked North Korean Actor. Retrieved March 1, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-26">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2019/01/apt39-iranian-cyber-espionage-group-focused-on-personal-information.html" name="scite-26" rel="nofollow" target="_blank">
        Hawley et al. (2019, January 29). APT39: An Iranian Cyber Espionage Group Focused on Personal Information. Retrieved February 19, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-27">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cybereason.com/blog/information-stealing-malware-targeting-brazil-full-research" name="scite-27" rel="nofollow" target="_blank">
        Salem, E. (2019, February 13). ASTAROTH MALWARE USES LEGITIMATE OS AND ANTIVIRUS PROCESSES TO STEAL PASSWORDS AND PERSONAL DATA. Retrieved April 17, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-28">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.novetta.com/wp-content/uploads/2014/11/Executive_Summary-Final_1.pdf" name="scite-28" rel="nofollow" target="_blank">
        Novetta. (n.d.). Operation SMN: Axiom Threat Actor Group Report. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-29">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/11/unit42-new-wine-old-bottle-new-azorult-variant-found-findmyname-campaign-using-fallout-exploit-kit/" name="scite-29" rel="nofollow" target="_blank">
        Yan, T., et al. (2018, November 21). New Wine in Old Bottle: New Azorult Variant Found in FindMyName Campaign using Fallout Exploit Kit. Retrieved November 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-30">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/Dragonfly_Threat_Against_Western_Energy_Suppliers.pdf" name="scite-30" rel="nofollow" target="_blank">
        Symantec Security Response. (2014, July 7). Dragonfly: Cyberespionage Attacks Against Energy Suppliers. Retrieved April 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-31">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/bronze-butler-targets-japanese-businesses" name="scite-31" rel="nofollow" target="_blank">
        Counter Threat Unit Research Team. (2017, October 12). BRONZE BUTLER Targets Japanese Enterprises. Retrieved January 4, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-32">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2017/06/behind-the-carbanak-backdoor.html" name="scite-32" rel="nofollow" target="_blank">
        Bennett, J., Vengerik, B. (2017, June 12). Behind the CARBANAK Backdoor. Retrieved June 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-33">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf" name="scite-33" rel="nofollow" target="_blank">
        PwC and BAE Systems. (2017, April). Operation Cloud Hopper: Technical Annex. Retrieved April 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-34">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf" name="scite-34" rel="nofollow" target="_blank">
        Cylance. (2014, December). Operation Cleaver. Retrieved September 14, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-35">
      <span class="scite-citation-text">
       <a class="external text" href="https://cobaltstrike.com/downloads/csmanual38.pdf" name="scite-35" rel="nofollow" target="_blank">
        Strategic Cyber LLC. (2017, March 14). Cobalt Strike Manual. Retrieved May 24, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-36">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.f-secure.com/documents/996508/1030745/dukes_whitepaper.pdf" name="scite-36" rel="nofollow" target="_blank">
        F-Secure Labs. (2015, September 17). The Dukes: 7 years of Russian cyberespionage. Retrieved December 10, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-37">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.f-secure.com/documents/996508/1030745/CozyDuke" name="scite-37" rel="nofollow" target="_blank">
        F-Secure Labs. (2015, April 22). CozyDuke: Malware Analysis. Retrieved December 10, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-38">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/sites/default/files/proofpoint-operation-transparent-tribe-threat-insight-en.pdf" name="scite-38" rel="nofollow" target="_blank">
        Huss, D.. (2016, March 1). Operation Transparent Tribe. Retrieved June 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-39">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/connect/blogs/tick-cyberespionage-group-zeros-japan" name="scite-39" rel="nofollow" target="_blank">
        DiMaggio, J. (2016, April 28). Tick cyberespionage group zeros in on Japan. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-40">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" name="scite-40" rel="nofollow" target="_blank">
        US-CERT. (2018, March 16). Alert (TA18-074A): Russian Government Cyber Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved June 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-41">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA17-293A" name="scite-41" rel="nofollow" target="_blank">
        US-CERT. (2017, October 20). Alert (TA17-293A): Advanced Persistent Threat Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved November 2, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-42">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.coresecurity.com/corelabs-research/open-source-tools/impacket" name="scite-42" rel="nofollow" target="_blank">
        Core Security. (n.d.). Impacket. Retrieved November 2, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-43">
      <span class="scite-citation-text">
       <a class="external text" href="https://documents.trendmicro.com/assets/white_papers/ExploringEmotetsActivities_Final.pdf" name="scite-43" rel="nofollow" target="_blank">
        Trend Micro. (2019, January 16). Exploring Emotet's Activities . Retrieved March 25, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-44">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellEmpire/Empire" name="scite-44" rel="nofollow" target="_blank">
        Schroeder, W., Warner, J., Nelson, M. (n.d.). Github PowerShellEmpire. Retrieved April 28, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-45">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.darkreading.com/analytics/prolific-cybercrime-gang-favors-legit-login-credentials/d/d-id/1322645?" name="scite-45" rel="nofollow" target="_blank">
        Higgins, K. (2015, October 13). Prolific Cybercrime Gang Favors Legit Login Credentials. Retrieved October 4, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-46">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.youtube.com/watch?v=fevGZs0EQu8" name="scite-46" rel="nofollow" target="_blank">
        Bromiley, M. and Lewis, P. (2016, October 7). Attacking the Hospitality and Gaming Industries: Tracking an Attacker Around the World in 7 Years. Retrieved October 6, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-47">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin6.pdf" name="scite-47" rel="nofollow" target="_blank">
        FireEye Threat Intelligence. (2016, April). Follow the Money: Dissecting the Operations of the Cyber Crime Group FIN6. Retrieved June 1, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-48">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2019/04/pick-six-intercepting-a-fin6-intrusion.html" name="scite-48" rel="nofollow" target="_blank">
        McKeague, B. et al. (2019, April 5). Pick-Six: Intercepting a FIN6 Intrusion, an Actor Recently Tied to Ryuk and LockerGoga Ransomware. Retrieved April 17, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-49">
      <span class="scite-citation-text">
       <a class="external text" href="https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html" name="scite-49" rel="nofollow" target="_blank">
        Elovitz, S. &amp; Ahl, I. (2016, August 18). Know Your Enemy:  New Financially-Motivated &amp; Spear-Phishing Group. Retrieved February 26, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-50">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2018/10/ESET_GreyEnergy.pdf" name="scite-50" rel="nofollow" target="_blank">
        Cherepanov, A. (2018, October). GREYENERGY A successor to BlackEnergy. Retrieved November 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-51">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.truesec.se/sakerhet/verktyg/saakerhet/gsecdump_v2.0b5" name="scite-51" rel="nofollow" target="_blank">
        TrueSec. (n.d.). gsecdump v2.0b5. Retrieved September 29, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-52">
      <span class="scite-citation-text">
       <a class="external text" href="http://blogs.cisco.com/security/h1n1-technical-analysis-reveals-new-capabilities-part-2" name="scite-52" rel="nofollow" target="_blank">
        Reynolds, J.. (2016, September 14). H1N1: Technical analysis reveals new capabilities – part 2. Retrieved September 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-53">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html" name="scite-53" rel="nofollow" target="_blank">
        FireEye. (2018, March 16). Suspected Chinese Cyber Espionage Group (TEMP.Periscope) Targeting U.S. Engineering and Maritime Industries. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-54">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/analysis-reports/AR19-100A" name="scite-54" rel="nofollow" target="_blank">
        US-CERT. (2019, April 10). MAR-10135536-8 – North Korean Trojan: HOPLIGHT. Retrieved April 19, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-55">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureauth.com/labs/open-source-tools/impacket" name="scite-55" rel="nofollow" target="_blank">
        SecureAuth. (n.d.).  Retrieved January 15, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-56">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/wp-operation-ke3chang.pdf" name="scite-56" rel="nofollow" target="_blank">
        Villeneuve, N., Bennett, J. T., Moran, N., Haq, T., Scott, M., &amp; Geers, K. (2014). OPERATION “KE3CHANG”: Targeted Attacks Against Ministries of Foreign Affairs. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-57">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/" name="scite-57" rel="nofollow" target="_blank">
        Smallridge, R. (2018, March 10). APT15 is alive and strong: An analysis of RoyalCli and RoyalDNS. Retrieved April 4, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-58">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/zerosum0x0/koadic" name="scite-58" rel="nofollow" target="_blank">
        Magius, J., et al. (2017, July 19). Koadic. Retrieved June 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-59">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2017/05/konni-malware-under-radar-for-years.html" name="scite-59" rel="nofollow" target="_blank">
        Rascagneres, P. (2017, May 03). KONNI: A Malware Under The Radar For Years. Retrieved November 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-60">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/AlessandroZ/LaZagne" name="scite-60" rel="nofollow" target="_blank">
        Zanni, A. (n.d.). The LaZagne Project !!!. Retrieved December 14, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="61.0">
    <li>
     <span class="scite-citation" id="scite-61">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2018/04/03/lazarus-killdisk-central-american-casino/" name="scite-61" rel="nofollow" target="_blank">
        Kálnai, P., Cherepanov A. (2018, April 03). Lazarus KillDisks Central American casino. Retrieved May 17, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-62">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/leafminer-espionage-middle-east" name="scite-62" rel="nofollow" target="_blank">
        Symantec Security Response. (2018, July 25). Leafminer: New Espionage Campaigns Targeting Middle Eastern Regions. Retrieved August 28, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-63">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2019/03/apt40-examining-a-china-nexus-espionage-actor.html" name="scite-63" rel="nofollow" target="_blank">
        Plan, F., et all. (2019, March 4). APT40: Examining a China-Nexus Espionage Actor. Retrieved March 18, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-64">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/content/dam/collateral/en/mtrends-2018.pdf" name="scite-64" rel="nofollow" target="_blank">
        Mandiant. (2018). Mandiant M-Trends 2018. Retrieved July 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-65">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.clearskysec.com/wp-content/uploads/2017/07/Operation_Wilted_Tulip.pdf" name="scite-65" rel="nofollow" target="_blank">
        ClearSky Cyber Security and Trend Micro. (2017, July). Operation Wilted Tulip: Exposing a cyber espionage apparatus. Retrieved August 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-66">
      <span class="scite-citation-text">
       <a class="external text" href="https://s3-eu-west-1.amazonaws.com/minervaresearchpublic/CopyKittens/CopyKittens.pdf" name="scite-66" rel="nofollow" target="_blank">
        Minerva Labs LTD and ClearSky Cyber Security. (2015, November 23). CopyKittens Attack Group. Retrieved September 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-67">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/Twi1ight/AD-Pentest-Script/blob/master/wmiexec.vbs" name="scite-67" rel="nofollow" target="_blank">
        Twi1ight. (2015, July 11). AD-Pentest-Script - wmiexec.vbs. Retrieved June 29, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-68">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/gentilkiwi/mimikatz" name="scite-68" rel="nofollow" target="_blank">
        Deply, B. (n.d.). Mimikatz. Retrieved September 29, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-69">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.dsinternals.com/en/retrieving-dpapi-backup-keys-from-active-directory/" name="scite-69" rel="nofollow" target="_blank">
        Grafnetter, M. (2015, October 26). Retrieving DPAPI Backup Keys from Active Directory. Retrieved December 19, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-70">
      <span class="scite-citation-text">
       <a class="external text" href="https://s3.eu-west-1.amazonaws.com/ncsc-content/files/Joint%20report%20on%20publicly%20available%20hacking%20tools%20%28NCSC%29.pdf" name="scite-70" rel="nofollow" target="_blank">
        The Australian Cyber Security Centre (ACSC), the Canadian Centre for Cyber Security (CCCS), the New Zealand National Cyber Security Centre (NZ NCSC), CERT New Zealand, the UK National Cyber Security Centre (UK NCSC) and the US National Cybersecurity and Communications Integration Center (NCCIC). (2018, October 11). Joint report on publicly available hacking tools. Retrieved March 11, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-71">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/huntergregal/mimipenguin" name="scite-71" rel="nofollow" target="_blank">
        Gregal, H. (2017, May 12). MimiPenguin. Retrieved December 5, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-72">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/security_response/writeup.jsp?docid=2015-020623-0740-99&amp;tabid=2" name="scite-72" rel="nofollow" target="_blank">
        Stama, D.. (2015, February 6). Backdoor.Mivast. Retrieved February 15, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-73">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.clearskysec.com/wp-content/uploads/2016/01/Operation%20DustySky_TLP_WHITE.pdf" name="scite-73" rel="nofollow" target="_blank">
        ClearSky. (2016, January 7). Operation DustySky. Retrieved January 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-74">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/11/unit42-muddying-the-water-targeted-attacks-in-the-middle-east/" name="scite-74" rel="nofollow" target="_blank">
        Lancaster, T.. (2017, November 14). Muddying the Water: Targeted Attacks in the Middle East. Retrieved March 15, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-75">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/seedworm-espionage-group" name="scite-75" rel="nofollow" target="_blank">
        Symantec DeepSight Adversary Intelligence Team. (2018, December 10). Seedworm: Group Compromises Government Agencies, Oil &amp; Gas, NGOs, Telecoms, and IT Firms. Retrieved December 14, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-76">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/wp-content/uploads/2011/02/McAfee_NightDragon_wp_draft_to_customersv1-1.pdf" name="scite-76" rel="nofollow" target="_blank">
        McAfee® Foundstone® Professional Services and McAfee Labs™. (2011, February 10). Global Energy Cyberattacks: “Night Dragon”. Retrieved February 19, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-77">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2017/06/worldwide-ransomware-variant.html" name="scite-77" rel="nofollow" target="_blank">
        Chiu, A. (2016, June 27). New Ransomware Variant "Nyetya" Compromises Systems Worldwide. Retrieved March 26, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-78">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA17-181A" name="scite-78" rel="nofollow" target="_blank">
        US-CERT. (2017, July 1). Alert (TA17-181A): Petya Ransomware. Retrieved March 15, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-79">
      <span class="scite-citation-text">
       <a class="external text" href="https://pan-unit42.github.io/playbook_viewer/" name="scite-79" rel="nofollow" target="_blank">
        Unit 42. (2017, December 15). Unit 42 Playbook Viewer. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-80">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.brighttalk.com/webcast/10703/296317/apt34-new-targeted-attack-in-the-middle-east" name="scite-80" rel="nofollow" target="_blank">
        Davis, S. and Caban, D. (2017, December 19). APT34 - New Targeted Attack in the Middle East. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-81">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/rpt-apt28.pdf" name="scite-81" rel="nofollow" target="_blank">
        FireEye. (2015). APT28: A WINDOW INTO RUSSIA’S CYBER ESPIONAGE OPERATIONS?. Retrieved August 19, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-82">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/02/olympic-destroyer.html" name="scite-82" rel="nofollow" target="_blank">
        Mercer, W. and Rascagneres, P. (2018, February 12). Olympic Destroyer Takes Aim At Winter Olympics. Retrieved March 14, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-83">
      <span class="scite-citation-text">
       <a class="external text" href="https://s3-us-west-2.amazonaws.com/cymmetria-blog/public/Unveiling_Patchwork.pdf" name="scite-83" rel="nofollow" target="_blank">
        Cymmetria. (2016). Unveiling Patchwork - The Copy-Paste APT. Retrieved August 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-84">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/poseidon-group-a-targeted-attack-boutique-specializing-in-global-cyber-espionage/73673/" name="scite-84" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2016, February 9). Poseidon Group: a Targeted Attack Boutique specializing in global cyber-espionage. Retrieved March 16, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-85">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/nettitude/PoshC2" name="scite-85" rel="nofollow" target="_blank">
        Nettitude. (2016, June 8). PoshC2: Powershell C2 Server and Implants. Retrieved April 23, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-86">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellMafia/PowerSploit" name="scite-86" rel="nofollow" target="_blank">
        PowerShellMafia. (2012, May 26). PowerSploit - A PowerShell Post-Exploitation Framework. Retrieved February 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-87">
      <span class="scite-citation-text">
       <a class="external text" href="http://powersploit.readthedocs.io" name="scite-87" rel="nofollow" target="_blank">
        PowerSploit. (n.d.). PowerSploit. Retrieved February 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-88">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.welivesecurity.com/wp-content/uploads/2016/05/Operation-Groundbait.pdf" name="scite-88" rel="nofollow" target="_blank">
        Cherepanov, A.. (2016, May 17). Operation Groundbait: Analysis of a surveillance toolkit. Retrieved May 18, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-89">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/n1nj4sec/pupy" name="scite-89" rel="nofollow" target="_blank">
        Nicolas Verdier. (n.d.). Retrieved January 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-90">
      <span class="scite-citation-text">
       <a class="external text" href="https://en.wikipedia.org/wiki/Pwdump" name="scite-90" rel="nofollow" target="_blank">
        Wikipedia. (1985, June 22). pwdump. Retrieved June 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-91">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/quasar/QuasarRAT" name="scite-91" rel="nofollow" target="_blank">
        MaxXor. (n.d.). QuasarRAT. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-92">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/" name="scite-92" rel="nofollow" target="_blank">
        Meltzer, M, et al. (2018, June 07). Patchwork APT Group Targets US Think Tanks. Retrieved July 16, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-93">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.accenture.com/t20180423T055005Z_w_/se-en/_acnmedia/PDF-76/Accenture-Hogfish-Threat-Analysis.pdf" name="scite-93" rel="nofollow" target="_blank">
        Accenture Security. (2018, April 23). Hogfish Redleaves Campaign. Retrieved July 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-94">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/files/2016/07/The-ProjectSauron-APT_Technical_Analysis_KL.pdf" name="scite-94" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research &amp; Analysis Team. (2016, August 9). The ProjectSauron APT. Technical Analysis. Retrieved August 17, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-95">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.talosintelligence.com/2018/01/korea-in-crosshairs.html" name="scite-95" rel="nofollow" target="_blank">
        Mercer, W., Rascagneres, P. (2018, January 16). Korea In The Crosshairs. Retrieved May 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-96">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/connect/blogs/sowbug-cyber-espionage-group-targets-south-american-and-southeast-asian-governments" name="scite-96" rel="nofollow" target="_blank">
        Symantec Security Response. (2017, November 7). Sowbug: Cyber espionage group targets South American and Southeast Asian governments. Retrieved November 16, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-97">
      <span class="scite-citation-text">
       <a class="external text" href="https://citizenlab.org/2016/05/stealth-falcon/" name="scite-97" rel="nofollow" target="_blank">
        Marczak, B. and Scott-Railton, J.. (2016, May 29). Keep Calm and (Don’t) Enable Macros: A New Threat Actor Targets UAE Dissidents. Retrieved June 8, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-98">
      <span class="scite-citation-text">
       <a class="external text" href="https://asert.arbornetworks.com/stolen-pencil-campaign-targets-academia/" name="scite-98" rel="nofollow" target="_blank">
        ASERT team. (2018, December 5). STOLEN PENCIL Campaign Targets Academia. Retrieved February 5, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-99">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/files/2016/07/The-ProjectSauron-APT_research_KL.pdf" name="scite-99" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research &amp; Analysis Team. (2016, August 9). The ProjectSauron APT. Retrieved August 17, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-100">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.symantec.com/connect/blogs/indian-organizations-targeted-suckfly-attacks" name="scite-100" rel="nofollow" target="_blank">
        DiMaggio, J.. (2016, May 17). Indian organizations targeted in Suckfly attacks. Retrieved August 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-101">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2019/04/triton-actor-ttp-profile-custom-attack-tools-detections.html" name="scite-101" rel="nofollow" target="_blank">
        Miller, S, et al. (2019, April 10). TRITON Actor TTP Profile, Custom Attack Tools, Detections, and ATT&amp;CK Mapping. Retrieved April 16, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-102">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage" name="scite-102" rel="nofollow" target="_blank">
        Dell SecureWorks Counter Threat Unit Threat Intelligence. (2015, August 5). Threat Group-3390 Targets Organizations for Cyberespionage. Retrieved August 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-103">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/bronze-union" name="scite-103" rel="nofollow" target="_blank">
        Counter Threat Unit Research Team. (2017, June 27). BRONZE UNION Cyberespionage Persists Despite Disclosures. Retrieved July 13, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-104">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" name="scite-104" rel="nofollow" target="_blank">
        Settle, A., et al. (2016, August 8). MONSOON - Analysis Of An APT Campaign. Retrieved September 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-105">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.ampliasecurity.com/research/wcefaq.html" name="scite-105" rel="nofollow" target="_blank">
        Amplia Security. (n.d.). Windows Credentials Editor (WCE) F.A.Q.. Retrieved December 17, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-106">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access-reference-material#a-nameesaebmaesae-administrative-forest-design-approach" name="scite-106" rel="nofollow" target="_blank">
        Plett, C., Poggemeyer, L. (12, October 26). Securing Privileged Access Reference Material. Retrieved April 25, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-107">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/dn408187.aspx" name="scite-107" rel="nofollow" target="_blank">
        Microsoft. (2013, July 31). Configuring Additional LSA Protection. Retrieved February 13, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-108">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-108" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-109">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-109" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-110">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-110" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-111">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" name="scite-111" rel="nofollow" target="_blank">
        Corio, C., &amp; Sayana, D. P. (2008, June). Application Lockdown with Software Restriction Policies. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-112">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" name="scite-112" rel="nofollow" target="_blank">
        Microsoft. (2012, June 27). Using Software Restriction Policies and AppLocker Policies. Retrieved April 7, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-113">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/itpro/windows/keep-secure/credential-guard" name="scite-113" rel="nofollow" target="_blank">
        Lich, B. (2016, May 31). Protect derived domain credentials with Credential Guard. Retrieved June 1, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-114">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/iadgov/Secure-Host-Baseline/tree/master/Credential%20Guard" name="scite-114" rel="nofollow" target="_blank">
        NSA IAD. (2017, April 20). Secure Host Baseline - Credential Guard. Retrieved April 25, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-115">
      <span class="scite-citation-text">
       <a class="external text" href="https://adsecurity.org/?p=1729" name="scite-115" rel="nofollow" target="_blank">
        Metcalf, S. (2015, September 25). Mimikatz DCSync Usage, Exploitation, and Detection. Retrieved December 4, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-116">
      <span class="scite-citation-text">
       <a class="external text" href="https://support.microsoft.com/help/303972/how-to-grant-the-replicating-directory-changes-permission-for-the-micr" name="scite-116" rel="nofollow" target="_blank">
        Microsoft. (n.d.). How to grant the "Replicating Directory Changes" permission for the Microsoft Metadirectory Services ADMA service account. Retrieved December 4, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-117">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/library/jj865668.aspx" name="scite-117" rel="nofollow" target="_blank">
        Microsoft. (2012, November 29). Using security policies to restrict NTLM traffic. Retrieved December 4, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-118">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/mattifestation/PowerSploit" name="scite-118" rel="nofollow" target="_blank">
        PowerSploit. (n.d.). Retrieved December 4, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-119">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.harmj0y.net/blog/redteaming/mimikatz-and-dcsync-and-extrasids-oh-my/" name="scite-119" rel="nofollow" target="_blank">
        Schroeder, W. (2015, September 22). Mimikatz and DCSync and ExtraSids, Oh My. Retrieved December 4, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-120">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/cc245496.aspx" name="scite-120" rel="nofollow" target="_blank">
        Microsoft. (n.d.). MS-SAMR Security Account Manager (SAM) Remote Protocol (Client-to-Server) - Transport. Retrieved December 4, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
