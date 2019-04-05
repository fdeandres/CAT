<div class="container-fluid">
 <h1>
  Hidden Files and Directories
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    To prevent normal users from accidentally changing special files on a system, most operating systems have the concept of a ‘hidden’ file. These files don’t show up when a user browses the file system with a GUI or when using normal commands on the command line. Users must explicitly ask to show the hidden files either via a series of Graphical User Interface (GUI) prompts or with command line switches (
    <code>
     dir /a
    </code>
    for Windows and
    <code>
     ls –a
    </code>
    for Linux and macOS).
   </p>
   <p>
    Adversaries can use this to their advantage to hide files and folders anywhere on the system for persistence and evading a typical user or system analysis that does not incorporate investigation of hidden files.
   </p>
   <h3>
    Windows
   </h3>
   <p>
    Users can mark specific files as hidden by using the attrib.exe binary. Simply do
    <code>
     attrib +h filename
    </code>
    to mark a file or folder as hidden. Similarly, the "+s" marks a file as a system file and the "+r" flag marks the file as read only. Like most windows binaries, the attrib.exe binary provides the ability to apply these changes recursively "/S".
   </p>
   <h3>
    Linux/Mac
   </h3>
   <p>
    Users can mark specific files as hidden simply by putting a "." as the first character in the file or folder name
    <span class="scite-citeref-number" data-reference="Sofacy Komplex Trojan" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://researchcenter.paloaltonetworks.com/2016/09/unit42-sofacys-komplex-os-x-trojan/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Antiquated Mac Malware" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://blog.malwarebytes.com/threat-analysis/2017/01/new-mac-backdoor-using-antiquated-code/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    . Files and folder that start with a period, ‘.’, are by default hidden from being viewed in the Finder application and standard command-line utilities like "ls". Users must specifically change settings to have these files viewable. For command line usages, there is typically a flag to see all files (including hidden ones). To view these files in the Finder Application, the following command must be executed:
    <code>
     defaults write com.apple.finder AppleShowAllFiles YES
    </code>
    , and then relaunch the Finder Application.
   </p>
   <h3>
    Mac
   </h3>
   <p>
    Files on macOS can be marked with the UF_HIDDEN flag which prevents them from being seen in Finder.app, but still allows them to be seen in Terminal.app
    <span class="scite-citeref-number" data-reference="WireLurker" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.paloaltonetworks.com/content/dam/pan/en_US/assets/pdf/reports/Unit_42/unit42-wirelurker.pdf" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    .Many applications create these hidden files and folders to store information so that it doesn’t clutter up the user’s workspace. For example, SSH utilities create a .ssh folder that’s hidden and contains the user’s known hosts and keys.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1158
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
      : Defense Evasion, Persistence
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
      File monitoring, Process monitoring, Process command-line parameters
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
      Host forensic analysis
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
     <a href="https://attack.mitre.org/groups/G0007">
      APT28
     </a>
    </td>
    <td>
     <p>
      An
      <a href="https://attack.mitre.org/groups/G0007">
       APT28
      </a>
      loader Trojan saves its payload with hidden file attributes.
      <span class="scite-citeref-number" data-reference="Unit 42 Playbook Dec 2017" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://pan-unit42.github.io/playbook_viewer/" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0274">
      Calisto
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0274">
       Calisto
      </a>
      uses a hidden directory named .calisto to store data from the victim’s machine before exfiltration.
      <span class="scite-citeref-number" data-reference="Securelist Calisto July 2018" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://securelist.com/calisto-trojan-for-macos/86543/" target="_blank">
         [5]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="Symantec Calisto July 2018" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.symantec.com/security-center/writeup/2018-073014-2512-99?om_rssid=sr-latestthreats30days" target="_blank">
         [6]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0277">
      FruitFly
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0277">
       FruitFly
      </a>
      saves itself with a leading "." to make it a hidden file.
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
     <a href="https://attack.mitre.org/software/S0278">
      iKitten
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0278">
       iKitten
      </a>
      saves itself with a leading "." so that it's hidden from users by default.
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
      payload is stored in a hidden directory at
      <code>
       /Users/Shared/.local/kextd
      </code>
      .
      <span class="scite-citeref-number" data-reference="Sofacy Komplex Trojan" id="scite-ref-1-a" onclick="scrollToRef('scite-1')">
       <sup>
        <a aria-describedby="qtip-0" data-hasqtip="0" href="https://researchcenter.paloaltonetworks.com/2016/09/unit42-sofacys-komplex-os-x-trojan/" target="_blank">
         [1]
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
      A
      <a href="https://attack.mitre.org/groups/G0032">
       Lazarus Group
      </a>
      VBA Macro sets its file attributes to System and Hidden.
      <span class="scite-citeref-number" data-reference="McAfee Lazarus Resurfaces Feb 2018" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
       <sup>
        <a aria-describedby="qtip-7" data-hasqtip="7" href="https://securingtomorrow.mcafee.com/mcafee-labs/lazarus-resurfaces-targets-global-banks-bitcoin-users/" target="_blank">
         [8]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0282">
      MacSpy
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0282">
       MacSpy
      </a>
      stores itself in
      <code>
       ~/Library/.DS_Stores/
      </code>
      <span class="scite-citeref-number" data-reference="alientvault macspy" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
       <sup>
        <a aria-describedby="qtip-8" data-hasqtip="8" href="https://www.alienvault.com/blogs/labs-research/macspy-os-x-rat-as-a-service" target="_blank">
         [9]
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
  Mitigation of this technique may be difficult and unadvised due to the the legitimate use of hidden files and directories.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor the file system and shell commands for files being created with a leading "." and the Windows command-line use of attrib.exe to add the hidden attribute.
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
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2016/09/unit42-sofacys-komplex-os-x-trojan/" name="scite-1" rel="nofollow" target="_blank">
        Dani Creus, Tyler Halfpop, Robert Falcone. (2016, September 26). Sofacy's 'Komplex' OS X Trojan. Retrieved July 8, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.malwarebytes.com/threat-analysis/2017/01/new-mac-backdoor-using-antiquated-code/" name="scite-2" rel="nofollow" target="_blank">
        Thomas Reed. (2017, January 18). New Mac backdoor using antiquated code. Retrieved July 5, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.paloaltonetworks.com/content/dam/pan/en_US/assets/pdf/reports/Unit_42/unit42-wirelurker.pdf" name="scite-3" rel="nofollow" target="_blank">
        Claud Xiao. (n.d.). WireLurker: A New Era in iOS and OS X Malware. Retrieved July 10, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://pan-unit42.github.io/playbook_viewer/" name="scite-4" rel="nofollow" target="_blank">
        Unit 42. (2017, December 15). Unit 42 Playbook Viewer. Retrieved December 20, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/calisto-trojan-for-macos/86543/" name="scite-5" rel="nofollow" target="_blank">
        Kuzin, M., Zelensky S. (2018, July 20). Calisto Trojan for macOS. Retrieved September 7, 2018.
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
       <a class="external text" href="https://www.symantec.com/security-center/writeup/2018-073014-2512-99?om_rssid=sr-latestthreats30days" name="scite-6" rel="nofollow" target="_blank">
        Pantig, J. (2018, July 30). OSX.Calisto. Retrieved September 7, 2018.
       </a>
      </span>
     </span>
    </li>
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
       <a class="external text" href="https://securingtomorrow.mcafee.com/mcafee-labs/lazarus-resurfaces-targets-global-banks-bitcoin-users/" name="scite-8" rel="nofollow" target="_blank">
        Sherstobitoff, R. (2018, February 12). Lazarus Resurfaces, Targets Global Banks and Bitcoin Users. Retrieved February 19, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.alienvault.com/blogs/labs-research/macspy-os-x-rat-as-a-service" name="scite-9" rel="nofollow" target="_blank">
        PETER EWANE. (2017, June 9). MacSpy: OS X RAT as a Service. Retrieved September 21, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
