<div class="container-fluid">
 <h1>
  SSH Hijacking
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Secure Shell (SSH) is a standard means of remote access on Linux and macOS systems. It allows a user to connect to another system via an encrypted tunnel, commonly authenticating through a password, certificate or the use of an asymmetric encryption key pair.
   </p>
   <p>
    In order to move laterally from a compromised host, adversaries may take advantage of trust relationships established with other systems via public key authentication in active SSH sessions by hijacking an existing connection to another system. This may occur through compromising the SSH agent itself or by having access to the agent's socket. If an adversary is able to obtain root access, then hijacking SSH sessions is likely trivial.
    <span class="scite-citeref-number" data-reference="Slideshare Abusing SSH" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://www.slideshare.net/morisson/mistrusting-and-abusing-ssh-13526219" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="SSHjack Blackhat" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.blackhat.com/presentations/bh-usa-05/bh-us-05-boileau.pdf" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Clockwork SSH Agent Hijacking" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.clockwork.com/news/2012/09/28/602/ssh_agent_hijacking" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    Compromising the SSH agent also provides access to intercept SSH credentials.
    <span class="scite-citeref-number" data-reference="Welivesecurity Ebury SSH" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.welivesecurity.com/2014/02/21/an-in-depth-analysis-of-linuxebury/" target="_blank">
       [4]
      </a>
     </sup>
    </span>
   </p>
   <p>
    <a href="https://attack.mitre.org/techniques/T1184">
     SSH Hijacking
    </a>
    differs from use of
    <a href="https://attack.mitre.org/techniques/T1021">
     Remote Services
    </a>
    because it injects into an existing SSH session rather than creating a new session using
    <a href="https://attack.mitre.org/techniques/T1078">
     Valid Accounts
    </a>
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
      : T1184
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
      : Lateral Movement
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
      User, root
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
      Authentication logs
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
      Anastasios Pingios
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
 <h2 class="pt-3" id="mitigation">
  Mitigation
 </h2>
 <p>
  Ensure SSH key pairs have strong passwords and refrain from using key-store technologies such as ssh-agent unless they are properly protected. Ensure that all private keys are stored securely in locations where only the legitimate owner has access to with strong passwords and are rotated frequently. Ensure proper file permissions are set and harden system to prevent root privilege escalation opportunities. Do not allow remote access via SSH as root or other privileged accounts. Ensure that agent forwarding is disabled on systems that do not explicitly require this feature to prevent misuse.
  <span class="scite-citeref-number" data-reference="Symantec SSH and ssh-agent" id="scite-ref-5-a">
   <sup>
    <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.symantec.com/connect/articles/ssh-and-ssh-agent" target="_blank">
     [5]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Use of SSH may be legitimate, depending upon the network environment and how it is used. Other factors, such as access patterns and activity that occurs after a remote login, may indicate suspicious or malicious behavior with SSH. Monitor for user accounts logged into systems they would not normally access or access patterns to multiple systems over a relatively short period of time. Also monitor user SSH-agent socket files being used by different users.
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
       <a class="external text" href="https://www.slideshare.net/morisson/mistrusting-and-abusing-ssh-13526219" name="scite-1" rel="nofollow" target="_blank">
        Duarte, H., Morrison, B. (2012). (Mis)trusting and (ab)using ssh. Retrieved January 8, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.blackhat.com/presentations/bh-usa-05/bh-us-05-boileau.pdf" name="scite-2" rel="nofollow" target="_blank">
        Adam Boileau. (2005, August 5). Trust Transience:  Post Intrusion SSH Hijacking. Retrieved December 19, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.clockwork.com/news/2012/09/28/602/ssh_agent_hijacking" name="scite-3" rel="nofollow" target="_blank">
        Beuchler, B. (2012, September 28). SSH Agent Hijacking. Retrieved December 20, 2017.
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
       <a class="external text" href="https://www.welivesecurity.com/2014/02/21/an-in-depth-analysis-of-linuxebury/" name="scite-4" rel="nofollow" target="_blank">
        M.Léveillé, M. (2014, February 21). An In-depth Analysis of Linux/Ebury. Retrieved January 8, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/connect/articles/ssh-and-ssh-agent" name="scite-5" rel="nofollow" target="_blank">
        Hatch, B. (2004, November 22). SSH and ssh-agent. Retrieved January 8, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
