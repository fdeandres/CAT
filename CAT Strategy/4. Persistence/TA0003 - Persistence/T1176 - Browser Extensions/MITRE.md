<div class="container-fluid">
 <h1>
  Browser Extensions
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Browser extensions or plugins are small programs that can add functionality and customize aspects of internet browsers. They can be installed directly or through a browser's app store. Extensions generally have access and permissions to everything that the browser can access.
    <span class="scite-citeref-number" data-reference="Wikipedia Browser Extension" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://en.wikipedia.org/wiki/Browser_extension" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Chrome Extensions Definition" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://developer.chrome.com/extensions" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <p>
    Malicious extensions can be installed into a browser through malicious app store downloads masquerading as legitimate extensions, through social engineering, or by an adversary that has already compromised a system. Security can be limited on browser app stores so may not be difficult for malicious extensions to defeat automated scanners and be uploaded.
    <span class="scite-citeref-number" data-reference="Malicious Chrome Extension Numbers" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/43824.pdf" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    Once the extension is installed, it can browse to websites in the background,
    <span class="scite-citeref-number" data-reference="Chrome Extension Crypto Miner" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.ghacks.net/2017/09/19/first-chrome-extension-with-javascript-crypto-miner-detected/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="ICEBRG Chrome Extensions" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.icebrg.io/blog/malicious-chrome-extensions-enable-criminals-to-impact-over-half-a-million-users-and-global-businesses" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    steal all information that a user enters into a browser, to include credentials,
    <span class="scite-citeref-number" data-reference="Banker Google Chrome Extension Steals Creds" id="scite-ref-6-a">
     <sup>
      <a aria-describedby="qtip-5" data-hasqtip="5" href="https://isc.sans.edu/forums/diary/BankerGoogleChromeExtensiontargetingBrazil/22722/" target="_blank">
       [6]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Catch All Chrome Extension" id="scite-ref-7-a">
     <sup>
      <a aria-describedby="qtip-6" data-hasqtip="6" href="https://isc.sans.edu/forums/diary/CatchAll+Google+Chrome+Malicious+Extension+Steals+All+Posted+Data/22976/https:/threatpost.com/malicious-chrome-extension-steals-data-posted-to-any-website/128680/)" target="_blank">
       [7]
      </a>
     </sup>
    </span>
    and be used as an installer for a RAT for persistence. There have been instances of botnets using a persistent backdoor through malicious Chrome extensions.
    <span class="scite-citeref-number" data-reference="Stantinko Botnet" id="scite-ref-8-a">
     <sup>
      <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.welivesecurity.com/2017/07/20/stantinko-massive-adware-campaign-operating-covertly-since-2012/" target="_blank">
       [8]
      </a>
     </sup>
    </span>
    There have also been similar examples of extensions being used for command &amp; control
    <span class="scite-citeref-number" data-reference="Chrome Extension C2 Malware" id="scite-ref-9-a">
     <sup>
      <a aria-describedby="qtip-8" data-hasqtip="8" href="https://kjaer.io/extension-malware/" target="_blank">
       [9]
      </a>
     </sup>
    </span>
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
      : T1176
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
      : Persistence
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
      </span>
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
      Network protocol analysis, Packet capture, System calls, Process use of network, Process monitoring, Browser extensions
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
      Justin Warner, ICEBRG
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
     <a href="https://attack.mitre.org/groups/G0086">
      Stolen Pencil
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0086">
       Stolen Pencil
      </a>
      victims are prompted to install malicious Google Chrome extensions which gave the threat actor the ability to read data from any website accessed.
      <span class="scite-citeref-number" data-reference="Netscout Stolen Pencil Dec 2018" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
       <sup>
        <a aria-describedby="qtip-9" data-hasqtip="9" href="https://asert.arbornetworks.com/stolen-pencil-campaign-targets-academia/" target="_blank">
         [10]
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
  Only install browser extensions from trusted sources that can be verified. Ensure extensions that are installed are the intended ones as many malicious extensions will masquerade as legitimate ones.
 </p>
 <p>
  Browser extensions for some browsers can be controlled through Group Policy. Set a browser extension white or black list as appropriate for your security policy.
  <span class="scite-citeref-number" data-reference="Technospot Chrome Extensions GP" id="scite-ref-11-a">
   <sup>
    <a aria-describedby="qtip-10" data-hasqtip="10" href="http://www.technospot.net/blogs/block-chrome-extensions-using-google-chrome-group-policy-settings/" target="_blank">
     [11]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Change settings to prevent the browser from installing extensions without sufficient permissions.
 </p>
 <p>
  Close out all browser sessions when finished using them.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Inventory and monitor browser extension installations that deviate from normal, expected, and benign extensions. Process and network monitoring can be used to detect browsers communicating with a C2 server. However, this may prove to be a difficult way of initially detecting a malicious extension depending on the nature and volume of the traffic it generates.
 </p>
 <p>
  Monitor for any new items written to the Registry or PE files written to disk. That may correlate with browser extension installation.
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
       <a class="external text" href="https://en.wikipedia.org/wiki/Browser_extension" name="scite-1" rel="nofollow" target="_blank">
        Wikipedia. (2017, October 8). Browser Extension. Retrieved January 11, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://developer.chrome.com/extensions" name="scite-2" rel="nofollow" target="_blank">
        Chrome. (n.d.). What are Extensions?. Retrieved November 16, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/43824.pdf" name="scite-3" rel="nofollow" target="_blank">
        Jagpal, N., et al. (2015, August). Trends and Lessons from Three Years Fighting Malicious Extensions. Retrieved November 17, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.ghacks.net/2017/09/19/first-chrome-extension-with-javascript-crypto-miner-detected/" name="scite-4" rel="nofollow" target="_blank">
        Brinkmann, M. (2017, September 19). First Chrome extension with JavaScript Crypto Miner detected. Retrieved November 16, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.icebrg.io/blog/malicious-chrome-extensions-enable-criminals-to-impact-over-half-a-million-users-and-global-businesses" name="scite-5" rel="nofollow" target="_blank">
        De Tore, M., Warner, J. (2018, January 15). MALICIOUS CHROME EXTENSIONS ENABLE CRIMINALS TO IMPACT OVER HALF A MILLION USERS AND GLOBAL BUSINESSES. Retrieved January 17, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://isc.sans.edu/forums/diary/BankerGoogleChromeExtensiontargetingBrazil/22722/" name="scite-6" rel="nofollow" target="_blank">
        Marinho, R. (n.d.). (Banker(GoogleChromeExtension)).targeting. Retrieved November 18, 2017.
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
       <a class="external text" href="https://isc.sans.edu/forums/diary/CatchAll+Google+Chrome+Malicious+Extension+Steals+All+Posted+Data/22976/https:/threatpost.com/malicious-chrome-extension-steals-data-posted-to-any-website/128680/)" name="scite-7" rel="nofollow" target="_blank">
        Marinho, R. (n.d.). "Catch-All" Google Chrome Malicious Extension Steals All Posted Data. Retrieved November 16, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.welivesecurity.com/2017/07/20/stantinko-massive-adware-campaign-operating-covertly-since-2012/" name="scite-8" rel="nofollow" target="_blank">
        Vachon, F., Faou, M. (2017, July 20). Stantinko: A massive adware campaign operating covertly since 2012. Retrieved November 16, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://kjaer.io/extension-malware/" name="scite-9" rel="nofollow" target="_blank">
        Kjaer, M. (2016, July 18). Malware in the browser: how you might get hacked by a Chrome extension. Retrieved November 22, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://asert.arbornetworks.com/stolen-pencil-campaign-targets-academia/" name="scite-10" rel="nofollow" target="_blank">
        ASERT team. (2018, December 5). STOLEN PENCIL Campaign Targets Academia. Retrieved February 5, 2019.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.technospot.net/blogs/block-chrome-extensions-using-google-chrome-group-policy-settings/" name="scite-11" rel="nofollow" target="_blank">
        Mohta, A. (n.d.). Block Chrome Extensions using Google Chrome Group Policy Settings. Retrieved January 10, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
