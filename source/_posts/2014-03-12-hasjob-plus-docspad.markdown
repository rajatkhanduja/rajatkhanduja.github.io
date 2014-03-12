---
layout: post
title: "Uploading document on HasJob via Docspad"
date: 2014-03-12 00:06:09 +0530
comments: true
categories: Hasjob github Docspad Bookpad python flask api

---

About two months ago, [Niketh](http://twitter.com/sniketh) came up with an idea
to augment the job application process on [Hasjob](https://hasjob.co).  Having
made the quite awesome product, [Docspad](http://docspad.com) for handling
documents in web applications, he certainly noticed the lack of the option to
let a job applicant upload a CV while applying through Hasjob. While the user
could add details about himself/herself in a text field, nothing tells as much
about an applicant as a personalized CV. As the [code for the website is open
sourced](https://github.com/hasgeek/hasjob) and written in Python, I took this
opportunity to check out the [Docspad
APIs](http://docspad.com/documentation/gettingstarted) and spend a weekend
contributing to a Python based open source project! 

But before I dive into the task and the experience, let's first discuss more about 
Hasjob and Docspad.

Hasjob is [HasGeek](http://hasgeek.com)'s job board. Hasgeek, based out of
Bangalore, is known for organizing technology events for geeks and developers
in India. Some of these events include Hackathons and
[Hacknights](https://hacknight.in), which are loved among the geeks. HasGeek
lives up to its name by providing the source code to their website and its
components under open source licenses on [Github](https://github.com/hasgeek/).

With the goal of making digital content more accessible, Niketh and
[Aditya](https://twitter.com/bandiaditya) founded [Bookpad](http://bookpad.in)
([@bookpadinc](http://twitter.com/bookpadinc)). [Docspad](http://docspad.com) is
their first product, which provides an easy solution for developers to make
applications with document handling capabilities. The set of APIs make it easy
for a developer to provide users with the option to upload and view documents
through the web browser on any device ranging from mobile to desktop.
<!--more-->

Now, the primary task was to provide a job applicant with the option to upload
a document as his CV and allow the employer to view the same. Moreover, we
wanted the integration to make as little changes to the current workflow and
code architecture.  The reason behind this was two-fold : 

- allow seamless transition to the new workflow.

- avoid making changes to the database layer or code architecture to make it
  easy to integrate and make it live at the earliest.


As a result, we settled on providing the user the option to upload a PDF, DOC
or a DOCX file while filling up the rest of the application. To avoid making
changes to the database layer, this document is only temporarily stored on the
HasJob server until it is uploaded to Docspad.  Thereafter, a URL based on the
`docid` returned by Docspad Upload API is simply attached to the
`apply_message` field, which is the one that the employer receives in an email
allowing the employer to view the document with or without downloading it to
his device. The Docspad HTML5 based viewer can be embeded right into the
application, allowing us to let the user view the uploaded content from within
Hasjob's website. 

This process is quite simple to code, made simpler by the quite flexible 
[Flask microframework](http://flask.pocoo.org) used for the Hasjob site along
with the easy Docspad API.

Some highlights of the project were :- 


1. **Wrapping around Docspad API**
    
   Since Docspad didn't have any publicly available SDKs at the time, I began
   by building a wrapper around the APIs. [This code](https://github.com/rajatkhanduja/hasjob/commit/45945f1cbad17dbc03839388a05cacb0bbf3d07b)
   later became the boilerplate for a [Python SDK for Docspad](https://github.com/Bookpad/docspad-sdk-python),
   which will soon be stable. SDKs for several other languages and platforms
   are in the pipeline too. SDKs not only make it easier to build applications
   on, but also provide sample code for using the APIs for those who like to
   build their own tools.


2. **Lastuser and HasGeek Auth**
    
   HasGeek uses [HasGeek Auth](http://auth.hasgeek.com) for authorization and
   user management for its sites. It is powered by [Lastuser](https://github.com/hasgeek/lastuser),
   which has been developed by HasGeek themselves! At that time, I was still 
   getting to know more about HasGeek's open sourced components and was quite
   impressed with their dedication to sharing all these tools that they had
   developed. 


In the end, it turned out to be a great weekend project and let me get
acquainted with Flask and Docspad API. Now, every time I encounter a site that
doesn't provide good support for uploading/viewing documents, I wonder all the
things they could do with the API! In fact, there are several other job portals
that could make use of the API in quite the same way. 

While I didn't follow up much after sending them the
[pull request](https://github.com/hasgeek/hasjob/pull/81), Niketh has been in
touch with them and informs me that they are quite pleased with the
implementation. Eagerly awaiting for the integration to go live! 

Do leave your suggestions, about the blog or the project, in the comments below.
