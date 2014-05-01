---
layout: post
title: "Docspad SDK"
date: 2014-05-01 16:46:51 +0530
comments: true
categories: Docspad SDK api python ruby
---

In an [earlier post]({% post_url 2014-03-12-hasjob-plus-docspad %}), I had
discussed how I integrated [Docspad API](http://docspad.com) with
[Hasjob](http://hasjob.co).  As there was no Docspad SDK at that time, its
absence made me realize their importance. Having to deal with raw API calls,
these were the primary problems that I faced, which I thought could be resolved
by a Software Development Kit (SDK) :-

1. **API lets me talk to your tool, but not in my language**

    Say I am developing in Python and I have a dictionary of parameters explaining 
    all that I need the API to do, but the API doesn't understand the dictionary!
    I would need to convert all those parameters and variables in GET/POST variables
    that before I can get the task done. Moreover, the conventions in your API
    might be extremely different from those of my project, making things worse.

    Certainly, I could work around that by wrapping around your API, which brings
    me to the next point.

2. **Managing network calls and errors is annoying**

    There are API errors and then there are network/connection errors, timeouts
    and what not. The last thing I need when dealing with a project idea is to
    get stuck understanding what an error code means. SDKs not only help translate
    the content in the developer's language, but also the errors. An exception
    that describes the error makes it easy for the developer to handle
    certain edge cases without the program blowing up in the users' face.

3. **SDKs provide code samples**

    Even if a developer doesn't need the entire SDK, either because he only
    requires to make a few calls to the API or he/she does not think the SDK
    interacts well with his tool, an openly available SDK still provides code
    samples to the developer to help him/her manage basic things. Be it managing
    errors or creating request URLs, SDKs can act as a good demonstration of how
    the APIs must be used.

[Niketh](https://twitter.com/sniketh) had already been planning to release SDKs
himself, so when I suggested it to him, he was eager to get started! Soon
<!--more-->
after, I began working on a Python SDK as I already had written some [code to
wrap around Docspad API while integrating with
Hasjob](https://github.com/rajatkhanduja/hasjob/commit/45945f1cbad17dbc03839388a05cacb0bbf3d07b).
For inspiration and ideas about how a SDK should be structured, I looked at
other popular SDKs, especially the [Dropbox
SDKs](https://www.dropbox.com/developers/core/sdks/python). 

Once we had worked out the design and structure of the [Python
SDK](https://github.com/bookpad/docspad-sdk-python), we aimed to keep other SDKs
quite similar so as to have a common interface throughout languages. However, as 
different languaes have different programming idioms and conventions, having 
the *exact same* interface across languages would beat the purpose by forcing
the developers to think in terms of another language. As a result, while the
basic ideas and interface remains similar across languages, there are minor 
differences.

With [Ajay's](https://twitter.com/ajayn1609) help, we have been able to release
an entire [arsenal of SDKs](https://github.com/Bookpad/?query=docspad-sdk) for
[PHP](https://github.com/bookpad/docspad-sdk-php),
[Java](https://github.com/bookpad/docspad-sdk-java) and
[Ruby](https://github.com/bookpad/docspad-sdk-ruby) developers as well.

<blockquote class="twitter-tweet" lang="en"><p>For all the PHP developers out there, we have officially released our PHP SDK, Happy Hacking <a href="https://t.co/BHvmu7623g">https://t.co/BHvmu7623g</a> !!</p>&mdash; Bookpad Inc (@bookpadinc) <a href="https://twitter.com/bookpadinc/statuses/450967924216692736">April 1, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>


So how do our SDKs solve the problems discussed in the beginning? Using the
Ruby SDK, for instance, this is how one could write a program to upload a
document, create a new session, get a view url and then delete the document.

{% codeblock lang:ruby %}
load 'docspad.rb'

begin
    client = DocspadClient.new(YOUR_API_KEY)
    doc = client.upload(PATH_TO_FILE) # Uploads file; returns an instance of DocspadDocument
    begin 
        status = doc.getStatus 
        puts status
        sleep (1)
    end until status.conversionStatus == DocspadDocument::ConversionStatus::COMPLETED

    session = doc.newSession
    puts doc.getViewUrl(session)
    doc.deleteSession(session)
    doc.delete
rescue DocspadError => error
    puts error
end
{% endcodeblock %}

Note how not only the developer doesn't need to care about the details of the
network call, such as URL and the POST parameters, he is also freed of the hassle
of checking and managing all the errors that could arise. Moreover, with little
documentation available with the methods, a developer can get started
integrating the API into his project, without going through the entire [API
documentation](http://bookpad.in/developer/gettingstarted) and preparing
himself for all kinds of response the API could return.

So, what are you waiting for? Get yourself an [API
key](http://docspad.com/signup/freetrial) now and jump start your Docspad
integration with the SDKs. For issues or bugs with the SDKs, you could use the
issue tracker on Github or reach out to Docspad
([@docspadofficial](https://twitter.com/docspadofficial)) on Twitter [or just
drop by and say Hi]. If you are looking for SDK for some other language or have something to say about the post, leave a comment below.
leave a comment below
