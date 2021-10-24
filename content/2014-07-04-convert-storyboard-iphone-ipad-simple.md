---
title: Converting Storyboard from iPhone to iPad in 4 simple steps
author: Vikram Bahl
type: post
date: 2014-07-04T09:56:41+00:00
url: /convert-storyboard-iphone-ipad-simple/
ssb_old_counts:
  - 'a:6:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;}'
ssb_cache_timestamp:
  - 449424
categories:
  - iOS Development
  - Xcode
tags:
  - ios
  - app dev

---
Developing a universal iOS app means that you have to maintain two storyboards. Sometimes, all you want is your iPad user interface to be somewhat similar to your iPhone UI. However, making 2 interfaces is a big pain and a mega resource expender. The solution is simple. Just create your iPhone UI in Xcode as you do, then to make a new storyboard for the iPad without doing unnecessary back breaking, do the following steps:

1) Make a copy of your iPhone storyboard in Xcode. You can do this by right clicking on the storyboard file in Xcode and selecting &#8220;Show in Finder&#8221;. Now locate the storyboard file in the finder window that pops (you may have to go into a few folders to find it). Copy the file to desktop and rename it &#8220;MainStoryboard_iPad.storyboard&#8221;

2) Now open this file &#8220;MainStoryboard_iPad.storyboard&#8221; in a text editor like Text Wrangler or Sublime Text etc.

3) Now perform the following 2 search and replaces in the &#8220;MainStoryboard_iPad.storyboard&#8221; file:

  * Search for 
    <pre>targetRuntime="iOS.CocoaTouch"</pre>
    
    and replace it with
    
    <pre>targetRuntime="iOS.CocoaTouch.iPad"</pre>
    
    &nbsp;</li> 
    
      * Search for 
        <pre>&lt;simulatedScreenMetrics key="destination" type="retina4"/&gt;</pre>
        
        and replace it with
        
        <pre>&lt;simulatedScreenMetrics key="destination"/&gt;</pre></ul> 
    
    &nbsp;
    
    4) Save the file. Reopen Xcode and add this file to the project either by dragging and dropping to the project folder or by going to File -> Add Files to <your-project-name>
    
    Now head over to the &#8216;General&#8217; section by choosing your applications target in Xcode. Under &#8216;Deployment Info&#8217;, choose iPad from &#8216;Devices&#8217;. A pop-up will appear asking if you want to copy the iPhone interface and use it for iPad. Choose &#8216;Dont Copy&#8217;. Now from the &#8216;Main Interface&#8217; drop down menu, choose &#8220;MainStoryboard_iPad.storyboard&#8221; .
    
    And done!
    
    You may have to re-arrange all the views in your interface but thats not really much of a headache compared to creating a new UI from scratch.
    
    Inspiration for this post: <http://stackoverflow.com/questions/8465769/converting-storyboard-from-iphone-to-ipad>
    
    [ ][1]

 [1]: http://stackoverflow.com/questions/8465769/converting-storyboard-from-iphone-to-ipad