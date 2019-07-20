<div class="container-fluid">
 <h1>
  Hardware Additions
 </h1>
 <div class="row">
  <div class="col-md-8 description-body">
   <p>
    Computer accessories, computers, or networking hardware may be introduced into a system as a vector to gain execution. While public references of usage by APT groups are scarce, many penetration testers leverage hardware additions for initial access. Commercial and open source products are leveraged with capabilities such as passive network tapping
    <span class="scite-citeref-number" data-reference="Ossmann Star Feb 2011" id="scite-ref-1-a">
     <sup>
      <a aria-describedby="qtip-0" data-hasqtip="0" href="https://ossmann.blogspot.com/2011/02/throwing-star-lan-tap.html" target="_blank">
       [1]
      </a>
     </sup>
    </span>
    , man-in-the middle encryption breaking
    <span class="scite-citeref-number" data-reference="Aleks Weapons Nov 2015" id="scite-ref-2-a">
     <sup>
      <a aria-describedby="qtip-1" data-hasqtip="1" href="http://www.bsidesto.ca/2015/slides/Weapons_of_a_Penetration_Tester.pptx" target="_blank">
       [2]
      </a>
     </sup>
    </span>
    , keystroke injection
    <span class="scite-citeref-number" data-reference="Hak5 RubberDuck Dec 2016" id="scite-ref-3-a">
     <sup>
      <a aria-describedby="qtip-2" data-hasqtip="2" href="https://www.hak5.org/blog/main-blog/stealing-files-with-the-usb-rubber-ducky-usb-exfiltration-explained" target="_blank">
       [3]
      </a>
     </sup>
    </span>
    , kernel memory reading via DMA
    <span class="scite-citeref-number" data-reference="Frisk DMA August 2016" id="scite-ref-4-a">
     <sup>
      <a aria-describedby="qtip-3" data-hasqtip="3" href="https://www.youtube.com/watch?v=fXthwl6ShOg" target="_blank">
       [4]
      </a>
     </sup>
    </span>
    , adding new wireless access to an existing network
    <span class="scite-citeref-number" data-reference="McMillan Pwn March 2012" id="scite-ref-5-a">
     <sup>
      <a aria-describedby="qtip-4" data-hasqtip="4" href="https://arstechnica.com/information-technology/2012/03/the-pwn-plug-is-a-little-white-box-that-can-hack-your-network/" target="_blank">
       [5]
      </a>
     </sup>
    </span>
    , and others.
   </p>
  </div>
  <div class="col-md-4">
   <div class="card">
    <div class="card-body">
     <div class="card-data">
      <span class="h5 card-title">
       ID
      </span>
      : T1200
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
       Data Sources:
      </span>
      Asset management, Data loss prevention
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
  Establish network access control policies, such as using device certificates and the 802.1x standard.
  <span class="scite-citeref-number" data-reference="Wikipedia 802.1x" id="scite-ref-6-a">
   <sup>
    <a aria-describedby="qtip-5" data-hasqtip="5" href="https://en.wikipedia.org/wiki/IEEE_802.1X" target="_blank">
     [6]
    </a>
   </sup>
  </span>
  Restrict use of DHCP to registered devices to prevent unregistered devices from communicating with trusted systems.
 </p>
 <p>
  Block unknown devices and accessories by endpoint security configuration and monitoring agent.
 </p>
 <h2 class="pt-3" id="detection">
  Detection
 </h2>
 <p>
  Asset management systems may help with the detection of computer systems or network devices that should not exist on a network.
 </p>
 <p>
  Endpoint sensors may be able to detect the addition of hardware via USB, Thunderbolt, and other external device communication ports.
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
       <a class="external text" href="https://ossmann.blogspot.com/2011/02/throwing-star-lan-tap.html" name="scite-1" rel="nofollow" target="_blank">
        Michael Ossmann. (2011, February 17). Throwing Star LAN Tap. Retrieved March 30, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-2">
      <span class="scite-citation-text">
       <a class="external text" href="http://www.bsidesto.ca/2015/slides/Weapons_of_a_Penetration_Tester.pptx" name="scite-2" rel="nofollow" target="_blank">
        Nick Aleks. (2015, November 7). Weapons of a Pentester - Understanding the virtual &amp; physical tools used by white/black hat hackers. Retrieved March 30, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-3">
      <span class="scite-citation-text">
       <a class="external text" href="https://www.hak5.org/blog/main-blog/stealing-files-with-the-usb-rubber-ducky-usb-exfiltration-explained" name="scite-3" rel="nofollow" target="_blank">
        Hak5. (2016, December 7). Stealing Files with the USB Rubber Ducky – USB Exfiltration Explained. Retrieved March 30, 2018.
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
       <a class="external text" href="https://www.youtube.com/watch?v=fXthwl6ShOg" name="scite-4" rel="nofollow" target="_blank">
        Ulf Frisk. (2016, August 5). Direct Memory Attack the Kernel. Retrieved March 30, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-5">
      <span class="scite-citation-text">
       <a class="external text" href="https://arstechnica.com/information-technology/2012/03/the-pwn-plug-is-a-little-white-box-that-can-hack-your-network/" name="scite-5" rel="nofollow" target="_blank">
        Robert McMillan. (2012, March 3). The Pwn Plug is a little white box that can hack your network. Retrieved March 30, 2018.
       </a>
      </span>
     </span>
    </li>
    <li>
     <span class="scite-citation" id="scite-6">
      <span class="scite-citation-text">
       <a class="external text" href="https://en.wikipedia.org/wiki/IEEE_802.1X" name="scite-6" rel="nofollow" target="_blank">
        Wikipedia. (2018, March 30). IEEE 802.1X. Retrieved April 11, 2018.
       </a>
      </span>
     </span>
    </li>
   </ol>
  </div>
 </div>
</div>
