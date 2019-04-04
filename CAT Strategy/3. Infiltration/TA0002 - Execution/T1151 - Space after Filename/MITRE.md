<div class="container-fluid">
 <h1>
  Space after Filename
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Adversaries can hide a program's true filetype by changing the extension of a file. With certain file types (specifically this does not work with .app extensions), appending a space to the end of a filename will change how the file is processed by the operating system. For example, if there is a Mach-O executable file called evil.bin, when it is double clicked by a user, it will launch Terminal.app and execute. If this file is renamed to evil.txt, then when double clicked by a user, it will launch with the default text editing application (not executing the binary). However, if the file is renamed to "evil.txt " (note the space at the end), then when double clicked by a user, the true file type is determined by the OS and handled appropriately and the binary will be executed
    <span class="scite-citeref-number" data-reference="Mac Backdoors are back" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://arstechnica.com/security/2016/07/after-hiatus-in-the-wild-mac-backdoors-are-suddenly-back/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    .
   </p>
   <p>
    Adversaries can use this feature to trick users into double clicking benign-looking files of any format and ultimately executing something malicious.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1151
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
      : Defense Evasion, Execution
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Platform:
      </span>
      Linux, macOS
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
      Erye Hernandez, Palo Alto Networks
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
     <a href="https://attack.mitre.org/software/S0276">
      Keydnap
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0276">
       Keydnap
      </a>
      puts a space after a false .jpg extension so that execution actually goes through the Terminal.app program.
      <span class="scite-citeref-number" data-reference="synack 2016 review" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.synack.com/2017/01/01/mac-malware-2016/" target="_blank">
         [2]
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
  Prevent files from having a trailing space after the extension.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  It's not common for spaces to be at the end of filenames, so this is something that can easily be checked with file monitoring. From the user's perspective though, this is very hard to notice from within the Finder.app or on the command-line in Terminal.app. Processes executed from binaries containing non-standard extensions in the filename are suspicious.
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
       <a class="external text" href="https://arstechnica.com/security/2016/07/after-hiatus-in-the-wild-mac-backdoors-are-suddenly-back/" name="scite-1" rel="nofollow" target="_blank">
        Dan Goodin. (2016, July 6). After hiatus, in-the-wild Mac backdoors are suddenly back. Retrieved July 8, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="2.0">
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.synack.com/2017/01/01/mac-malware-2016/" name="scite-2" rel="nofollow" target="_blank">
        Patrick Wardle. (2017, January 1). Mac Malware of 2016. Retrieved September 21, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
