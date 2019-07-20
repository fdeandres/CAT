<div class="container-fluid">
 <h1>
  Gatekeeper Bypass
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    In macOS and OS X, when applications or programs are downloaded from the internet, there is a special attribute set on the file called
    <code>
     com.apple.quarantine
    </code>
    . This attribute is read by Apple's Gatekeeper defense program at execution time and provides a prompt to the user to allow or deny execution.
   </p>
   <p>
    Apps loaded onto the system from USB flash drive, optical disk, external hard drive, or even from a drive shared over the local network won’t set this flag. Additionally, other utilities or events like drive-by downloads don’t necessarily set it either. This completely bypasses the built-in Gatekeeper check.
    <span class="scite-citeref-number" data-reference="Methods of Mac Malware Persistence" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.virusbulletin.com/uploads/pdf/conference/vb2014/VB2014-Wardle.pdf" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    The presence of the quarantine flag can be checked by the xattr command
    <code>
     xattr /path/to/MyApp.app
    </code>
    for
    <code>
     com.apple.quarantine
    </code>
    . Similarly, given sudo access or elevated permission, this attribute can be removed with xattr as well,
    <code>
     sudo xattr -r -d com.apple.quarantine /path/to/MyApp.app
    </code>
    .
    <span class="scite-citeref-number" data-reference="Clearing quarantine attribute" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://derflounder.wordpress.com/2012/11/20/clearing-the-quarantine-extended-attribute-from-downloaded-applications/" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="OceanLotus for OS X" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.alienvault.com/blogs/labs-research/oceanlotus-for-os-x-an-application-bundle-pretending-to-be-an-adobe-flash-update" target="_blank">
       [3]
      </a>
     </sup>
    </span>
   </p>
   <p>
    In typical operation, a file will be downloaded from the internet and given a quarantine flag before being saved to disk. When the user tries to open the file or application, macOS’s gatekeeper will step in and check for the presence of this flag. If it exists, then macOS will then prompt the user to confirmation that they want to run the program and will even provide the URL where the application came from. However, this is all based on the file being downloaded from a quarantine-savvy application.
    <span class="scite-citeref-number" data-reference="Bypassing Gatekeeper" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://blog.malwarebytes.com/cybercrime/2015/10/bypassing-apples-gatekeeper/" target="_blank">
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
      : T1144
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
      macOS
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
       Defense Bypassed:
      </span>
      Application whitelisting, Anti-virus
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
     <a href="https://attack.mitre.org/software/S0369">
      CoinTicker
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0369">
       CoinTicker
      </a>
      downloads the EggShell mach-o binary using curl, which does not set the quarantine flag.
      <span class="scite-citeref-number" data-reference="CoinTicker 2019" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://blog.malwarebytes.com/threat-analysis/2018/10/mac-cryptocurrency-ticker-app-installs-backdoors/" target="_blank">
         [5]
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
  Other tools should be used to supplement Gatekeeper's functionality. Additionally, system settings can prevent applications from running that haven't been downloaded through the Apple Store which can help mitigate some of these issues.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitoring for the removal of the
  <code>
   com.apple.quarantine
  </code>
  flag by a user instead of the operating system is a suspicious action and should be examined further.
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
       <a class="external text" href="https://www.virusbulletin.com/uploads/pdf/conference/vb2014/VB2014-Wardle.pdf" name="scite-1" rel="nofollow" target="_blank">
        Patrick Wardle. (2014, September). Methods of Malware Persistence on Mac OS X. Retrieved July 5, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://derflounder.wordpress.com/2012/11/20/clearing-the-quarantine-extended-attribute-from-downloaded-applications/" name="scite-2" rel="nofollow" target="_blank">
        Rich Trouton. (2012, November 20). Clearing the quarantine extended attribute from downloaded applications. Retrieved July 5, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.alienvault.com/blogs/labs-research/oceanlotus-for-os-x-an-application-bundle-pretending-to-be-an-adobe-flash-update" name="scite-3" rel="nofollow" target="_blank">
        Eddie Lee. (2016, February 17). OceanLotus for OS X - an Application Bundle Pretending to be an Adobe Flash Update. Retrieved July 5, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="4.5">
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.malwarebytes.com/cybercrime/2015/10/bypassing-apples-gatekeeper/" name="scite-4" rel="nofollow" target="_blank">
        Thomas Reed. (2016, March 31). Bypassing Apple's Gatekeeper. Retrieved July 5, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.malwarebytes.com/threat-analysis/2018/10/mac-cryptocurrency-ticker-app-installs-backdoors/" name="scite-5" rel="nofollow" target="_blank">
        Thomas Reed. (2018, October 29). Mac cryptocurrency ticker app installs backdoors. Retrieved April 23, 2019.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
