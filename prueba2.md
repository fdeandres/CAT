<!DOCTYPE html>
<html lang="en">
 <head>
  <!-- Global site tag (gtag.js) - Google Analytics -->
  <script async="" src="https://www.googletagmanager.com/gtag/js?id=UA-62667723-1">
  </script>
  <script src="/theme/scripts/analytics.js">
  </script>
  <meta content="2oJKLqNN62z6AOCb0A0IXGtbQuj-lev5YPAHFF_cbHQ" name="google-site-verification"/>
  <meta charset="utf-8"/>
  <meta content="width=device-width, initial-scale=1, shrink-to-fit=no" name="viewport"/>
  <meta content="IE=edge" http-equiv="X-UA-Compatible"/>
  <link href="/theme/favicon.ico" rel="shortcut icon" type="image/x-icon"/>
  <title>
   Technique: Drive-by Compromise - MITRE ATT&amp;CK™
  </title>
  <!-- Bootstrap CSS -->
  <link href="/theme/style/bootstrap.min.css" rel="stylesheet">
   <link href="/theme/style/bootstrap-glyphicon.min.css" rel="stylesheet"/>
   <link href="/theme/style/style.css" rel="stylesheet" type="text/css"/>
  </link>
 </head>
 <body>
  <!--stopindex-->
  <header>
   <nav class="navbar navbar-expand-lg navbar-dark fixed-top bg-mitre-red border-bottom">
    <a class="navbar-brand" href="/">
     <img height="50px" src="/theme/images/mitre_attack.png"/>
    </a>
    <button aria-controls="navbarCollapse" aria-expanded="false" aria-label="Toggle navigation" class="navbar-toggler" data-target="#navbarCollapse" data-toggle="collapse" type="button">
     <span class="navbar-toggler-icon" onclick="search('')">
     </span>
    </button>
    <div class="collapse navbar-collapse" id="navbarCollapse">
     <ul class="nav nav-tabs ml-auto">
      <li class="nav-item">
       <a class="nav-link" href="/matrices/enterprise">
        <b>
         Matrices
        </b>
       </a>
      </li>
      <li class="nav-item dropdown">
       <a aria-expanded="false" aria-haspopup="true" class="nav-link dropdown-toggle" data-toggle="dropdown" href="/tactics/enterprise" id="navbarDropdown" role="button">
        <b>
         Tactics
        </b>
       </a>
       <div aria-labelledby="navbarDropdown" class="dropdown-menu">
        <a class="dropdown-item" href="/tactics/pre">
         PRE-ATT&amp;CK
        </a>
        <a class="dropdown-item" href="/tactics/enterprise">
         Enterprise
        </a>
        <a class="dropdown-item" href="/tactics/mobile">
         Mobile
        </a>
       </div>
      </li>
      <li class="nav-item dropdown">
       <a aria-expanded="false" aria-haspopup="true" class="nav-link dropdown-toggle" data-toggle="dropdown" href="/techniques/enterprise" id="navbarDropdown" role="button">
        <b>
         Techniques
        </b>
       </a>
       <div aria-labelledby="navbarDropdown" class="dropdown-menu">
        <a class="dropdown-item" href="/techniques/pre">
         PRE-ATT&amp;CK
        </a>
        <a class="dropdown-item" href="/techniques/enterprise">
         Enterprise
        </a>
        <a class="dropdown-item" href="/techniques/mobile">
         Mobile
        </a>
       </div>
      </li>
      <li class="nav-item">
       <a class="nav-link" href="/groups/">
        <b>
         Groups
        </b>
       </a>
      </li>
      <li class="nav-item">
       <a class="nav-link" href="/software/">
        <b>
         Software
        </b>
       </a>
      </li>
      <li class="nav-item dropdown">
       <a aria-expanded="false" aria-haspopup="true" class="nav-link dropdown-toggle" data-toggle="dropdown" href="/resources/" id="navbarDropdown" role="button">
        <b>
         Resources
        </b>
       </a>
       <div aria-labelledby="navbarDropdown" class="dropdown-menu">
        <a class="dropdown-item" href="/resources/">
         General
        </a>
        <a class="dropdown-item" href="/resources/getting-started/">
         Getting Started
        </a>
        <a class="dropdown-item" href="/resources/attackcon/">
         ATT&amp;CKcon
        </a>
        <a class="dropdown-item" href="/resources/faq/">
         FAQ
        </a>
        <a class="dropdown-item" href="/resources/updates/">
         Updates
        </a>
        <!-- <a class="dropdown-item" href="/resources/supporters/">Supporters</a>
                                            <a class="dropdown-item" href="/resources/industry-news/">Industry News</a> -->
       </div>
      </li>
      <li class="nav-item">
       <a class="nav-link" href="https://medium.com/mitre-attack/" target="_blank">
        <b>
         Blog
        </b>
        <img alt="External site" class="external-icon" src="/theme/images/external-site.svg"/>
       </a>
      </li>
      <li class="nav-item">
       <a class="nav-link" href="/contact/">
        <b>
         Contact
        </b>
       </a>
      </li>
     </ul>
     <ul class="navbar-nav flex-row d-md-flex" style="float: right">
      <!-- ml-md-auto d-none-->
      <li>
       <form class="form-inline pl-2">
        <input aria-label="Search" autocomplete="off" class="form-control" id="search" placeholder="Search site" type="text"/>
       </form>
       <div class="search-results">
       </div>
      </li>
     </ul>
    </div>
   </nav>
  </header>
  <div class="container-fluid under-development">
   Check out the results from our first round of ATT&amp;CK Evaluations at
   <a href="https://attackevals.mitre.org" target="_blank">
    attackevals.mitre.org
   </a>
   !
  </div>
  <!--startindex-->
  <div id="content">
   <div class="container-fluid">
    <div class="row">
     <!--stopindex-->
     <div aria-orientation="vertical" class="nav flex-column col-xl-2 col-lg-2 col-md-3 sidebar nav pt-5 pb-3 pl-3 border-right" id="v-tab" role="tablist">
      <button aria-expanded="false" aria-haspopup="true" class="btn btn-default dropdown-toggle heading-dropdown" data-toggle="dropdown" id="dropdownMenuButton" type="button">
       ENTERPRISE
      </button>
      <br/>
      <div aria-labelledby="dropdownMenuButton" class="dropdown-menu">
       <a class="dropdown-item" href="/techniques/enterprise">
        ENTERPRISE
       </a>
       <a class="dropdown-item" href="/techniques/mobile">
        MOBILE
       </a>
       <a class="dropdown-item" href="/techniques/pre">
        PRE-ATT&amp;CK
       </a>
      </div>
      <span aria-selected="false" class="heading" id="v-home-tab">
       TECHNIQUES
      </span>
      <!-- <a class="nav-link side active show" id="v-overview-tab" data-toggle="tab" href="#v-overview" role="tab" aria-controls="v-overview" aria-selected="false">Overview</a> -->
      <a aria-controls="{}" aria-expanded="false" class="nav-link side expand-title" href="/techniques/enterprise" id="v-{}-tab" role="tab">
       All
      </a>
      <a aria-controls="initial access" aria-expanded="false" class="nav-link side expand-title" data-toggle="collapse" href="#initial access" id="v-initial access-tab" role="tab">
       <span id="initial access-tooltip" title="Initial Access">
        Initial Access
       </span>
       <span aria-hidden="true" class="glyphicon glyphicon-minus float-right expand-icon">
       </span>
      </a>
      <div aria-labelledby="v-initial access-tab" class="collapse show" id="initial access">
       <div aria-orientation="vertical" class="nav flex-column nav pl-3" id="v-tab" role="tablist">
        <a aria-controls="v-Drive-by Compromise-initial access" aria-selected="false" class="nav-link side active show" href="/techniques/T1189" id="v-Drive-by Compromise-initial access-tab">
         Drive-by Compromise
        </a>
        <a aria-controls="v-Exploit Public-Facing Application-initial access" aria-selected="false" class="nav-link side" href="/techniques/T1190" id="v-Exploit Public-Facing Application-initial access-tab">
         Exploit Public-Facing Application
        </a>
        <a aria-controls="v-Hardware Additions-initial access" aria-selected="false" class="nav-link side" href="/techniques/T1200" id="v-Hardware Additions-initial access-tab">
         Hardware Additions
        </a>
        <a aria-controls="v-Replication Through Removable Media-initial access" aria-selected="false" class="nav-link side" href="/techniques/T1091" id="v-Replication Through Removable Media-initial access-tab">
         Replication Through Removable Media
        </a>
        <a aria-controls="v-Spearphishing Attachment-initial access" aria-selected="false" class="nav-link side" href="/techniques/T1193" id="v-Spearphishing Attachment-initial access-tab">
         Spearphishing Attachment
        </a>
        <a aria-controls="v-Spearphishing Link-initial access" aria-selected="false" class="nav-link side" href="/techniques/T1192" id="v-Spearphishing Link-initial access-tab">
         Spearphishing Link
        </a>
        <a aria-controls="v-Spearphishing via Service-initial access" aria-selected="false" class="nav-link side" href="/techniques/T1194" id="v-Spearphishing via Service-initial access-tab">
         Spearphishing via Service
        </a>
        <a aria-controls="v-Supply Chain Compromise-initial access" aria-selected="false" class="nav-link side" href="/techniques/T1195" id="v-Supply Chain Compromise-initial access-tab">
         Supply Chain Compromise
        </a>
        <a aria-controls="v-Trusted Relationship-initial access" aria-selected="false" class="nav-link side" href="/techniques/T1199" id="v-Trusted Relationship-initial access-tab">
         Trusted Relationship
        </a>
        <a aria-controls="v-Valid Accounts-initial access" aria-selected="false" class="nav-link side" href="/techniques/T1078" id="v-Valid Accounts-initial access-tab">
         Valid Accounts
        </a>
       </div>
      </div>
      <a aria-controls="execution" aria-expanded="false" class="nav-link side expand-title" data-toggle="collapse" href="#execution" id="v-execution-tab" role="tab">
       <span id="execution-tooltip" title="Execution">
        Execution
       </span>
       <span aria-hidden="true" class="glyphicon glyphicon-plus float-right expand-icon">
       </span>
      </a>
      <div aria-labelledby="v-execution-tab" class="collapse" id="execution">
       <div aria-orientation="vertical" class="nav flex-column nav pl-3" id="v-tab" role="tablist">
        <a aria-controls="v-AppleScript-execution" aria-selected="false" class="nav-link side" href="/techniques/T1155" id="v-AppleScript-execution-tab">
         AppleScript
        </a>
        <a aria-controls="v-CMSTP-execution" aria-selected="false" class="nav-link side" href="/techniques/T1191" id="v-CMSTP-execution-tab">
         CMSTP
        </a>
        <a aria-controls="v-Command-Line Interface-execution" aria-selected="false" class="nav-link side" href="/techniques/T1059" id="v-Command-Line Interface-execution-tab">
         Command-Line Interface
        </a>
        <a aria-controls="v-Compiled HTML File-execution" aria-selected="false" class="nav-link side" href="/techniques/T1223" id="v-Compiled HTML File-execution-tab">
         Compiled HTML File
        </a>
        <a aria-controls="v-Control Panel Items-execution" aria-selected="false" class="nav-link side" href="/techniques/T1196" id="v-Control Panel Items-execution-tab">
         Control Panel Items
        </a>
        <a aria-controls="v-Dynamic Data Exchange-execution" aria-selected="false" class="nav-link side" href="/techniques/T1173" id="v-Dynamic Data Exchange-execution-tab">
         Dynamic Data Exchange
        </a>
        <a aria-controls="v-Execution through API-execution" aria-selected="false" class="nav-link side" href="/techniques/T1106" id="v-Execution through API-execution-tab">
         Execution through API
        </a>
        <a aria-controls="v-Execution through Module Load-execution" aria-selected="false" class="nav-link side" href="/techniques/T1129" id="v-Execution through Module Load-execution-tab">
         Execution through Module Load
        </a>
        <a aria-controls="v-Exploitation for Client Execution-execution" aria-selected="false" class="nav-link side" href="/techniques/T1203" id="v-Exploitation for Client Execution-execution-tab">
         Exploitation for Client Execution
        </a>
        <a aria-controls="v-Graphical User Interface-execution" aria-selected="false" class="nav-link side" href="/techniques/T1061" id="v-Graphical User Interface-execution-tab">
         Graphical User Interface
        </a>
        <a aria-controls="v-InstallUtil-execution" aria-selected="false" class="nav-link side" href="/techniques/T1118" id="v-InstallUtil-execution-tab">
         InstallUtil
        </a>
        <a aria-controls="v-Launchctl-execution" aria-selected="false" class="nav-link side" href="/techniques/T1152" id="v-Launchctl-execution-tab">
         Launchctl
        </a>
        <a aria-controls="v-Local Job Scheduling-execution" aria-selected="false" class="nav-link side" href="/techniques/T1168" id="v-Local Job Scheduling-execution-tab">
         Local Job Scheduling
        </a>
        <a aria-controls="v-LSASS Driver-execution" aria-selected="false" class="nav-link side" href="/techniques/T1177" id="v-LSASS Driver-execution-tab">
         LSASS Driver
        </a>
        <a aria-controls="v-Mshta-execution" aria-selected="false" class="nav-link side" href="/techniques/T1170" id="v-Mshta-execution-tab">
         Mshta
        </a>
        <a aria-controls="v-PowerShell-execution" aria-selected="false" class="nav-link side" href="/techniques/T1086" id="v-PowerShell-execution-tab">
         PowerShell
        </a>
        <a aria-controls="v-Regsvcs/Regasm-execution" aria-selected="false" class="nav-link side" href="/techniques/T1121" id="v-Regsvcs/Regasm-execution-tab">
         Regsvcs/Regasm
        </a>
        <a aria-controls="v-Regsvr32-execution" aria-selected="false" class="nav-link side" href="/techniques/T1117" id="v-Regsvr32-execution-tab">
         Regsvr32
        </a>
        <a aria-controls="v-Rundll32-execution" aria-selected="false" class="nav-link side" href="/techniques/T1085" id="v-Rundll32-execution-tab">
         Rundll32
        </a>
        <a aria-controls="v-Scheduled Task-execution" aria-selected="false" class="nav-link side" href="/techniques/T1053" id="v-Scheduled Task-execution-tab">
         Scheduled Task
        </a>
        <a aria-controls="v-Scripting-execution" aria-selected="false" class="nav-link side" href="/techniques/T1064" id="v-Scripting-execution-tab">
         Scripting
        </a>
        <a aria-controls="v-Service Execution-execution" aria-selected="false" class="nav-link side" href="/techniques/T1035" id="v-Service Execution-execution-tab">
         Service Execution
        </a>
        <a aria-controls="v-Signed Binary Proxy Execution-execution" aria-selected="false" class="nav-link side" href="/techniques/T1218" id="v-Signed Binary Proxy Execution-execution-tab">
         Signed Binary Proxy Execution
        </a>
        <a aria-controls="v-Signed Script Proxy Execution-execution" aria-selected="false" class="nav-link side" href="/techniques/T1216" id="v-Signed Script Proxy Execution-execution-tab">
         Signed Script Proxy Execution
        </a>
        <a aria-controls="v-Source-execution" aria-selected="false" class="nav-link side" href="/techniques/T1153" id="v-Source-execution-tab">
         Source
        </a>
        <a aria-controls="v-Space after Filename-execution" aria-selected="false" class="nav-link side" href="/techniques/T1151" id="v-Space after Filename-execution-tab">
         Space after Filename
        </a>
        <a aria-controls="v-Third-party Software-execution" aria-selected="false" class="nav-link side" href="/techniques/T1072" id="v-Third-party Software-execution-tab">
         Third-party Software
        </a>
        <a aria-controls="v-Trap-execution" aria-selected="false" class="nav-link side" href="/techniques/T1154" id="v-Trap-execution-tab">
         Trap
        </a>
        <a aria-controls="v-Trusted Developer Utilities-execution" aria-selected="false" class="nav-link side" href="/techniques/T1127" id="v-Trusted Developer Utilities-execution-tab">
         Trusted Developer Utilities
        </a>
        <a aria-controls="v-User Execution-execution" aria-selected="false" class="nav-link side" href="/techniques/T1204" id="v-User Execution-execution-tab">
         User Execution
        </a>
        <a aria-controls="v-Windows Management Instrumentation-execution" aria-selected="false" class="nav-link side" href="/techniques/T1047" id="v-Windows Management Instrumentation-execution-tab">
         Windows Management Instrumentation
        </a>
        <a aria-controls="v-Windows Remote Management-execution" aria-selected="false" class="nav-link side" href="/techniques/T1028" id="v-Windows Remote Management-execution-tab">
         Windows Remote Management
        </a>
        <a aria-controls="v-XSL Script Processing-execution" aria-selected="false" class="nav-link side" href="/techniques/T1220" id="v-XSL Script Processing-execution-tab">
         XSL Script Processing
        </a>
       </div>
      </div>
      <a aria-controls="persistence" aria-expanded="false" class="nav-link side expand-title" data-toggle="collapse" href="#persistence" id="v-persistence-tab" role="tab">
       <span id="persistence-tooltip" title="Persistence">
        Persistence
       </span>
       <span aria-hidden="true" class="glyphicon glyphicon-plus float-right expand-icon">
       </span>
      </a>
      <div aria-labelledby="v-persistence-tab" class="collapse" id="persistence">
       <div aria-orientation="vertical" class="nav flex-column nav pl-3" id="v-tab" role="tablist">
        <a aria-controls="v-.bash_profile and .bashrc-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1156" id="v-.bash_profile and .bashrc-persistence-tab">
         .bash_profile and .bashrc
        </a>
        <a aria-controls="v-Accessibility Features-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1015" id="v-Accessibility Features-persistence-tab">
         Accessibility Features
        </a>
        <a aria-controls="v-Account Manipulation-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1098" id="v-Account Manipulation-persistence-tab">
         Account Manipulation
        </a>
        <a aria-controls="v-AppCert DLLs-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1182" id="v-AppCert DLLs-persistence-tab">
         AppCert DLLs
        </a>
        <a aria-controls="v-AppInit DLLs-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1103" id="v-AppInit DLLs-persistence-tab">
         AppInit DLLs
        </a>
        <a aria-controls="v-Application Shimming-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1138" id="v-Application Shimming-persistence-tab">
         Application Shimming
        </a>
        <a aria-controls="v-Authentication Package-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1131" id="v-Authentication Package-persistence-tab">
         Authentication Package
        </a>
        <a aria-controls="v-BITS Jobs-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1197" id="v-BITS Jobs-persistence-tab">
         BITS Jobs
        </a>
        <a aria-controls="v-Bootkit-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1067" id="v-Bootkit-persistence-tab">
         Bootkit
        </a>
        <a aria-controls="v-Browser Extensions-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1176" id="v-Browser Extensions-persistence-tab">
         Browser Extensions
        </a>
        <a aria-controls="v-Change Default File Association-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1042" id="v-Change Default File Association-persistence-tab">
         Change Default File Association
        </a>
        <a aria-controls="v-Component Firmware-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1109" id="v-Component Firmware-persistence-tab">
         Component Firmware
        </a>
        <a aria-controls="v-Component Object Model Hijacking-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1122" id="v-Component Object Model Hijacking-persistence-tab">
         Component Object Model Hijacking
        </a>
        <a aria-controls="v-Create Account-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1136" id="v-Create Account-persistence-tab">
         Create Account
        </a>
        <a aria-controls="v-DLL Search Order Hijacking-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1038" id="v-DLL Search Order Hijacking-persistence-tab">
         DLL Search Order Hijacking
        </a>
        <a aria-controls="v-Dylib Hijacking-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1157" id="v-Dylib Hijacking-persistence-tab">
         Dylib Hijacking
        </a>
        <a aria-controls="v-External Remote Services-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1133" id="v-External Remote Services-persistence-tab">
         External Remote Services
        </a>
        <a aria-controls="v-File System Permissions Weakness-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1044" id="v-File System Permissions Weakness-persistence-tab">
         File System Permissions Weakness
        </a>
        <a aria-controls="v-Hidden Files and Directories-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1158" id="v-Hidden Files and Directories-persistence-tab">
         Hidden Files and Directories
        </a>
        <a aria-controls="v-Hooking-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1179" id="v-Hooking-persistence-tab">
         Hooking
        </a>
        <a aria-controls="v-Hypervisor-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1062" id="v-Hypervisor-persistence-tab">
         Hypervisor
        </a>
        <a aria-controls="v-Image File Execution Options Injection-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1183" id="v-Image File Execution Options Injection-persistence-tab">
         Image File Execution Options Injection
        </a>
        <a aria-controls="v-Kernel Modules and Extensions-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1215" id="v-Kernel Modules and Extensions-persistence-tab">
         Kernel Modules and Extensions
        </a>
        <a aria-controls="v-Launch Agent-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1159" id="v-Launch Agent-persistence-tab">
         Launch Agent
        </a>
        <a aria-controls="v-Launch Daemon-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1160" id="v-Launch Daemon-persistence-tab">
         Launch Daemon
        </a>
        <a aria-controls="v-Launchctl-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1152" id="v-Launchctl-persistence-tab">
         Launchctl
        </a>
        <a aria-controls="v-LC_LOAD_DYLIB Addition-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1161" id="v-LC_LOAD_DYLIB Addition-persistence-tab">
         LC_LOAD_DYLIB Addition
        </a>
        <a aria-controls="v-Local Job Scheduling-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1168" id="v-Local Job Scheduling-persistence-tab">
         Local Job Scheduling
        </a>
        <a aria-controls="v-Login Item-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1162" id="v-Login Item-persistence-tab">
         Login Item
        </a>
        <a aria-controls="v-Logon Scripts-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1037" id="v-Logon Scripts-persistence-tab">
         Logon Scripts
        </a>
        <a aria-controls="v-LSASS Driver-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1177" id="v-LSASS Driver-persistence-tab">
         LSASS Driver
        </a>
        <a aria-controls="v-Modify Existing Service-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1031" id="v-Modify Existing Service-persistence-tab">
         Modify Existing Service
        </a>
        <a aria-controls="v-Netsh Helper DLL-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1128" id="v-Netsh Helper DLL-persistence-tab">
         Netsh Helper DLL
        </a>
        <a aria-controls="v-New Service-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1050" id="v-New Service-persistence-tab">
         New Service
        </a>
        <a aria-controls="v-Office Application Startup-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1137" id="v-Office Application Startup-persistence-tab">
         Office Application Startup
        </a>
        <a aria-controls="v-Path Interception-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1034" id="v-Path Interception-persistence-tab">
         Path Interception
        </a>
        <a aria-controls="v-Plist Modification-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1150" id="v-Plist Modification-persistence-tab">
         Plist Modification
        </a>
        <a aria-controls="v-Port Knocking-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1205" id="v-Port Knocking-persistence-tab">
         Port Knocking
        </a>
        <a aria-controls="v-Port Monitors-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1013" id="v-Port Monitors-persistence-tab">
         Port Monitors
        </a>
        <a aria-controls="v-Rc.common-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1163" id="v-Rc.common-persistence-tab">
         Rc.common
        </a>
        <a aria-controls="v-Re-opened Applications-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1164" id="v-Re-opened Applications-persistence-tab">
         Re-opened Applications
        </a>
        <a aria-controls="v-Redundant Access-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1108" id="v-Redundant Access-persistence-tab">
         Redundant Access
        </a>
        <a aria-controls="v-Registry Run Keys / Startup Folder-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1060" id="v-Registry Run Keys / Startup Folder-persistence-tab">
         Registry Run Keys / Startup Folder
        </a>
        <a aria-controls="v-Scheduled Task-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1053" id="v-Scheduled Task-persistence-tab">
         Scheduled Task
        </a>
        <a aria-controls="v-Screensaver-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1180" id="v-Screensaver-persistence-tab">
         Screensaver
        </a>
        <a aria-controls="v-Security Support Provider-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1101" id="v-Security Support Provider-persistence-tab">
         Security Support Provider
        </a>
        <a aria-controls="v-Service Registry Permissions Weakness-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1058" id="v-Service Registry Permissions Weakness-persistence-tab">
         Service Registry Permissions Weakness
        </a>
        <a aria-controls="v-Setuid and Setgid-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1166" id="v-Setuid and Setgid-persistence-tab">
         Setuid and Setgid
        </a>
        <a aria-controls="v-Shortcut Modification-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1023" id="v-Shortcut Modification-persistence-tab">
         Shortcut Modification
        </a>
        <a aria-controls="v-SIP and Trust Provider Hijacking-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1198" id="v-SIP and Trust Provider Hijacking-persistence-tab">
         SIP and Trust Provider Hijacking
        </a>
        <a aria-controls="v-Startup Items-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1165" id="v-Startup Items-persistence-tab">
         Startup Items
        </a>
        <a aria-controls="v-System Firmware-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1019" id="v-System Firmware-persistence-tab">
         System Firmware
        </a>
        <a aria-controls="v-Time Providers-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1209" id="v-Time Providers-persistence-tab">
         Time Providers
        </a>
        <a aria-controls="v-Trap-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1154" id="v-Trap-persistence-tab">
         Trap
        </a>
        <a aria-controls="v-Valid Accounts-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1078" id="v-Valid Accounts-persistence-tab">
         Valid Accounts
        </a>
        <a aria-controls="v-Web Shell-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1100" id="v-Web Shell-persistence-tab">
         Web Shell
        </a>
        <a aria-controls="v-Windows Management Instrumentation Event Subscription-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1084" id="v-Windows Management Instrumentation Event Subscription-persistence-tab">
         Windows Management Instrumentation Event Subscription
        </a>
        <a aria-controls="v-Winlogon Helper DLL-persistence" aria-selected="false" class="nav-link side" href="/techniques/T1004" id="v-Winlogon Helper DLL-persistence-tab">
         Winlogon Helper DLL
        </a>
       </div>
      </div>
      <a aria-controls="privilege escalation" aria-expanded="false" class="nav-link side expand-title" data-toggle="collapse" href="#privilege escalation" id="v-privilege escalation-tab" role="tab">
       <span id="privilege_escalation-tooltip" title="Privilege Escalation">
        Privilege Escalation
       </span>
       <span aria-hidden="true" class="glyphicon glyphicon-plus float-right expand-icon">
       </span>
      </a>
      <div aria-labelledby="v-privilege escalation-tab" class="collapse" id="privilege escalation">
       <div aria-orientation="vertical" class="nav flex-column nav pl-3" id="v-tab" role="tablist">
        <a aria-controls="v-Access Token Manipulation-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1134" id="v-Access Token Manipulation-privilege escalation-tab">
         Access Token Manipulation
        </a>
        <a aria-controls="v-Accessibility Features-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1015" id="v-Accessibility Features-privilege escalation-tab">
         Accessibility Features
        </a>
        <a aria-controls="v-AppCert DLLs-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1182" id="v-AppCert DLLs-privilege escalation-tab">
         AppCert DLLs
        </a>
        <a aria-controls="v-AppInit DLLs-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1103" id="v-AppInit DLLs-privilege escalation-tab">
         AppInit DLLs
        </a>
        <a aria-controls="v-Application Shimming-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1138" id="v-Application Shimming-privilege escalation-tab">
         Application Shimming
        </a>
        <a aria-controls="v-Bypass User Account Control-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1088" id="v-Bypass User Account Control-privilege escalation-tab">
         Bypass User Account Control
        </a>
        <a aria-controls="v-DLL Search Order Hijacking-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1038" id="v-DLL Search Order Hijacking-privilege escalation-tab">
         DLL Search Order Hijacking
        </a>
        <a aria-controls="v-Dylib Hijacking-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1157" id="v-Dylib Hijacking-privilege escalation-tab">
         Dylib Hijacking
        </a>
        <a aria-controls="v-Exploitation for Privilege Escalation-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1068" id="v-Exploitation for Privilege Escalation-privilege escalation-tab">
         Exploitation for Privilege Escalation
        </a>
        <a aria-controls="v-Extra Window Memory Injection-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1181" id="v-Extra Window Memory Injection-privilege escalation-tab">
         Extra Window Memory Injection
        </a>
        <a aria-controls="v-File System Permissions Weakness-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1044" id="v-File System Permissions Weakness-privilege escalation-tab">
         File System Permissions Weakness
        </a>
        <a aria-controls="v-Hooking-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1179" id="v-Hooking-privilege escalation-tab">
         Hooking
        </a>
        <a aria-controls="v-Image File Execution Options Injection-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1183" id="v-Image File Execution Options Injection-privilege escalation-tab">
         Image File Execution Options Injection
        </a>
        <a aria-controls="v-Launch Daemon-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1160" id="v-Launch Daemon-privilege escalation-tab">
         Launch Daemon
        </a>
        <a aria-controls="v-New Service-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1050" id="v-New Service-privilege escalation-tab">
         New Service
        </a>
        <a aria-controls="v-Path Interception-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1034" id="v-Path Interception-privilege escalation-tab">
         Path Interception
        </a>
        <a aria-controls="v-Plist Modification-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1150" id="v-Plist Modification-privilege escalation-tab">
         Plist Modification
        </a>
        <a aria-controls="v-Port Monitors-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1013" id="v-Port Monitors-privilege escalation-tab">
         Port Monitors
        </a>
        <a aria-controls="v-Process Injection-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1055" id="v-Process Injection-privilege escalation-tab">
         Process Injection
        </a>
        <a aria-controls="v-Scheduled Task-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1053" id="v-Scheduled Task-privilege escalation-tab">
         Scheduled Task
        </a>
        <a aria-controls="v-Service Registry Permissions Weakness-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1058" id="v-Service Registry Permissions Weakness-privilege escalation-tab">
         Service Registry Permissions Weakness
        </a>
        <a aria-controls="v-Setuid and Setgid-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1166" id="v-Setuid and Setgid-privilege escalation-tab">
         Setuid and Setgid
        </a>
        <a aria-controls="v-SID-History Injection-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1178" id="v-SID-History Injection-privilege escalation-tab">
         SID-History Injection
        </a>
        <a aria-controls="v-Startup Items-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1165" id="v-Startup Items-privilege escalation-tab">
         Startup Items
        </a>
        <a aria-controls="v-Sudo-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1169" id="v-Sudo-privilege escalation-tab">
         Sudo
        </a>
        <a aria-controls="v-Sudo Caching-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1206" id="v-Sudo Caching-privilege escalation-tab">
         Sudo Caching
        </a>
        <a aria-controls="v-Valid Accounts-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1078" id="v-Valid Accounts-privilege escalation-tab">
         Valid Accounts
        </a>
        <a aria-controls="v-Web Shell-privilege escalation" aria-selected="false" class="nav-link side" href="/techniques/T1100" id="v-Web Shell-privilege escalation-tab">
         Web Shell
        </a>
       </div>
      </div>
      <a aria-controls="defense evasion" aria-expanded="false" class="nav-link side expand-title" data-toggle="collapse" href="#defense evasion" id="v-defense evasion-tab" role="tab">
       <span id="defense_evasion-tooltip" title="Defense Evasion">
        Defense Evasion
       </span>
       <span aria-hidden="true" class="glyphicon glyphicon-plus float-right expand-icon">
       </span>
      </a>
      <div aria-labelledby="v-defense evasion-tab" class="collapse" id="defense evasion">
       <div aria-orientation="vertical" class="nav flex-column nav pl-3" id="v-tab" role="tablist">
        <a aria-controls="v-Access Token Manipulation-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1134" id="v-Access Token Manipulation-defense evasion-tab">
         Access Token Manipulation
        </a>
        <a aria-controls="v-Binary Padding-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1009" id="v-Binary Padding-defense evasion-tab">
         Binary Padding
        </a>
        <a aria-controls="v-BITS Jobs-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1197" id="v-BITS Jobs-defense evasion-tab">
         BITS Jobs
        </a>
        <a aria-controls="v-Bypass User Account Control-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1088" id="v-Bypass User Account Control-defense evasion-tab">
         Bypass User Account Control
        </a>
        <a aria-controls="v-Clear Command History-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1146" id="v-Clear Command History-defense evasion-tab">
         Clear Command History
        </a>
        <a aria-controls="v-CMSTP-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1191" id="v-CMSTP-defense evasion-tab">
         CMSTP
        </a>
        <a aria-controls="v-Code Signing-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1116" id="v-Code Signing-defense evasion-tab">
         Code Signing
        </a>
        <a aria-controls="v-Compiled HTML File-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1223" id="v-Compiled HTML File-defense evasion-tab">
         Compiled HTML File
        </a>
        <a aria-controls="v-Component Firmware-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1109" id="v-Component Firmware-defense evasion-tab">
         Component Firmware
        </a>
        <a aria-controls="v-Component Object Model Hijacking-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1122" id="v-Component Object Model Hijacking-defense evasion-tab">
         Component Object Model Hijacking
        </a>
        <a aria-controls="v-Control Panel Items-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1196" id="v-Control Panel Items-defense evasion-tab">
         Control Panel Items
        </a>
        <a aria-controls="v-DCShadow-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1207" id="v-DCShadow-defense evasion-tab">
         DCShadow
        </a>
        <a aria-controls="v-Deobfuscate/Decode Files or Information-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1140" id="v-Deobfuscate/Decode Files or Information-defense evasion-tab">
         Deobfuscate/Decode Files or Information
        </a>
        <a aria-controls="v-Disabling Security Tools-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1089" id="v-Disabling Security Tools-defense evasion-tab">
         Disabling Security Tools
        </a>
        <a aria-controls="v-DLL Search Order Hijacking-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1038" id="v-DLL Search Order Hijacking-defense evasion-tab">
         DLL Search Order Hijacking
        </a>
        <a aria-controls="v-DLL Side-Loading-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1073" id="v-DLL Side-Loading-defense evasion-tab">
         DLL Side-Loading
        </a>
        <a aria-controls="v-Exploitation for Defense Evasion-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1211" id="v-Exploitation for Defense Evasion-defense evasion-tab">
         Exploitation for Defense Evasion
        </a>
        <a aria-controls="v-Extra Window Memory Injection-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1181" id="v-Extra Window Memory Injection-defense evasion-tab">
         Extra Window Memory Injection
        </a>
        <a aria-controls="v-File Deletion-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1107" id="v-File Deletion-defense evasion-tab">
         File Deletion
        </a>
        <a aria-controls="v-File Permissions Modification-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1222" id="v-File Permissions Modification-defense evasion-tab">
         File Permissions Modification
        </a>
        <a aria-controls="v-File System Logical Offsets-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1006" id="v-File System Logical Offsets-defense evasion-tab">
         File System Logical Offsets
        </a>
        <a aria-controls="v-Gatekeeper Bypass-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1144" id="v-Gatekeeper Bypass-defense evasion-tab">
         Gatekeeper Bypass
        </a>
        <a aria-controls="v-Hidden Files and Directories-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1158" id="v-Hidden Files and Directories-defense evasion-tab">
         Hidden Files and Directories
        </a>
        <a aria-controls="v-Hidden Users-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1147" id="v-Hidden Users-defense evasion-tab">
         Hidden Users
        </a>
        <a aria-controls="v-Hidden Window-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1143" id="v-Hidden Window-defense evasion-tab">
         Hidden Window
        </a>
        <a aria-controls="v-HISTCONTROL-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1148" id="v-HISTCONTROL-defense evasion-tab">
         HISTCONTROL
        </a>
        <a aria-controls="v-Image File Execution Options Injection-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1183" id="v-Image File Execution Options Injection-defense evasion-tab">
         Image File Execution Options Injection
        </a>
        <a aria-controls="v-Indicator Blocking-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1054" id="v-Indicator Blocking-defense evasion-tab">
         Indicator Blocking
        </a>
        <a aria-controls="v-Indicator Removal from Tools-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1066" id="v-Indicator Removal from Tools-defense evasion-tab">
         Indicator Removal from Tools
        </a>
        <a aria-controls="v-Indicator Removal on Host-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1070" id="v-Indicator Removal on Host-defense evasion-tab">
         Indicator Removal on Host
        </a>
        <a aria-controls="v-Indirect Command Execution-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1202" id="v-Indirect Command Execution-defense evasion-tab">
         Indirect Command Execution
        </a>
        <a aria-controls="v-Install Root Certificate-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1130" id="v-Install Root Certificate-defense evasion-tab">
         Install Root Certificate
        </a>
        <a aria-controls="v-InstallUtil-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1118" id="v-InstallUtil-defense evasion-tab">
         InstallUtil
        </a>
        <a aria-controls="v-Launchctl-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1152" id="v-Launchctl-defense evasion-tab">
         Launchctl
        </a>
        <a aria-controls="v-LC_MAIN Hijacking-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1149" id="v-LC_MAIN Hijacking-defense evasion-tab">
         LC_MAIN Hijacking
        </a>
        <a aria-controls="v-Masquerading-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1036" id="v-Masquerading-defense evasion-tab">
         Masquerading
        </a>
        <a aria-controls="v-Modify Registry-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1112" id="v-Modify Registry-defense evasion-tab">
         Modify Registry
        </a>
        <a aria-controls="v-Mshta-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1170" id="v-Mshta-defense evasion-tab">
         Mshta
        </a>
        <a aria-controls="v-Network Share Connection Removal-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1126" id="v-Network Share Connection Removal-defense evasion-tab">
         Network Share Connection Removal
        </a>
        <a aria-controls="v-NTFS File Attributes-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1096" id="v-NTFS File Attributes-defense evasion-tab">
         NTFS File Attributes
        </a>
        <a aria-controls="v-Obfuscated Files or Information-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1027" id="v-Obfuscated Files or Information-defense evasion-tab">
         Obfuscated Files or Information
        </a>
        <a aria-controls="v-Plist Modification-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1150" id="v-Plist Modification-defense evasion-tab">
         Plist Modification
        </a>
        <a aria-controls="v-Port Knocking-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1205" id="v-Port Knocking-defense evasion-tab">
         Port Knocking
        </a>
        <a aria-controls="v-Process Doppelgänging-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1186" id="v-Process Doppelgänging-defense evasion-tab">
         Process Doppelgänging
        </a>
        <a aria-controls="v-Process Hollowing-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1093" id="v-Process Hollowing-defense evasion-tab">
         Process Hollowing
        </a>
        <a aria-controls="v-Process Injection-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1055" id="v-Process Injection-defense evasion-tab">
         Process Injection
        </a>
        <a aria-controls="v-Redundant Access-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1108" id="v-Redundant Access-defense evasion-tab">
         Redundant Access
        </a>
        <a aria-controls="v-Regsvcs/Regasm-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1121" id="v-Regsvcs/Regasm-defense evasion-tab">
         Regsvcs/Regasm
        </a>
        <a aria-controls="v-Regsvr32-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1117" id="v-Regsvr32-defense evasion-tab">
         Regsvr32
        </a>
        <a aria-controls="v-Rootkit-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1014" id="v-Rootkit-defense evasion-tab">
         Rootkit
        </a>
        <a aria-controls="v-Rundll32-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1085" id="v-Rundll32-defense evasion-tab">
         Rundll32
        </a>
        <a aria-controls="v-Scripting-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1064" id="v-Scripting-defense evasion-tab">
         Scripting
        </a>
        <a aria-controls="v-Signed Binary Proxy Execution-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1218" id="v-Signed Binary Proxy Execution-defense evasion-tab">
         Signed Binary Proxy Execution
        </a>
        <a aria-controls="v-Signed Script Proxy Execution-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1216" id="v-Signed Script Proxy Execution-defense evasion-tab">
         Signed Script Proxy Execution
        </a>
        <a aria-controls="v-SIP and Trust Provider Hijacking-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1198" id="v-SIP and Trust Provider Hijacking-defense evasion-tab">
         SIP and Trust Provider Hijacking
        </a>
        <a aria-controls="v-Software Packing-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1045" id="v-Software Packing-defense evasion-tab">
         Software Packing
        </a>
        <a aria-controls="v-Space after Filename-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1151" id="v-Space after Filename-defense evasion-tab">
         Space after Filename
        </a>
        <a aria-controls="v-Template Injection-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1221" id="v-Template Injection-defense evasion-tab">
         Template Injection
        </a>
        <a aria-controls="v-Timestomp-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1099" id="v-Timestomp-defense evasion-tab">
         Timestomp
        </a>
        <a aria-controls="v-Trusted Developer Utilities-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1127" id="v-Trusted Developer Utilities-defense evasion-tab">
         Trusted Developer Utilities
        </a>
        <a aria-controls="v-Valid Accounts-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1078" id="v-Valid Accounts-defense evasion-tab">
         Valid Accounts
        </a>
        <a aria-controls="v-Web Service-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1102" id="v-Web Service-defense evasion-tab">
         Web Service
        </a>
        <a aria-controls="v-XSL Script Processing-defense evasion" aria-selected="false" class="nav-link side" href="/techniques/T1220" id="v-XSL Script Processing-defense evasion-tab">
         XSL Script Processing
        </a>
       </div>
      </div>
      <a aria-controls="credential access" aria-expanded="false" class="nav-link side expand-title" data-toggle="collapse" href="#credential access" id="v-credential access-tab" role="tab">
       <span id="credential_access-tooltip" title="Credential Access">
        Credential Access
       </span>
       <span aria-hidden="true" class="glyphicon glyphicon-plus float-right expand-icon">
       </span>
      </a>
      <div aria-labelledby="v-credential access-tab" class="collapse" id="credential access">
       <div aria-orientation="vertical" class="nav flex-column nav pl-3" id="v-tab" role="tablist">
        <a aria-controls="v-Account Manipulation-credential access" aria-selected="false" class="nav-link side" href="/techniques/T1098" id="v-Account Manipulation-credential access-tab">
         Account Manipulation
        </a>
        <a aria-controls="v-Bash History-credential access" aria-selected="false" class="nav-link side" href="/techniques/T1139" id="v-Bash History-credential access-tab">
         Bash History
        </a>
        <a aria-controls="v-Brute Force-credential access" aria-selected="false" class="nav-link side" href="/techniques/T1110" id="v-Brute Force-credential access-tab">
         Brute Force
        </a>
        <a aria-controls="v-Credential Dumping-credential access" aria-selected="false" class="nav-link side" href="/techniques/T1003" id="v-Credential Dumping-credential access-tab">
         Credential Dumping
        </a>
        <a aria-controls="v-Credentials in Files-credential access" aria-selected="false" class="nav-link side" href="/techniques/T1081" id="v-Credentials in Files-credential access-tab">
         Credentials in Files
        </a>
        <a aria-controls="v-Credentials in Registry-credential access" aria-selected="false" class="nav-link side" href="/techniques/T1214" id="v-Credentials in Registry-credential access-tab">
         Credentials in Registry
        </a>
        <a aria-controls="v-Exploitation for Credential Access-credential access" aria-selected="false" class="nav-link side" href="/techniques/T1212" id="v-Exploitation for Credential Access-credential access-tab">
         Exploitation for Credential Access
        </a>
        <a aria-controls="v-Forced Authentication-credential access" aria-selected="false" class="nav-link side" href="/techniques/T1187" id="v-Forced Authentication-credential access-tab">
         Forced Authentication
        </a>
        <a aria-controls="v-Hooking-credential access" aria-selected="false" class="nav-link side" href="/techniques/T1179" id="v-Hooking-credential access-tab">
         Hooking
        </a>
        <a aria-controls="v-Input Capture-credential access" aria-selected="false" class="nav-link side" href="/techniques/T1056" id="v-Input Capture-credential access-tab">
         Input Capture
        </a>
        <a aria-controls="v-Input Prompt-credential access" aria-selected="false" class="nav-link side" href="/techniques/T1141" id="v-Input Prompt-credential access-tab">
         Input Prompt
        </a>
        <a aria-controls="v-Kerberoasting-credential access" aria-selected="false" class="nav-link side" href="/techniques/T1208" id="v-Kerberoasting-credential access-tab">
         Kerberoasting
        </a>
        <a aria-controls="v-Keychain-credential access" aria-selected="false" class="nav-link side" href="/techniques/T1142" id="v-Keychain-credential access-tab">
         Keychain
        </a>
        <a aria-controls="v-LLMNR/NBT-NS Poisoning-credential access" aria-selected="false" class="nav-link side" href="/techniques/T1171" id="v-LLMNR/NBT-NS Poisoning-credential access-tab">
         LLMNR/NBT-NS Poisoning
        </a>
        <a aria-controls="v-Network Sniffing-credential access" aria-selected="false" class="nav-link side" href="/techniques/T1040" id="v-Network Sniffing-credential access-tab">
         Network Sniffing
        </a>
        <a aria-controls="v-Password Filter DLL-credential access" aria-selected="false" class="nav-link side" href="/techniques/T1174" id="v-Password Filter DLL-credential access-tab">
         Password Filter DLL
        </a>
        <a aria-controls="v-Private Keys-credential access" aria-selected="false" class="nav-link side" href="/techniques/T1145" id="v-Private Keys-credential access-tab">
         Private Keys
        </a>
        <a aria-controls="v-Securityd Memory-credential access" aria-selected="false" class="nav-link side" href="/techniques/T1167" id="v-Securityd Memory-credential access-tab">
         Securityd Memory
        </a>
        <a aria-controls="v-Two-Factor Authentication Interception-credential access" aria-selected="false" class="nav-link side" href="/techniques/T1111" id="v-Two-Factor Authentication Interception-credential access-tab">
         Two-Factor Authentication Interception
        </a>
       </div>
      </div>
      <a aria-controls="discovery" aria-expanded="false" class="nav-link side expand-title" data-toggle="collapse" href="#discovery" id="v-discovery-tab" role="tab">
       <span id="discovery-tooltip" title="Discovery">
        Discovery
       </span>
       <span aria-hidden="true" class="glyphicon glyphicon-plus float-right expand-icon">
       </span>
      </a>
      <div aria-labelledby="v-discovery-tab" class="collapse" id="discovery">
       <div aria-orientation="vertical" class="nav flex-column nav pl-3" id="v-tab" role="tablist">
        <a aria-controls="v-Account Discovery-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1087" id="v-Account Discovery-discovery-tab">
         Account Discovery
        </a>
        <a aria-controls="v-Application Window Discovery-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1010" id="v-Application Window Discovery-discovery-tab">
         Application Window Discovery
        </a>
        <a aria-controls="v-Browser Bookmark Discovery-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1217" id="v-Browser Bookmark Discovery-discovery-tab">
         Browser Bookmark Discovery
        </a>
        <a aria-controls="v-File and Directory Discovery-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1083" id="v-File and Directory Discovery-discovery-tab">
         File and Directory Discovery
        </a>
        <a aria-controls="v-Network Service Scanning-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1046" id="v-Network Service Scanning-discovery-tab">
         Network Service Scanning
        </a>
        <a aria-controls="v-Network Share Discovery-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1135" id="v-Network Share Discovery-discovery-tab">
         Network Share Discovery
        </a>
        <a aria-controls="v-Network Sniffing-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1040" id="v-Network Sniffing-discovery-tab">
         Network Sniffing
        </a>
        <a aria-controls="v-Password Policy Discovery-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1201" id="v-Password Policy Discovery-discovery-tab">
         Password Policy Discovery
        </a>
        <a aria-controls="v-Peripheral Device Discovery-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1120" id="v-Peripheral Device Discovery-discovery-tab">
         Peripheral Device Discovery
        </a>
        <a aria-controls="v-Permission Groups Discovery-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1069" id="v-Permission Groups Discovery-discovery-tab">
         Permission Groups Discovery
        </a>
        <a aria-controls="v-Process Discovery-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1057" id="v-Process Discovery-discovery-tab">
         Process Discovery
        </a>
        <a aria-controls="v-Query Registry-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1012" id="v-Query Registry-discovery-tab">
         Query Registry
        </a>
        <a aria-controls="v-Remote System Discovery-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1018" id="v-Remote System Discovery-discovery-tab">
         Remote System Discovery
        </a>
        <a aria-controls="v-Security Software Discovery-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1063" id="v-Security Software Discovery-discovery-tab">
         Security Software Discovery
        </a>
        <a aria-controls="v-System Information Discovery-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1082" id="v-System Information Discovery-discovery-tab">
         System Information Discovery
        </a>
        <a aria-controls="v-System Network Configuration Discovery-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1016" id="v-System Network Configuration Discovery-discovery-tab">
         System Network Configuration Discovery
        </a>
        <a aria-controls="v-System Network Connections Discovery-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1049" id="v-System Network Connections Discovery-discovery-tab">
         System Network Connections Discovery
        </a>
        <a aria-controls="v-System Owner/User Discovery-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1033" id="v-System Owner/User Discovery-discovery-tab">
         System Owner/User Discovery
        </a>
        <a aria-controls="v-System Service Discovery-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1007" id="v-System Service Discovery-discovery-tab">
         System Service Discovery
        </a>
        <a aria-controls="v-System Time Discovery-discovery" aria-selected="false" class="nav-link side" href="/techniques/T1124" id="v-System Time Discovery-discovery-tab">
         System Time Discovery
        </a>
       </div>
      </div>
      <a aria-controls="lateral movement" aria-expanded="false" class="nav-link side expand-title" data-toggle="collapse" href="#lateral movement" id="v-lateral movement-tab" role="tab">
       <span id="lateral_movement-tooltip" title="Lateral Movement">
        Lateral Movement
       </span>
       <span aria-hidden="true" class="glyphicon glyphicon-plus float-right expand-icon">
       </span>
      </a>
      <div aria-labelledby="v-lateral movement-tab" class="collapse" id="lateral movement">
       <div aria-orientation="vertical" class="nav flex-column nav pl-3" id="v-tab" role="tablist">
        <a aria-controls="v-AppleScript-lateral movement" aria-selected="false" class="nav-link side" href="/techniques/T1155" id="v-AppleScript-lateral movement-tab">
         AppleScript
        </a>
        <a aria-controls="v-Application Deployment Software-lateral movement" aria-selected="false" class="nav-link side" href="/techniques/T1017" id="v-Application Deployment Software-lateral movement-tab">
         Application Deployment Software
        </a>
        <a aria-controls="v-Distributed Component Object Model-lateral movement" aria-selected="false" class="nav-link side" href="/techniques/T1175" id="v-Distributed Component Object Model-lateral movement-tab">
         Distributed Component Object Model
        </a>
        <a aria-controls="v-Exploitation of Remote Services-lateral movement" aria-selected="false" class="nav-link side" href="/techniques/T1210" id="v-Exploitation of Remote Services-lateral movement-tab">
         Exploitation of Remote Services
        </a>
        <a aria-controls="v-Logon Scripts-lateral movement" aria-selected="false" class="nav-link side" href="/techniques/T1037" id="v-Logon Scripts-lateral movement-tab">
         Logon Scripts
        </a>
        <a aria-controls="v-Pass the Hash-lateral movement" aria-selected="false" class="nav-link side" href="/techniques/T1075" id="v-Pass the Hash-lateral movement-tab">
         Pass the Hash
        </a>
        <a aria-controls="v-Pass the Ticket-lateral movement" aria-selected="false" class="nav-link side" href="/techniques/T1097" id="v-Pass the Ticket-lateral movement-tab">
         Pass the Ticket
        </a>
        <a aria-controls="v-Remote Desktop Protocol-lateral movement" aria-selected="false" class="nav-link side" href="/techniques/T1076" id="v-Remote Desktop Protocol-lateral movement-tab">
         Remote Desktop Protocol
        </a>
        <a aria-controls="v-Remote File Copy-lateral movement" aria-selected="false" class="nav-link side" href="/techniques/T1105" id="v-Remote File Copy-lateral movement-tab">
         Remote File Copy
        </a>
        <a aria-controls="v-Remote Services-lateral movement" aria-selected="false" class="nav-link side" href="/techniques/T1021" id="v-Remote Services-lateral movement-tab">
         Remote Services
        </a>
        <a aria-controls="v-Replication Through Removable Media-lateral movement" aria-selected="false" class="nav-link side" href="/techniques/T1091" id="v-Replication Through Removable Media-lateral movement-tab">
         Replication Through Removable Media
        </a>
        <a aria-controls="v-Shared Webroot-lateral movement" aria-selected="false" class="nav-link side" href="/techniques/T1051" id="v-Shared Webroot-lateral movement-tab">
         Shared Webroot
        </a>
        <a aria-controls="v-SSH Hijacking-lateral movement" aria-selected="false" class="nav-link side" href="/techniques/T1184" id="v-SSH Hijacking-lateral movement-tab">
         SSH Hijacking
        </a>
        <a aria-controls="v-Taint Shared Content-lateral movement" aria-selected="false" class="nav-link side" href="/techniques/T1080" id="v-Taint Shared Content-lateral movement-tab">
         Taint Shared Content
        </a>
        <a aria-controls="v-Third-party Software-lateral movement" aria-selected="false" class="nav-link side" href="/techniques/T1072" id="v-Third-party Software-lateral movement-tab">
         Third-party Software
        </a>
        <a aria-controls="v-Windows Admin Shares-lateral movement" aria-selected="false" class="nav-link side" href="/techniques/T1077" id="v-Windows Admin Shares-lateral movement-tab">
         Windows Admin Shares
        </a>
        <a aria-controls="v-Windows Remote Management-lateral movement" aria-selected="false" class="nav-link side" href="/techniques/T1028" id="v-Windows Remote Management-lateral movement-tab">
         Windows Remote Management
        </a>
       </div>
      </div>
      <a aria-controls="collection" aria-expanded="false" class="nav-link side expand-title" data-toggle="collapse" href="#collection" id="v-collection-tab" role="tab">
       <span id="collection-tooltip" title="Collection">
        Collection
       </span>
       <span aria-hidden="true" class="glyphicon glyphicon-plus float-right expand-icon">
       </span>
      </a>
      <div aria-labelledby="v-collection-tab" class="collapse" id="collection">
       <div aria-orientation="vertical" class="nav flex-column nav pl-3" id="v-tab" role="tablist">
        <a aria-controls="v-Audio Capture-collection" aria-selected="false" class="nav-link side" href="/techniques/T1123" id="v-Audio Capture-collection-tab">
         Audio Capture
        </a>
        <a aria-controls="v-Automated Collection-collection" aria-selected="false" class="nav-link side" href="/techniques/T1119" id="v-Automated Collection-collection-tab">
         Automated Collection
        </a>
        <a aria-controls="v-Clipboard Data-collection" aria-selected="false" class="nav-link side" href="/techniques/T1115" id="v-Clipboard Data-collection-tab">
         Clipboard Data
        </a>
        <a aria-controls="v-Data from Information Repositories-collection" aria-selected="false" class="nav-link side" href="/techniques/T1213" id="v-Data from Information Repositories-collection-tab">
         Data from Information Repositories
        </a>
        <a aria-controls="v-Data from Local System-collection" aria-selected="false" class="nav-link side" href="/techniques/T1005" id="v-Data from Local System-collection-tab">
         Data from Local System
        </a>
        <a aria-controls="v-Data from Network Shared Drive-collection" aria-selected="false" class="nav-link side" href="/techniques/T1039" id="v-Data from Network Shared Drive-collection-tab">
         Data from Network Shared Drive
        </a>
        <a aria-controls="v-Data from Removable Media-collection" aria-selected="false" class="nav-link side" href="/techniques/T1025" id="v-Data from Removable Media-collection-tab">
         Data from Removable Media
        </a>
        <a aria-controls="v-Data Staged-collection" aria-selected="false" class="nav-link side" href="/techniques/T1074" id="v-Data Staged-collection-tab">
         Data Staged
        </a>
        <a aria-controls="v-Email Collection-collection" aria-selected="false" class="nav-link side" href="/techniques/T1114" id="v-Email Collection-collection-tab">
         Email Collection
        </a>
        <a aria-controls="v-Input Capture-collection" aria-selected="false" class="nav-link side" href="/techniques/T1056" id="v-Input Capture-collection-tab">
         Input Capture
        </a>
        <a aria-controls="v-Man in the Browser-collection" aria-selected="false" class="nav-link side" href="/techniques/T1185" id="v-Man in the Browser-collection-tab">
         Man in the Browser
        </a>
        <a aria-controls="v-Screen Capture-collection" aria-selected="false" class="nav-link side" href="/techniques/T1113" id="v-Screen Capture-collection-tab">
         Screen Capture
        </a>
        <a aria-controls="v-Video Capture-collection" aria-selected="false" class="nav-link side" href="/techniques/T1125" id="v-Video Capture-collection-tab">
         Video Capture
        </a>
       </div>
      </div>
      <a aria-controls="exfiltration" aria-expanded="false" class="nav-link side expand-title" data-toggle="collapse" href="#exfiltration" id="v-exfiltration-tab" role="tab">
       <span id="exfiltration-tooltip" title="Exfiltration">
        Exfiltration
       </span>
       <span aria-hidden="true" class="glyphicon glyphicon-plus float-right expand-icon">
       </span>
      </a>
      <div aria-labelledby="v-exfiltration-tab" class="collapse" id="exfiltration">
       <div aria-orientation="vertical" class="nav flex-column nav pl-3" id="v-tab" role="tablist">
        <a aria-controls="v-Automated Exfiltration-exfiltration" aria-selected="false" class="nav-link side" href="/techniques/T1020" id="v-Automated Exfiltration-exfiltration-tab">
         Automated Exfiltration
        </a>
        <a aria-controls="v-Data Compressed-exfiltration" aria-selected="false" class="nav-link side" href="/techniques/T1002" id="v-Data Compressed-exfiltration-tab">
         Data Compressed
        </a>
        <a aria-controls="v-Data Encrypted-exfiltration" aria-selected="false" class="nav-link side" href="/techniques/T1022" id="v-Data Encrypted-exfiltration-tab">
         Data Encrypted
        </a>
        <a aria-controls="v-Data Transfer Size Limits-exfiltration" aria-selected="false" class="nav-link side" href="/techniques/T1030" id="v-Data Transfer Size Limits-exfiltration-tab">
         Data Transfer Size Limits
        </a>
        <a aria-controls="v-Exfiltration Over Alternative Protocol-exfiltration" aria-selected="false" class="nav-link side" href="/techniques/T1048" id="v-Exfiltration Over Alternative Protocol-exfiltration-tab">
         Exfiltration Over Alternative Protocol
        </a>
        <a aria-controls="v-Exfiltration Over Command and Control Channel-exfiltration" aria-selected="false" class="nav-link side" href="/techniques/T1041" id="v-Exfiltration Over Command and Control Channel-exfiltration-tab">
         Exfiltration Over Command and Control Channel
        </a>
        <a aria-controls="v-Exfiltration Over Other Network Medium-exfiltration" aria-selected="false" class="nav-link side" href="/techniques/T1011" id="v-Exfiltration Over Other Network Medium-exfiltration-tab">
         Exfiltration Over Other Network Medium
        </a>
        <a aria-controls="v-Exfiltration Over Physical Medium-exfiltration" aria-selected="false" class="nav-link side" href="/techniques/T1052" id="v-Exfiltration Over Physical Medium-exfiltration-tab">
         Exfiltration Over Physical Medium
        </a>
        <a aria-controls="v-Scheduled Transfer-exfiltration" aria-selected="false" class="nav-link side" href="/techniques/T1029" id="v-Scheduled Transfer-exfiltration-tab">
         Scheduled Transfer
        </a>
       </div>
      </div>
      <a aria-controls="command and control" aria-expanded="false" class="nav-link side expand-title" data-toggle="collapse" href="#command and control" id="v-command and control-tab" role="tab">
       <span id="command_and_control-tooltip" title="Command and Control">
        Command and Control
       </span>
       <span aria-hidden="true" class="glyphicon glyphicon-plus float-right expand-icon">
       </span>
      </a>
      <div aria-labelledby="v-command and control-tab" class="collapse" id="command and control">
       <div aria-orientation="vertical" class="nav flex-column nav pl-3" id="v-tab" role="tablist">
        <a aria-controls="v-Commonly Used Port-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1043" id="v-Commonly Used Port-command and control-tab">
         Commonly Used Port
        </a>
        <a aria-controls="v-Communication Through Removable Media-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1092" id="v-Communication Through Removable Media-command and control-tab">
         Communication Through Removable Media
        </a>
        <a aria-controls="v-Connection Proxy-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1090" id="v-Connection Proxy-command and control-tab">
         Connection Proxy
        </a>
        <a aria-controls="v-Custom Command and Control Protocol-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1094" id="v-Custom Command and Control Protocol-command and control-tab">
         Custom Command and Control Protocol
        </a>
        <a aria-controls="v-Custom Cryptographic Protocol-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1024" id="v-Custom Cryptographic Protocol-command and control-tab">
         Custom Cryptographic Protocol
        </a>
        <a aria-controls="v-Data Encoding-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1132" id="v-Data Encoding-command and control-tab">
         Data Encoding
        </a>
        <a aria-controls="v-Data Obfuscation-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1001" id="v-Data Obfuscation-command and control-tab">
         Data Obfuscation
        </a>
        <a aria-controls="v-Domain Fronting-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1172" id="v-Domain Fronting-command and control-tab">
         Domain Fronting
        </a>
        <a aria-controls="v-Fallback Channels-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1008" id="v-Fallback Channels-command and control-tab">
         Fallback Channels
        </a>
        <a aria-controls="v-Multi-hop Proxy-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1188" id="v-Multi-hop Proxy-command and control-tab">
         Multi-hop Proxy
        </a>
        <a aria-controls="v-Multi-Stage Channels-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1104" id="v-Multi-Stage Channels-command and control-tab">
         Multi-Stage Channels
        </a>
        <a aria-controls="v-Multiband Communication-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1026" id="v-Multiband Communication-command and control-tab">
         Multiband Communication
        </a>
        <a aria-controls="v-Multilayer Encryption-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1079" id="v-Multilayer Encryption-command and control-tab">
         Multilayer Encryption
        </a>
        <a aria-controls="v-Port Knocking-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1205" id="v-Port Knocking-command and control-tab">
         Port Knocking
        </a>
        <a aria-controls="v-Remote Access Tools-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1219" id="v-Remote Access Tools-command and control-tab">
         Remote Access Tools
        </a>
        <a aria-controls="v-Remote File Copy-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1105" id="v-Remote File Copy-command and control-tab">
         Remote File Copy
        </a>
        <a aria-controls="v-Standard Application Layer Protocol-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1071" id="v-Standard Application Layer Protocol-command and control-tab">
         Standard Application Layer Protocol
        </a>
        <a aria-controls="v-Standard Cryptographic Protocol-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1032" id="v-Standard Cryptographic Protocol-command and control-tab">
         Standard Cryptographic Protocol
        </a>
        <a aria-controls="v-Standard Non-Application Layer Protocol-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1095" id="v-Standard Non-Application Layer Protocol-command and control-tab">
         Standard Non-Application Layer Protocol
        </a>
        <a aria-controls="v-Uncommonly Used Port-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1065" id="v-Uncommonly Used Port-command and control-tab">
         Uncommonly Used Port
        </a>
        <a aria-controls="v-Web Service-command and control" aria-selected="false" class="nav-link side" href="/techniques/T1102" id="v-Web Service-command and control-tab">
         Web Service
        </a>
       </div>
      </div>
     </div>
     <!--startindex-->
     <div class="tab-content col-xl-10 col-lg-10 col-md-9 pt-4" id="v-tabContent">
      <div aria-labelledby="v-attckmatrix-tab" class="tab-pane fade show active" id="v-attckmatrix" role="tabpanel">
       <ol class="breadcrumb">
        <li class="breadcrumb-item">
         <a href="/">
          Home
         </a>
        </li>
        <li class="breadcrumb-item">
         <a href="/techniques/enterprise">
          Techniques
         </a>
        </li>
        <li class="breadcrumb-item">
         <a href="/techniques/enterprise">
          Enterprise
         </a>
        </li>
        <li class="breadcrumb-item">
         Drive-by Compromise
        </li>
       </ol>
       <div aria-labelledby="v--tab" class="tab-pane fade show active" id="v-" role="tabpanel">
       </div>
       <div class="row">
        <div class="col-xl-12">
         <div class="jumbotron jumbotron-fluid bg-white">
          <div class="container-fluid">
           <h1>
            Drive-by Compromise
           </h1>
           <div class="row">
            <div class="col-md-8 description-body">
             <p>
              A drive-by compromise is when an adversary gains access to a system through a user visiting a website over the normal course of browsing. With this technique, the user's web browser is targeted for exploitation. This can happen in several ways, but there are a few main components:
             </p>
             <p>
              Multiple ways of delivering exploit code to a browser exist, including:
             </p>
             <ul>
              <li>
               A legitimate website is compromised where adversaries have injected some form of malicious code such as JavaScript, iFrames, cross-site scripting.
              </li>
              <li>
               Malicious ads are paid for and served through legitimate ad providers.
              </li>
              <li>
               Built-in web application interfaces are leveraged for the insertion of any other kind of object that can be used to display web content or contain a script that executes on the visiting client (e.g. forum posts, comments, and other user controllable web content).
              </li>
             </ul>
             <p>
              Often the website used by an adversary is one visited by a specific community, such as government, a particular industry, or region, where the goal is to compromise a specific user or set of users based on a shared interest. This kind of targeted attack is referred to a strategic web compromise or watering hole attack. There are several known examples of this occurring.
              <span class="scite-citeref-number" data-reference="Shadowserver Strategic Web Compromise" id="scite-ref-1-a">
               <sup>
                <a aria-describedby="qtip-0" data-hasqtip="0" href="http://blog.shadowserver.org/2012/05/15/cyber-espionage-strategic-web-compromises-trusted-websites-serving-dangerous-results/" target="_blank">
                 [1]
                </a>
               </sup>
              </span>
             </p>
             <p>
              Typical drive-by compromise process:
             </p>
             <ol>
              <li>
               A user visits a website that is used to host the adversary controlled content.
              </li>
              <li>
               Scripts automatically execute, typically searching versions of the browser and plugins for a potentially vulnerable version.
               <ul>
                <li>
                 The user may be required to assist in this process by enabling scripting or active website components and ignoring warning dialog boxes.
                </li>
               </ul>
              </li>
              <li>
               Upon finding a vulnerable version, exploit code is delivered to the browser.
              </li>
              <li>
               If exploitation is successful, then it will give the adversary code execution on the user's system unless other protections are in place.
               <ul>
                <li>
                 In some cases a second visit to the website after the initial scan is required before exploit code is delivered.
                </li>
               </ul>
              </li>
             </ol>
             <p>
              Unlike
              <a href="/techniques/T1190">
               Exploit Public-Facing Application
              </a>
              , the focus of this technique is to exploit software on a client endpoint upon visiting a website. This will commonly give an adversary access to systems on the internal network instead of external systems that may be in a DMZ.
             </p>
            </div>
            <div class="col-md-4">
             <div class="card">
              <div class="card-body">
               <div class="card-data">
                <span class="h5 card-title">
                 ID
                </span>
                : T1189
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
                : Initial Access
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
                Packet capture, Network device logs, Process use of network, Web proxy, Network intrusion detection system, SSL/TLS inspection
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
               <a href="/groups/G0073">
                APT19
               </a>
              </td>
              <td>
               <p>
                <a href="/groups/G0073">
                 APT19
                </a>
                performed a watering hole attack on forbes.com in 2014 to compromise targets.
                <span class="scite-citeref-number" data-reference="Unit 42 C0d0so0 Jan 2016" id="scite-ref-2-a" onclick="scrollToRef('scite-2')">
                 <sup>
                  <a aria-describedby="qtip-1" data-hasqtip="1" href="https://researchcenter.paloaltonetworks.com/2016/01/new-attacks-linked-to-c0d0s0-group/" target="_blank">
                   [2]
                  </a>
                 </sup>
                </span>
               </p>
              </td>
             </tr>
<tr>
 <td>
  <a href="/groups/G0050">
   APT32
  </a>
 </td>
 <td>
  <p>
   <a href="/groups/G0050">
    APT32
   </a>
   has infected victims by tricking them into visiting compromised watering hole websites.
   <span class="scite-citeref-number" data-reference="ESET OceanLotus" id="scite-ref-3-a" onclick="scrollToRef('scite-3')">
    <sup>
     <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.welivesecurity.com/2018/03/13/oceanlotus-ships-new-backdoor/" target="_blank">
      [3]
     </a>
    </sup>
   </span>
  </p>
 </td>
</tr>
<tr>
 <td>
  <a href="/groups/G0067">
   APT37
  </a>
 </td>
 <td>
  <p>
   <a href="/groups/G0067">
    APT37
   </a>
   has used strategic web compromises, particularly of South Korean websites, to distribute malware. The group has also used torrent file-sharing sites to more indiscriminately disseminate malware to victims. As part of their compromises, the group has used a Javascript based profiler called RICECURRY to profile a victim's web browser and deliver malicious code accordingly.
   <span class="scite-citeref-number" data-reference="Securelist ScarCruft Jun 2016" id="scite-ref-4-a" onclick="scrollToRef('scite-4')">
    <sup>
     <a aria-describedby="qtip-3" data-hasqtip="3" href="https://securelist.com/operation-daybreak/75100/" target="_blank">
      [4]
     </a>
    </sup>
   </span>
   <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
    <sup>
     <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
      [5]
     </a>
    </sup>
   </span>
  </p>
 </td>
</tr>
<tr>
 <td>
  <a href="/groups/G0060">
   BRONZE BUTLER
  </a>
 </td>
 <td>
  <p>
   <a href="/groups/G0060">
    BRONZE BUTLER
   </a>
   compromised three Japanese websites using a Flash exploit to perform watering hole attacks.
   <span class="scite-citeref-number" data-reference="Symantec Tick Apr 2016" id="scite-ref-6-a" onclick="scrollToRef('scite-6')">
    <sup>
     <a aria-describedby="qtip-5" data-hasqtip="5" href="https://www.symantec.com/connect/blogs/tick-cyberespionage-group-zeros-japan" target="_blank">
      [6]
     </a>
    </sup>
   </span>
  </p>
 </td>
</tr>
<tr>
 <td>
  <a href="/groups/G0070">
   Dark Caracal
  </a>
 </td>
 <td>
  <p>
   <a href="/groups/G0070">
    Dark Caracal
   </a>
   leveraged a watering hole to serve up malicious code.
   <span class="scite-citeref-number" data-reference="Lookout Dark Caracal Jan 2018" id="scite-ref-7-a" onclick="scrollToRef('scite-7')">
    <sup>
     <a aria-describedby="qtip-6" data-hasqtip="6" href="https://info.lookout.com/rs/051-ESQ-475/images/Lookout_Dark-Caracal_srr_20180118_us_v.1.0.pdf" target="_blank">
      [7]
     </a>
    </sup>
   </span>
  </p>
 </td>
</tr>
<tr>
 <td>
  <a href="/groups/G0074">
   Dragonfly 2.0
  </a>
 </td>
 <td>
  <p>
   <a href="/groups/G0074">
    Dragonfly 2.0
   </a>
   compromised legitimate organizations' websites to create watering holes to compromise victims.
   <span class="scite-citeref-number" data-reference="US-CERT TA18-074A" id="scite-ref-8-a" onclick="scrollToRef('scite-8')">
    <sup>
     <a aria-describedby="qtip-7" data-hasqtip="7" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" target="_blank">
      [8]
     </a>
    </sup>
   </span>
  </p>
 </td>
</tr>
<tr>
 <td>
  <a href="/groups/G0066">
   Elderwood
  </a>
 </td>
 <td>
  <p>
   <a href="/groups/G0066">
    Elderwood
   </a>
   has delivered zero-day exploits and malware to victims by injecting malicious code into specific public Web pages visited by targets within a particular sector.
   <span class="scite-citeref-number" data-reference="Symantec Elderwood Sept 2012" id="scite-ref-9-a" onclick="scrollToRef('scite-9')">
    <sup>
     <a aria-describedby="qtip-8" data-hasqtip="8" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/the-elderwood-project.pdf" target="_blank">
      [9]
     </a>
    </sup>
   </span>
   <span class="scite-citeref-number" data-reference="CSM Elderwood Sept 2012" id="scite-ref-10-a" onclick="scrollToRef('scite-10')">
    <sup>
     <a aria-describedby="qtip-9" data-hasqtip="9" href="https://www.csmonitor.com/USA/2012/0914/Stealing-US-business-secrets-Experts-ID-two-huge-cyber-gangs-in-China" target="_blank">
      [10]
     </a>
    </sup>
   </span>
   <span class="scite-citeref-number" data-reference="Security Affairs Elderwood Sept 2012" id="scite-ref-11-a" onclick="scrollToRef('scite-11')">
    <sup>
     <a aria-describedby="qtip-10" data-hasqtip="10" href="http://securityaffairs.co/wordpress/8528/hacking/elderwood-project-who-is-behind-op-aurora-and-ongoing-attacks.html" target="_blank">
      [11]
     </a>
    </sup>
   </span>
  </p>
 </td>
</tr>
<tr>
 <td>
  <a href="/software/S0215">
   KARAE
  </a>
 </td>
 <td>
  <p>
   <a href="/software/S0215">
    KARAE
   </a>
   was distributed through torrent file-sharing websites to South Korean victims, using a YouTube video downloader application as a lure.
   <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
    <sup>
     <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
      [5]
     </a>
    </sup>
   </span>
  </p>
 </td>
</tr>
<tr>
 <td>
  <a href="/groups/G0032">
   Lazarus Group
  </a>
 </td>
 <td>
  <p>
   <a href="/groups/G0032">
    Lazarus Group
   </a>
   delivered
   <a href="/software/S0241">
    RATANKBA
   </a>
   to victims via a compromised legitimate website.
   <span class="scite-citeref-number" data-reference="RATANKBA" id="scite-ref-12-a" onclick="scrollToRef('scite-12')">
    <sup>
     <a aria-describedby="qtip-11" data-hasqtip="11" href="https://blog.trendmicro.com/trendlabs-security-intelligence/ratankba-watering-holes-against-enterprises/" target="_blank">
      [12]
     </a>
    </sup>
   </span>
  </p>
 </td>
</tr>
<tr>
 <td>
  <a href="/groups/G0077">
   Leafminer
  </a>
 </td>
 <td>
  <p>
   <a href="/groups/G0077">
    Leafminer
   </a>
   has infected victims using watering holes.
   <span class="scite-citeref-number" data-reference="Symantec Leafminer July 2018" id="scite-ref-13-a" onclick="scrollToRef('scite-13')">
    <sup>
     <a aria-describedby="qtip-12" data-hasqtip="12" href="https://www.symantec.com/blogs/threat-intelligence/leafminer-espionage-middle-east" target="_blank">
      [13]
     </a>
    </sup>
   </span>
  </p>
 </td>
</tr>
<tr>
 <td>
  <a href="/groups/G0040">
   Patchwork
  </a>
 </td>
 <td>
  <p>
   <a href="/groups/G0040">
    Patchwork
   </a>
   has used watering holes to deliver files with exploits to initial victims.
   <span class="scite-citeref-number" data-reference="Symantec Patchwork" id="scite-ref-14-a" onclick="scrollToRef('scite-14')">
    <sup>
     <a aria-describedby="qtip-13" data-hasqtip="13" href="http://www.symantec.com/connect/blogs/patchwork-cyberespionage-group-expands-targets-governments-wide-range-industries" target="_blank">
      [14]
     </a>
    </sup>
   </span>
   <span class="scite-citeref-number" data-reference="Volexity Patchwork June 2018" id="scite-ref-15-a" onclick="scrollToRef('scite-15')">
    <sup>
     <a aria-describedby="qtip-14" data-hasqtip="14" href="https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/" target="_blank">
      [15]
     </a>
    </sup>
   </span>
  </p>
 </td>
</tr>
<tr>
 <td>
  <a href="/groups/G0068">
   PLATINUM
  </a>
 </td>
 <td>
  <p>
   <a href="/groups/G0068">
    PLATINUM
   </a>
   has sometimes used drive-by attacks against vulnerable browser plugins.
   <span class="scite-citeref-number" data-reference="Microsoft PLATINUM April 2016" id="scite-ref-16-a" onclick="scrollToRef('scite-16')">
    <sup>
     <a aria-describedby="qtip-15" data-hasqtip="15" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" target="_blank">
      [16]
     </a>
    </sup>
   </span>
  </p>
 </td>
</tr>
<tr>
 <td>
  <a href="/software/S0216">
   POORAIM
  </a>
 </td>
 <td>
  <p>
   <a href="/software/S0216">
    POORAIM
   </a>
   has been delivered through compromised sites acting as watering holes.
   <span class="scite-citeref-number" data-reference="FireEye APT37 Feb 2018" id="scite-ref-5-a" onclick="scrollToRef('scite-5')">
    <sup>
     <a aria-describedby="qtip-4" data-hasqtip="4" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" target="_blank">
      [5]
     </a>
    </sup>
   </span>
  </p>
 </td>
</tr>
<tr>
 <td>
  <a href="/groups/G0027">
   Threat Group-3390
  </a>
 </td>
 <td>
  <p>
   <a href="/groups/G0027">
    Threat Group-3390
   </a>
   has has extensively used strategic Web compromises to target victims.
   <span class="scite-citeref-number" data-reference="Dell TG-3390" id="scite-ref-17-a" onclick="scrollToRef('scite-17')">
    <sup>
     <a aria-describedby="qtip-16" data-hasqtip="16" href="https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage" target="_blank">
      [17]
     </a>
    </sup>
   </span>
   <span class="scite-citeref-number" data-reference="Securelist LuckyMouse June 2018" id="scite-ref-18-a" onclick="scrollToRef('scite-18')">
    <sup>
     <a aria-describedby="qtip-17" data-hasqtip="17" href="https://securelist.com/luckymouse-hits-national-data-center/86083/" target="_blank">
      [18]
     </a>
    </sup>
   </span>
  </p>
 </td>
</tr>
<h2 class="pt-3" id="mitigation">
 Mitigation
</h2>
<p>
 Drive-by compromise relies on there being a vulnerable piece of software on the client end systems. Use modern browsers with security features turned on. Ensure all browsers and plugins kept updated can help prevent the exploit phase of this technique.
</p>
<p>
 For malicious code served up through ads, adblockers can help prevent that code from executing in the first place. Script blocking extensions can help prevent the execution of JavaScript that may commonly be used during the exploitation process.
</p>
<p>
 Browser sandboxes can be used to mitigate some of the impact of exploitation, but sandbox escapes may still exist.
 <span class="scite-citeref-number" data-reference="Windows Blogs Microsoft Edge Sandbox" id="scite-ref-19-a">
  <sup>
   <a aria-describedby="qtip-18" data-hasqtip="18" href="https://blogs.windows.com/msedgedev/2017/03/23/strengthening-microsoft-edge-sandbox/" target="_blank">
    [19]
   </a>
  </sup>
 </span>
 <span class="scite-citeref-number" data-reference="Ars Technica Pwn2Own 2017 VM Escape" id="scite-ref-20-a">
  <sup>
   <a aria-describedby="qtip-19" data-hasqtip="19" href="https://arstechnica.com/information-technology/2017/03/hack-that-escapes-vm-by-exploiting-edge-browser-fetches-105000-at-pwn2own/" target="_blank">
    [20]
   </a>
  </sup>
 </span>
</p>
<p>
 Other types of virtualization and application microsegmentation may also mitigate the impact of client-side exploitation. The risks of additional exploits and weaknesses in implementation may still exist.
 <span class="scite-citeref-number" data-reference="Ars Technica Pwn2Own 2017 VM Escape" id="scite-ref-20-a">
  <sup>
   <a aria-describedby="qtip-19" data-hasqtip="19" href="https://arstechnica.com/information-technology/2017/03/hack-that-escapes-vm-by-exploiting-edge-browser-fetches-105000-at-pwn2own/" target="_blank">
    [20]
   </a>
  </sup>
 </span>
</p>
<p>
 Security applications that look for behavior used during exploitation such as Windows Defender Exploit Guard (WDEG) and the Enhanced Mitigation Experience Toolkit (EMET) can be used to mitigate some exploitation behavior.
 <span class="scite-citeref-number" data-reference="TechNet Moving Beyond EMET" id="scite-ref-21-a">
  <sup>
   <a aria-describedby="qtip-20" data-hasqtip="20" href="https://blogs.technet.microsoft.com/srd/2017/08/09/moving-beyond-emet-ii-windows-defender-exploit-guard/" target="_blank">
    [21]
   </a>
  </sup>
 </span>
 Control flow integrity checking is another way to potentially identify and stop a software exploit from occurring.
 <span class="scite-citeref-number" data-reference="Wikipedia Control Flow Integrity" id="scite-ref-22-a">
  <sup>
   <a aria-describedby="qtip-21" data-hasqtip="21" href="https://en.wikipedia.org/wiki/Control-flow_integrity" target="_blank">
    [22]
   </a>
  </sup>
 </span>
 Many of these protections depend on the architecture and target application binary for compatibility.
</p>
<h2 class="pt-3" id="detection">
 Detection
</h2>
<p>
 Firewalls and proxies can inspect URLs for potentially known-bad domains or parameters. They can also do reputation-based analytics on websites and their requested resources such as how old a domain is, who it's registered to, if it's on a known bad list, or how many other users have connected to it before.
</p>
<p>
 Network intrusion detection systems, sometimes with SSL/TLS MITM inspection, can be used to look for known malicious scripts (recon, heap spray, and browser identification scripts have been frequently reused), common script obfuscation, and exploit code.
</p>
<p>
 Detecting compromise based on the drive-by exploit from a legitimate website may be difficult. Also look for behavior on the endpoint system that might indicate successful compromise, such as abnormal behavior of browser processes. This could include suspicious files written to disk, evidence of
 <a href="/techniques/T1055">
  Process Injection
 </a>
 for attempts to hide execution, evidence of Discovery, or other unusual network traffic that may indicate additional tools transferred to the system.
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
      <a class="external text" href="http://blog.shadowserver.org/2012/05/15/cyber-espionage-strategic-web-compromises-trusted-websites-serving-dangerous-results/" name="scite-1" rel="nofollow" target="_blank">
       Adair, S., Moran, N. (2012, May 15). Cyber Espionage &amp; Strategic Web Compromises – Trusted Websites Serving Dangerous Results. Retrieved March 13, 2018.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-2">
     <span class="scite-citation-text">
      <a class="external text" href="https://researchcenter.paloaltonetworks.com/2016/01/new-attacks-linked-to-c0d0s0-group/" name="scite-2" rel="nofollow" target="_blank">
       Grunzweig, J., Lee, B. (2016, January 22). New Attacks Linked to C0d0so0 Group. Retrieved August 2, 2018.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-3">
     <span class="scite-citation-text">
      <a class="external text" href="https://www.welivesecurity.com/2018/03/13/oceanlotus-ships-new-backdoor/" name="scite-3" rel="nofollow" target="_blank">
       Foltýn, T. (2018, March 13). OceanLotus ships new backdoor using old tricks. Retrieved May 22, 2018.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-4">
     <span class="scite-citation-text">
      <a class="external text" href="https://securelist.com/operation-daybreak/75100/" name="scite-4" rel="nofollow" target="_blank">
       Raiu, C., and Ivanov, A. (2016, June 17). Operation Daybreak. Retrieved February 15, 2018.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-5">
     <span class="scite-citation-text">
      <a class="external text" href="https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf" name="scite-5" rel="nofollow" target="_blank">
       FireEye. (2018, February 20). APT37 (Reaper): The Overlooked North Korean Actor. Retrieved March 1, 2018.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-6">
     <span class="scite-citation-text">
      <a class="external text" href="https://www.symantec.com/connect/blogs/tick-cyberespionage-group-zeros-japan" name="scite-6" rel="nofollow" target="_blank">
       DiMaggio, J. (2016, April 28). Tick cyberespionage group zeros in on Japan. Retrieved July 16, 2018.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-7">
     <span class="scite-citation-text">
      <a class="external text" href="https://info.lookout.com/rs/051-ESQ-475/images/Lookout_Dark-Caracal_srr_20180118_us_v.1.0.pdf" name="scite-7" rel="nofollow" target="_blank">
       Blaich, A., et al. (2018, January 18). Dark Caracal: Cyber-espionage at a Global Scale. Retrieved April 11, 2018.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-8">
     <span class="scite-citation-text">
      <a class="external text" href="https://www.us-cert.gov/ncas/alerts/TA18-074A" name="scite-8" rel="nofollow" target="_blank">
       US-CERT. (2018, March 16). Alert (TA18-074A): Russian Government Cyber Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved June 6, 2018.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-9">
     <span class="scite-citation-text">
      <a class="external text" href="http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/the-elderwood-project.pdf" name="scite-9" rel="nofollow" target="_blank">
       O'Gorman, G., and McDonald, G.. (2012, September 6). The Elderwood Project. Retrieved February 15, 2018.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-10">
     <span class="scite-citation-text">
      <a class="external text" href="https://www.csmonitor.com/USA/2012/0914/Stealing-US-business-secrets-Experts-ID-two-huge-cyber-gangs-in-China" name="scite-10" rel="nofollow" target="_blank">
       Clayton, M.. (2012, September 14). Stealing US business secrets: Experts ID two huge cyber 'gangs' in China. Retrieved February 15, 2018.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-11">
     <span class="scite-citation-text">
      <a class="external text" href="http://securityaffairs.co/wordpress/8528/hacking/elderwood-project-who-is-behind-op-aurora-and-ongoing-attacks.html" name="scite-11" rel="nofollow" target="_blank">
       Paganini, P. (2012, September 9). Elderwood project, who is behind Op. Aurora and ongoing attacks?. Retrieved February 13, 2018.
      </a>
     </span>
    </span>
   </li>
  </ol>
 </div>
 <div class="col">
  <ol start="12.0">
   <li>
    <span class="scite-citation" id="scite-12">
     <span class="scite-citation-text">
      <a class="external text" href="https://blog.trendmicro.com/trendlabs-security-intelligence/ratankba-watering-holes-against-enterprises/" name="scite-12" rel="nofollow" target="_blank">
       Trend Micro. (2017, February 27). RATANKBA: Delving into Large-scale Watering Holes against Enterprises. Retrieved May 22, 2018.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-13">
     <span class="scite-citation-text">
      <a class="external text" href="https://www.symantec.com/blogs/threat-intelligence/leafminer-espionage-middle-east" name="scite-13" rel="nofollow" target="_blank">
       Symantec Security Response. (2018, July 25). Leafminer: New Espionage Campaigns Targeting Middle Eastern Regions. Retrieved August 28, 2018.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-14">
     <span class="scite-citation-text">
      <a class="external text" href="http://www.symantec.com/connect/blogs/patchwork-cyberespionage-group-expands-targets-governments-wide-range-industries" name="scite-14" rel="nofollow" target="_blank">
       Hamada, J.. (2016, July 25). Patchwork cyberespionage group expands targets from governments to wide range of industries. Retrieved August 17, 2016.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-15">
     <span class="scite-citation-text">
      <a class="external text" href="https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/" name="scite-15" rel="nofollow" target="_blank">
       Meltzer, M, et al. (2018, June 07). Patchwork APT Group Targets US Think Tanks. Retrieved July 16, 2018.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-16">
     <span class="scite-citation-text">
      <a class="external text" href="https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf" name="scite-16" rel="nofollow" target="_blank">
       Windows Defender Advanced Threat Hunting Team. (2016, April 29). PLATINUM: Targeted attacks in South and Southeast Asia. Retrieved February 15, 2018.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-17">
     <span class="scite-citation-text">
      <a class="external text" href="https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage" name="scite-17" rel="nofollow" target="_blank">
       Dell SecureWorks Counter Threat Unit Threat Intelligence. (2015, August 5). Threat Group-3390 Targets Organizations for Cyberespionage. Retrieved August 18, 2018.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-18">
     <span class="scite-citation-text">
      <a class="external text" href="https://securelist.com/luckymouse-hits-national-data-center/86083/" name="scite-18" rel="nofollow" target="_blank">
       Legezo, D. (2018, June 13). LuckyMouse hits national data center to organize country-level waterholing campaign. Retrieved August 18, 2018.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-19">
     <span class="scite-citation-text">
      <a class="external text" href="https://blogs.windows.com/msedgedev/2017/03/23/strengthening-microsoft-edge-sandbox/" name="scite-19" rel="nofollow" target="_blank">
       Cowan, C. (2017, March 23). Strengthening the Microsoft Edge Sandbox. Retrieved March 12, 2018.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-20">
     <span class="scite-citation-text">
      <a class="external text" href="https://arstechnica.com/information-technology/2017/03/hack-that-escapes-vm-by-exploiting-edge-browser-fetches-105000-at-pwn2own/" name="scite-20" rel="nofollow" target="_blank">
       Goodin, D. (2017, March 17). Virtual machine escape fetches $105,000 at Pwn2Own hacking contest - updated. Retrieved March 12, 2018.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-21">
     <span class="scite-citation-text">
      <a class="external text" href="https://blogs.technet.microsoft.com/srd/2017/08/09/moving-beyond-emet-ii-windows-defender-exploit-guard/" name="scite-21" rel="nofollow" target="_blank">
       Nunez, N. (2017, August 9). Moving Beyond EMET II – Windows Defender Exploit Guard. Retrieved March 12, 2018.
      </a>
     </span>
    </span>
   </li>
   <li>
    <span class="scite-citation" id="scite-22">
     <span class="scite-citation-text">
      <a class="external text" href="https://en.wikipedia.org/wiki/Control-flow_integrity" name="scite-22" rel="nofollow" target="_blank">
       Wikipedia. (2018, January 11). Control-flow integrity. Retrieved March 12, 2018.
      </a>
     </span>
    </span>
   </li>
  </ol>
 </div>
</div>
<!-- <div class="col-xl-2 col-lg-2 col-md-0 d-block d-sm-none d-md-none d-lg-block">
      <p>Content</p>
      <div><a href="#description">Description</a></div>
      <div><a href="#examples">Examples</a></div>
      <div><a href="#techniques"></a></div>
      <div><a href="#mitigation">Mitigation</a></div>
      <div><a href="#detection">Detection</a></div>
      <div><a href="#detectable"></a></div>
      <div><a href="#difficulty"></a></div>
      <div><a href="#references">References</a></div>
   </div> -->
<!--stopindex-->
<footer class="footer pt-3 pb-2">
 <div class="container-fluid text-center">
  <a aria-label="Twitter" class="btn btn-primary float-right mr-4" href="https://twitter.com/MITREattack" rel="noopener" target="_blank">
   <img class="mx-auto d-block" height="28" src="/theme/images/twitter.png" width="28"/>
   Follow us!
  </a>
  <a aria-label="MITRE" class="float-left ml-4" href="https://www.mitre.org" rel="noopener" target="_blank">
   <img height="66" src="/theme/images/mitrelogowhiteontrans.gif" width="144"/>
  </a>
  <br>
   <p>
    <br>
     Copyright © 2018, The MITRE Corporation. MITRE ATT&amp;CK and ATT&amp;CK are trademarks of The MITRE
            Corporation.
    </br>
   </p>
   <small>
    <a class="footer-link" href="/resources/privacy">
     Privacy Policy
    </a>
    <a class="footer-link" href="/resources/terms-of-use">
     Terms of Use
    </a>
   </small>
  </br>
 </div>
</footer>
<!--SCRIPTS-->
<script src="/theme/scripts/jquery-3.2.1.min.js">
</script>
<script src="/theme/scripts/popper.min.js">
</script>
<script src="/theme/scripts/bootstrap.min.js">
</script>
<script src="/theme/scripts/site.js">
</script>
<script src="/theme/scripts/lunr-2.3.3.js">
</script>
<script src="/theme/scripts/search.js">
</script>
<script src="/theme/scripts/index.js">
</script>
<!--SCRIPTS-->
<script src="/theme/scripts/techniques.js">
</script>
<!--startindex-->
