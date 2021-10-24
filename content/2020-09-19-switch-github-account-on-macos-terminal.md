---
title: Switch GitHub account on macOS terminal
author: Vikram Bahl
type: post
date: 2020-09-19T10:27:46+00:00
url: /switch-github-account-on-macos-terminal/
ssb_old_counts:
  - 'a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}'
ssb_cache_timestamp:
  - 450866
categories:
  - GitHub
tags:
  - github
  - macos

---
If you have multiple GitHub accounts and are getting error messages like this while pushing code to the repo

&#8220;remote: Permission to svram/twittering.git denied to <currently-configured-username>  
fatal: unable to access &#8216;https://github.com/svram/<reponame>.git/&#8217;: The requested URL returned error: 403&#8243;

This means that the currently configured username on your terminal is not the one whose repo you are intending to commit code to. The first step to fix this is to list the current configuration like so

`git config --list`

You will get a result which will inform you about the username and email which is currently configured.

<pre lang="bash">credential.helper=osxkeychain
user.name=svram
user.email=&lt;something>@gmail.com
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
core.ignorecase=true
core.precomposeunicode=true
remote.origin.url=https://github.com/svram/reponame.git
remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*
branch.master.remote=origin
branch.master.merge=refs/heads/master</pre>

If your github username and email are not consistent then change those first with

<pre lang="bash">git config --global user.name ""
git config --global user.email ""</pre>

One of the simple ways to do this on macOS is to delete the password of the existing GitHub account configured from the Keychain.

  * Open the Keychain, click on All Items and then search for git. You can delete the password entry which comes.
  * Once this is done, try to do a git push and it should ask you to reauthenticate. I recommend using the [visual studio integration][1]. It makes life really simple while developing code<figure class="wp-block-image size-large">

<img src="/images/keychain.png">

There are other ways to do this which would work across windows, linux and macOS too. That involves generating an SSH keypair and authenticating your terminal/computer with GitHub. I recommend following [this tutorial][2] for the steps.

 [1]: https://visualstudio.github.com/
 [2]: https://medium.com/@aklson_DS/how-to-properly-setup-your-github-repository-mac-version-3a8047b899e5