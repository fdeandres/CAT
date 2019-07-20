<div class="container-fluid">
 <h1>
  Bash History
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Bash keeps track of the commands users type on the command-line with the "history" utility. Once a user logs out, the history is flushed to the user’s
    <code>
     .bash_history
    </code>
    file. For each user, this file resides at the same location:
    <code>
     ~/.bash_history
    </code>
    . Typically, this file keeps track of the user’s last 500 commands. Users often type usernames and passwords on the command-line as parameters to programs, which then get saved to this file when they log out. Attackers can abuse this by looking through the file for potential credentials.
    <span class="scite-citeref-number" data-reference="External to DA, the OS X Way" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="http://www.slideshare.net/StephanBorosh/external-to-da-the-os-x-way" target="_blank">
       [1]
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
      : T1139
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
      : Credential Access
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
 <h2 class="pt-3" id="mitigation">
  Mitigation
 </h2>
 <p>
  There are multiple methods of preventing a user's command history from being flushed to their .bash_history file, including use of the following commands:
  <code>
   set +o history
  </code>
  and
  <code>
   set -o history
  </code>
  to start logging again;
  <code>
   unset HISTFILE
  </code>
  being added to a user's .bash_rc file; and
  <code>
   ln -s /dev/null ~/.bash_history
  </code>
  to write commands to
  <code>
   /dev/null
  </code>
  instead.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitoring when the user's
  <code>
   .bash_history
  </code>
  is read can help alert to suspicious activity. While users do typically rely on their history of commands, they often access this history through other utilities like "history" instead of commands like
  <code>
   cat ~/.bash_history
  </code>
  .
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
       <a class="external text" href="http://www.slideshare.net/StephanBorosh/external-to-da-the-os-x-way" name="scite-1" rel="nofollow" target="_blank">
        Alex Rymdeko-Harvey, Steve Borosh. (2016, May 14). External to DA, the OS X Way. Retrieved July 3, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
  </div>
 </div>
</div>
