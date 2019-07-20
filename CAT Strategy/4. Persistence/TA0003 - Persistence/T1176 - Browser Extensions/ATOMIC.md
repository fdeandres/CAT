<div class="Box-body readme blob instapaper_body js-code-block-container" id="readme">
    <article class="markdown-body entry-content p-3 p-md-6" itemprop="text"><h1><a aria-hidden="true" class="anchor" href="#t1176---browser-extensions" id="user-content-t1176---browser-extensions"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>T1176 - Browser Extensions</h1>
<h2><a aria-hidden="true" class="anchor" href="#description-from-attck" id="user-content-description-from-attck"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a><a href="https://attack.mitre.org/wiki/Technique/T1176" rel="nofollow">Description from ATT&amp;CK</a></h2>
<blockquote>Browser extensions or plugins are small programs that can add functionality and customize aspects of internet browsers. They can be installed directly or through a browser's app store. Extensions generally have access and permissions to everything that the browser can access. (Citation: Wikipedia Browser Extension) (Citation: Chrome Extensions Definition)
<p>Malicious extensions can be installed into a browser through malicious app store downloads masquerading as legitimate extensions, through social engineering, or by an adversary that has already compromised a system. Security can be limited on browser app stores so may not be difficult for malicious extensions to defeat automated scanners and be uploaded. (Citation: Malicious Chrome Extension Numbers) Once the extension is installed, it can browse to websites in the background, (Citation: Chrome Extension Crypto Miner) (Citation: ICEBRG Chrome Extensions) steal all information that a user enters into a browser, to include credentials, (Citation: Banker Google Chrome Extension Steals Creds) (Citation: Catch All Chrome Extension) and be used as an installer for a RAT for persistence. There have been instances of botnets using a persistent backdoor through malicious Chrome extensions. (Citation: Stantinko Botnet) There have also been similar examples of extensions being used for command &amp; control  (Citation: Chrome Extension C2 Malware).</p></blockquote><p></p>
<h2><a aria-hidden="true" class="anchor" href="#atomic-tests" id="user-content-atomic-tests"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Atomic Tests</h2>
<ul>
<li>
<p><a href="#atomic-test-1---chrome-developer-mode">Atomic Test #1 - Chrome (Developer Mode)</a></p>
</li>
<li>
<p><a href="#atomic-test-2---chrome-chrome-web-store">Atomic Test #2 - Chrome (Chrome Web Store)</a></p>
</li>
<li>
<p><a href="#atomic-test-3---firefox">Atomic Test #3 - Firefox</a></p>
</li>
</ul>
<br/>
<h2><a aria-hidden="true" class="anchor" href="#atomic-test-1---chrome-developer-mode" id="user-content-atomic-test-1---chrome-developer-mode"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Atomic Test #1 - Chrome (Developer Mode)</h2>
<p>xxx</p>
<p><strong>Supported Platforms:</strong> Linux, Windows, macOS</p>
<h4><a aria-hidden="true" class="anchor" href="#run-it-with-these-steps" id="user-content-run-it-with-these-steps"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Run it with these steps!</h4>
<ol>
<li>
<p>Navigate to chrome://extensions and
tick 'Developer Mode'.</p>
</li>
<li>
<p>Click 'Load unpacked extension...' and navigate to
<a href="/redcanaryco/atomic-red-team/blob/master/atomics/t1176">Browser_Extension</a></p>
</li>
<li>
<p>Click 'Select'</p>
</li>
</ol>
<br/>
<br/>
<h2><a aria-hidden="true" class="anchor" href="#atomic-test-2---chrome-chrome-web-store" id="user-content-atomic-test-2---chrome-chrome-web-store"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Atomic Test #2 - Chrome (Chrome Web Store)</h2>
<p>xxx</p>
<p><strong>Supported Platforms:</strong> Linux, Windows, macOS</p>
<h4><a aria-hidden="true" class="anchor" href="#run-it-with-these-steps-1" id="user-content-run-it-with-these-steps-1"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Run it with these steps!</h4>
<ol>
<li>
<p>Navigate to <a href="https://chrome.google.com/webstore/detail/minimum-viable-malicious/odlpfdolehmhciiebahbpnaopneicend" rel="nofollow">https://chrome.google.com/webstore/detail/minimum-viable-malicious/odlpfdolehmhciiebahbpnaopneicend</a>
in Chrome</p>
</li>
<li>
<p>Click 'Add to Chrome'</p>
</li>
</ol>
<br/>
<br/>
<h2><a aria-hidden="true" class="anchor" href="#atomic-test-3---firefox" id="user-content-atomic-test-3---firefox"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Atomic Test #3 - Firefox</h2>
<p>Create a file called test.wma, with the duration of 30 seconds</p>
<p><strong>Supported Platforms:</strong> Linux, Windows, macOS</p>
<h4><a aria-hidden="true" class="anchor" href="#run-it-with-these-steps-2" id="user-content-run-it-with-these-steps-2"><svg aria-hidden="true" class="octicon octicon-link" height="16" version="1.1" viewBox="0 0 16 16" width="16"><path d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z" fill-rule="evenodd"></path></svg></a>Run it with these steps!</h4>
<ol>
<li>
<p>Navigate to about:debugging and
click "Load Temporary Add-on"</p>
</li>
<li>
<p>Navigate to <a href="/redcanaryco/atomic-red-team/blob/master/atomics/T1176/manifest.json">manifest.json</a></p>
</li>
<li>
<p>Then click 'Open'</p>
</li>
</ol>
<br/>
</article>
  </div>