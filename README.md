# MobusiMediationSDK-iOS

## MobusiMediation iOS SDK Swift 

MobusiMediationLayer SDK iOS version [iOS](ios.cs).

The current **version (2.2.1)** is tested with  **Xcode8 or above** and is compatible with  **iOS 8 and above.**

### Apply Framework To Your Project

Add the MobusiMediationLayer.framework to your project in General tab Linked Frameworks and Libraries. Now you must add the following frameworks and libs to your project in General tab Linked Frameworks and Libraries.

      AdSupport.framework
      AudioToolbox.framework
      AVFoundation.framework
      CFNetwork.framework
      CoreGraphics.framework
      CoreMedia.framework
      EventKit.framework
      EventKitUI.framework
      Foundation.framework
      libz.dylib or libz.tbd
      libc++.tbd
      MediaPlayer.framework
      QuartzCore.framework
      StoreKit.framework
      SystemConfiguration.framework
      UIKit.framework
      WebKit.framework

Lastly, add the following values to the **Other Linker Flags** in the **Build Settings** field: 

      -ObjC,-fobjc-arc

You must create a header file (.h) and add to your project, for example called "Mobusi-Bridging-Header.h", and add this line of code to it:

```objectivec
#import <MobusiMediationLayer/MobusiMediationLayer.h>
```
Now in build settings tab in "Swift Compiler - General" in the field "Objective-C Bridging Header" add the file create above. Now you are ready to use the MobusiMediation with Swift.

### Implementation 

Launch the SDK with the following action setting **App ID** as parameter and **uIViewController** as delegate. 

```objectivec
MobusiMediation.initWithAppID("App ID", autoFetch: true, delegate: self, viewController: self)
```

Below are the following methods of how to request different ad formats, the parameters are the
“delegate” and the “zone” refers to where the advertising format can be kept track of.

```objectivec
MobusiMediationLayer.showBannerAd(with: self, zone: "home", viewController: self)
MobusiMediationLayer.showInterstitialAd(with: self, zone: "home", viewController: self)
MobusiMediationLayer.showRewardedVideoAd(with: self, zone: "home", viewController: self)
```objectivec

The parameter zone is to tag your ads, for now is unavailable.

To optimize the integration, the following methods are provided:

```objectivec
 func  advertLoaded(_ provider: String!, view advert: MMLBannerView!, type: MMLType, zone zoneId: String!) {
    }


 func advertDidInteract(_ provider: String!, type: MMLType, zone: String!) {
        
    }

 func advertDidPresentScreen(_ provider: String!, type: MMLType, zone: String!) {
        
    }

 func advertDidDismissScreen(_ provider: String!, type: MMLType, zone: String!) {
        
    }

 func advertWebViewDidClose(_ provider: String!, type: MMLType, zone zoneId: String!) {
        
    }

 func advertsRequestFail(_ provider: String!, type: MMLType, zone zoneId: String!) {
        
    }

 func rewardUser(_ provider: String!, type: MMLType, zone zoneId: String!) {
        
    }
```
