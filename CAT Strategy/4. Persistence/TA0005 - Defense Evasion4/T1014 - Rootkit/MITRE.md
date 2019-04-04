<div class="container-fluid">
 <h1>
  Rootkit
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Rootkits are programs that hide the existence of malware by intercepting (i.e.,
    <a href="https://attack.mitre.org/techniques/T1179">
     Hooking
    </a>
    ) and modifying operating system API calls that supply system information.
    <span class="scite-citeref-number" data-reference="Symantec Windows Rootkits" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.symantec.com/avcenter/reference/windows.rootkit.overview.pdf" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    Rootkits or rootkit enabling functionality may reside at the user or kernel level in the operating system or lower, to include a
    <a href="https://attack.mitre.org/techniques/T1062">
     Hypervisor
    </a>
    , Master Boot Record, or the
    <a href="https://attack.mitre.org/techniques/T1019">
     System Firmware
    </a>
    .
    <span class="scite-citeref-number" data-reference="Wikipedia Rootkit" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://en.wikipedia.org/wiki/Rootkit" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Adversaries may use rootkits to hide the presence of programs, files, network connections, services, drivers, and other system components. Rootkits have been seen for Windows, Linux, and Mac OS X systems.
    <span class="scite-citeref-number" data-reference="CrowdStrike Linux Rootkit" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.crowdstrike.com/blog/http-iframe-injecting-linux-rootkit/" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="BlackHat Mac OSX Rootkit" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="http://www.blackhat.com/docs/asia-14/materials/Tsai/WP-Asia-14-Tsai-You-Cant-See-Me-A-Mac-OS-X-Rootkit-Uses-The-Tricks-You-Havent-Known-Yet.pdf" target="_blank">
       [4]
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
      : T1014
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
      Linux, macOS, Windows
      <br/>
      <br/>
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
      BIOS, MBR, System calls
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
      File monitoring, Host intrusion prevention systems, Process whitelisting, Signature-based detection, System access controls, Whitelisting by file name or path, Anti-virus
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
     <a href="https://attack.mitre.org/software/S0047">
      Hacking Team UEFI Rootkit
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0047">
       Hacking Team UEFI Rootkit
      </a>
      is a UEFI BIOS rootkit developed by the company Hacking Team to persist remote access software on some targeted systems.
      <span class="scite-citeref-number" data-reference="TrendMicro Hacking Team UEFI" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="http://blog.trendmicro.com/trendlabs-security-intelligence/hacking-team-uses-uefi-bios-rootkit-to-keep-rcs-9-agent-in-target-systems/" target="_blank">
         [5]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0135">
      HIDEDRV
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0135">
       HIDEDRV
      </a>
      is a rootkit that hides certain operating system artifacts.
      <span class="scite-citeref-number" data-reference="ESET Sednit Part 3" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part3.pdf" target="_blank">
         [6]
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
      starts a rootkit from a malicious file dropped to disk.
      <span class="scite-citeref-number" data-reference="Symantec Darkmoon Aug 2005" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
       <sup>
        <a aria-describedby="qtip-6" data-hasqtip="6" href="https://www.symantec.com/security_response/writeup.jsp?docid=2005-081910-3934-99" target="_blank">
         [7]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0221">
      Umbreon
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0221">
       Umbreon
      </a>
      hides from defenders by hooking libc function calls, hiding artifacts that would reveal its presence, such as the user account it creates to provide access and undermining strace, a tool often used to identify malware.
      <span class="scite-citeref-number" data-reference="Umbreon Trend Micro" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://blog.trendmicro.com/trendlabs-security-intelligence/pokemon-themed-umbreon-linux-rootkit-hits-x86-arm-systems/?_ga=2.180041126.367598458.1505420282-1759340220.1502477046" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0022">
      Uroburos
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0022">
       Uroburos
      </a>
      is a rootkit used by
      <a href="https://attack.mitre.org/groups/G0010">
       Turla
      </a>
      .
      <span class="scite-citeref-number" data-reference="Kaspersky Turla" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://securelist.com/the-epic-turla-operation/65545/" target="_blank">
         [9]
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
      used a rootkit to modify typical server functionality.
      <span class="scite-citeref-number" data-reference="Kaspersky Winnti April 2013" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://securelist.com/winnti-more-than-just-a-game/37029/" target="_blank">
         [10]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0027">
      Zeroaccess
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0027">
       Zeroaccess
      </a>
      is a kernel-mode rootkit.
      <span class="scite-citeref-number" data-reference="Sophos ZeroAccess" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="https://sophosnews.files.wordpress.com/2012/04/zeroaccess2.pdf" target="_blank">
         [11]
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
  Identify potentially malicious software that may contain rootkit functionality, and audit and/or block it by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-12-a">
   <sup>
    <a aria-describedby="qtip-11" data-hasqtip="11" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [12]
    </a>
   </sup>
  </span>
  tools, like AppLocker,
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-13-a">
   <sup>
    <a aria-describedby="qtip-12" data-hasqtip="12" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [13]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-14-a">
   <sup>
    <a aria-describedby="qtip-13" data-hasqtip="13" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [14]
    </a>
   </sup>
  </span>
  or Software Restriction Policies
  <span class="scite-citeref-number" data-reference="Corio 2008" id="scite-ref-15-a">
   <sup>
    <a aria-describedby="qtip-14" data-hasqtip="14" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" target="_blank">
     [15]
    </a>
   </sup>
  </span>
  where appropriate.
  <span class="scite-citeref-number" data-reference="TechNet Applocker vs SRP" id="scite-ref-16-a">
   <sup>
    <a aria-describedby="qtip-15" data-hasqtip="15" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" target="_blank">
     [16]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Some rootkit protections may be built into anti-virus or operating system software. There are dedicated rootkit detection tools that look for specific types of rootkit behavior. Monitor for the existence of unrecognized DLLs, devices, services, and changes to the MBR.
  <span class="scite-citeref-number" data-reference="Wikipedia Rootkit" id="scite-ref-2-a">
   <sup>
    <a aria-describedby="qtip-1" data-hasqtip="1" href="https://en.wikipedia.org/wiki/Rootkit" target="_blank">
     [2]
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
       <a class="external text" href="https://www.symantec.com/avcenter/reference/windows.rootkit.overview.pdf" name="scite-1" rel="nofollow" target="_blank">
        Symantec. (n.d.). Windows Rootkit Overview. Retrieved December 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://en.wikipedia.org/wiki/Rootkit" name="scite-2" rel="nofollow" target="_blank">
        Wikipedia. (2016, June 1). Rootkit. Retrieved June 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.crowdstrike.com/blog/http-iframe-injecting-linux-rootkit/" name="scite-3" rel="nofollow" target="_blank">
        Kurtz, G. (2012, November 19). HTTP iframe Injecting Linux Rootkit. Retrieved December 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.blackhat.com/docs/asia-14/materials/Tsai/WP-Asia-14-Tsai-You-Cant-See-Me-A-Mac-OS-X-Rootkit-Uses-The-Tricks-You-Havent-Known-Yet.pdf" name="scite-4" rel="nofollow" target="_blank">
        Pan, M., Tsai, S. (2014). You can’t see me: A Mac OS X Rootkit uses the tricks you haven't known yet. Retrieved December 21, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.trendmicro.com/trendlabs-security-intelligence/hacking-team-uses-uefi-bios-rootkit-to-keep-rcs-9-agent-in-target-systems/" name="scite-5" rel="nofollow" target="_blank">
        Lin, P. (2015, July 13). Hacking Team Uses UEFI BIOS Rootkit to Keep RCS 9 Agent in Target Systems. Retrieved December 11, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part3.pdf" name="scite-6" rel="nofollow" target="_blank">
        ESET. (2016, October). En Route with Sednit - Part 3: A Mysterious Downloader. Retrieved November 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/security_response/writeup.jsp?docid=2005-081910-3934-99" name="scite-7" rel="nofollow" target="_blank">
        Hayashi, K. (2005, August 18). Backdoor.Darkmoon. Retrieved February 23, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/pokemon-themed-umbreon-linux-rootkit-hits-x86-arm-systems/?_ga=2.180041126.367598458.1505420282-1759340220.1502477046" name="scite-8" rel="nofollow" target="_blank">
        Fernando Mercês. (2016, September 5). Pokémon-themed Umbreon Linux Rootkit Hits x86, ARM Systems. Retrieved March 5, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="9.0">
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/the-epic-turla-operation/65545/" name="scite-9" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2014, August 7). The Epic Turla Operation: Solving some of the mysteries of Snake/Uroburos. Retrieved December 11, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/winnti-more-than-just-a-game/37029/" name="scite-10" rel="nofollow" target="_blank">
        Kaspersky Lab's Global Research and Analysis Team. (2013, April 11). Winnti. More than just a game. Retrieved February 8, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://sophosnews.files.wordpress.com/2012/04/zeroaccess2.pdf" name="scite-11" rel="nofollow" target="_blank">
        Wyke, J. (2012, April). ZeroAccess. Retrieved July 18, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-12" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-13" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-14" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" name="scite-15" rel="nofollow" target="_blank">
        Corio, C., &amp; Sayana, D. P. (2008, June). Application Lockdown with Software Restriction Policies. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/en-us/library/ee791851.aspx" name="scite-16" rel="nofollow" target="_blank">
        Microsoft. (2012, June 27). Using Software Restriction Policies and AppLocker Policies. Retrieved April 7, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
