---
title: Google Maps SDK for iOS in Xcode Storyboard
author: Vikram Bahl
type: post
date: 2014-07-01T05:20:40+00:00
url: /google-maps-ios-xcode-storyboards/
ssb_old_counts:
  - 'a:6:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;}'
ssb_fbshare_counts:
  - 8
ssb_total_counts:
  - 8
ssb_cache_timestamp:
  - 450869
categories:
  - Google Maps SDK
  - iOS Development
tags:
  - ios
  - app dev
  - google maps

---
Developing a location based application on iOS with Google Maps is super easy with the Google Maps SDK for iOS. So here’s the complete step-by-step way to add a google map to your iOS application using storyboards in Xcode 5.

This is what your app will look like in the end:

[![Google Maps in iPhone using Xcode Storyboards](/images/google-maps-ios/finalApp.png "Google Maps in iPhone using Xcode Storyboards")](/images/google-maps-ios/finalApp.png)


Download code from Github: [https://github.com/svram/GoogleMapSDKiOS-Storyboards](https://github.com/svram/GoogleMapSDKiOS-Storyboards)

1. Download the Google Maps SDK for iOS:

[https://developers.google.com/maps/documentation/ios/start#getting_the_google_maps_sdk_for_ios](https://developers.google.com/maps/documentation/ios/start#getting_the_google_maps_sdk_for_ios)

The current version is 1.8.1

2. Obtain an API key from the Google Developers console. Do the easy to follow instructions here:

[https://developers.google.com/maps/documentation/ios/start#the_google_maps_api_key](https://developers.google.com/maps/documentation/ios/start#the_google_maps_api_key)

3. Setup Xcode Environment to work with Google Maps SDK

a) Open Xcode and Create a new project.

b) Create a new ‘Single View Application’ template.

[![Create Single View Application in Xcode](/images/google-maps-ios/singleViewApp.png)](/images/google-maps-ios/singleViewApp.png)

Create Single View Application in Xcode

c) Enter Product, Organization & Company names. Enter a class prefix and choose iPhone from the devices drop down menu.

[![Add product name, company etc](/images/google-maps-ios/add-details.png)](/images/google-maps-ios/add-details.png)

Add product name, company etc

d) Save your project to disk.

e) Unzip and open the Google Maps iOS SDK that you downloaded in Step 1.

[![Google Maps SDK iOS folder on desktop](/images/google-maps-ios/add-framework.png "Google Maps SDK iOS folder on desktop")](/images/google-maps-ios/add-framework.png)


f) Add the “GoogleMaps.framework” bundle to the “Frameworks” Folder in Xcode by dragging it there. When prompted, select “Copy items into destination group’s folder”.

[![Drag the GoogleMaps.framework bundle to the Frameworks folder in Xcode](/images/google-maps-ios/drag-image.png "Drag the GoogleMaps.framework bundle to the Frameworks folder in Xcode")](/images/google-maps-ios/drag-image.png)


[![Select Copy items into destination group's folder](/images/google-maps-ios/copy-items.png "Select Copy items into destination group's folder")](/images/google-maps-ios/copy-items.png)

g) Similarly, drag the “GoogleMaps.bundle” from the  _GoogleMaps.framework -> Resources_  folder to the “Frameworks” folder in Xcode. When prompted DO NOT select “Copy items into destination group’s folder”.

f) Then, select your project from the Project Navigator and select your applications “Target” (not the “Project”).

[![Select applications Target in project navigator](/images/google-maps-ios/select-target.png "Select applications Target in project navigator")](/images/google-maps-ios/select-target.png)

g) Then go to the “Build Phases” tab and then open “Link Binary With Libraries”. Then click on the “+” button at the bottom left and add the following libraries to be compiled along with your app binaries:

-   AVFoundation.framework
-   CoreData.framework
-   CoreLocation.framework
-   CoreText.framework
-   GLKit.framework
-   ImageIO.framework
-   libc++.dylib
-   libicucore.dylib
-   libz.dylib
-   OpenGLES.framework
-   QuartzCore.framework
-   SystemConfiguration.framework

[![Go To Build Phases -> Link Binary With Libraries](/images/google-maps-ios/build-phases.png "Go To Build Phases -> Link Binary With Libraries")](/images/google-maps-ios/build-phases.png)

[![Add the frameworks](/images/google-maps-ios/add-frameworks.png "Add the frameworks")](/images/google-maps-ios/add-frameworks.png)

This is what your Xcode environment should look like:

[![XCode environment after adding the frameworks](/images/google-maps-ios/after-adding-frameworks.png "XCode environment after adding the frameworks")](/images/google-maps-ios/after-adding-frameworks.png)

h) Now choose your “Project” rather than a “Target” and open the “Build Settings” tab. Scroll down till you find the “Linking” section and under that find “Other Linker Flags”. Now open the section and click the “+” next to “Debug” and add “-ObjC” in the text field. If these settings are not visible, change the filter in the “Build Settings” to “All” instead of “Basic”.

[![Add the '-ObjC' flag in Other Linker Flags under Build Settings tab](/images/google-maps-ios/other-linker-flags.png "Add the '-ObjC' flag in Other Linker Flags under Build Settings tab")](/images/google-maps-ios/other-linker-flags.png)

Add the ‘-ObjC’ flag in Other Linker Flags under Build Settings tab

4. Begin Coding

a) Open your AppDelegate.m file and add the following import statement:

    #import <GoogleMaps/GoogleMaps.h>;
    
    //Copy the API Key you created in Step 2 and enter the following code in the method
    
    application: didFinishLaunchingWithOptions:
    
    [GMSServices provideAPIKey:@"API_KEY"];

Replace API_KEY with your API key.

[![Add Google Maps API Key to the AppDelegate.m application:didFinishLaunchingWithOptions: method](/images/google-maps-ios/add-api-key.png "Add Google Maps API Key to the AppDelegate.m application:didFinishLaunchingWithOptions: method")](/images/google-maps-ios/add-api-key.png)


b) Open “Main.Storyboard” and drag a UIView object from the Object Library. Now open the Identity Inspector and under Custom Class add “GMSMapView”.

[![Drag a UIView from object library to the main storyboard](/images/google-maps-ios/drag-uiview.png "Drag a UIView from object library to the main storyboard")](/images/google-maps-ios/drag-uiview.png)

[![Assign Custom class 'GMSMapView' to the UIView object in the Identity Inspector](/images/google-maps-ios/add-custom-class.png "Assign Custom class 'GMSMapView' to the UIView object in the Identity Inspector")](/images/google-maps-ios/add-custom-class.png)


c) Control drag from the UIView (GMSMapView) object to your ViewController.h file to create an outlet with the name “mapView”. Don’t forget to add the GoogleMaps import statement in your ViewController.h file.

[![Create an outlet for the GMSMapView object in the ViewController.h file](/images/google-maps-ios/mapview-outlet.png "Create an outlet for the GMSMapView object in the ViewController.h file")](/images/google-maps-ios/mapview-outlet.png)

d) Make the ViewController conform to the “GMSMapViewDelegate” protocol.

[![Make the ViewController conform to the GMSMapViewDelegate protocol](/images/google-maps-ios/delegate-protocol.png "Make the ViewController conform to the GMSMapViewDelegate protocol")](/images/google-maps-ios/delegate-protocol.png)


e) Finally, add the following code to your ViewController.m file in the viewDidLoad: method

    //Controls whether the My Location dot and accuracy circle is enabled.
     
    self.mapView.myLocationEnabled = YES;
     
    //Controls the type of map tiles that should be displayed.
     
    self.mapView.mapType = kGMSTypeNormal;
     
    //Shows the compass button on the map
     
    self.mapView.settings.compassButton = YES;
     
    //Shows the my location button on the map
     
    self.mapView.settings.myLocationButton = YES;
     
    //Sets the view controller to be the GMSMapView delegate
     
    self.mapView.delegate = self;

[![viewDidLoad: method in ViewController.m](/images/google-maps-ios/viewdidload.png "viewDidLoad: method in ViewController.m")](/images/google-maps-ios/viewdidload.png)

f) Now run the app in the simulator. Choose a location from the Debug -> Location menu option. Click on the my location button the app to move to your current location. And done!

[![iOS Simulator choose location from Debug -> Location](/images/google-maps-ios/debug-location.png "iOS Simulator choose location from Debug -> Location")](/images/google-maps-ios/debug-location.png)

[![Successfully added a google map to Xcode storyboard](/images/google-maps-ios/successful-maps-add.png "Successfully added a google map to Xcode storyboard")](/images/google-maps-ios/successful-maps-add.png)

g) Almost done. Finally some cosmetic changes. Go to your main storyboard and click on the view controller. Now go to the menu add a navigation controller by choosing “Editor -> Embed In -> Navigation Controller”.

This will add a navigator controller to your main storyboard.

Next give the navigation bar a title by adding the following code in your ViewController.m file:

self.title = @"Google Maps in iOS";

Feel free to add any other UIView objects. I have added a dummy button and a UITextView object.

[![Embed a Navigation Controller](/images/google-maps-ios/embed-navcontroller.png "Embed a Navigation Controller")](/images/google-maps-ios/embed-navcontroller.png)

Get the project files on  [Github](https://github.com/svram/GoogleMapSDKiOS-Storyboards).