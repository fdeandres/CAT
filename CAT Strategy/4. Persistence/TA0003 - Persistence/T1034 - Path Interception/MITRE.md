<div class="container-fluid">
 <h1>
  Path Interception
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Path interception occurs when an executable is placed in a specific path so that it is executed by an application instead of the intended target. One example of this was the use of a copy of
    <a href="https://attack.mitre.org/software/S0106">
     cmd
    </a>
    in the current working directory of a vulnerable application that loads a CMD or BAT file with the CreateProcess function.
    <span class="scite-citeref-number" data-reference="TechNet MS14-019" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://blogs.technet.microsoft.com/srd/2014/04/08/ms14-019-fixing-a-binary-hijacking-via-cmd-or-bat-file/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
   </p>
   <p>
    There are multiple distinct weaknesses or misconfigurations that adversaries may take advantage of when performing path interception: unquoted paths, path environment variable misconfigurations, and search order hijacking. The first vulnerability deals with full program paths, while the second and third occur when program paths are not specified. These techniques can be used for persistence if executables are called on a regular basis, as well as privilege escalation if intercepted executables are started by a higher privileged process.
   </p>
   <h3>
    Unquoted Paths
   </h3>
   <p>
    Service paths (stored in Windows Registry keys)
    <span class="scite-citeref-number" data-reference="Microsoft Subkey" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="http://support.microsoft.com/KB/103000" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    and shortcut paths are vulnerable to path interception if the path has one or more spaces and is not surrounded by quotation marks (e.g.,
    <code>
     C:\unsafe path with space\program.exe
    </code>
    vs.
    <code>
     "C:\safe path with space\program.exe"
    </code>
    ).
    <span class="scite-citeref-number" data-reference="Baggett 2012" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://isc.sans.edu/diary/Help+eliminate+unquoted+path+vulnerabilities/14464" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    An adversary can place an executable in a higher level directory of the path, and Windows will resolve that executable instead of the intended executable. For example, if the path in a shortcut is
    <code>
     C:\program files\myapp.exe
    </code>
    , an adversary may create a program at
    <code>
     C:\program.exe
    </code>
    that will be run instead of the intended program.
    <span class="scite-citeref-number" data-reference="SecurityBoulevard Unquoted Services APR 2018" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://securityboulevard.com/2018/04/windows-privilege-escalation-unquoted-services/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="SploitSpren Windows Priv Jan 2018" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.sploitspren.com/2018-01-26-Windows-Privilege-Escalation-Guide/" target="_blank">
       [5]
      </a>
     </sup>
    </span>
   </p>
   <h3>
    PATH Environment Variable Misconfiguration
   </h3>
   <p>
    The PATH environment variable contains a list of directories. Certain methods of executing a program (namely using cmd.exe or the command-line) rely solely on the PATH environment variable to determine the locations that are searched for a program when the path for the program is not given. If any directories are listed in the PATH environment variable before the Windows directory,
    <code>
     %SystemRoot%\system32
    </code>
    (e.g.,
    <code>
     C:\Windows\system32
    </code>
    ), a program may be placed in the preceding directory that is named the same as a Windows program (such as cmd, PowerShell, or Python), which will be executed when that command is executed from a script or command-line.
   </p>
   <p>
    For example, if
    <code>
     C:\example path
    </code>
    precedes
    <code>
     C:\Windows\system32
    </code>
    is in the PATH environment variable, a program that is named net.exe and placed in
    <code>
     C:\example path
    </code>
    will be called instead of the Windows system "net" when "net" is executed from the command-line.
   </p>
   <h3>
    Search Order Hijacking
   </h3>
   <p>
    Search order hijacking occurs when an adversary abuses the order in which Windows searches for programs that are not given a path. The search order differs depending on the method that is used to execute the program.
    <span class="scite-citeref-number" data-reference="Microsoft CreateProcess" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="http://msdn.microsoft.com/en-us/library/ms682425" target="_blank">
       [6]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Hill NT Shell" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="http://technet.microsoft.com/en-us/library/cc723564.aspx#XSLTsection127121120120" target="_blank">
       [7]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Microsoft WinExec" id="scite-ref-8-a">
     <sup>
      <a aria-describedby="qtip-7" data-hasqtip="7" href="http://msdn.microsoft.com/en-us/library/ms687393" target="_blank">
       [8]
      </a>
     </sup>
    </span>
    However, it is common for Windows to search in the directory of the initiating program before searching through the Windows system directory. An adversary who finds a program vulnerable to search order hijacking (i.e., a program that does not specify the path to an executable) may take advantage of this vulnerability by creating a program named after the improperly specified program and placing it within the initiating program's directory.
   </p>
   <p>
    For example, "example.exe" runs "cmd.exe" with the command-line argument
    <code>
     net user
    </code>
    . An adversary may place a program called "net.exe" within the same directory as example.exe, "net.exe" will be run instead of the Windows system utility net. In addition, if an adversary places a program called "net.com" in the same directory as "net.exe", then
    <code>
     cmd.exe /C net user
    </code>
    will execute "net.com" instead of "net.exe" due to the order of executable extensions defined under PATHEXT.
    <span class="scite-citeref-number" data-reference="MSDN Environment Property" id="scite-ref-9-a">
     <sup>
      <a aria-describedby="qtip-8" data-hasqtip="8" href="https://msdn.microsoft.com/en-us/library/fd7hxfdd.aspx" target="_blank">
       [9]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Search order hijacking is also a common practice for hijacking DLL loads and is covered in
    <a href="https://attack.mitre.org/techniques/T1038">
     DLL Search Order Hijacking
    </a>
    .
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1034
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
      : Persistence, Privilege Escalation
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
      User, Administrator, SYSTEM
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Effective Permissions:
      </span>
      User, Administrator, SYSTEM
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      File monitoring, Process monitoring
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
       CAPEC ID:
      </span>
      <a href="https://capec.mitre.org/data/definitions/159.html" target="_blank">
       CAPEC-159
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
      Stefan Kanthak
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
     <a href="https://attack.mitre.org/software/S0194">
      PowerSploit
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0194">
       PowerSploit
      </a>
      contains a collection of Privesc-PowerUp modules that can discover and exploit various path interception opportunities in services, processes, and variables.
      <span class="scite-citeref-number" data-reference="GitHub PowerSploit May 2012" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://github.com/PowerShellMafia/PowerSploit" target="_blank">
         [10]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="PowerSploit Documentation" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
       <sup>
        <a aria-describedby="qtip-10" data-hasqtip="10" href="http://powersploit.readthedocs.io" target="_blank">
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
  Eliminate path interception weaknesses in program configuration files, scripts, the PATH environment variable, services, and in shortcuts by surrounding PATH variables with quotation marks when functions allow for them
  <span class="scite-citeref-number" data-reference="Microsoft CreateProcess" id="scite-ref-6-a">
   <sup>
    <a aria-describedby="qtip-5" data-hasqtip="5" href="http://msdn.microsoft.com/en-us/library/ms682425" target="_blank">
     [6]
    </a>
   </sup>
  </span>
  . Be aware of the search order Windows uses for executing or loading binaries and use fully qualified paths wherever appropriate
  <span class="scite-citeref-number" data-reference="MSDN DLL Security" id="scite-ref-12-a">
   <sup>
    <a aria-describedby="qtip-11" data-hasqtip="11" href="https://msdn.microsoft.com/en-us/library/ff919712.aspx" target="_blank">
     [12]
    </a>
   </sup>
  </span>
  . Clean up old Windows Registry keys when software is uninstalled to avoid keys with no associated legitimate binaries.
 </p>
 <p>
  Periodically search for and correct or report path interception weaknesses on systems that may have been introduced using custom or available tools that report software using insecure path configurations
  <span class="scite-citeref-number" data-reference="Kanthak Sentinel" id="scite-ref-13-a">
   <sup>
    <a aria-describedby="qtip-12" data-hasqtip="12" href="https://skanthak.homepage.t-online.de/sentinel.html" target="_blank">
     [13]
    </a>
   </sup>
  </span>
  .
 </p>
 <p>
  Require that all executables be placed in write-protected directories. Ensure that proper permissions and directory access control are set to deny users the ability to write files to the top-level directory
  <code>
   C:
  </code>
  and system directories, such as
  <code>
   C:\Windows\
  </code>
  , to reduce places where malicious files could be placed for execution.
 </p>
 <p>
  Identify and block potentially malicious software that may be executed through the path interception by using whitelisting
  <span class="scite-citeref-number" data-reference="Beechey 2010" id="scite-ref-14-a">
   <sup>
    <a aria-describedby="qtip-13" data-hasqtip="13" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" target="_blank">
     [14]
    </a>
   </sup>
  </span>
  tools, like AppLocker
  <span class="scite-citeref-number" data-reference="Windows Commands JPCERT" id="scite-ref-15-a">
   <sup>
    <a aria-describedby="qtip-14" data-hasqtip="14" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" target="_blank">
     [15]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="NSA MS AppLocker" id="scite-ref-16-a">
   <sup>
    <a aria-describedby="qtip-15" data-hasqtip="15" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" target="_blank">
     [16]
    </a>
   </sup>
  </span>
  or Software Restriction Policies,
  <span class="scite-citeref-number" data-reference="Corio 2008" id="scite-ref-17-a">
   <sup>
    <a aria-describedby="qtip-16" data-hasqtip="16" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" target="_blank">
     [17]
    </a>
   </sup>
  </span>
  that are capable of auditing and/or blocking unknown executables.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor file creation for files named after partial directories and in locations that may be searched for common processes through the environment variable, or otherwise should not be user writable. Monitor the executing process for process executable paths that are named for partial directories. Monitor file creation for programs that are named after Windows system programs or programs commonly executed without a path (such as "findstr," "net," and "python"). If this activity occurs outside of known administration activity, upgrades, installations, or patches, then it may be suspicious.
 </p>
 <p>
  Data and events should not be viewed in isolation, but as part of a chain of behavior that could lead to other activities, such as network connections made for Command and Control, learning details about the environment through Discovery, and Lateral Movement.
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
       <a class="external text" href="https://blogs.technet.microsoft.com/srd/2014/04/08/ms14-019-fixing-a-binary-hijacking-via-cmd-or-bat-file/" name="scite-1" rel="nofollow" target="_blank">
        Nagaraju, S. (2014, April 8). MS14-019 – Fixing a binary hijacking via .cmd or .bat file. Retrieved July 25, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://support.microsoft.com/KB/103000" name="scite-2" rel="nofollow" target="_blank">
        Microsoft. (n.d.). CurrentControlSet\Services Subkey Entries. Retrieved November 30, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://isc.sans.edu/diary/Help+eliminate+unquoted+path+vulnerabilities/14464" name="scite-3" rel="nofollow" target="_blank">
        Baggett, M. (2012, November 8). Help eliminate unquoted path vulnerabilities. Retrieved December 4, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://securityboulevard.com/2018/04/windows-privilege-escalation-unquoted-services/" name="scite-4" rel="nofollow" target="_blank">
        HackHappy. (2018, April 23). Windows Privilege Escalation – Unquoted Services. Retrieved August 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.sploitspren.com/2018-01-26-Windows-Privilege-Escalation-Guide/" name="scite-5" rel="nofollow" target="_blank">
        McFarland, R. (2018, January 26). Windows Privilege Escalation Guide. Retrieved August 10, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="http://msdn.microsoft.com/en-us/library/ms682425" name="scite-6" rel="nofollow" target="_blank">
        Microsoft. (n.d.). CreateProcess function. Retrieved December 5, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/library/cc723564.aspx#XSLTsection127121120120" name="scite-7" rel="nofollow" target="_blank">
        Hill, T. (n.d.). Windows NT Command Shell. Retrieved December 5, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="http://msdn.microsoft.com/en-us/library/ms687393" name="scite-8" rel="nofollow" target="_blank">
        Microsoft. (n.d.). WinExec function. Retrieved December 5, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/en-us/library/fd7hxfdd.aspx" name="scite-9" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Environment Property. Retrieved July 27, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="10.5">
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellMafia/PowerSploit" name="scite-10" rel="nofollow" target="_blank">
        PowerShellMafia. (2012, May 26). PowerSploit - A PowerShell Post-Exploitation Framework. Retrieved February 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="http://powersploit.readthedocs.io" name="scite-11" rel="nofollow" target="_blank">
        PowerSploit. (n.d.). PowerSploit. Retrieved February 6, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/en-us/library/ff919712.aspx" name="scite-12" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Dynamic-Link Library Security. Retrieved July 25, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-13">
      <span class="scite-citation-text">
       <a class="external text" href="https://skanthak.homepage.t-online.de/sentinel.html" name="scite-13" rel="nofollow" target="_blank">
        Kanthak, S. (2016, July 20). Vulnerability and Exploit Detector. Retrieved February 3, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-14">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599" name="scite-14" rel="nofollow" target="_blank">
        Beechey, J. (2010, December). Application Whitelisting: Panacea or Propaganda?. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-15">
      <span class="scite-citation-text">
       <a class="external text" href="http://blog.jpcert.or.jp/2016/01/windows-commands-abused-by-attackers.html" name="scite-15" rel="nofollow" target="_blank">
        Tomonaga, S. (2016, January 26). Windows Commands Abused by Attackers. Retrieved February 2, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-16">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.iad.gov/iad/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm" name="scite-16" rel="nofollow" target="_blank">
        NSA Information Assurance Directorate. (2014, August). Application Whitelisting Using Microsoft AppLocker. Retrieved March 31, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-17">
      <span class="scite-citation-text">
       <a class="external text" href="http://technet.microsoft.com/en-us/magazine/2008.06.srp.aspx" name="scite-17" rel="nofollow" target="_blank">
        Corio, C., &amp; Sayana, D. P. (2008, June). Application Lockdown with Software Restriction Policies. Retrieved November 18, 2014.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
