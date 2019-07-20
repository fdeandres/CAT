<div class="container-fluid">
 <h1>
  Access Token Manipulation
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Windows uses access tokens to determine the ownership of a running process. A user can manipulate access tokens to make a running process appear as though it belongs to someone other than the user that started the process. When this occurs, the process also takes on the security context associated with the new token. For example, Microsoft promotes the use of access tokens as a security best practice. Administrators should log in as a standard user but run their tools with administrator privileges using the built-in access token manipulation command
    <code>
     runas
    </code>
    .
    <span class="scite-citeref-number" data-reference="Microsoft runas" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://technet.microsoft.com/en-us/library/bb490994.aspx" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries may use access tokens to operate under a different user or system security context to perform actions and evade detection. An adversary can use built-in Windows API functions to copy access tokens from existing processes; this is known as token stealing. An adversary must already be in a privileged user context (i.e. administrator) to steal a token. However, adversaries commonly use token stealing to elevate their security context from the administrator level to the SYSTEM level. An adversary can use a token to authenticate to a remote system as the account for that token if the account has appropriate permissions on the remote system.
    <span class="scite-citeref-number" data-reference="Pentestlab Token Manipulation" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://pentestlab.blog/2017/04/03/token-manipulation/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Access tokens can be leveraged by adversaries through three methods:
    <span class="scite-citeref-number" data-reference="BlackHat Atkinson Winchester Token Manipulation" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.blackhat.com/docs/eu-17/materials/eu-17-Atkinson-A-Process-Is-No-One-Hunting-For-Token-Manipulation.pdf" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    <strong>
     Token Impersonation/Theft
    </strong>
    - An adversary creates a new access token that duplicates an existing token using
    <code>
     DuplicateToken(Ex)
    </code>
    . The token can then be used with
    <code>
     ImpersonateLoggedOnUser
    </code>
    to allow the calling thread to impersonate a logged on user's security context, or with
    <code>
     SetThreadToken
    </code>
    to assign the impersonated token to a thread. This is useful for when the target user has a non-network logon session on the system.
   </p>
   <p>
    <strong>
     Create Process with a Token
    </strong>
    - An adversary creates a new access token with
    <code>
     DuplicateToken(Ex)
    </code>
    and uses it with
    <code>
     CreateProcessWithTokenW
    </code>
    to create a new process running under the security context of the impersonated user. This is useful for creating a new process under the security context of a different user.
   </p>
   <p>
    <strong>
     Make and Impersonate Token
    </strong>
    - An adversary has a username and password but the user is not logged onto the system. The adversary can then create a logon session for the user using the
    <code>
     LogonUser
    </code>
    function. The function will return a copy of the new session's access token and the adversary can use
    <code>
     SetThreadToken
    </code>
    to assign the token to a thread.
   </p>
   <p>
    Any standard user can use the
    <code>
     runas
    </code>
    command, and the Windows API functions, to create impersonation tokens; it does not require access to an administrator account.
   </p>
   <p>
    Metasploit’s Meterpreter payload allows arbitrary token manipulation and uses token impersonation to escalate privileges.
    <span class="scite-citeref-number" data-reference="Metasploit access token" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.offensive-security.com/metasploit-unleashed/fun-incognito/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    The Cobalt Strike beacon payload allows arbitrary token impersonation and can also create tokens.
    <span class="scite-citeref-number" data-reference="Cobalt Strike Access Token" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://blog.cobaltstrike.com/2015/12/16/windows-access-tokens-and-alternate-credentials/" target="_blank">
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
      : T1134
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
      : Defense Evasion, Privilege Escalation
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
      User, Administrator
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Effective Permissions:
      </span>
      SYSTEM
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      API monitoring, Access tokens, Process monitoring, Process command-line parameters
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
      Tom Ueltschi @c_APT_ure; Travis Smith, Tripwire; Robby Winchester, @robwinchester3; Jared Atkinson, @jaredcatkinson
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
      has used CVE-2015-1701 to access the SYSTEM token and copy it into the current process as part of privilege escalation.
      <span class="scite-citeref-number" data-reference="FireEye Op RussianDoll" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.fireeye.com/blog/threat-research/2015/04/probable_apt28_useo.html" target="_blank">
         [6]
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
      can call WTSQueryUserToken and CreateProcessAsUser to start a new process with local system privileges.
      <span class="scite-citeref-number" data-reference="Unit42 Azorult Nov 2018" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://researchcenter.paloaltonetworks.com/2018/11/unit42-new-wine-old-bottle-new-azorult-variant-found-findmyname-campaign-using-fallout-exploit-kit/" target="_blank">
         [7]
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
      grabs a user token using WTSQueryUserToken and then creates a process by impersonating a logged-on user.
      <span class="scite-citeref-number" data-reference="McAfee Bankshot" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://securingtomorrow.mcafee.com/mcafee-labs/hidden-cobra-targets-turkish-financial-sector-new-bankshot-implant/" target="_blank">
         [8]
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
      can steal access tokens from exiting processes and make tokens from known credentials.
      <span class="scite-citeref-number" data-reference="cobaltstrike manual" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://cobaltstrike.com/downloads/csmanual38.pdf" target="_blank">
         [9]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0038">
      Duqu
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0038">
       Duqu
      </a>
      examines running system processes for tokens that have specific system privileges. If it finds one, it will copy the token and store it for later use. Eventually it will start new processes with the stored token attached. It can also steal tokens to acquire administrative privileges.
      <span class="scite-citeref-number" data-reference="Kaspersky Duqu 2.0" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://securelist.com/files/2015/06/The_Mystery_of_Duqu_2_0_a_sophisticated_cyberespionage_actor_returns.pdf" target="_blank">
         [10]
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
      can use
      <code>
       Invoke-RunAs
      </code>
      to make tokens as well as
      <a href="https://attack.mitre.org/software/S0194">
       PowerSploit
      </a>
      's
      <code>
       Invoke-TokenManipulation
      </code>
      to manipulate access tokens.
      <span class="scite-citeref-number" data-reference="Github PowerShell Empire" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://github.com/PowerShellEmpire/Empire" target="_blank">
         [11]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0182">
      FinFisher
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0182">
       FinFisher
      </a>
      uses token manipulation with NtFilterToken as part of UAC bypass.
      <span class="scite-citeref-number" data-reference="FinFisher Citation" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="http://www.finfisher.com/FinFisher/index.html" target="_blank">
         [12]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Microsoft FinFisher March 2018" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://cloudblogs.microsoft.com/microsoftsecure/2018/03/01/finfisher-exposed-a-researchers-tale-of-defeating-traps-tricks-and-complex-virtual-machines/" target="_blank">
         [13]
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
      creates a backdoor through which remote attackers can adjust token privileges.
      <span class="scite-citeref-number" data-reference="Symantec Hydraq Jan 2010" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://www.symantec.com/security_response/writeup.jsp?docid=2010-011114-1830-99" target="_blank">
         [14]
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
      keylogger KiloAlfa obtains user tokens from interactive sessions to execute itself with API call
      <code>
       CreateProcessAsUserA
      </code>
      under that user's context.
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" target="_blank">
         [15]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Novetta Blockbuster Tools" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Tools-Report.pdf" target="_blank">
         [16]
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
      contains a number of modules, such as
      <code>
       Invoke-RunAs
      </code>
      and
      <code>
       Invoke-TokenManipulation
      </code>
      , for manipulating tokens.
      <span class="scite-citeref-number" data-reference="GitHub PoshC2" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://github.com/nettitude/PoshC2" target="_blank">
         [17]
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
      's
      <code>
       Invoke-TokenManipulation
      </code>
      Exfiltration module can be used to locate and impersonate user logon tokens.
      <span class="scite-citeref-number" data-reference="GitHub PowerSploit May 2012" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="https://github.com/PowerShellMafia/PowerSploit" target="_blank">
         [18]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PowerSploit Documentation" id="scite-ref-19-a" onclick="scrollToRef('scite-19')">
       <sup>
        <a aria-describedby="qtip-18" data-hasqtip="18" href="http://powersploit.readthedocs.io" target="_blank">
         [19]
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
      can obtain a list of SIDs and provide the option for selecting process tokens to impersonate.
      <span class="scite-citeref-number" data-reference="GitHub Pupy" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://github.com/n1nj4sec/pupy" target="_blank">
         [20]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0058">
      SslMM
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0058">
       SslMM
      </a>
      contains a feature to manipulate process privileges and tokens.
      <span class="scite-citeref-number" data-reference="Baumgartner Naikon 2015" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07205555/TheNaikonAPT-MsnMM1.pdf" target="_blank">
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
  Access tokens are an integral part of the security system within Windows and cannot be turned off. However, an attacker must already have administrator level access on the local system to make full use of this technique; be sure to restrict users and accounts to the least privileges they require to do their job.
 </p>
 <p>
  Any user can also spoof access tokens if they have legitimate credentials. Follow mitigation guidelines for preventing adversary use of
  <a href="https://attack.mitre.org/techniques/T1078">
   Valid Accounts
  </a>
  . Limit permissions so that users and user groups cannot create tokens. This setting should be defined for the local system account only. GPO: Computer Configuration &gt; [Policies] &gt; Windows Settings &gt; Security Settings &gt; Local Policies &gt; User Rights Assignment: Create a token object.
  <span class="scite-citeref-number" data-reference="Microsoft Create Token" id="scite-ref-22-a">
   <sup>
    <a aria-describedby="qtip-21" data-hasqtip="21" href="https://docs.microsoft.com/windows/device-security/security-policy-settings/create-a-token-object" target="_blank">
     [22]
    </a>
   </sup>
  </span>
  Also define who can create a process level token to only the local and network service through GPO: Computer Configuration &gt; [Policies] &gt; Windows Settings &gt; Security Settings &gt; Local Policies &gt; User Rights Assignment: Replace a process level token.
  <span class="scite-citeref-number" data-reference="Microsoft Replace Process Token" id="scite-ref-23-a">
   <sup>
    <a aria-describedby="qtip-22" data-hasqtip="22" href="https://docs.microsoft.com/windows/device-security/security-policy-settings/replace-a-process-level-token" target="_blank">
     [23]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Also limit opportunities for adversaries to increase privileges by limiting Privilege Escalation opportunities.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  If an adversary is using a standard command-line shell, analysts can detect token manipulation by auditing command-line activity. Specifically, analysts should look for use of the
  <code>
   runas
  </code>
  command. Detailed command-line logging is not enabled by default in Windows.
  <span class="scite-citeref-number" data-reference="Microsoft Command-line Logging" id="scite-ref-24-a">
   <sup>
    <a aria-describedby="qtip-23" data-hasqtip="23" href="https://technet.microsoft.com/en-us/windows-server-docs/identity/ad-ds/manage/component-updates/command-line-process-auditing" target="_blank">
     [24]
    </a>
   </sup>
  </span>
 </p>
 <p>
  If an adversary is using a payload that calls the Windows token APIs directly, analysts can detect token manipulation only through careful analysis of user network activity, examination of running processes, and correlation with other endpoint and network behavior.
 </p>
 <p>
  There are many Windows API calls a payload can take advantage of to manipulate access tokens (e.g.,
  <code>
   LogonUser
  </code>
  <span class="scite-citeref-number" data-reference="Microsoft LogonUser" id="scite-ref-25-a">
   <sup>
    <a aria-describedby="qtip-24" data-hasqtip="24" href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa378184(v=vs.85).aspx" target="_blank">
     [25]
    </a>
   </sup>
  </span>
  ,
  <code>
   DuplicateTokenEx
  </code>
  <span class="scite-citeref-number" data-reference="Microsoft DuplicateTokenEx" id="scite-ref-26-a">
   <sup>
    <a aria-describedby="qtip-25" data-hasqtip="25" href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa446617(v=vs.85).aspx" target="_blank">
     [26]
    </a>
   </sup>
  </span>
  , and
  <code>
   ImpersonateLoggedOnUser
  </code>
  <span class="scite-citeref-number" data-reference="Microsoft ImpersonateLoggedOnUser" id="scite-ref-27-a">
   <sup>
    <a aria-describedby="qtip-26" data-hasqtip="26" href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa378612(v=vs.85).aspx" target="_blank">
     [27]
    </a>
   </sup>
  </span>
  ). Please see the referenced Windows API pages for more information.
 </p>
 <p>
  Query systems for process and thread token information and look for inconsistencies such as user owns processes impersonating the local SYSTEM account.
  <span class="scite-citeref-number" data-reference="BlackHat Atkinson Winchester Token Manipulation" id="scite-ref-3-a">
   <sup>
    <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.blackhat.com/docs/eu-17/materials/eu-17-Atkinson-A-Process-Is-No-One-Hunting-For-Token-Manipulation.pdf" target="_blank">
     [3]
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
       <a class="external text" href="https://technet.microsoft.com/en-us/library/bb490994.aspx" name="scite-1" rel="nofollow" target="_blank">
        Microsoft TechNet. (n.d.). Runas. Retrieved April 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://pentestlab.blog/2017/04/03/token-manipulation/" name="scite-2" rel="nofollow" target="_blank">
        netbiosX. (2017, April 3). Token Manipulation. Retrieved April 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.blackhat.com/docs/eu-17/materials/eu-17-Atkinson-A-Process-Is-No-One-Hunting-For-Token-Manipulation.pdf" name="scite-3" rel="nofollow" target="_blank">
        Atkinson, J., Winchester, R. (2017, December 7). A Process is No One: Hunting for Token Manipulation. Retrieved December 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.offensive-security.com/metasploit-unleashed/fun-incognito/" name="scite-4" rel="nofollow" target="_blank">
        Offensive Security. (n.d.). What is Incognito. Retrieved April 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.cobaltstrike.com/2015/12/16/windows-access-tokens-and-alternate-credentials/" name="scite-5" rel="nofollow" target="_blank">
        Mudge, R. (n.d.). Windows Access Tokens and Alternate Credentials. Retrieved April 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2015/04/probable_apt28_useo.html" name="scite-6" rel="nofollow" target="_blank">
        FireEye Labs. (2015, April 18). Operation RussianDoll: Adobe &amp; Windows Zero-Day Exploits Likely Leveraged by Russia’s APT28 in Highly-Targeted Attack. Retrieved April 24, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/11/unit42-new-wine-old-bottle-new-azorult-variant-found-findmyname-campaign-using-fallout-exploit-kit/" name="scite-7" rel="nofollow" target="_blank">
        Yan, T., et al. (2018, November 21). New Wine in Old Bottle: New Azorult Variant Found in FindMyName Campaign using Fallout Exploit Kit. Retrieved November 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/hidden-cobra-targets-turkish-financial-sector-new-bankshot-implant/" name="scite-8" rel="nofollow" target="_blank">
        Sherstobitoff, R. (2018, March 08). Hidden Cobra Targets Turkish Financial Sector With New Bankshot Implant. Retrieved May 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://cobaltstrike.com/downloads/csmanual38.pdf" name="scite-9" rel="nofollow" target="_blank">
        Strategic Cyber LLC. (2017, March 14). Cobalt Strike Manual. Retrieved May 24, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/files/2015/06/The_Mystery_of_Duqu_2_0_a_sophisticated_cyberespionage_actor_returns.pdf" name="scite-10" rel="nofollow" target="_blank">
        Kaspersky Lab. (2015, June 11). The Duqu 2.0. Retrieved April 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellEmpire/Empire" name="scite-11" rel="nofollow" target="_blank">
        Schroeder, W., Warner, J., Nelson, M. (n.d.). Github PowerShellEmpire. Retrieved April 28, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.finfisher.com/FinFisher/index.html" name="scite-12" rel="nofollow" target="_blank">
        FinFisher. (n.d.). Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://cloudblogs.microsoft.com/microsoftsecure/2018/03/01/finfisher-exposed-a-researchers-tale-of-defeating-traps-tricks-and-complex-virtual-machines/" name="scite-13" rel="nofollow" target="_blank">
        Allievi, A.,Flori, E. (2018, March 01). FinFisher exposed: A researcher’s tale of defeating traps, tricks, and complex virtual machines. Retrieved July 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2010-011114-1830-99" name="scite-14" rel="nofollow" target="_blank">
        Lelli, A. (2010, January 11). Trojan.Hydraq. Retrieved February 20, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="15.5">
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf" name="scite-15" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Unraveling the Long Thread of the Sony Attack. Retrieved February 25, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Tools-Report.pdf" name="scite-16" rel="nofollow" target="_blank">
        Novetta Threat Research Group. (2016, February 24). Operation Blockbuster: Tools Report. Retrieved March 10, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/nettitude/PoshC2" name="scite-17" rel="nofollow" target="_blank">
        Nettitude. (2016, June 8). PoshC2: Powershell C2 Server and Implants. Retrieved April 23, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellMafia/PowerSploit" name="scite-18" rel="nofollow" target="_blank">
        PowerShellMafia. (2012, May 26). PowerSploit - A PowerShell Post-Exploitation Framework. Retrieved February 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-19">
      <span class="scite-citation-text">
       <a class="external text" href="http://powersploit.readthedocs.io" name="scite-19" rel="nofollow" target="_blank">
        PowerSploit. (n.d.). PowerSploit. Retrieved February 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-20">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/n1nj4sec/pupy" name="scite-20" rel="nofollow" target="_blank">
        Nicolas Verdier. (n.d.). Retrieved January 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07205555/TheNaikonAPT-MsnMM1.pdf" name="scite-21" rel="nofollow" target="_blank">
        Baumgartner, K., Golovkin, M.. (2015, May). The MsnMM Campaigns: The Earliest Naikon APT Campaigns. Retrieved April 10, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/windows/device-security/security-policy-settings/create-a-token-object" name="scite-22" rel="nofollow" target="_blank">
        Brower, N., Lich, B. (2017, April 19). Create a token object. Retrieved December 19, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-23">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/windows/device-security/security-policy-settings/replace-a-process-level-token" name="scite-23" rel="nofollow" target="_blank">
        Brower, N., Lich, B. (2017, April 19). Replace a process level token. Retrieved December 19, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-24">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/windows-server-docs/identity/ad-ds/manage/component-updates/command-line-process-auditing" name="scite-24" rel="nofollow" target="_blank">
        Mathers, B. (2017, March 7). Command line process auditing. Retrieved April 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-25">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa378184(v=vs.85).aspx" name="scite-25" rel="nofollow" target="_blank">
        Microsoft TechNet. (n.d.). Retrieved April 25, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-26">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa446617(v=vs.85).aspx" name="scite-26" rel="nofollow" target="_blank">
        Microsoft TechNet. (n.d.). Retrieved April 25, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-27">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa378612(v=vs.85).aspx" name="scite-27" rel="nofollow" target="_blank">
        Microsoft TechNet. (n.d.). Retrieved April 25, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
