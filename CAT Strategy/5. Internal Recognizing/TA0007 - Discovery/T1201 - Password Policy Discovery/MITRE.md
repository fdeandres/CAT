<div class="container-fluid">
 <h1>
  Password Policy Discovery
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Password policies for networks are a way to enforce complex passwords that are difficult to guess or crack through
    <a href="https://attack.mitre.org/techniques/T1110">
     Brute Force
    </a>
    . An adversary may attempt to access detailed information about the password policy used within an enterprise network. This would help the adversary to create a list of common passwords and launch dictionary and/or brute force attacks which adheres to the policy (e.g. if the minimum password length should be 8, then not trying passwords such as 'pass123'; not checking for more than 3-4 passwords per account if the lockout is set to 6 as to not lock out accounts).
   </p>
   <p>
    Password policies can be set and discovered on Windows, Linux, and macOS systems.
    <span class="scite-citeref-number" data-reference="Superuser Linux Password Policies" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://superuser.com/questions/150675/how-to-display-password-policy-information-for-a-user-ubuntu" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    <span class="scite-citeref-number" data-reference="Jamf User Password Policies" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://www.jamf.com/jamf-nation/discussions/18574/user-password-policies-on-non-ad-machines" target="_blank">
       [2]
      </a>
     </sup>
    </span>
   </p>
   <h3>
    Windows
   </h3>
   <ul>
    <li>
     <code>
      net accounts
     </code>
    </li>
    <li>
     <code>
      net accounts /domain
     </code>
    </li>
   </ul>
   <h3>
    Linux
   </h3>
   <ul>
    <li>
     <code>
      chage -l
      <username>
      </username>
     </code>
    </li>
    <li>
     <code>
      cat /etc/pam.d/common-password
     </code>
    </li>
   </ul>
   <h3>
    macOS
   </h3>
   <ul>
    <li>
     <code>
      pwpolicy getaccountpolicies
     </code>
    </li>
   </ul>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1201
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
      : Discovery
      <br/>
      <br/>
     </div>
     <div class="card-data">
      <span class="h5 card-title">
       Platform:
      </span>
      Windows, Linux, macOS
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
      Process command-line parameters, Process monitoring
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
      Sudhanshu Chauhan, @Sudhanshu_C
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
     <a href="https://attack.mitre.org/software/S0236">
      Kwampirs
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0236">
       Kwampirs
      </a>
      collects password policy information with the command
      <code>
       net accounts
      </code>
      .
      <span class="scite-citeref-number" data-reference="Symantec Orangeworm April 2018" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
       <sup>
        <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.symantec.com/blogs/threat-intelligence/orangeworm-targets-healthcare-us-europe-asia" target="_blank">
         [3]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0039">
      Net
     </a>
    </td>
    <td>
     <p>
      The
      <code>
       net accounts
      </code>
      and
      <code>
       net accounts /domain
      </code>
      commands with
      <a href="https://attack.mitre.org/software/S0039">
       Net
      </a>
      can be used to obtain password policy information.
      <span class="scite-citeref-number" data-reference="Savill 1999" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="http://windowsitpro.com/windows/netexe-reference" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/groups/G0049">
      OilRig
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/groups/G0049">
       OilRig
      </a>
      has used net.exe in a script with
      <code>
       net accounts /domain
      </code>
      to find the password policy of a domain.
      <span class="scite-citeref-number" data-reference="FireEye Targeted Attacks Middle East Banks" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www.fireeye.com/blog/threat-research/2016/05/targeted_attacksaga.html" target="_blank">
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
  Mitigating discovery of password policies is not advised since the information is required to be known by systems and users of a network. Ensure password policies are such that they mitigate brute force attacks yet will not give an adversary an information advantage because the policies are too light. Active Directory is a common way to set and enforce password policies throughout an enterprise network.
  <span class="scite-citeref-number" data-reference="Microsoft Password Complexity" id="scite-ref-6-a">
   <sup>
    <a aria-describedby="qtip-5" data-hasqtip="5" href="https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/password-must-meet-complexity-requirements" target="_blank">
     [6]
    </a>
   </sup>
  </span>
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Monitor processes for tools and command line arguments that may indicate they're being used for password policy discovery. Correlate that activity with other suspicious activity from the originating system to reduce potential false positives from valid user or administrator activity. Adversaries will likely attempt to find the password policy early in an operation and the activity is likely to happen with other Discovery activity.
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
       <a class="external text" href="https://superuser.com/questions/150675/how-to-display-password-policy-information-for-a-user-ubuntu" name="scite-1" rel="nofollow" target="_blank">
        Matutiae, M. (2014, August 6). How to display password policy information for a user (Ubuntu)?. Retrieved April 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.jamf.com/jamf-nation/discussions/18574/user-password-policies-on-non-ad-machines" name="scite-2" rel="nofollow" target="_blank">
        Holland, J. (2016, January 25). User password policies on non AD machines. Retrieved April 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/orangeworm-targets-healthcare-us-europe-asia" name="scite-3" rel="nofollow" target="_blank">
        Symantec Security Response Attack Investigation Team. (2018, April 23). New Orangeworm attack group targets the healthcare sector in the U.S., Europe, and Asia. Retrieved May 8, 2018.
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
       <a class="external text" href="http://windowsitpro.com/windows/netexe-reference" name="scite-4" rel="nofollow" target="_blank">
        Savill, J. (1999, March 4). Net.exe reference. Retrieved September 22, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.fireeye.com/blog/threat-research/2016/05/targeted_attacksaga.html" name="scite-5" rel="nofollow" target="_blank">
        Singh, S., Yin, H. (2016, May 22). https://www.fireeye.com/blog/threat-research/2016/05/targeted_attacksaga.html. Retrieved April 5, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/password-must-meet-complexity-requirements" name="scite-6" rel="nofollow" target="_blank">
        Hall, J., Lich, B. (2017, September 9). Password must meet complexity requirements. Retrieved April 5, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
