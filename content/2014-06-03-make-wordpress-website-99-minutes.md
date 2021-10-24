---
title: How to make a WordPress Website in 99 minutes
author: Vikram Bahl
type: post
date: 2014-06-03T16:33:58+00:00
url: /make-wordpress-website-99-minutes/
ssb_old_counts:
  - 'a:6:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;}'
ssb_cache_timestamp:
  - 450497
categories:
  - Create a wordpress website
  - Hostgator
  - Hosting
  - Web Development
  - Wordpress
tags:
  - hostgator
  - plugins
  - web design
  - web development
  - wordpress website

---

### Update 2021

So the content on this page needs to be refreshed to reflect modern web development. The steps to register the domain name and build the site may not work as shown in the video. I plan to refresh the content on this page.

--

_**This is a Step-by-Step tutorial on how to make a wordpress website. By the end of this article you will have made a fully fledged wordpress website with a Home, About Me, Contact Us and a Blog page. You will learn how to choose a hosting provider, select a domain name, install wordpress on your website, upload your photos/videos and configure your website.**_

_**Time taken to complete this task: 99 &#8211; 140 minutes**_

_**Prerequisites: None**_

There are 2 ways to complete this tutorial. First way is to watch the YouTube video of the tutorial. The second way is to complete this tutorial in parts. Apart from a massive 144 minute YouTube video, I have divided the same video into 10 parts so you can consume the content step-by-step. All of these videos are embedded on this page along with useful text descriptions and the occasional screenshot to clear things up. I leave this choice upto you. **The meat of the learning is in watching the videos**. I have deliberately explained every menial thing that I do while creating the website so you can latch onto the thought process and methodology of creating websites.

* * *

## The FULL video tutorial:

{{<youtube 9lYgK-LDMYE>}}

#### The learning road map

The respective time stamp range is provided next to the task.

Register a domain name & get hosting: 0:00 &#8211; 15:33  
cPanel & Installing WordPress: 15:36 &#8211; 22:25  
Install a WordPress Theme, Create Homepage: 22:27 &#8211; 32:07  
Adding Logos: 32:11 &#8211; 40:17  
Customize Slider/Adding Pages/Image Galleries/Embed YouTube Videos: 40:21 &#8211; 1:01:47  
Adding Blogposts & Portfolio Items: 1:01:50 &#8211; 1:25:01  
Adding Icon Menu/Finishing up the Homepage: 1:25:08 &#8211; 1:33:30  
Adding Contact form/Embed Google Maps/Install Facebook Plugin/configuring the sidebar: 1:33:36 &#8211; 1:51:40  
Adding a Multilevel Menu: 1:51:45 &#8211; 1:56:20  
Add Login Page/Configuring the footer/Add a Favicon/Conclusion: 1:56:24 &#8211; 2:21:43

Download this wordpress theme

Virtue WordPress Theme: <http://www.kadencethemes.com/product/virtue-free-theme/>

* * *

_**For those of you who want to watch the video in parts and follow along with some text and screenshots, proceed ahead:**_

## Introduction

You will never learn what you are about to read in any university or high school. Computer science courses in university focus on teaching you how to program websites. You learn HTML, CSS, JavaScript and PHP/Python. Most websites in the world use these technologies, so these are useful skills to learn. But in college you have only one semester to learn all this. This means that all the focus is on learning how to code. You practice your web development skills on the university machines which take care of storing your webpages on a server. They provide you with a nifty little tool to edit and upload  your code on the cloud and all you have to do is refresh the page to see the changes you have made.

All this is fine but this is only half the picture.  It is only when you come to the industry or when you want to launch a real world website when questions like..

_&#8220;ok, how do i register a .com website?&#8221;_ 

or

_&#8220;ok.what is server hosting and how do i get it?&#8221;_ 

..come to mind. This is VITAL real world information which is left out of university education. Mainly because you need a credit card to register a domain name, ie, a &#8220;.com&#8221; website and most 18 year old university students do not have credit cards.

Registering a domain name, getting hosting, configuring the DNS, migrating code and managing databases are essential tasks that need to be performed when you want to make a website. Fortunately, these are simple to learn and it takes less than a day to get familiar with these technologies. A week if you don&#8217;t know the difference between DNS and HTTP.

You will learn all this as we go over the steps leading to creating your own website.

Having your own website adds tremendous professional pedigree to your online profile. Surely, &#8220;yourname.com&#8221; sounds better than &#8220;yourname.wordpress.com&#8221; or &#8220;yourname.blogspot.freedomain.mycoolfreesite.com&#8221;. :p

Read on to find out how to make your very own website on a domain name of your choice.

## Choosing a hosting provider

or _&#8220;How to choose a web host for my website?&#8221;_

or &#8220;_Where will my website live?_&#8221;

First off, who exactly is a web host. A web host or hosting provider is a server (usually a bunch of servers) which store all the files and databases which constitute your website. A server is just a technical term for an industrial computer whose purpose is to interact with other computers by responding to their requests for data. For example, Facebook stores all the data (profile pics, wall posts, albums, sharing preferences etc) associated with a profile on its servers. Whenever you click on your profile button, your browser sends a request to the [facebook server][2] where your profile information is stored asking for your profile page. Upon receiving this request, the FB server responds to your browser by sending it your profile page with all the data (like first post, profile info etc) and your browser formats the appearance and presents it to you. Facebook owns thousands of such servers which it places in the same room and calls it a &#8220;data center&#8221;.

A web host or hosting provider also owns many such servers in a data center where it stores website data for thousands of websites. If you want to have a website, you HAVE to rent space at some web host. Alternatively, you could convert your computer into a server and save on hosting fees but when you turn your computer off, your website also shuts down. Inconvenient.

Fortunately for us, there are plenty of web hosts. Some good, some awful. Based on my experience, the best web hosts are the ones with excellent customer service. You don&#8217;t want to pay for a cheap host and then have to cluelessly run around trying to figure out how to add a subdomain and do the most basic of website maintenance tasks (or worse when you accidentally break your website and need an expert to revert to your old site).

One web hosting provider which provides excellent customer service at a cheap price is <a title="Hostgator" href="http://secure.hostgator.com/~affiliat/cgi-bin/affiliates/clickthru.cgi?id=svram" target="_blank">Hostgator</a>. These guys have been around for a long time. They have a 24&#215;7 LiveChat service manned by web engineers who patiently solve even the most ridiculous of requests. From database maintenance to website recovery to simple tasks like spoonfeeding you the process of creating an email account are carried out by these blessed customer service reps at Hostgator. I have registered  tens of domain names with Hostgator and introduced many clients to them. In the past 4 years or so, there hasn&#8217;t been a single downtime issue.

If you are serious about having your own website, then you must get hosting. Go to the Hostgator website and move on to the next Step to learn how to purchase hosting and create a domain name.

## Part 1/10: Register a Domain Name & Get Hosting

_After completing this section you will have registered a domain name and acquired hosting with Hostgator._

See the video of Part 1/10 here:  

{{<youtube SbGmUBo5R98>}}
  

_IMPORTANT NOTE: Your domain may take 24-48hours to fully propagate across the web. This means that if your website does not open, just clear your browser history and cache and keep refreshing the page. Either you page may not open or you will get a message from Hostgator saying that it will take 24-48 hours for your domain name to propagate across all the DNS servers around the web. Since this is a new domain, all the name servers have to be notified of a new website and have to update their directories accordingly. This is carried out automatically by Hostgator, so feel free to move on to the next section where you will install wordpress on your website and create a Home page, add a blog post, upload a photo/video and create many boilerplate pages like Contact us etc._

&nbsp;

## Part 2/10: Installing WordPress on your website

_After completing this section you will get acquainted with cPanel and will install wordpress on your website through one-click QuickInstall. You will then proceed to login to your wordpress website, take a short tour of the dashboard and change your password_
See the video here:  

{{<youtube FidLELNpJ4Y>}}
  

## PART 3/10: Install a new WordPress Theme & Create a Homepage

**_After completing this section you will have installed a new theme and created you first page &#8211; the Homepage!_**

See the video here:  

{{<youtube vo0HS__IuEk>}}

## PART 4/10: Add a logo to your website

_**After completing this section you will have added your own logo to the website and will learn how to upload images to your wordpress.**_

See the Video here:

{{<youtube 15A0Wm75Obk>}}

## PART 5/10: Add Slider, Create Pages, Add Images/Image Galleries & Embed YouTube Videos

**After completing this section you will have:**

- added a customized slider to the homepage 
- added 3 pages
- added images to your pages
- added an image gallery to your page
- embedded a video from youtube to your page

See the video here:  

{{<youtube wtD6zATdZr0>}}

## PART 6/10: Adding Blog posts & Portfolio pages of your creative work

_After completing this section you will have:_

- added blog posts with image sliders to your website
- created portfolio pages to display your projects, creative work etc

See the video here:  

{{<youtube evoUwWPV9Fc>}}

## PART 7/10: Adding Icon Menu & completing the Homepage

_After completing this section you will have:_

- added icon menus to the homepage to display features related to the website you are making
- completed customizing the homepage to include blogposts, portfolio slideshow and an icon menu

See the video here:  

{{<youtube ND3oOF4NFqI>}}

## PART 8/10: Contact forms, Embed google maps to your page, add a Facebook &#8216;Like&#8217; box & configure the sidebar

_After completing this section you will have:_

- added a contact form to your contact us page.
- embedded a google map to your page to display your address.
- install the Facebook plugin and add a &#8216;Like&#8217; box to your facebook page on your sidebar
- create and customize your sidebar

See the video here:  

{{<youtube kNnB0qZINb0>}}

## PART 9/10: Add a multi-level menu

_After completing this section you will have:_

- added a multi-level menu to your website.

See the video here:  

{{<youtube jkkJdlrnm1g>}}

## PART 10/10: Customize footer area, add a favicon & a login page

**After completing this section you will have:**
- customized the look and placement of the main menu.
- added a &#8216;login&#8217; page to your website using the &#8216;Theme My Login&#8217; plugin for wordpress 
- customized the footer area of the website
- added a favicon to your website

See the video here:

{{<youtube D75BskKW6RA>}}

 [1]: http://secure.hostgator.com/~affiliat/cgi-bin/affiliates/clickthru.cgi?id=svram
 [2]: https://www.facebook.com/PrinevilleDataCenter