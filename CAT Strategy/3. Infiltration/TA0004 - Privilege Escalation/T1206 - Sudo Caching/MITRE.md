<div class="container-fluid">
 <h1>
  Sudo Caching
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    The
    <code>
     sudo
    </code>
    command "allows a system administrator to delegate authority to give certain users (or groups of users) the ability to run some (or all) commands as root or another user while providing an audit trail of the commands and their arguments."
    <span class="scite-citeref-number" data-reference="sudo man page 2018" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.sudo.ws/" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    Since sudo was made for the system administrator, it has some useful configuration features such as a
    <code>
     timestamp_timeout
    </code>
    that is the amount of time in minutes between instances of
    <code>
     sudo
    </code>
    before it will re-prompt for a password. This is because
    <code>
     sudo
    </code>
    has the ability to cache credentials for a period of time. Sudo creates (or touches) a file at
    <code>
     /var/db/sudo
    </code>
    with a timestamp of when sudo was last run to determine this timeout. Additionally, there is a
    <code>
     tty_tickets
    </code>
    variable that treats each new tty (terminal session) in isolation. This means that, for example, the sudo timeout of one tty will not affect another tty (you will have to type the password again).
   </p>
   <p>
    Adversaries can abuse poor configurations of this to escalate privileges without needing the user's password.
    <code>
     /var/db/sudo
    </code>
    's timestamp can be monitored to see if it falls within the
    <code>
     timestamp_timeout
    </code>
    range. If it does, then malware can execute sudo commands without needing to supply the user's password. When
    <code>
     tty_tickets
    </code>
    is disabled, adversaries can do this from any tty for that user.
   </p>
   <p>
    The OSX Proton Malware has disabled
    <code>
     tty_tickets
    </code>
    to potentially make scripting easier by issuing
    <code>
     echo \'Defaults !tty_tickets\' &gt;&gt; /etc/sudoers
    </code>
    <span class="scite-citeref-number" data-reference="cybereason osx proton" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.cybereason.com/blog/labs-proton-b-what-this-mac-malware-actually-does" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    . In order for this change to be reflected, the Proton malware also must issue
    <code>
     killall Terminal
    </code>
    . As of macOS Sierra, the sudoers file has
    <code>
     tty_tickets
    </code>
    enabled by default.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1206
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
      : Privilege Escalation
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
       Effective Permissions:
      </span>
      root
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Data Sources:
      </span>
      File monitoring, Process command-line parameters
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
     <a href="https://attack.mitre.org/software/S0279">
      Proton
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0279">
       Proton
      </a>
      modifies the tty_tickets line in the sudoers file.
      <span class="scite-citeref-number" data-reference="objsee mac malware 2017" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://objective-see.com/blog/blog_0x25.html" target="_blank">
         [3]
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
  Setting the
  <code>
   timestamp_timeout
  </code>
  to 0 will require the user to input their password every time
  <code>
   sudo
  </code>
  is executed. Similarly, ensuring that the
  <code>
   tty_tickets
  </code>
  setting is enabled will prevent this leakage across tty sessions.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  This technique is abusing normal functionality in macOS and Linux systems, but sudo has the ability to log all input and output based on the
  <code>
   LOG_INPUT
  </code>
  and
  <code>
   LOG_OUTPUT
  </code>
  directives in the
  <code>
   /etc/sudoers
  </code>
  file.
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
       <a class="external text" href="https://www.sudo.ws/" name="scite-1" rel="nofollow" target="_blank">
        Todd C. Miller. (2018). Sudo Man Page. Retrieved March 19, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.cybereason.com/blog/labs-proton-b-what-this-mac-malware-actually-does" name="scite-2" rel="nofollow" target="_blank">
        Amit Serper. (2018, May 10). ProtonB What this Mac Malware Actually Does. Retrieved March 19, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="3.5">
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://objective-see.com/blog/blog_0x25.html" name="scite-3" rel="nofollow" target="_blank">
        Patrick Wardle. (n.d.). Mac Malware of 2017. Retrieved September 21, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
