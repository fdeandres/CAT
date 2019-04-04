<div class="container-fluid">
<h1>
               Drive-by Compromise
            </h1>
<div class="row">
<div class="col-md-8 description-body">
<p>A drive-by compromise is when an adversary gains access to a system through a user visiting a website over the normal course of browsing. With this technique, the user's web browser is targeted for exploitation. This can happen in several ways, but there are a few main components: </p><p>Multiple ways of delivering exploit code to a browser exist, including:</p><ul><li>A legitimate website is compromised where adversaries have injected some form of malicious code such as JavaScript, iFrames, cross-site scripting.</li><li>Malicious ads are paid for and served through legitimate ad providers.</li><li>Built-in web application interfaces are leveraged for the insertion of any other kind of object that can be used to display web content or contain a script that executes on the visiting client (e.g. forum posts, comments, and other user controllable web content).</li></ul><p>Often the website used by an adversary is one visited by a specific community, such as government, a particular industry, or region, where the goal is to compromise a specific user or set of users based on a shared interest. This kind of targeted attack is referred to a strategic web compromise or watering hole attack. There are several known examples of this occurring. <span class="scite-citeref-number" data-reference="Shadowserver Strategic Web Compromise" id="scite-ref-1-a"><sup><a aria-describedby="qtip-0" data-hasqtip="0" href="http://blog.shadowserver.org/2012/05/15/cyber-espionage-strategic-web-compromises-trusted-websites-serving-dangerous-results/" target="_blank">[1]</a></sup></span></p><p>Typical drive-by compromise process:</p><ol><li>A user visits a website that is used to host the adversary controlled content.</li><li>Scripts automatically execute, typically searching versions of the browser and plugins for a potentially vulnerable version. <ul><li>The user may be required to assist in this process by enabling scripting or active website components and ignoring warning dialog boxes.</li></ul></li><li>Upon finding a vulnerable version, exploit code is delivered to the browser.</li><li>If exploitation is successful, then it will give the adversary code execution on the user's system unless other protections are in place.<ul><li>In some cases a second visit to the website after the initial scan is required before exploit code is delivered.</li></ul></li></ol><p>Unlike <a href="/techniques/T1190">Exploit Public-Facing Application</a>, the focus of this technique is to exploit software on a client endpoint upon visiting a website. This will commonly give an adversary access to systems on the internal network instead of external systems that may be in a DMZ.</p>
</div>
<div class="col-md-4">
<div class="card">
<div class="card-body">
<div class="card-data"><span class="h5 card-title">ID</span>: T1189<br/><br/></div>
<div class="card-data"><span class="h5 card-title"></span> </div>
<div class="card-data"><span class="h5 card-title">Tactic</span>: Initial Access<br/><br/></div>
<div class="card-data"><span class="h5 card-title">Platform: </span> Windows, Linux, macOS<br/><br/></div>
<div class="card-data"><span class="h5 card-title">Permissions Required: </span> User<br/><br/></div>
<div class="card-data"><span class="h5 card-title"></span> </div>
<div class="card-data"><span class="h5 card-title">Data Sources: </span> Packet capture, Network device logs, Process use of network, Web proxy, Network intrusion detection system, SSL/TLS inspection<br/><br/></div>
<div class="card-data"><span class="h5 card-title"></span> </div>
<div class="card-data"><span class="h5 card-title"></span> </div>
<div class="card-data"><span class="h5 card-title"></span> </div>
<div class="card-data"><span class="h5 card-title"></span> </div>
<div class="card-data"><span class="h5 card-title"></span> </div>
<div class="card-data"><span class="h5 card-title"></span> </div>
<div class="card-data"><span class="h5 card-title">Version</span>: 1.0</div>
</div>
</div>
</div>
</div>
<h2 class="pt-3" id="examples">Examples</h2><table class="table table-bordered table-light mt-2"><thead><tr> <th scope="col">Name</th><th scope="col">Description</th></tr></thead><tbody class="bg-white"><tr><td><a href="/groups/G0073">APT19</a></td><td><p><a href="/groups/G0073">APT19</a> performed a watering hole attack on forbes.com in 2014 to compromise targets.<span class="scite-citeref-number" data-reference="Unit 42 C0d0so0 Jan 2016" id="scite-ref-2-a" onclick="scrollToRef('scite-2')"><sup><a aria-describedby="qtip-1" data-hasqtip="1" href="https://researchcenter.paloaltonetworks.com/2016/01/new-attacks-linked-to-c0d0s0-group/" target="_blank">[2]</a></sup></span></p></td></tr></tbody></table></div>