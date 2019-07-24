<div class="container-fluid">
 <h1>
  Device Type Discovery
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    On Android, device type information is accessible to apps through the android.os.Build class
    <span class="scite-citeref-number" data-reference="Android-Build" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://zeltser.com/third-party-keyboards-security/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    . Device information could be used to target privilege escalation exploits.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1419
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Tactic Type:
      </span>
      Post-Adversary Device Access
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Tactic
      </span>
      : Discovery
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Platform:
      </span>
      Android
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
 <h2 class="pt-3" id="mitigations">
  Mitigations
 </h2>
 <table class="table table-bordered table-light mt-2">
  <thead>
   <tr>
    <th scope="col">
     Mitigation
    </th>
    <th scope="col">
     Description
    </th>
   </tr>
  </thead>
  <tbody class="bg-white">
   <tr>
    <td>
     <a href="https://attack.mitre.org/mitigations/M1005">
      Application Vetting
     </a>
    </td>
    <td>
     App vetting procedures can search for apps that use the android.os.Build class, but these procedures could potentially be evaded and are likely not practical in this case, as many apps are likely to use this functionality as part of their legitimate behavior.
    </td>
   </tr>
  </tbody>
 </table>
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
     <a href="https://attack.mitre.org/software/S0304">
      Android/Chuli.A
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0304">
       Android/Chuli.A
      </a>
      gathered device data including phone number, OS version, phone model, and SDK version.
      <span class="scite-citeref-number" data-reference="Kaspersky-WUC" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://securelist.com/android-trojan-found-in-targeted-attack-58/35552/" target="_blank">
         [2]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0310">
      ANDROIDOS_ANSERVER.A
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0310">
       ANDROIDOS_ANSERVER.A
      </a>
      gathers the device build version, manufacturer, and model.
      <span class="scite-citeref-number" data-reference="TrendMicro-Anserver2" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.trendmicro.com/vinfo/us/threat-encyclopedia/malware/ANDROIDOS_ANSERVER.A" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0326">
      RedDrop
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0326">
       RedDrop
      </a>
      exfiltrates details of the victim device operating system and manufacturer.
      <span class="scite-citeref-number" data-reference="Wandera-RedDrop" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.wandera.com/reddrop-malware/" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
  </tbody>
 </table>
 <h2 class="pt-3" id="references">
  References
 </h2>
 <div class="row">
  <div class="col">
   <ol>
    <li>
     <span class="scite-citation" id="scite-1">
      <span class="scite-citation-text">
       <a class="external text" href="https://zeltser.com/third-party-keyboards-security/" name="scite-1" rel="nofollow" target="_blank">
        Android. (n.d.). Build. Retrieved December 21, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://securelist.com/android-trojan-found-in-targeted-attack-58/35552/" name="scite-2" rel="nofollow" target="_blank">
        Costin Raiu, Denis Maslennikov, Kurt Baumgartner. (2013, March 26). Android Trojan Found in Targeted Attack. Retrieved December 23, 2016.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="3.0">
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.trendmicro.com/vinfo/us/threat-encyclopedia/malware/ANDROIDOS_ANSERVER.A" name="scite-3" rel="nofollow" target="_blank">
        Karl Dominguez. (2011, September 27). ANDROIDOS_ANSERVER.A. Retrieved November 30, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.wandera.com/reddrop-malware/" name="scite-4" rel="nofollow" target="_blank">
        Nell Campbell. (2018, February 27). RedDrop: the blackmailing mobile malware family lurking in app stores. Retrieved September 18, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
