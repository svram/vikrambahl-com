---
title: Adding Animated Gif’s in iOS Applications using Xcode Storyboards
author: Vikram Bahl
type: post
date: 2014-07-03T02:41:05+00:00
url: /animated-gifs-ios-xcode-storyboards/
ssb_old_counts:
  - 'a:6:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;}'
ssb_cache_timestamp:
  - 450725
categories:
  - iOS Development
  - Software
tags:
  - ios
  - app dev
  - gifs

---
<p style="text-align: left;">
  There is no out of the box support provided by Apple to add animated GIF&#8217;s to your iOS applications. There are many convoluted solutions available on the interwebs. After trying a few, I have come to rely on the super-easy to integrate solution by Flipboard Inc. (key development by Flipboard engineer <a href="http://www.raphaelschaad.com/">Raphael Schaad</a>, follow him <a href="https://twitter.com/raphaelschaad">on twitter</a>)Their library makes it a piece of cake to add animated GIF&#8217;s to your iOS applications using storyboards in Xcode. Following this, your app will support animated GIF&#8217;s. This post will walk you step by step through the process of doing so.
</p>

<p style="text-align: left;">
  Download code from Github: <a href="https://github.com/svram/AnimatedGIF-Xcode-Storyboards-iOS">https://github.com/svram/AnimatedGIF-Xcode-Storyboards-iOS</a>
</p>

<p style="text-align: left;">
  1) This is what your app will look like if you follow all the steps (it&#8217;ll be smoother in the simulation, had to convert a .mov file to gif):
</p>

<img src="/images/flanimatedimage-ios/gifMovie3.gif">

<ul style="text-align: left;">
  <li>
    Open Xcode, create a new project  and choose the &#8220;Single View Application&#8221; template.
  </li>
  <li>
    Enter Product, Organisation & Company names. Enter a class prefix and choose iPhone from the devices drop down menu.
  </li>
  <li>
    Save the project to disk
  </li>
</ul>

<p style="text-align: left;">
  2)  Download Flipboards FLAnimatedImage library from github:
</p>

<p style="text-align: left;">
  <a href="https://github.com/Flipboard/FLAnimatedImage">https://github.com/Flipboard/FLAnimatedImage</a>
</p>

<p style="text-align: left;">
  (Just download the ZIP file to your disk)
</p>

<p style="text-align: left;">
  3) Open Xcode and right-click the project in the project navigator and choose &#8216;New Group&#8217;. A new folder gets added to your project files. Name this folder &#8216;Library&#8217;.
</p>

<img src="/images/flanimatedimage-ios/newgroup.png" alt= "Create new group in Xcode named &#8216;Library&#8217;">

<img src="/images/flanimatedimage-ios/newgroup2.png" alt= "Create new group in Xcode named &#8216;Library&#8217;">

<p style="text-align: left;">
  4) Now open the folder where you saved the FLAnimatedImage library you downloaded in Step 2.
</p>

<p style="text-align: left;">
  Locate the following four files and drag them to the &#8216;Library&#8217; folder in Xcode that you created in Step 3.
</p>

<pre lang="objc">FLAnimatedImage.h

FLAnimatedImage.m

FLAnimatedImageView.h

FLAnimatedImageView.m</pre>

<p style="text-align: left;">
  It should be located in the folder hierarchy:
</p>

<p style="text-align: left;">
  FLAnimatedImage-master -> FLAnimatedImageDemo -> FLAnimatedImage
</p>

<p style="text-align: left;">
  When prompted, select the &#8216;Copy items into destination groups folder&#8217; and click ok.
</p>

<img src="/images/flanimatedimage-ios/dragfiles.png" alt= "Drag and add the FLAnimatedImageView to the Library folder">
    
<img src="/images/flanimatedimage-ios/addToLibrary.png" alt= "Drag and add the FLAnimatedImageView to the Library folder">

<p style="text-align: left;">
  5) Open your ViewController.h and add the following import statements:
</p>

<pre lang="objc">#import "FLAnimatedImage.h"
#import "FLAnimatedImageView.h"</pre>

6) Open the Main Storyboard file and add 3 UIImageView objects from the Object Library in the Utilities area on the right. Resize them so your storyboard looks like the one below.

&nbsp;

<img src="/images/flanimatedimage-ios/addComponents.png" alt= "Drag 3 UIImageView objects to the storyboard">
  
<img src="/images/flanimatedimage-ios/alignComponents.png" alt= "Final storyboard orientation with 3 image views">
  

7) Now click on one of the UIImageView objects that you added to the storyboard and under the Identity Inspector on the right, locate  the &#8216;Custom Class&#8217; section. In the &#8216;Class&#8217; text field enter &#8216;FLAnimatedImageView&#8217;.

Do this for all 3 UIImageView objects. The objects are of type FLAnimatedImageView which is a subclass of UIImageView.

<img src="/images/flanimatedimage-ios/changeClass.png" alt= "Change the class of each of the image views to FLAnimatedImageView in the Identity Inspector in Xcode">

8) Open the Assistance Editor in Xcode such that the Storyboard and your ViewController.h files are side by side.

Control drag from each of the image views in the storyboard to your ViewController.h file between the @interface and @end statements. Give your outlet a name and let it be of type FLAnimatedImageView. At the end of it, your ViewController.h file should look like this:

<pre lang="objc">#import &lt;UIKit/UIKit.h&gt;
#import "FLAnimatedImageView.h"
#import "FLAnimatedImage.h"

@interface VBViewController : UIViewController
@property (strong, nonatomic) IBOutlet FLAnimatedImageView *lightningImageView;
@property (strong, nonatomic) IBOutlet FLAnimatedImageView *manWalkingImageView;

@property (strong, nonatomic) IBOutlet FLAnimatedImageView *pageLoadingImageView;

@end</pre>

<img src="/images/flanimatedimage-ios/addCode.png" alt= "Connect outlets from the FLAnimatedImageViews in the storyboard to the ViewController.h file">

9) With your view controller selected in the storyboard, we will add a navigation controller for aesthetics sake. In the menubar, go to Editor -> Embed In -> Navigation Controller.

<img src="/images/flanimatedimage-ios/embed.png" alt= "Add a navigation controller in Xcode storyboard">

10) Open your ViewController.m file and add code to the viewDidLoad: method to set the title of the navigation bar.

<pre lang="objc">self.title = @"I Love GIF's";</pre>

Now, we will add 3 gifs to each of the image views programmatically. First download them to your disk here:

http://vikrambahl.com/wp-content/uploads/2014/07/manWalking.gif

http://vikrambahl.com/wp-content/uploads/2014/07/lightning.gif

The third GIF we will load via a URL.

Just right click and save it.

Once saved, add it to your project by dragging the images to your project folder in Xcode. When prompted, select Copy items into destination groups folder.

<img src="/images/flanimatedimage-ios/addGifs.png" alt= "Adding GIF&#8217;s to the project folder in Xcode">

11) Now we will load each of the three images with FLAnimatedImage instead of UIImage. Add the following code to your viewDidLoad: method in your ViewController.m file:

<pre lang="objc">FLAnimatedImage *manWalkingImage = [[FLAnimatedImage alloc] initWithAnimatedGIFData:[NSData dataWithContentsOfFile:[[NSBundle mainBundle] pathForResource:@"manWalking" ofType:@"gif"]]];

FLAnimatedImage *lightningImage = [[FLAnimatedImage alloc] initWithAnimatedGIFData:[NSData dataWithContentsOfFile:[[NSBundle mainBundle] pathForResource:@"lightning" ofType:@"gif"]]];

FLAnimatedImage *loadingImage = [[FLAnimatedImage alloc] initWithAnimatedGIFData:[NSData dataWithContentsOfURL:[NSURL URLWithString:@"http://vikrambahl.com/wp-content/uploads/2014/06/ajax_loader_blue_512.gif"]]];</pre>

Now,  assign the FLAnimatedImage types to each of the FLAnimatedImageViews via the animatedImage property:

<pre lang="objc">self.lightningImageView.animatedImage = lightningImage;</pre>

And add the FLAnimatedImage view objects as subviews:

<pre lang="objc">[self.view addSubview:self.lightningImageView];</pre>

Finally, your viewDidLoad: method should look like this:

<pre lang="objc">- (void)viewDidLoad

{

[super viewDidLoad];

// Do any additional setup after loading the view, typically from a nib.

//Set the title of the naviagation bar

self.title = @"I Love GIF's";

//Add the gifs as FLAnimatedImage objects

FLAnimatedImage *manWalkingImage = [[FLAnimatedImage alloc] initWithAnimatedGIFData:[NSData dataWithContentsOfFile:[[NSBundle mainBundle] pathForResource:@"manWalking" ofType:@"gif"]]];

FLAnimatedImage *lightningImage = [[FLAnimatedImage alloc] initWithAnimatedGIFData:[NSData dataWithContentsOfFile:[[NSBundle mainBundle] pathForResource:@"lightning" ofType:@"gif"]]];

//Loading a gif from URL

FLAnimatedImage *loadingImage = [[FLAnimatedImage alloc] initWithAnimatedGIFData:[NSData dataWithContentsOfURL:[NSURL URLWithString:@"http://vikrambahl.com/wp-content/uploads/2014/06/ajax_loader_blue_512.gif"]]];

//Assign the FLAnimatedImage types to each of the FLAnimatedImageViews via the animatedImage property

self.lightningImageView.animatedImage = lightningImage;

self.manWalkingImageView.animatedImage = manWalkingImage;

self.pageLoadingImageView.animatedImage = loadingImage;

//Add the FLAnimatedImage view objects as subviews

[self.view addSubview:self.lightningImageView];

[self.view addSubview:self.manWalkingImageView];

[self.view addSubview:self.pageLoadingImageView];

}</pre>

Now just run the program in the simulator and you should see your three GIFs loading perfectly.