---
layout: post
title: "Tech News: Slingshot, JS Cryptography, Dropbox, ..."
date: 2014-06-18 23:22:07 +0530
comments: true
categories: tech-news facebook slingshot privacy cryptography javascript
            apple acquisition dropbox          
---

1. **[Facebook's Slingshot challenges SnapChat with 'Reply to Unlock'](http://techcrunch.com/2014/06/17/facebook-slingshot/)**
    - Facebook's new app [Slingshot](http://www.sling.me/) is being seen as a 
      competitor to SnapChat. 
    - It lets you share photos and 15-second videos with users on Slingshot.
    - The content is meant to be ephemeral, much like SnapChat. 

      {% blockquote %}
      As for what happens to your content, once everyone you’ve slinged something to views it, Facebook says it will delete the photo or video from its servers. There is a seven-day delay in case it has to investigate abuse reports, but the team says the content is gone after that. Whether users trust Facebook to keep its word is up to them. Past privacy missteps might scare people, but Facebook is under close scrutiny from the FTC to abide by the privacy policies it puts forward.
      {% endblockquote %}

    - An important catch in the app is that you can't view the content shared 
      by the user until you reply to it. ('Reply to Unlock')
    - This aims to increase reciprocation and make everyone a content generator.
    - Slingshot was born out of a hackathon. The motivation can be summarized by 
      {% blockquote %}
      “My brothers are really not technical in any way”, Slingshot inventor and four-year Facebook Product Designer Joey Flynn tells me. “I’d take a photo, upload it in iMessage, and send it to them. And I would just see “Seen”, or in a month I’d see them and they‘d say ‘that was a cool photo’. But hey, I want to see what you’re up to! There was this missing reciprocation” he explains. That was the spark for Slingshot.
      {% endblockquote %}
    - This app was [earlier released on app stored by mistake](http://mashable.com/2014/06/09/slingshot-app/)
    - Facebook had tried to buy off SnapChat, but [SnapChat had rejected the $3 billion buyout offer](http://www.reuters.com/article/2013/11/13/us-facebook-snapchat-idUSBRE9AC11E20131113)

    <iframe src="//player.vimeo.com/video/98214265" width="500" height="400" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

2. **[Browser based javascript cryptography considered harmful](http://matasano.com/articles/javascript-cryptography/)**
    
    Some of the things pointed out in the article. *[Not being an expert in cryptography, I would recommend readers to read
      the original article to avoid any miscommunication]*

    - Code could be injected when in transit. Can use SSL/TLS to avoid that, but 
      then, in most cases, you could simply avoid cryptography at 
      user end.
    - There's no certainty of information being removed from memory.
    - It is not possible to verify the code/environment to be exactly as it is 
      required to be. 
    - Javascript lacks a Cryptographically Secure Pseudo-Random Number Generator (CSPRNG). 
    - [Stanford Javascript Crypto library (SJCL)](https://crypto.stanford.edu/sjcl/)
      developed at Stanford is a great work, but still insecure.
      {% blockquote %}
      The authors of SJCL themselves say, "Unfortunately, this is not as great as in desktop applications because it is not feasible to completely protect against code injection, malicious servers and side-channel attacks." That last example is a killer: what they're really saying is, "we don't know enough about Javascript runtimes to know whether we can securely host cryptography on them". Again, that's painful-but-tolerable in a server-side application, where you can always call out to native code as a workaround. It's death to a browser.
      {% endblockquote %}

3. **[UK intelligence forced to reveal secret policy for mass surveillance of
   residents’ Facebook and Google
   use](https://www.privacyinternational.org/press-releases/uk-intelligence-forced-to-reveal-secret-policy-for-mass-surveillance-of-residents)**
   - Secret policy define UK residents' communication on Facebook, Google, Twitter, etc.
     as 'external communication' because they use platforms based in the US, even
     if the communication is between two people in the UK.
   - This grants the secret services to indiscriminately intercept communication
     on these platforms.
   - For an 'internal communication', a warrant would be required, however that 
     is not the case with 'external communication'.
     {% blockquote %}
     The Government believes that, even when privacy violations happen, it is not an “active intrusion” because the analyst reading or listening to an individual’s communication will inevitably forget about it anyway.
     {% endblockquote %}

4. **[Dropbox acquired Parastructure, a Big Data Startup](http://techcrunch.com/2014/06/16/dropbox-has-quietly-acquired-parastructure-a-big-data-startup-in-stealth/)**
    -
    {% blockquote %}
    So what exactly is Parastructure? According to the company’s LinkedIn profile, and its (now-offline) home page, it builds “beautiful data analysis software powered by cutting-edge open source infrastructure.” Parastructure’s GitHub pages give some clues as to what that data-analysis software was tackling, with areas covering Spark for cluster computing; Phoenix, a SQL skin over HBase; CrunchBase; and so on
    {% endblockquote %}
    
    - The acquisition was done quite stealthily.
    - Probably, Dropbox requires the software and the team to analyze its data
    - Parastructure was an enterprise oriented startup and its acquisition indicates 
      Dropbox's intention on strengthening their image as an enterprise product.
    - Dropbox's increased effort in [Dropbox for
      Business](https://www.dropbox.com/business) brings it in direct
      competition with Box, which is currently leading as an enterprise
      solution.
    - Both the companies are quite aggressively acquiring companies. 
    - In fact, Parastructure was acquired on the same day as 
      [Box acquired Streem]({% post_url 2014-06-17-tech-news-about-qeexos-fingersense-wristify-loon  %})

5. **[Apple adds a new entry level iMac for ~$1,100](http://techcrunch.com/2014/06/18/apple-adds-a-new-entry-level-imac-for-1099/)**
    - 1.4GHz dual-core Intel Core i5 processor, 8GB memory, 500GB HDD, Intel HD Graphics 5000 on board
&nbsp;
&nbsp;

----
*'[Tech News](/techblog/categories/tech-news)' is a series of articles where I attempt to share and summarize
recent developments in technology (and the related industry) that interest,
amaze and/or excite me. These would attempt to cover topics ranging from impressive 
apps to Google's latest acquisition to jaw-dropping updates from SpaceX or Tesla Motors
and much more.*

