---
title: Python code to list all files in a directory
author: Vikram Bahl
type: post
date: 2014-03-16T11:26:48+00:00
url: /python-code-to-list-all-files-in/
ssb_old_counts:
  - 'a:6:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;}'
ssb_cache_timestamp:
  - 447281
categories:
  - Python
tags:
  - python

---
Python contains useful modules to execute file and folder operations. It makes use of the &#8216;os&#8217; module to carry out file system operations. To illustrate, the python code to get the current working directory is:

<pre lang="python">import os 
os.getcwd()</pre>

.  
On OSX, the output of that is:

<pre lang="bash">'/Users/vikrambahl/Documents'</pre>

.  
The &#8216;os&#8217; module makes it easy to manipulate files and folders on a file system. To list all the files in a directory, you type in the following code:

<pre lang="python">import os
os.listdir(os.getcwd())</pre>

The piece of code above will return a list of all the files contained in the directory specified within the parentheses of &#8216;os.listdir()&#8217;. In this case, it will list out all the files contained in the current directory as specified by the function call &#8216;os.getcwd()&#8217;.  
The usage is:

<pre lang="python">os.listdir()</pre>

The output of the command on idle is something like:

<pre lang="bash">['.DS_Store', '.localized', 'Digital Editions', 'Microsoft User Data', 'RDC Connections', 'signal_processing', 'wallapers']</pre>

Find out more about the &#8216;os&#8217; module at the [python docs.][1]

 [1]: http://docs.python.org/2/library/os.html