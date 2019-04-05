<div class="container-fluid">
 <h1>
  Bypass User Account Control
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Windows User Account Control (UAC) allows a program to elevate its privileges to perform a task under administrator-level permissions by prompting the user for confirmation. The impact to the user ranges from denying the operation under high enforcement to allowing the user to perform the action if they are in the local administrators group and click through the prompt or allowing them to enter an administrator password to complete the action.
    <span class="scite-citeref-number" data-reference="TechNet How UAC Works" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://technet.microsoft.com/en-us/itpro/windows/keep-secure/how-user-account-control-works" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    If the UAC protection level of a computer is set to anything but the highest level, certain Windows programs are allowed to elevate privileges or execute some elevated COM objects without prompting the user through the UAC notification box.
    <span class="scite-citeref-number" data-reference="TechNet Inside UAC" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://technet.microsoft.com/en-US/magazine/2009.07.uac.aspx" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="MSDN COM Elevation" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://msdn.microsoft.com/en-us/library/ms679687.aspx" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    An example of this is use of rundll32.exe to load a specifically crafted DLL which loads an auto-elevated COM object and performs a file operation in a protected directory which would typically require elevated access. Malicious software may also be injected into a trusted process to gain elevated privileges without prompting a user.
    <span class="scite-citeref-number" data-reference="Davidson Windows" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="http://www.pretentiousname.com/misc/win7_uac_whitelist2.html" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    Adversaries can use these techniques to elevate privileges to administrator if the target process is unprotected.
   </p>
   <p>
    Many methods have been discovered to bypass UAC. The Github readme page for UACMe contains an extensive list of methods
    <span class="scite-citeref-number" data-reference="Github UACMe" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://github.com/hfiref0x/UACME" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    that have been discovered and implemented within UACMe, but may not be a comprehensive list of bypasses. Additional bypass methods are regularly discovered and some used in the wild, such as:
   </p>
   <ul>
    <li>
     <code>
      eventvwr.exe
     </code>
     can auto-elevate and execute a specified binary or script.
     <span class="scite-citeref-number" data-reference="enigma0x3 Fileless UAC Bypass" id="scite-ref-6-a">
      <sup>
       <a aria-describedby="qtip-5" data-hasqtip="5" href="https://enigma0x3.net/2016/08/15/fileless-uac-bypass-using-eventvwr-exe-and-registry-hijacking/" target="_blank">
        [6]
       </a>
      </sup>
     </span>
     <span class="scite-citeref-number" data-reference="Fortinet Fareit" id="scite-ref-7-a">
      <sup>
       <a aria-describedby="qtip-6" data-hasqtip="6" href="https://blog.fortinet.com/2016/12/16/malicious-macro-bypasses-uac-to-elevate-privilege-for-fareit-malware" target="_blank">
        [7]
       </a>
      </sup>
     </span>
    </li>
   </ul>
   <p>
    Another bypass is possible through some Lateral Movement techniques if credentials for an account with administrator privileges are known, since UAC is a single system security mechanism, and the privilege or integrity of a process running on one system will be unknown on lateral systems and default to high integrity.
    <span class="scite-citeref-number" data-reference="SANS UAC Bypass" id="scite-ref-8-a">
     <sup>
      <a aria-describedby="qtip-7" data-hasqtip="7" href="http://pen-testing.sans.org/blog/pen-testing/2013/08/08/psexec-uac-bypass" target="_blank">
       [8]
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
      : T1088
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
      Administrator
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      System calls, Process monitoring, Authentication logs, Process command-line parameters
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
       Contributors:
      </span>
      Stefan Kanthak; Casey Smith
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
     <a href="https://attack.mitre.org/groups/G0016">
      APT29
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0016">
       APT29
      </a>
      has bypassed UAC.
      <span class="scite-citeref-number" data-reference="Mandiant No Easy Breach" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="http://www.slideshare.net/MatthewDunwoody1/no-easy-breach-derby-con-2016" target="_blank">
         [9]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0129">
      AutoIt backdoor
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0129">
       AutoIt backdoor
      </a>
      attempts to escalate privileges by bypassing User Access Control.
      <span class="scite-citeref-number" data-reference="Forcepoint Monsoon" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0089">
      BlackEnergy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0089">
       BlackEnergy
      </a>
      attempts to bypass default User Access Control (UAC) settings by exploiting a backward-compatibility setting found in Windows 7 and later.
      <span class="scite-citeref-number" data-reference="F-Secure BlackEnergy 2014" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://www.f-secure.com/documents/996508/1030745/blackenergy_whitepaper.pdf" target="_blank">
         [11]
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
      malware xxmm contains a UAC bypass tool for privilege escalation.
      <span class="scite-citeref-number" data-reference="Secureworks BRONZE BUTLER Oct 2017" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
       <sup>
        <a aria-describedby="qtip-11" data-hasqtip="11" href="https://www.secureworks.com/research/bronze-butler-targets-japanese-businesses" target="_blank">
         [12]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0080">
      Cobalt Group
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0080">
       Cobalt Group
      </a>
      has bypassed UAC.
      <span class="scite-citeref-number" data-reference="Group IB Cobalt Aug 2017" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
       <sup>
        <a aria-describedby="qtip-12" data-hasqtip="12" href="https://www.group-ib.com/blog/cobalt" target="_blank">
         [13]
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
      can use a number of known techniques to bypass Windows UAC.
      <span class="scite-citeref-number" data-reference="cobaltstrike manual" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
       <sup>
        <a aria-describedby="qtip-13" data-hasqtip="13" href="https://cobaltstrike.com/downloads/csmanual38.pdf" target="_blank">
         [14]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0134">
      Downdelph
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0134">
       Downdelph
      </a>
      bypasses UAC to escalate privileges by using a custom "RedirectEXE" shim database.
      <span class="scite-citeref-number" data-reference="ESET Sednit Part 3" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
       <sup>
        <a aria-describedby="qtip-14" data-hasqtip="14" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part3.pdf" target="_blank">
         [15]
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
      performs UAC bypass.
      <span class="scite-citeref-number" data-reference="FinFisher Citation" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
       <sup>
        <a aria-describedby="qtip-15" data-hasqtip="15" href="http://www.finfisher.com/FinFisher/index.html" target="_blank">
         [16]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Microsoft FinFisher March 2018" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
       <sup>
        <a aria-describedby="qtip-16" data-hasqtip="16" href="https://cloudblogs.microsoft.com/microsoftsecure/2018/03/01/finfisher-exposed-a-researchers-tale-of-defeating-traps-tricks-and-complex-virtual-machines/" target="_blank">
         [17]
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
      bypasses user access control by using a DLL hijacking vulnerability in the Windows Update Standalone Installer (wusa.exe).
      <span class="scite-citeref-number" data-reference="Cisco H1N1 Part 2" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
       <sup>
        <a aria-describedby="qtip-17" data-hasqtip="17" href="http://blogs.cisco.com/security/h1n1-technical-analysis-reveals-new-capabilities-part-2" target="_blank">
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
      uses a combination of NTWDBLIB.dll and cliconfg.exe to bypass UAC protections using DLL hijacking.
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
     <a href="https://attack.mitre.org/software/S0260">
      InvisiMole
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0260">
       InvisiMole
      </a>
      can bypass UAC and create an elevated COM object to escalate privileges.
      <span class="scite-citeref-number" data-reference="ESET InvisiMole June 2018" id="scite-ref-20-a" onclick="scrollToRef('scite-20')">
       <sup>
        <a aria-describedby="qtip-19" data-hasqtip="19" href="https://www.welivesecurity.com/2018/06/07/invisimole-equipped-spyware-undercover/" target="_blank">
         [20]
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
      has 2 methods for elevating integrity. It can bypass UAC through eventvwr.exe and sdclt.exe.
      <span class="scite-citeref-number" data-reference="Github Koadic" id="scite-ref-21-a" onclick="scrollToRef('scite-21')">
       <sup>
        <a aria-describedby="qtip-20" data-hasqtip="20" href="https://github.com/zerosum0x0/koadic" target="_blank">
         [21]
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
      bypassed User Access Control (UAC).
      <span class="scite-citeref-number" data-reference="Cymmetria Patchwork" id="scite-ref-22-a" onclick="scrollToRef('scite-22')">
       <sup>
        <a aria-describedby="qtip-21" data-hasqtip="21" href="https://s3-us-west-2.amazonaws.com/cymmetria-blog/public/Unveiling_Patchwork.pdf" target="_blank">
         [22]
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
      An older variant of
      <a href="https://attack.mitre.org/software/S0254">
       PLAINTEE
      </a>
      performs UAC bypass.
      <span class="scite-citeref-number" data-reference="Rancor Unit42 June 2018" id="scite-ref-23-a" onclick="scrollToRef('scite-23')">
       <sup>
        <a aria-describedby="qtip-22" data-hasqtip="22" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-rancor-targeted-attacks-south-east-asia-using-plaintee-ddkong-malware-families/" target="_blank">
         [23]
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
      can bypass Windows UAC through either DLL hijacking, eventvwr, or appPaths.
      <span class="scite-citeref-number" data-reference="GitHub Pupy" id="scite-ref-24-a" onclick="scrollToRef('scite-24')">
       <sup>
        <a aria-describedby="qtip-23" data-hasqtip="23" href="https://github.com/n1nj4sec/pupy" target="_blank">
         [24]
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
      can attempt to run the program as admin, then show a fake error message and a legitimate UAC bypass prompt to the user in an attempt to socially engineer the user into escalating privileges.
      <span class="scite-citeref-number" data-reference="ESET RTM Feb 2017" id="scite-ref-25-a" onclick="scrollToRef('scite-25')">
       <sup>
        <a aria-describedby="qtip-24" data-hasqtip="24" href="https://www.welivesecurity.com/wp-content/uploads/2017/02/Read-The-Manual.pdf" target="_blank">
         [25]
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
      contains UAC bypass code for both 32- and 64-bit systems.
      <span class="scite-citeref-number" data-reference="Dell Sakula" id="scite-ref-26-a" onclick="scrollToRef('scite-26')">
       <sup>
        <a aria-describedby="qtip-25" data-hasqtip="25" href="http://www.secureworks.com/cyber-threat-intelligence/threats/sakula-malware-family/" target="_blank">
         [26]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0140">
      Shamoon
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0140">
       Shamoon
      </a>
      attempts to disable UAC remote restrictions by modifying the Registry.
      <span class="scite-citeref-number" data-reference="Palo Alto Shamoon Nov 2016" id="scite-ref-27-a" onclick="scrollToRef('scite-27')">
       <sup>
        <a aria-describedby="qtip-26" data-hasqtip="26" href="http://researchcenter.paloaltonetworks.com/2016/11/unit42-shamoon-2-return-disttrack-wiper/" target="_blank">
         [27]
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
      A
      <a href="https://attack.mitre.org/groups/G0027">
       Threat Group-3390
      </a>
      tool can use a public UAC bypass method to elevate privileges.
      <span class="scite-citeref-number" data-reference="Nccgroup Emissary Panda May 2018" id="scite-ref-28-a" onclick="scrollToRef('scite-28')">
       <sup>
        <a aria-describedby="qtip-27" data-hasqtip="27" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/may/emissary-panda-a-potential-new-malicious-tool/" target="_blank">
         [28]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0116">
      UACMe
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0116">
       UACMe
      </a>
      contains many methods for bypassing Windows User Account Control on multiple versions of the operating system.
      <span class="scite-citeref-number" data-reference="Github UACMe" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://github.com/hfiref0x/UACME" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0230">
      ZeroT
     </a>
    </td>
    <td>
     <p>
      Many
      <a href="https://attack.mitre.org/software/S0230">
       ZeroT
      </a>
      samples can perform UAC bypass by using eventvwr.exe to execute a malicious file.
      <span class="scite-citeref-number" data-reference="Proofpoint ZeroT Feb 2017" id="scite-ref-29-a" onclick="scrollToRef('scite-29')">
       <sup>
        <a aria-describedby="qtip-28" data-hasqtip="28" href="https://www.proofpoint.com/us/threat-insight/post/APT-targets-russia-belarus-zerot-plugx" target="_blank">
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
  Remove users from the local administrator group on systems. Although UAC bypass techniques exist, it is still prudent to use the highest enforcement level for UAC when possible and mitigate bypass opportunities that exist with techniques such as
  <a href="https://attack.mitre.org/techniques/T1038">
   DLL Search Order Hijacking
  </a>
  .
 </p>
 <p>
  Check for common UAC bypass weaknesses on Windows systems to be aware of the risk posture and address issues where appropriate.
  <span class="scite-citeref-number" data-reference="Github UACMe" id="scite-ref-5-a">
   <sup>
    <a aria-describedby="qtip-4" data-hasqtip="4" href="https://github.com/hfiref0x/UACME" target="_blank">
     [5]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  There are many ways to perform UAC bypasses when a user is in the local administrator group on a system, so it may be difficult to target detection on all variations. Efforts should likely be placed on mitigation and collecting enough information on process launches and actions that could be performed before and after a UAC bypass is performed. Monitor process API calls for behavior that may be indicative of
  <a href="https://attack.mitre.org/techniques/T1055">
   Process Injection
  </a>
  and unusual loaded DLLs through
  <a href="https://attack.mitre.org/techniques/T1038">
   DLL Search Order Hijacking
  </a>
  , which indicate attempts to gain access to higher privileged processes.
 </p>
 <p>
  Some UAC bypass methods rely on modifying specific, user-accessible Registry settings. For example:
 </p>
 <ul>
  <li>
   The
   <code>
    eventvwr.exe
   </code>
   bypass uses the
   <code>
    [HKEY_CURRENT_USER]\Software\Classes\mscfile\shell\open\command
   </code>
   Registry key.
   <span class="scite-citeref-number" data-reference="enigma0x3 Fileless UAC Bypass" id="scite-ref-6-a">
    <sup>
     <a aria-describedby="qtip-5" data-hasqtip="5" href="https://enigma0x3.net/2016/08/15/fileless-uac-bypass-using-eventvwr-exe-and-registry-hijacking/" target="_blank">
      [6]
     </a>
    </sup>
   </span>
  </li>
  <li>
   The
   <code>
    sdclt.exe
   </code>
   bypass uses the
   <code>
    [HKEY_CURRENT_USER]\Software\Microsoft\Windows\CurrentVersion\App Paths\control.exe
   </code>
   and
   <code>
    [HKEY_CURRENT_USER]\Software\Classes\exefile\shell\runas\command\isolatedCommand
   </code>
   Registry keys.
   <span class="scite-citeref-number" data-reference="enigma0x3 sdclt app paths" id="scite-ref-30-a">
    <sup>
     <a aria-describedby="qtip-29" data-hasqtip="29" href="https://enigma0x3.net/2017/03/14/bypassing-uac-using-app-paths/" target="_blank">
      [30]
     </a>
    </sup>
   </span>
   <span class="scite-citeref-number" data-reference="enigma0x3 sdclt bypass" id="scite-ref-31-a">
    <sup>
     <a aria-describedby="qtip-30" data-hasqtip="30" href="https://enigma0x3.net/2017/03/17/fileless-uac-bypass-using-sdclt-exe/" target="_blank">
      [31]
     </a>
    </sup>
   </span>
  </li>
 </ul>
 <p>
  Analysts should monitor these Registry settings for unauthorized changes.
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
       <a class="external text" href="https://technet.microsoft.com/en-us/itpro/windows/keep-secure/how-user-account-control-works" name="scite-1" rel="nofollow" target="_blank">
        Lich, B. (2016, May 31). How User Account Control Works. Retrieved June 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-US/magazine/2009.07.uac.aspx" name="scite-2" rel="nofollow" target="_blank">
        Russinovich, M. (2009, July). User Account Control: Inside Windows 7 User Account Control. Retrieved July 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/en-us/library/ms679687.aspx" name="scite-3" rel="nofollow" target="_blank">
        Microsoft. (n.d.). The COM Elevation Moniker. Retrieved July 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.pretentiousname.com/misc/win7_uac_whitelist2.html" name="scite-4" rel="nofollow" target="_blank">
        Davidson, L. (n.d.). Windows 7 UAC whitelist. Retrieved November 12, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/hfiref0x/UACME" name="scite-5" rel="nofollow" target="_blank">
        UACME Project. (2016, June 16). UACMe. Retrieved July 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://enigma0x3.net/2016/08/15/fileless-uac-bypass-using-eventvwr-exe-and-registry-hijacking/" name="scite-6" rel="nofollow" target="_blank">
        Nelson, M. (2016, August 15). "Fileless" UAC Bypass using eventvwr.exe and Registry Hijacking. Retrieved December 27, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.fortinet.com/2016/12/16/malicious-macro-bypasses-uac-to-elevate-privilege-for-fareit-malware" name="scite-7" rel="nofollow" target="_blank">
        Salvio, J., Joven, R. (2016, December 16). Malicious Macro Bypasses UAC to Elevate Privilege for Fareit Malware. Retrieved December 27, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="http://pen-testing.sans.org/blog/pen-testing/2013/08/08/psexec-uac-bypass" name="scite-8" rel="nofollow" target="_blank">
        Medin, T. (2013, August 8). PsExec UAC Bypass. Retrieved June 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.slideshare.net/MatthewDunwoody1/no-easy-breach-derby-con-2016" name="scite-9" rel="nofollow" target="_blank">
        Dunwoody, M. and Carr, N.. (2016, September 27). No Easy Breach DerbyCon 2016. Retrieved October 4, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf" name="scite-10" rel="nofollow" target="_blank">
        Settle, A., et al. (2016, August 8). MONSOON - Analysis Of An APT Campaign. Retrieved September 22, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.f-secure.com/documents/996508/1030745/blackenergy_whitepaper.pdf" name="scite-11" rel="nofollow" target="_blank">
        F-Secure Labs. (2014). BlackEnergy &amp; Quedagh: The convergence of crimeware and APT attacks. Retrieved March 24, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.secureworks.com/research/bronze-butler-targets-japanese-businesses" name="scite-12" rel="nofollow" target="_blank">
        Counter Threat Unit Research Team. (2017, October 12). BRONZE BUTLER Targets Japanese Enterprises. Retrieved January 4, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.group-ib.com/blog/cobalt" name="scite-13" rel="nofollow" target="_blank">
        Matveeva, V. (2017, August 15). Secrets of Cobalt. Retrieved October 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://cobaltstrike.com/downloads/csmanual38.pdf" name="scite-14" rel="nofollow" target="_blank">
        Strategic Cyber LLC. (2017, March 14). Cobalt Strike Manual. Retrieved May 24, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part3.pdf" name="scite-15" rel="nofollow" target="_blank">
        ESET. (2016, October). En Route with Sednit - Part 3: A Mysterious Downloader. Retrieved November 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.finfisher.com/FinFisher/index.html" name="scite-16" rel="nofollow" target="_blank">
        FinFisher. (n.d.). Retrieved December 20, 2017.
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
       <a class="external text" href="https://cloudblogs.microsoft.com/microsoftsecure/2018/03/01/finfisher-exposed-a-researchers-tale-of-defeating-traps-tricks-and-complex-virtual-machines/" name="scite-17" rel="nofollow" target="_blank">
        Allievi, A.,Flori, E. (2018, March 01). FinFisher exposed: A researcher’s tale of defeating traps, tricks, and complex virtual machines. Retrieved July 9, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-18">
      <span class="scite-citation-text">
       <a class="external text" href="http://blogs.cisco.com/security/h1n1-technical-analysis-reveals-new-capabilities-part-2" name="scite-18" rel="nofollow" target="_blank">
        Reynolds, J.. (2016, September 14). H1N1: Technical analysis reveals new capabilities – part 2. Retrieved September 26, 2016.
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
       <a class="external text" href="https://www.welivesecurity.com/2018/06/07/invisimole-equipped-spyware-undercover/" name="scite-20" rel="nofollow" target="_blank">
        Hromcová, Z. (2018, June 07). InvisiMole: Surprisingly equipped spyware, undercover since 2013. Retrieved July 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-21">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/zerosum0x0/koadic" name="scite-21" rel="nofollow" target="_blank">
        Magius, J., et al. (2017, July 19). Koadic. Retrieved June 18, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-22">
      <span class="scite-citation-text">
       <a class="external text" href="https://s3-us-west-2.amazonaws.com/cymmetria-blog/public/Unveiling_Patchwork.pdf" name="scite-22" rel="nofollow" target="_blank">
        Cymmetria. (2016). Unveiling Patchwork - The Copy-Paste APT. Retrieved August 3, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-23">
      <span class="scite-citation-text">
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2018/06/unit42-rancor-targeted-attacks-south-east-asia-using-plaintee-ddkong-malware-families/" name="scite-23" rel="nofollow" target="_blank">
        Ash, B., et al. (2018, June 26). RANCOR: Targeted Attacks in South East Asia Using PLAINTEE and DDKONG Malware Families. Retrieved July 2, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-24">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/n1nj4sec/pupy" name="scite-24" rel="nofollow" target="_blank">
        Nicolas Verdier. (n.d.). Retrieved January 29, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-25">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/wp-content/uploads/2017/02/Read-The-Manual.pdf" name="scite-25" rel="nofollow" target="_blank">
        Faou, M. and Boutin, J.. (2017, February). Read The Manual: A Guide to the RTM Banking Trojan. Retrieved March 9, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-26">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.secureworks.com/cyber-threat-intelligence/threats/sakula-malware-family/" name="scite-26" rel="nofollow" target="_blank">
        Dell SecureWorks Counter Threat Unit Threat Intelligence. (2015, July 30). Sakula Malware Family. Retrieved January 26, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-27">
      <span class="scite-citation-text">
       <a class="external text" href="http://researchcenter.paloaltonetworks.com/2016/11/unit42-shamoon-2-return-disttrack-wiper/" name="scite-27" rel="nofollow" target="_blank">
        Falcone, R.. (2016, November 30). Shamoon 2: Return of the Disttrack Wiper. Retrieved January 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-28">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/may/emissary-panda-a-potential-new-malicious-tool/" name="scite-28" rel="nofollow" target="_blank">
        Pantazopoulos, N., Henry T. (2018, May 18). Emissary Panda – A potential new malicious tool. Retrieved June 25, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-29">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.proofpoint.com/us/threat-insight/post/APT-targets-russia-belarus-zerot-plugx" name="scite-29" rel="nofollow" target="_blank">
        Huss, D., et al. (2017, February 2). Oops, they did it again: APT Targets Russia and Belarus with ZeroT and PlugX. Retrieved April 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-30">
      <span class="scite-citation-text">
       <a class="external text" href="https://enigma0x3.net/2017/03/14/bypassing-uac-using-app-paths/" name="scite-30" rel="nofollow" target="_blank">
        Nelson, M. (2017, March 14). Bypassing UAC using App Paths. Retrieved May 25, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-31">
      <span class="scite-citation-text">
       <a class="external text" href="https://enigma0x3.net/2017/03/17/fileless-uac-bypass-using-sdclt-exe/" name="scite-31" rel="nofollow" target="_blank">
        Nelson, M. (2017, March 17). "Fileless" UAC Bypass Using sdclt.exe. Retrieved May 25, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
