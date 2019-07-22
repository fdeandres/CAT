<div class="container-fluid">
 <h1>
  SID-History Injection
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    The Windows security identifier (SID) is a unique value that identifies a user or group account. SIDs are used by Windows security in both security descriptors and access tokens.
    <span class="scite-citeref-number" data-reference="Microsoft SID" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://msdn.microsoft.com/library/windows/desktop/aa379571.aspx" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    An account can hold additional SIDs in the SID-History Active Directory attribute
    <span class="scite-citeref-number" data-reference="Microsoft SID-History Attribute" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="https://msdn.microsoft.com/library/ms679833.aspx" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    , allowing inter-operable account migration between domains (e.g., all values in SID-History are included in access tokens).
   </p>
   <p>
    Adversaries may use this mechanism for privilege escalation. With Domain Administrator (or equivalent) rights, harvested or well-known SID values
    <span class="scite-citeref-number" data-reference="Microsoft Well Known SIDs Jun 2017" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://support.microsoft.com/help/243330/well-known-security-identifiers-in-windows-operating-systems" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    may be inserted into SID-History to enable impersonation of arbitrary users/groups such as Enterprise Administrators. This manipulation may result in elevated access to local resources and/or access to otherwise inaccessible domains via lateral movement techniques such as
    <a href="https://attack.mitre.org/techniques/T1021">
     Remote Services
    </a>
    ,
    <a href="https://attack.mitre.org/techniques/T1077">
     Windows Admin Shares
    </a>
    , or
    <a href="https://attack.mitre.org/techniques/T1028">
     Windows Remote Management
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
      : T1178
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
      Windows
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
      Administrator, SYSTEM
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
      API monitoring, Authentication logs, Windows event logs
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
      Vincent Le Toux; Alain Homewood, Insomnia Security
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
     <a href="https://attack.mitre.org/software/S0363">
      Empire
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0363">
       Empire
      </a>
      can add a SID-History to a user if on a domain controller.
      <span class="scite-citeref-number" data-reference="Github PowerShell Empire" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
       <sup>
        <a aria-describedby="qtip-3" data-hasqtip="3" href="https://github.com/PowerShellEmpire/Empire" target="_blank">
         [4]
        </a>
       </sup>
      </span>
     </p>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://attack.mitre.org/software/S0002">
      Mimikatz
     </a>
    </td>
    <td>
     <p>
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      's
      <code>
       MISC::AddSid
      </code>
      module can appended any SID or user/group account to a user's SID-History.
      <a href="https://attack.mitre.org/software/S0002">
       Mimikatz
      </a>
      also utilizes
      <a href="https://attack.mitre.org/techniques/T1178">
       SID-History Injection
      </a>
      to expand the scope of other components such as generated Kerberos Golden Tickets and DCSync beyond a single domain.
      <span class="scite-citeref-number" data-reference="Adsecurity Mimikatz Guide" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
       <sup>
        <a aria-describedby="qtip-4" data-hasqtip="4" href="https://adsecurity.org/?page_id=1821" target="_blank">
         [5]
        </a>
       </sup>
      </span>
      <span class="scite-citeref-number" data-reference="AdSecurity Kerberos GT Aug 2015" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
       <sup>
        <a aria-describedby="qtip-5" data-hasqtip="5" href="https://adsecurity.org/?p=1640" target="_blank">
         [6]
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
  Clean up SID-History attributes after legitimate account migration is complete.
 </p>
 <p>
  Consider applying SID Filtering to interforest trusts, such as forest trusts and external trusts, to exclude SID-History from requests to access domain resources. SID Filtering ensures that any authentication requests over a trust only contain SIDs of security principals from the trusted domain (i.e. preventing the trusted domain from claiming a user has membership in groups outside of the domain).
 </p>
 <p>
  SID Filtering of forest trusts is enabled by default, but may have been disabled in some cases to allow a child domain to transitively access forest trusts. SID Filtering of external trusts is automatically enabled on all created external trusts using Server 2003 or later domain controllers.
  <span class="scite-citeref-number" data-reference="Microsoft Trust Considerations Nov 2014" id="scite-ref-7-a">
   <sup>
    <a aria-describedby="qtip-6" data-hasqtip="6" href="https://technet.microsoft.com/library/cc755321.aspx" target="_blank">
     [7]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Microsoft SID Filtering Quarantining Jan 2009" id="scite-ref-8-a">
   <sup>
    <a aria-describedby="qtip-7" data-hasqtip="7" href="https://technet.microsoft.com/library/cc794757.aspx" target="_blank">
     [8]
    </a>
   </sup>
  </span>
  However note that SID Filtering is not automatically applied to legacy trusts or may have been deliberately disabled to allow inter-domain access to resources.
 </p>
 <p>
  SID Filtering can be applied by:
  <span class="scite-citeref-number" data-reference="Microsoft Netdom Trust Sept 2012" id="scite-ref-9-a">
   <sup>
    <a aria-describedby="qtip-8" data-hasqtip="8" href="https://technet.microsoft.com/library/cc835085.aspx" target="_blank">
     [9]
    </a>
   </sup>
  </span>
 </p>
 <ul>
  <li>
   Disabling SIDHistory on forest trusts using the netdom tool (
   <code>
    netdom trust
    <trustingdomainname>
     /domain:
     <trusteddomainname>
      /EnableSIDHistory:no
     </trusteddomainname>
    </trustingdomainname>
   </code>
   on the domain controller).
  </li>
  <li>
   Applying SID Filter Quarantining to external trusts using the netdom tool (
   <code>
    netdom trust
    <trustingdomainname>
     /domain:
     <trusteddomainname>
      /quarantine:yes
     </trusteddomainname>
    </trustingdomainname>
   </code>
   on the domain controller)Applying SID Filtering to domain trusts within a single forest is not recommended as it is an unsupported configuration and can cause breaking changes.
   <span class="scite-citeref-number" data-reference="Microsoft Netdom Trust Sept 2012" id="scite-ref-9-a">
    <sup>
     <a aria-describedby="qtip-8" data-hasqtip="8" href="https://technet.microsoft.com/library/cc835085.aspx" target="_blank">
      [9]
     </a>
    </sup>
   </span>
   <span class="scite-citeref-number" data-reference="AdSecurity Kerberos GT Aug 2015" id="scite-ref-6-a">
    <sup>
     <a aria-describedby="qtip-5" data-hasqtip="5" href="https://adsecurity.org/?p=1640" target="_blank">
      [6]
     </a>
    </sup>
   </span>
   If a domain within a forest is untrustworthy then it should not be a member of the forest. In this situation it is necessary to first split the trusted and untrusted domains into separate forests where SID Filtering can be applied to an interforest trust.
  </li>
 </ul>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Examine data in user’s SID-History attributes using the PowerShell Get-ADUser Cmdlet
  <span class="scite-citeref-number" data-reference="Microsoft Get-ADUser" id="scite-ref-10-a">
   <sup>
    <a aria-describedby="qtip-9" data-hasqtip="9" href="https://technet.microsoft.com/library/ee617241.aspx" target="_blank">
     [10]
    </a>
   </sup>
  </span>
  , especially users who have SID-History values from the same domain.
  <span class="scite-citeref-number" data-reference="AdSecurity SID History Sept 2015" id="scite-ref-11-a">
   <sup>
    <a aria-describedby="qtip-10" data-hasqtip="10" href="https://adsecurity.org/?p=1772" target="_blank">
     [11]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Monitor Account Management events on Domain Controllers for successful and failed changes to SID-History.
  <span class="scite-citeref-number" data-reference="AdSecurity SID History Sept 2015" id="scite-ref-11-a">
   <sup>
    <a aria-describedby="qtip-10" data-hasqtip="10" href="https://adsecurity.org/?p=1772" target="_blank">
     [11]
    </a>
   </sup>
  </span>
  <span class="scite-citeref-number" data-reference="Microsoft DsAddSidHistory" id="scite-ref-12-a">
   <sup>
    <a aria-describedby="qtip-11" data-hasqtip="11" href="https://msdn.microsoft.com/library/ms677982.aspx" target="_blank">
     [12]
    </a>
   </sup>
  </span>
 </p>
 <p>
  Monitor Windows API calls to the
  <code>
   DsAddSidHistory
  </code>
  function.
  <span class="scite-citeref-number" data-reference="Microsoft DsAddSidHistory" id="scite-ref-12-a">
   <sup>
    <a aria-describedby="qtip-11" data-hasqtip="11" href="https://msdn.microsoft.com/library/ms677982.aspx" target="_blank">
     [12]
    </a>
   </sup>
  </span>
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
       <a class="external text" href="https://msdn.microsoft.com/library/windows/desktop/aa379571.aspx" name="scite-1" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Security Identifiers. Retrieved November 30, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/ms679833.aspx" name="scite-2" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Active Directory Schema - SID-History attribute. Retrieved November 30, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://support.microsoft.com/help/243330/well-known-security-identifiers-in-windows-operating-systems" name="scite-3" rel="nofollow" target="_blank">
        Microsoft. (2017, June 23). Well-known security identifiers in Windows operating systems. Retrieved November 30, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-4">
      <span class="scite-citation-text">
       <a class="external text" href="https://github.com/PowerShellEmpire/Empire" name="scite-4" rel="nofollow" target="_blank">
        Schroeder, W., Warner, J., Nelson, M. (n.d.). Github PowerShellEmpire. Retrieved April 28, 2016.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://adsecurity.org/?page_id=1821" name="scite-5" rel="nofollow" target="_blank">
        Metcalf, S. (2015, November 13). Unofficial Guide to Mimikatz &amp; Command Reference. Retrieved December 23, 2015.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://adsecurity.org/?p=1640" name="scite-6" rel="nofollow" target="_blank">
        Metcalf, S. (2015, August 7). Kerberos Golden Tickets are Now More Golden. Retrieved December 1, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
  <div class="col">
   <ol start="7.0">
    <li>
     <span class="scite-citation" id="scite-7">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/library/cc755321.aspx" name="scite-7" rel="nofollow" target="_blank">
        Microsoft. (2014, November 19). Security Considerations for Trusts. Retrieved November 30, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-8">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/library/cc794757.aspx" name="scite-8" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Configuring SID Filter Quarantining on External Trusts. Retrieved November 30, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-9">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/library/cc835085.aspx" name="scite-9" rel="nofollow" target="_blank">
        Microsoft. (2012, September 11). Command-Line Reference - Netdom Trust. Retrieved November 30, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-10">
      <span class="scite-citation-text">
       <a class="external text" href="https://technet.microsoft.com/library/ee617241.aspx" name="scite-10" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Active Directory Cmdlets - Get-ADUser. Retrieved November 30, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-11">
      <span class="scite-citation-text">
       <a class="external text" href="https://adsecurity.org/?p=1772" name="scite-11" rel="nofollow" target="_blank">
        Metcalf, S. (2015, September 19). Sneaky Active Directory Persistence #14: SID History. Retrieved November 30, 2017.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-12">
      <span class="scite-citation-text">
       <a class="external text" href="https://msdn.microsoft.com/library/ms677982.aspx" name="scite-12" rel="nofollow" target="_blank">
        Microsoft. (n.d.). Using DsAddSidHistory. Retrieved November 30, 2017.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
