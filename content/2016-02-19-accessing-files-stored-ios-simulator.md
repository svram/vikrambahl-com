---
title: Accessing files stored by the iOS Simulator
author: Vikram Bahl
type: post
date: 2016-02-19T08:14:49+00:00
url: /accessing-files-stored-ios-simulator/
ssb_old_counts:
  - 'a:6:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;}'
ssb_cache_timestamp:
  - 450709
categories:
  - Apple
  - iOS Development
  - OSX
  - Software
  - Xcode
tags:
  - ios
  - app dev

---
iOS provides limited access to the directory structure for your device. You may often wonder what it looks like. If you are creating a temporary plist or generating a text file, you may want to see where exactly it gets stored on your device. For those with non-jailbroken devices, this can be a difficult task. Yes, you can always work with relative paths inside Xcode and there&#8217;s no problem, but certain frameworks generate files which are stored locally on the device. For eg.,  the [OpenEars][1] library running the [CMU speech recognition][2] engine generates a dictionary and language model (.arpa and .DMP) and stores it &#8216;somewhere&#8217; on the device. To access the directory structure for your iOS simulator, type in the following command in Terminal:

&nbsp;

<pre lang="bash">open -R `find ~/Library/Developer/CoreSimulator/Devices \
 -type d -depth 5 -name "*.app" -print0 | xargs -0 stat -f \
 "%m %N" | sort -rn | head -1 | cut -f2- -d" "`

</pre>

That will open the folder where your simulator has stored your filed. Now you just have to search for your filename and voila. Note that the above command opens up 5 levels deep in your folder structure. So you may have to move up a few level and then search for the file you are looking for.

<img src="/images/macos-folder.png">

 [1]: http://www.politepix.com/openears/
 [2]: http://cmusphinx.sourceforge.net/wiki/
 [3]: https://i1.wp.com/vikrambahl.com/wp-content/uploads/2016/02/Screenshot-2016-02-19-16.09.16.png