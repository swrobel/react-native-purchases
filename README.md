
<p align="center">
  <img src="https://uploads-ssl.webflow.com/5e2613cf294dc30503dcefb7/5e752025f8c3a31d56a51408_logo_red%20(1).svg" width="350" alt="RevenueCat"/>
<br>
React Native in-app subscriptions made easy
</p>

# What is react-native-purchases?

React Native Purchases is a client for the [RevenueCat](https://www.revenuecat.com/) subscription and purchase tracking system. It is an open source framework that provides a wrapper around `StoreKit`, `Google Play Billing` and the RevenueCat backend to make implementing in-app purchases in `React Native` easy.

## Features
|   | RevenueCat |
| --- | --- |
✅ | Server-side receipt validation
➡️ | [Webhooks](https://docs.revenuecat.com/docs/webhooks) - enhanced server-to-server communication with events for purchases, renewals, cancellations, and more   
🎯 | Subscription status tracking - know whether a user is subscribed whether they're on iOS, Android or web  
📊 | Analytics - automatic calculation of metrics like conversion, mrr, and churn  
📝 | [Online documentation](https://docs.revenuecat.com/docs) up to date  
🔀 | [Integrations](https://www.revenuecat.com/integrations) - over a dozen integrations to easily send purchase data where you need it  
💯 | Well maintained - [frequent releases](https://github.com/RevenueCat/purchases-ios/releases)  
📮 | Great support - [Help Center](https://revenuecat.zendesk.com) 

## Requirements

The minimum React Native version this SDK requires is `0.64`.

## Installation

ExpoKit projects of version 33 or higher can successfully use react-native-purchases. If you haven't upgraded, you can follow [the instructions here to upgrade](https://docs.expo.io/versions/latest/expokit/expokit/#upgrading-expokit). 

If you're planning on ejecting from Expo, upgrade your expo version _first_, THEN eject. It'll save you a whole lot of hassle.

### Add the library to the project

`$ npm install react-native-purchases --save`
or
`$ yarn add react-native-purchases`

### Link library to the project

`$ react-native link react-native-purchases`

### Additional iOS Setup

#### If your project uses Cocoapods
If your project already uses Cocoapods to install iOS dependencies, common in ExpoKit projects, linking the library should have added it to the podfile. If it hasn't, add the following to your project's podfile to reference the library from your node_modules folder:

```ruby
pod 'RNPurchases', :path => '../node_modules/react-native-purchases'
    :inhibit_warnings => true
```

In your `ios` folder, run `pod install`. If you've just upgraded ExpoKit, you might need to upgrade cocoapods to the newest version: `sudo gem install cocoapods`. 

#### Migrating from manual installation (if your project doesn't use CocoapodsCreate)

##### Remove the Framework Reference from your project

1. Remove `Purchases.framework` and `PurchasesHybridCommon.framework` from the libraries section of the project. 

##### Remove iOS Frameworks to Embedded Binaries
1. In Xcode, in project manager, select your app target.
1. Select the general tab
1. Look for `Purchases.framework` and `PurchasesHybridCommon.framework` in the Embedded Binaries section and remove them.

Remove `$(PROJECT_DIR)/../node_modules/react-native-purchases/ios` from Framework Search paths in build settings

##### Remove Strip Frameworks Phase
During the old manual installation instructions, now deprecated, we indicated to add a build phase to strip fat frameworks. 
1. In Xcode, in project manager, select your app target.
2. Open the `Build Phases` tab
3. Remove the added `Strip Frameworks` phase
4. Clean `Derived Data` 

##### Link static library
The `react-native link` command should have added the `libRNPurchases.a` library to the _Linked Frameworks and Libraries_ section of your app target. If it hasn't add it like this:

![](https://media.giphy.com/media/U2MMgrdYlkRhEcy80J/giphy.gif)

## Getting Started

Please follow the [Quickstart Guide](https://docs.revenuecat.com/docs/) for more information on how to use the SDK
