---
layout: post
title: "Tech News: Wearable computing, Cgrep, Web Starter Kit, ... "
date: 2014-06-21 23:30:20 +0530
comments: true
categories: tech-news google nest dropcam acquisition elon-musk patent
---
1. [Using Wearable Computers for Passive Haptic Learning and Rehabilitation]({% post_url 2014-06-21-tech-news-wearable-computing-cgrep-web-starter-kit %}#passive-haptic-learning)
2. [Cgrep: a context-aware grep for source codes]({% post_url 2014-06-21-tech-news-wearable-computing-cgrep-web-starter-kit %}#cgrep)
3. [Google backed Nest acquires Dropcam]({% post_url 2014-06-21-tech-news-wearable-computing-cgrep-web-starter-kit %}#nest-dropcam)
4. [B.C. court ruling orders Google to block sites worldwide]({% post_url 2014-06-21-tech-news-wearable-computing-cgrep-web-starter-kit %}#google-block-sites)
5. [Google launches starter kit for a more consistent web]({% post_url 2014-06-21-tech-news-wearable-computing-cgrep-web-starter-kit %}#google-web-starter-kit)

External links (not summarized below):

1. [Discussion on possible solution of the GHash problem in Bitcoin network](https://blog.ethereum.org/2014/06/19/mining/) 
    (would try to summarize this in a later post)
2. [Quantum Experiment Shows How Time ‘Emerges’ from Entanglement](https://medium.com/the-physics-arxiv-blog/quantum-experiment-shows-how-time-emerges-from-entanglement-d5d3dc850933)

<!--more-->

&nbsp;
&nbsp;

----

1. <a name='passive-haptic-learning'></a>[Using Wearable Computers for Passive Haptic Learning and Rehabilitation](https://plus.google.com/+ResearchatGoogle/posts/EgtfWJME37g)
    - At Georgia Institute of Technology, a wireless glove, Mobile Music Touch (MMT),
      has been developed that enables users to learn to play piano melodies while 
      performing everyday tasks. 
    - The process is called 'Passive Haptic Learning'.
      {% blockquote %}
      Vibration motors are embedded in the glove at the base of each finger and the thumb.  The song being learned can be loaded onto a user’s mobile phone and is played as they go about their business.  As each note is played, the glove taps the finger corresponding to the appropriate key on a piano keyboard.  The result: in as little as 30 minutes, the user learns the "muscle memory" of the first phrases of the song, even if their attention has been devoted to another task.
      {% endblockquote %}
    - Even when distracted while the MMT tapped their fingers by tasks, like reading
      emails, taking a graduate entrance exam and watching a movie, the subjects
      were able to learn to play the songs.
      
      {% blockquote %}
      Surprisingly, only the vibration was needed for the glove to be effective-- on average, participants who only "felt" the music performed as well as those who heard the audio concurrently.
      {% endblockquote %}
      
    - Experiments suggest that it can also use in rehabilitation to help those
      with paralysis because of spinal injuries.

    <iframe width="560" height="315" src="//www.youtube.com/embed/Zi6t89pi17c" frameborder="0" allowfullscreen></iframe>

2. <a name="cgrep"></a>[Cgrep: a context-aware grep for source codes](http://awgn.github.io/cgrep/)
    - Grep tool for large code repositories
    - Searches beyond simple pattern matching
      - Allows search in comments or code (except comment)
      - Allows searching in string literals
    - Claims to have semantic search capability
    - [Ack](http://beyondgrep.com/why-ack/) is another tool relevant for 
      grepping through source code. Doesn't have any semantic search capability


3. <a name="nest-dropcam"></a>[Google backed Nest acquires Dropcam](https://nest.com/blog/2014/06/20/the-nest-family-is-growing/)
    - Dropcam provides wifi connected camera setup to allow its customers to install
      in their houses, so that they can check in on their home, irrespective 
      of where they are in the world.
    - Dropcam can be used to keep tabs on doors, windows or valuables at home. 
      Even useful as a child monitoring tool.
    - Nest, the company that creates intelligent thermostats, was acquired 
      by Google recently. 
    - Like Nest's acquisition by Google, this raises some privacy concerns. 
    - Probably to stave off thoughts like, "Now Google gets a video feed in 
      my house!", Nest explains in it's blogpost that
      {% blockquote %}
      Once the deal closes, we’ll incorporate Dropcam into how we do business at Nest. That includes how we handle everything from customer support to customer privacy. Like Nest customer data, Dropcam will come under Nest’s privacy policy, which explains that data won’t be shared with anyone (including Google) without a customer’s permission. Nest has a paid-for business model and ads are not part of our strategy. In acquiring Dropcam, we’ll apply that same policy to Dropcam too.
      {% endblockquote %}
   - The numbers are not stated on their blogpost, but sources like [techrunch](http://techcrunch.com/2014/06/20/google-and-nest-acquire-dropcam-for-555-million/)
     quote a figure of $555m for the acquisition.

4. <a name="google-block-sites"></a>[B.C. court ruling orders Google to block sites worldwide](http://www.theglobeandmail.com/report-on-business/industry-news/the-law-page/bc-court-seeking-global-reach-orders-google-to-block-sites/article19212708/)
    - A British Columbia court ordered Google (temporary injunction) to block
      certain websites from 'worldwide search engine'
    - This raises the question of how much control can a country's court exert 
      on the Internet.
    - The case in discussion involves a company whose trade secrets were stollen 
      to create a competing product, which is being sold through a network 
      of websites despite several court orders.
    - While current procedures allow Google to block search results within 
      Canada, since most sales occur outside Canada, they have been asked to 
      block the site across the entire system. 
    - 
      {% blockquote %}
      But University of Ottawa law professor Michael Geist slammed the recent Google decision in a blog post on Tuesday, warning that it could lead to other countries demanding Google censor content worldwide, putting free speech at risk. “While the court does not grapple with this possibility, what happens if a Russian court orders Google to remove gay and lesbian sites from its database? Or if Iran orders it remove Israeli sites from the database?”
      {% endblockquote %}
    - Earlier, EU enforced Google to honor ['Right to be
      forgotten'](http://techcrunch.com/2014/05/30/right-to-be-forgotten-webform/)
      for its own citizens, which allows users to [request removal of
      pages/information from Google's indexes](https://support.google.com/legal/contact/lr_eudpa?product=websearch#).

5. <a name="google-web-starter-kit"></a>[Google launches starter kit for a more consistent web](http://readwrite.com/2014/06/19/google-launches-starter-kit-for-a-more-consistent-web)
    - With the different kind of devices, people expect the same website to 
      behave differently depending on the device (touchscreen vs desktop, 
      mobile vs tablet)
    - [Web Starter Kit](https://developers.google.com/web/starter-kit/) 
      provides a boilerplate for developers to get started with multi-device 
      development. 

&nbsp;
&nbsp;

----
*'[Tech News](/techblog/categories/tech-news)' is a series of articles where I attempt to share and summarize
recent developments in technology (and the related industry) that interest,
amaze and/or excite me. These would attempt to cover topics ranging from impressive 
apps to Google's latest acquisition to jaw-dropping updates from SpaceX or Tesla Motors
and much more.*
      
