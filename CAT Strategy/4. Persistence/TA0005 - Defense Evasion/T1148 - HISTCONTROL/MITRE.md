<div class="container-fluid">
 <h1>
  HISTCONTROL
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    The
    <code>
     HISTCONTROL
    </code>
    environment variable keeps track of what should be saved by the
    <code>
     history
    </code>
    command and eventually into the
    <code>
     ~/.bash_history
    </code>
    file when a user logs out. This setting can be configured to ignore commands that start with a space by simply setting it to "ignorespace".
    <code>
     HISTCONTROL
    </code>
    can also be set to ignore duplicate commands by setting it to "ignoredups". In some Linux systems, this is set by default to "ignoreboth" which covers both of the previous examples. This means that " ls" will not be saved, but "ls" would be saved by history.
    <code>
     HISTCONTROL
    </code>
    does not exist by default on macOS, but can be set by the user and will be respected. Adversaries can use this to operate without leaving traces by simply prepending a space to all of their terminal commands.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1148
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
      Process monitoring, Authentication logs, File monitoring, Environment variable
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
      Log analysis, Host forensic analysis
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
 <h2 class="pt-3" id="mitigation">
  Mitigation
 </h2>
 <p>
  Prevent users from changing the
  <code>
   HISTCONTROL
  </code>
  environment variable
  <span class="scite-citeref-number" data-reference="Securing bash history" id="scite-ref-1-a">
   <sup>
    <a aria-describedby="qtip-0" data-hasqtip="0" href="http://www.akyl.net/securing-bashhistory-file-make-sure-your-linux-system-users-won%E2%80%99t-hide-or-delete-their-bashhistory" target="_blank">
     [1]
    </a>
   </sup>
  </span>
  . Also, make sure that the
  <code>
   HISTCONTROL
  </code>
  environment variable is set to "ignoredup" instead of "ignoreboth" or "ignorespace".
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Correlating a user session with a distinct lack of new commands in their
  <code>
   .bash_history
  </code>
  can be a clue to suspicious behavior. Additionally, users checking or changing their
  <code>
   HISTCONTROL
  </code>
  environment variable is also suspicious.
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
       <a class="external text" href="http://www.akyl.net/securing-bashhistory-file-make-sure-your-linux-system-users-won%E2%80%99t-hide-or-delete-their-bashhistory" name="scite-1" rel="nofollow" target="_blank">
        Mathew Branwell. (2012, March 21). Securing .bash_history file. Retrieved July 8, 2017.
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
