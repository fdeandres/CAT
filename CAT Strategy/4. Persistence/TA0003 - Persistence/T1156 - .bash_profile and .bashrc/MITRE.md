<div class="container-fluid">
 <h1>
  .bash_profile and .bashrc
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    <code>
     ~/.bash_profile
    </code>
    and
    <code>
     ~/.bashrc
    </code>
    are executed in a user's context when a new shell opens or when a user logs in so that their environment is set correctly.
    <code>
     ~/.bash_profile
    </code>
    is executed for login shells and
    <code>
     ~/.bashrc
    </code>
    is executed for interactive non-login shells. This means that when a user logs in (via username and password) to the console (either locally or remotely via something like SSH),
    <code>
     ~/.bash_profile
    </code>
    is executed before the initial command prompt is returned to the user. After that, every time a new shell is opened,
    <code>
     ~/.bashrc
    </code>
    is executed. This allows users more fine grained control over when they want certain commands executed.
   </p>
   <p>
    Mac's Terminal.app is a little different in that it runs a login shell by default each time a new terminal window is opened, thus calling
    <code>
     ~/.bash_profile
    </code>
    each time instead of
    <code>
     ~/.bashrc
    </code>
    .
   </p>
   <p>
    These files are meant to be written to by the local user to configure their own environment; however, adversaries can also insert code into these files to gain persistence each time a user logs in or opens a new shell
    <span class="scite-citeref-number" data-reference="amnesia malware" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://researchcenter.paloaltonetworks.com/2017/04/unit42-new-iotlinux-malware-targets-dvrs-forms-botnet/" target="_blank">
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
      : T1156
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
      Linux, macOS
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
       Data Sources:
      </span>
      File monitoring, Process monitoring, Process command-line parameters, Process use of network
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
     <a href="https://attack.mitre.org/software/S0362">
      Linux Rabbit
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0362">
       Linux Rabbit
      </a>
      maintains persistence on an infected machine through rc.local and .bashrc files.
      <span class="scite-citeref-number" data-reference="Anomali Linux Rabbit 2018" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
       <sup>
        <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.anomali.com/blog/pulling-linux-rabbit-rabbot-malware-out-of-a-hat" target="_blank">
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
  Making these files immutable and only changeable by certain administrators will limit the ability for adversaries to easily create user level persistence.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  While users may customize their
  <code>
   ~/.bashrc
  </code>
  and
  <code>
   ~/.bash_profile
  </code>
  files , there are only certain types of commands that typically appear in these files. Monitor for abnormal commands such as execution of unknown programs, opening network sockets, or reaching out across the network when user profiles are loaded during the login process.
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
       <a class="external text" href="https://researchcenter.paloaltonetworks.com/2017/04/unit42-new-iotlinux-malware-targets-dvrs-forms-botnet/" name="scite-1" rel="nofollow" target="_blank">
        Claud Xiao, Cong Zheng, Yanhui Jia. (2017, April 6). New IoT/Linux Malware Targets DVRs, Forms Botnet. Retrieved February 19, 2018.
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
       <a class="external text" href="https://www.anomali.com/blog/pulling-linux-rabbit-rabbot-malware-out-of-a-hat" name="scite-2" rel="nofollow" target="_blank">
        Anomali Labs. (2018, December 6). Pulling Linux Rabbit/Rabbot Malware Out of a Hat. Retrieved March 4, 2019.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
