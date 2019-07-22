<div class="Box-body readme blob instapaper_body js-code-block-container" id="readme">
    <article class="markdown-body entry-content p-3 p-md-6" itemprop="text"><h1><a aria-hidden="true" class="anchor" href="#t1112---modify-registry" id="user-content-t1112---modify-registry"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>T1112 - Modify Registry</h1>
<h2><a aria-hidden="true" class="anchor" href="#description-from-attck" id="user-content-description-from-attck"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a><a href="https://attack.mitre.org/wiki/Technique/T1112" rel="nofollow">Description from ATT&amp;CK</a></h2>
<blockquote>Adversaries may interact with the Windows Registry to hide configuration information within Registry keys, remove information as part of cleaning up, or as part of other techniques to aid in Persistence and Execution.
<p>Access to specific areas of the Registry depends on account permissions, some requiring administrator-level access. The built-in Windows command-line utility <a href="https://attack.mitre.org/software/S0075" rel="nofollow">Reg</a> may be used for local or remote Registry modification. (Citation: Microsoft Reg) Other tools may also be used, such as a remote access tool, which may contain functionality to interact with the Registry through the Windows API (see examples).</p>
<p>Registry modifications may also include actions to hide keys, such as prepending key names with a null character, which will cause an error and/or be ignored when read via <a href="https://attack.mitre.org/software/S0075" rel="nofollow">Reg</a> or other utilities using the Win32 API. (Citation: Microsoft Reghide NOV 2006) Adversaries may abuse these pseudo-hidden keys to conceal payloads/commands used to establish Persistence. (Citation: TrendMicro POWELIKS AUG 2014) (Citation: SpectorOps Hiding Reg Jul 2017)</p>
<p>The Registry of a remote system may be modified to aid in execution of files as part of Lateral Movement. It requires the remote Registry service to be running on the target system. (Citation: Microsoft Remote) Often <a href="https://attack.mitre.org/techniques/T1078" rel="nofollow">Valid Accounts</a> are required, along with access to the remote system's <a href="https://attack.mitre.org/techniques/T1077" rel="nofollow">Windows Admin Shares</a> for RPC communication.</p></blockquote><p></p>
<h2><a aria-hidden="true" class="anchor" href="#atomic-tests" id="user-content-atomic-tests"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Atomic Tests</h2>
<ul>
<li>
<p><a href="#atomic-test-1---modify-registry-of-current-user-profile---cmd">Atomic Test #1 - Modify Registry of Current User Profile - cmd</a></p>
</li>
<li>
<p><a href="#atomic-test-2---modify-registry-of-local-machine---cmd">Atomic Test #2 - Modify Registry of Local Machine - cmd</a></p>
</li>
<li>
<p><a href="#atomic-test-3---modify-registry-of-another-user-profile">Atomic Test #3 - Modify Registry of Another User Profile</a></p>
</li>
</ul>
<br/>
<h2><a aria-hidden="true" class="anchor" href="#atomic-test-1---modify-registry-of-current-user-profile---cmd" id="user-content-atomic-test-1---modify-registry-of-current-user-profile---cmd"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Atomic Test #1 - Modify Registry of Current User Profile - cmd</h2>
<p>Modify the registry of the currently logged in user using reg.exe cia cmd console</p>
<p><strong>Supported Platforms:</strong> Windows</p>
<h4><a aria-hidden="true" class="anchor" href="#run-it-with-command_prompt" id="user-content-run-it-with-command_prompt"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Run it with <code>command_prompt</code>!</h4>
<pre><code>reg add HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced /t REG_DWORD /v HideFileExt /d 1 /f
</code></pre>
<br/>
<br/>
<h2><a aria-hidden="true" class="anchor" href="#atomic-test-2---modify-registry-of-local-machine---cmd" id="user-content-atomic-test-2---modify-registry-of-local-machine---cmd"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Atomic Test #2 - Modify Registry of Local Machine - cmd</h2>
<p>Modify the Local Machine registry RUN key to change Windows Defender executable that should be ran on startup.  This should only be possible when
CMD is ran as Administrative rights.</p>
<p><strong>Supported Platforms:</strong> Windows</p>
<h4><a aria-hidden="true" class="anchor" href="#run-it-with-command_prompt-1" id="user-content-run-it-with-command_prompt-1"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Run it with <code>command_prompt</code>!</h4>
<pre><code>reg add HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run /t REG_EXPAND_SZ /v SecurityHealth /d {some_other_executable} /f
</code></pre>
<br/>
<br/>
<h2><a aria-hidden="true" class="anchor" href="#atomic-test-3---modify-registry-of-another-user-profile" id="user-content-atomic-test-3---modify-registry-of-another-user-profile"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Atomic Test #3 - Modify Registry of Another User Profile</h2>
<p>Modify a registry key of each user profile not currently loaded on the machine using both powershell and cmd line tools.</p>
<p><strong>Supported Platforms:</strong> Windows</p>
<h4><a aria-hidden="true" class="anchor" href="#run-it-with-powershell" id="user-content-run-it-with-powershell"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Run it with <code>powershell</code>!</h4>
<pre><code># here is an example of using the same method of reg load, but without the New-PSDrive cmdlet.
# Here we can load all unloaded user hives and do whatever we want in the location below (comments)
$PatternSID = 'S-1-5-21-\d+-\d+\-\d+\-\d+$'

Write-Verbose -Message 'Gathering Profile List and loading their registry hives'
# Get Username, SID, and location of ntuser.dat for all users

$ProfileList = @()
$ProfileList = Get-ItemProperty 'HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList\*' | Where-Object { $_.PSChildName -match $PatternSID } |
  Select  @{ name = "SID"; expression = { $_.PSChildName } },
          @{ name = "UserHive"; expression = { "$($_.ProfileImagePath)\ntuser.dat" } },
          @{ name = "Username"; expression = { $_.ProfileImagePath -replace '^(.*[\\\/])', '' } }
  
# Get all user SIDs found in HKEY_USERS (ntuder.dat files that are loaded)
$LoadedHives = Get-ChildItem Registry::HKEY_USERS | ? { $_.PSChildname -match $PatternSID } | Select @{ name = "SID"; expression = { $_.PSChildName } }
      
$SIDObject = @()
  
foreach ($item in $LoadedHives)
{
    $props = @{
        SID = $item.SID
    }

    $TempSIDObject = New-Object -TypeName PSCustomObject -Property $props
    $SIDObject += $TempSIDObject
}

# We need to use ($ProfileList | Measure-Object).count instead of just ($ProfileList).count because in PS V2
# if the count is less than 2 it doesn't work. :)
for ($p = 0; $p -lt ($ProfileList | Measure-Object).count; $p++)
{
    for ($l = 0; $l -lt ($SIDObject | Measure-Object).count; $l++)
    {
        if (($ProfileList[$p].SID) -ne ($SIDObject[$l].SID))
        {
            $UnloadedHives += $ProfileList[$p].SID
            Write-Verbose -Message "Loading Registry hives for $($ProfileList[$p].SID)"
            reg load "HKU\$($ProfileList[$p].SID)" "$($ProfileList[$p].UserHive)"

            Write-Verbose -Message 'Attempting to modify registry keys for each profile'
            #####################################################################
            reg add "HKEY_CURRENT_USER\$($ProfileList[$p].SID)\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced" /t REG_DWORD /v HideFileExt /d 1 /f
    }
}

Write-Verbose 'Unloading Registry hives for all users'
# Unload ntuser.dat        
### Garbage collection and closing of ntuser.dat ###
[gc]::Collect()
reg unload "HKU\$($ProfileList[$p].SID)"
</code></pre>
<br/>
</article>
  </div>