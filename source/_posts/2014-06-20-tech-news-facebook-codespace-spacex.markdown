---
layout: post
title: "Tech News: Facebook's engineering & outage, CodeSpaces, SpaceX,..."
date: 2014-06-20 23:43:54 +0530
comments: true
categories: tech-news, spacex, elon musk, facebook, outage, open compute project,
            codespaces, ddos, skype, linux
---
1. [Facebook breaks the network switch into modules]({% post_url 2014-06-20-tech-news-facebook-codespace-spacex %}#fb-network-switch)
2. [Facebook Saves Developing World’s Data Plans With 65% Smaller, 50% More Efficient Android App]({% post_url 2014-06-20-tech-news-facebook-codespace-spacex %}#fb-android)
3. [Facebook outage; down for around 30 minutes]({% post_url 2014-06-20-tech-news-facebook-codespace-spacex %}#fb-outage)
4. [Code Spaces destroyed after attacked deletes Amazon-hosted data]({% post_url 2014-06-20-tech-news-facebook-codespace-spacex %}#codespaces)
5. [Elon Musk: Hopeful that the first people could be taken to Mars in 10 to 12 years]({% post_url 2014-06-20-tech-news-facebook-codespace-spacex %}#mars-spacex)
6. [Skype for Linux 4.3 Arrives with Desktop Call Monitor Widget, UI Changes]({% post_url 2014-06-20-tech-news-facebook-codespace-spacex %}#skype)

<!--more-->
---

1. <a name='fb-network-switch'></a>**[Facebook breaks the network switch into modules](http://www.datacenterknowledge.com/archives/2014/06/18/facebook-breaks-network-switch-modules/)**
    - Facebook has been trying to disaggregate mains parts of their data center
      to provide more flexibility. Components can be separately upgraded and
      congigured for optimal performance.
    - Until now, they had succeeded with compute, server and storage, but the
      traditional switches were being used.
    - Wedge, the new top-of-rack switch, breaks that.
    - Hardware and software components are broken into modules.
      {% blockquote %}
      The central modular hardware feature of Wedge is the OCP “Group Hug” motherboard, originally developed for microservers. A single Group Hug board can accommodate Intel, AMD or ARM processors.

      Besides configurability, using a server board makes the box behave less like a switch and more like a server. “It basically takes the switch and it turns the switch into … another server,” Parikh said.
      {% endblockquote %}
    - Facebook also designed FBOSS, a linux based OS, to make use of libraries
      and systems to manage their fleet of servers.
      {% blockquote %}
      FBOSS also puts an abstraction layer on top of the ASIC APIs of the switch which enables its engineers to treat it like they treat any other service in Facebook. “With FBOSS, all our infrastructure software engineers instantly become network engineers,” Bachar and Simpkins wrote.
      {% endblockquote %}
    - The design of the data switch will eventually be shared as part of its
      [Open Compute Project](http://www.opencompute.org/)

2. <a name='fb-android'></a>**[Facebook Saves Developing World’s Data Plans With 65% Smaller, 50% More Efficient Android App](http://techcrunch.com/2014/06/19/facebook-for-android/)**
    - Having reached most of the market in the developed countries, Facebook is
      trying to reach out in the emerging markets.
    - While Android is a good platform for that, it also poses the issue that 
      these markets have several low-end devices and expensive data plans. 
    - [Facebook has improved their Android app to counter these problems](https://code.facebook.com/posts/485459238254631/improving-facebook-on-android)
      {% blockquote %}
      To help accomplish this goal, a team of product managers and engineers traveled to Africa to examine mobile performance in developing countries. We purchased several different Android handsets to test the latest version of the Facebook app – and the testing process proved to be difficult. The combination of an intermittent, low-bandwidth network connection and a lack of memory space on the devices resulted in slow load times and constant crashes. We even burned through our monthly data plans in 40 minutes.
      {% endblockquote %}

    - Performance (start times reduced by more than 50%)
        {% blockquote %}
        we found that start times were slower on single-core devices because too many features concurrently initialized themselves on application startup. We made sure to defer these initializations until after startup and, in some cases, until the features are used.

        We also wanted the stories in News Feed to load faster. In order to rapidly display cached content on poor networks, we now fetch stories earlier in the process to allow more time to set up connections and download News Feed. The cold start path has been automated to ensure that we prevent further regressions in these areas.
        {% endblockquote %}

    - Data efficiency (because data is expensive in developing countries)
        - After trying alternatives, settled on WebP compression format for
          image transmission.
        {% blockquote %}
        The use of WebP for transmitting Facebook images resulted in data savings of 25 to 35 percent compared with JPG, and 80 percent compared with PNG. This all happened without perceived impact on quality.
        {% endblockquote %}
        - Instead of loading images at high resolution, load only resolution
          equivalent to the size of the viewport in which the images will appear.
        - Higher resolution image requested/downloaded only when someone wants
          to zoom-in on an image.
        - Fine tuned caching strategies and sizes to minimize evictions for 
          images that could be accessed again.
        {% blockquote %}
        The work on data efficiency resulted in a 50 percent reduction in data use compared with earlier last year.
        {% endblockquote %}
    - Networking
        - Current stack ([OkHttp](http://square.github.io/okhttp/)) allowed
          fast retries for intermittent network situations.
        - Tried to decrease the number of reports regarding failed image loads
          in News Feed. 
        - Fine tuned image pre-fetching algorithms and altered the process through
          which the images are queued for download. 
        - Ensured that the images expected to be downloaded next are prioritized and no image
          is stuck in queue for long.
        {% blockquote %}
        In combination with better data usage for images, reports of slow or failed image loads dropped by almost 90 percent over the past year.
        {% endblockquote %}

    - Application size
        - Reduced application size by using Google Play's options to provide 
          different APKs for different OS versions and screen resolutions.
        - Code of features or resources not supported on certain devices have
          been excluded to reduce the size of the app.

3. <a name='fb-outage'></a>**[Facebook outage; down for around 30 minutes](http://techcrunch.com/2014/06/19/facebook-goes-down-in-global-outage/)**
    - Apparently, this was not because of any attack on the system, but because
      of an internal error. 
    - Statement from Facebook
     
      {% blockquote %}
      Late last night, we ran into an issue while updating the configuration of one of our software systems. Not long after we made the change, some people started to have trouble accessing Facebook. We quickly spotted and fixed the problem, and in less than 30 minutes Facebook was back to 100% for everyone. This doesn’t happen often, but when it does we make sure we learn from the experience so we can make Facebook that much more reliable. Nothing is more important to us than making sure Facebook is there when people need it, and we apologize to anyone who may have had trouble connecting last night.
      {% endblockquote %}

4. <a name='codespaces'></a>**[Code Spaces destroyed after attacked deletes Amazon-hosted data](http://www.theregister.co.uk/2014/06/18/code_spaces_destroyed/)**
    - Code Spaces, a source code hosting provider, has [posted the details of the attack](http://www.codespaces.com/?hackernews)
      that has caused them to go out of business.
    - A DDOS attack started on 17th June and a hacker, who also gained access
      to their Amazon EC2 control panel, left an email address for them to contact
      through which they demanded a large some of money to stop the attack.
    - While their team tried to mitigate the attack and tried to regain control
      of their control panel, the hacker caused a lot of damage.

      {% blockquote %}
      At this point we took action to take control back of our panel by changing passwords, however the intruder had prepared for this and had already created a number of backup logins to the panel and upon seeing us make the attempted recovery of the account he proceeded to randomly delete artifacts from the panel. We finally managed to get our panel access back but not before he had removed all EBS snapshots, S3 buckets, all AMI's, some EBS instances and several machine instances.

      In summary, most of our data, backups, machine configurations and offsite backups were either partially or completely deleted.
      {% endblockquote %}
    - As a consequence, ...

      {% blockquote %}
      Code Spaces will not be able to operate beyond this point, the cost of resolving this issue to date and the expected cost of refunding customers who have been left without the service they paid for will put Code Spaces in a irreversible position both financially and in terms of on going credibility.

      As such at this point in time we have no alternative but to cease trading and concentrate on supporting our affected customers in exporting any remaining data they have left with us
      {% endblockquote %}


5. <a name='mars-spacex'></a>**[Elon Musk: Hopeful that the first people could be taken to Mars in 10 to 12 years](http://www.nbcnews.com/science/space/elon-musk-promises-spacex-will-stay-course-mars-n133971)**
    - [Dragon V2](http://en.wikipedia.org/wiki/Dragon_%28spacecraft%29#Dragon_V2),
      the second version of Dragon, is a fully reusable spacecraft (unlike 
      Dragon, which was 'partially' reusable) and can carry up to 7 astronauts.
    - SpaceX is competing for a contract with NASA to deliver some crew transport
      missions to International Space Station.
      
      {% blockquote %}
      [Elon Musk] noted that SpaceX's progression would be slowed down if the U.S. government doesn't choose the company's Dragon V2 as the next crew carrier to the International Space Station. 
      {% endblockquote %}
    - Focus on Mars
      {% blockquote %}
      For now, he says the company is focused on creating technology that with enable large groups of people to travel to Mars.

      "I'm hopeful that the first people could be taken to Mars in 10 to 12 years, I think it's certainly possible for that to occur," he said. "But the thing that matters long term is to have a self-sustaining city on Mars, to make life multiplanetary." 
      {% endblockquote %}

6. <a name='skype'></a>**[Skype for Linux 4.3 Arrives with Desktop Call Monitor Widget, UI Changes](http://www.omgubuntu.co.uk/2014/06/download-skype-4-3-linux-new-ui-download)**
    - Majorly UI improvements
    - Provides better desktop integration and some features that were already
      present in the Windows and Mac versions, like Desktop integration
      for notifications.


&nbsp;
&nbsp;

----
*'[Tech News](/techblog/categories/tech-news)' is a series of articles where I attempt to share and summarize
recent developments in technology (and the related industry) that interest,
amaze and/or excite me. These would attempt to cover topics ranging from impressive 
apps to Google's latest acquisition to jaw-dropping updates from SpaceX or Tesla Motors
and much more.*

