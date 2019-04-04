<div class="container-fluid">
 <h1>
  Login Item
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    MacOS provides the option to list specific applications to run when a user logs in. These applications run under the logged in user's context, and will be started every time the user logs in. Login items installed using the Service Management Framework are not visible in the System Preferences and can only be removed by the application that created them
    <span class="scite-citeref-number" data-reference="Adding Login Items" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/CreatingLoginItems.html" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    . Users have direct control over login items installed using a shared file list which are also visible in System Preferences
    <span class="scite-citeref-number" data-reference="Adding Login Items" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/CreatingLoginItems.html" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    . These login items are stored in the user's
    <code>
     ~/Library/Preferences/
    </code>
    directory in a plist file called
    <code>
     com.apple.loginitems.plist
    </code>
    <span class="scite-citeref-number" data-reference="Methods of Mac Malware Persistence" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.virusbulletin.com/uploads/pdf/conference/vb2014/VB2014-Wardle.pdf" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    . Some of these applications can open visible dialogs to the user, but they don’t all have to since there is an option to ‘Hide’ the window. If an adversary can register their own login item or modified an existing one, then they can use it to execute their code for a persistence mechanism each time the user logs in
    <span class="scite-citeref-number" data-reference="Malware Persistence on OS X" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.rsaconference.com/writable/presentations/file_upload/ht-r03-malware-persistence-on-os-x-yosemite_final.pdf" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="OSX.Dok Malware" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://blog.malwarebytes.com/threat-analysis/2017/04/new-osx-dok-malware-intercepts-web-traffic/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    . The API method
    <code>
     SMLoginItemSetEnabled
    </code>
    can be used to set Login Items, but scripting languages like
    <a href="https://attack.mitre.org/techniques/T1155">
     AppleScript
    </a>
    can do this as well
    <span class="scite-citeref-number" data-reference="Adding Login Items" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/CreatingLoginItems.html" target="_blank">
       [1]
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
      : T1162
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
      macOS
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
      File monitoring, API monitoring
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
     <a href="https://attack.mitre.org/software/S0281">
      Dok
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0281">
       Dok
      </a>
      persists via a login item.
      <span class="scite-citeref-number" data-reference="objsee mac malware 2017" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://objective-see.com/blog/blog_0x25.html" target="_blank">
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
  Restrict users from being able to create their own login items. Additionally, holding the shift key during login prevents apps from opening automatically
  <span class="scite-citeref-number" data-reference="Re-Open windows on Mac" id="scite-ref-6-a">
   <sup>
    <a aria-describedby="qtip-5" data-hasqtip="5" href="https://support.apple.com/en-us/HT204005" target="_blank">
     [6]
    </a>
   </sup>
  </span>
  .
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  All the login items created via shared file lists are viewable by going to the Apple menu -&gt; System Preferences -&gt; Users &amp; Groups -&gt; Login items. This area (and the corresponding file locations) should be monitored and whitelisted for known good applications. Otherwise, Login Items are located in
  <code>
   Contents/Library/LoginItems
  </code>
  within an application bundle, so these paths should be monitored as well
  <span class="scite-citeref-number" data-reference="Adding Login Items" id="scite-ref-1-a">
   <sup>
    <a aria-describedby="qtip-0" data-hasqtip="0" href="https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/CreatingLoginItems.html" target="_blank">
     [1]
    </a>
   </sup>
  </span>
  . Monitor process execution resulting from login actions for unusual or unknown applications.
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
       <a class="external text" href="https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/CreatingLoginItems.html" name="scite-1" rel="nofollow" target="_blank">
        Apple. (2016, September 13). Adding Login Items. Retrieved July 11, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.virusbulletin.com/uploads/pdf/conference/vb2014/VB2014-Wardle.pdf" name="scite-2" rel="nofollow" target="_blank">
        Patrick Wardle. (2014, September). Methods of Malware Persistence on Mac OS X. Retrieved July 5, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.rsaconference.com/writable/presentations/file_upload/ht-r03-malware-persistence-on-os-x-yosemite_final.pdf" name="scite-3" rel="nofollow" target="_blank">
        Patrick Wardle. (2015). Malware Persistence on OS X Yosemite. Retrieved July 10, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="4.0">
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://blog.malwarebytes.com/threat-analysis/2017/04/new-osx-dok-malware-intercepts-web-traffic/" name="scite-4" rel="nofollow" target="_blank">
        Thomas Reed. (2017, July 7). New OSX.Dok malware intercepts web traffic. Retrieved July 10, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://objective-see.com/blog/blog_0x25.html" name="scite-5" rel="nofollow" target="_blank">
        Patrick Wardle. (n.d.). Mac Malware of 2017. Retrieved September 21, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://support.apple.com/en-us/HT204005" name="scite-6" rel="nofollow" target="_blank">
        Apple. (2016, December 6). Automatically re-open windows, apps, and documents on your Mac. Retrieved July 11, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
