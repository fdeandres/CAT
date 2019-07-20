<div class="Box-body readme blob instapaper_body js-code-block-container" id="readme">
    <article class="markdown-body entry-content p-3 p-md-6" itemprop="text"><h1><a aria-hidden="true" class="anchor" href="#t1134---access-token-manipulation" id="user-content-t1134---access-token-manipulation"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>T1134 - Access Token Manipulation</h1>
<h2><a aria-hidden="true" class="anchor" href="#description-from-attck" id="user-content-description-from-attck"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a><a href="https://attack.mitre.org/wiki/Technique/T1134" rel="nofollow">Description from ATT&amp;CK</a></h2>
<blockquote>Windows uses access tokens to determine the ownership of a running process. A user can manipulate access tokens to make a running process appear as though it belongs to someone other than the user that started the process. When this occurs, the process also takes on the security context associated with the new token. For example, Microsoft promotes the use of access tokens as a security best practice. Administrators should log in as a standard user but run their tools with administrator privileges using the built-in access token manipulation command <code>runas</code>. (Citation: Microsoft runas)
<p>Adversaries may use access tokens to operate under a different user or system security context to perform actions and evade detection. An adversary can use built-in Windows API functions to copy access tokens from existing processes; this is known as token stealing. An adversary must already be in a privileged user context (i.e. administrator) to steal a token. However, adversaries commonly use token stealing to elevate their security context from the administrator level to the SYSTEM level. An adversary can use a token to authenticate to a remote system as the account for that token if the account has appropriate permissions on the remote system. (Citation: Pentestlab Token Manipulation)</p>
<p>Access tokens can be leveraged by adversaries through three methods: (Citation: BlackHat Atkinson Winchester Token Manipulation)</p>
<p><strong>Token Impersonation/Theft</strong> - An adversary creates a new access token that duplicates an existing token using <code>DuplicateToken(Ex)</code>. The token can then be used with <code>ImpersonateLoggedOnUser</code> to allow the calling thread to impersonate a logged on user's security context, or with <code>SetThreadToken</code> to assign the impersonated token to a thread. This is useful for when the target user has a non-network logon session on the system.</p>
<p><strong>Create Process with a Token</strong> - An adversary creates a new access token with <code>DuplicateToken(Ex)</code> and uses it with <code>CreateProcessWithTokenW</code> to create a new process running under the security context of the impersonated user. This is useful for creating a new process under the security context of a different user.</p>
<p><strong>Make and Impersonate Token</strong> - An adversary has a username and password but the user is not logged onto the system. The adversary can then create a logon session for the user using the <code>LogonUser</code> function. The function will return a copy of the new session's access token and the adversary can use <code>SetThreadToken</code> to assign the token to a thread.</p>
<p>Any standard user can use the <code>runas</code> command, and the Windows API functions, to create impersonation tokens; it does not require access to an administrator account.</p>
<p>Metasploit’s Meterpreter payload allows arbitrary token manipulation and uses token impersonation to escalate privileges. (Citation: Metasploit access token)  The Cobalt Strike beacon payload allows arbitrary token impersonation and can also create tokens. (Citation: Cobalt Strike Access Token)</p></blockquote><p></p>
<h2><a aria-hidden="true" class="anchor" href="#atomic-tests" id="user-content-atomic-tests"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Atomic Tests</h2>
<ul>
<li><a href="#atomic-test-1---access-token-manipulation">Atomic Test #1 - Access Token Manipulation</a></li>
</ul>
<br/>
<h2><a aria-hidden="true" class="anchor" href="#atomic-test-1---access-token-manipulation" id="user-content-atomic-test-1---access-token-manipulation"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Atomic Test #1 - Access Token Manipulation</h2>
<p>Creates a process as another user
Requires Administrator Privileges To Execute Test</p>
<p><strong>Supported Platforms:</strong> Windows</p>
<h4><a aria-hidden="true" class="anchor" href="#inputs" id="user-content-inputs"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Inputs</h4>
<table>
<thead>
<tr>
<th>Name</th>
<th>Description</th>
<th>Type</th>
<th>Default Value</th>
</tr>
</thead>
<tbody>
<tr>
<td>target_user</td>
<td>Username To Steal Token From</td>
<td>String</td>
<td>SYSTEM</td>
</tr>
</tbody>
</table>
<h4><a aria-hidden="true" class="anchor" href="#run-it-with-powershell" id="user-content-run-it-with-powershell"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Run it with <code>powershell</code>!</h4>
<pre><code>#list processes by user,

$owners = @{}
gwmi win32_process |% {$owners[$_.handle] = $_.getowner().user}
get-process | select processname,Id,@{l="Owner";e={$owners[$_.id.tostring()]}}
#Steal Token
. .\src\T1134.ps1
</code></pre>
<br/>
</article>
  </div>