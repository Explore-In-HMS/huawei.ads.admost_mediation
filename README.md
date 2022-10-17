 <h1 align="center">Huawei-AdMost Mediation Github Documentation</h3>
 
 
 ![Latest Version](https://img.shields.io/badge/latestVersion-2.6.6-yellow)
<br>
![Supported Platforms](https://img.shields.io/badge/Supported_Platforms:-Native_Android_-orange)


# Introduction

In this documentation we explained how to use Huawei-AdMost mediation plugin developed by AdMost. 
AdMost repository link is [here](https://github.com/admost/amrandroid)


# Compatibility

|   | Banner Ad | Interstitial Ad | Rewarded Ad | Native Ad |
| --- | --- | --- | --- | --- |
| Native (Java/Kotlin) | ✅ | ✅ | ✅ | ✅ |  ✅ |
| Unity |✅ |✅| ✅ | ❌ | ✅ |



# How to start?

## Create an ad unit on Huawei Publisher Service

1. Sign in to [Huawei Developer Console](https://developer.huawei.com/consumer/en/console) and create an AdUnit

## Create a mediation network on AdMost


1. Sign in to [AdMost Dashboard](https://dashboard.admost.com/Login.aspx)
2. Click on the "**+**" sign on the "**Networks Credentials**" page and activate "**Huawei Ads Network**"
3. Create an "**Ad Zone**" Select your app and click on "**+Zone**" 
4. Click on the "**Placements**"tab next to your app, then click on  "**+New Placement**". These actions are all taken on the My Apps page.
5. After that, Users can list, edit, and delete all of your placements from  "**Placements**" tab next to the app
6. Follow this [link](https://admost.github.io/amrandroid/) for the next integration steps
   <br>



   **Note:** This [link](https://admost.github.io/) also can be useful.
   
   
   
<h1 id="integrate-huawei-sdk">
Integrate the Huawei-AdMost Mediation SDK
</h1>

In the **project-level** build.gradle, include necessary Maven repositories.

```groovy
repositories {
    maven { url 'http://repo.admost.com:8081/artifactory/amr'; allowInsecureProtocol true } // Add this line
    maven { url 'https://developer.huawei.com/repo/' } // Add this line
   
}

...

allprojects {
    repositories {
        maven { url 'http://repo.admost.com:8081/artifactory/amr'; allowInsecureProtocol true } // Add this line
        maven { url 'https://developer.huawei.com/repo/' } // Add this line
        
    }
}
```

<h1 id="app-level">
</h1>
In the app-level build.gradle, include necessary dependencies

```groovy
dependencies {
    implementation 'com.android.volley:volley:1.2.1' 
    implementation 'com.admost.sdk:amr:2.6.6' 
    implementation 'com.google.android.gms:play-services-base:17.1.0' 
    implementation 'com.admost.sdk:admost-adapter:1.1.1.a32' 
    implementation 'com.admost.sdk:huawei-ads-adapter:3.4.55.302.a32' 
    implementation 'com.huawei.hms:ads-identifier:3.4.46.300'
    https://admost.github.io/amrandroid/
}
```   
 [Check the latest version here](https://admost.github.io/amrandroid/) <br>

**Important Note :** AdMost-Huawei Mediation SDK is released and maintained by AdMost team. Please use [this](https://admost.github.io/amrandroid/) link if you have any issues or feedbacks.



## **Permissions**
The HUAWEI Ads SDK (com.huawei.hms:ads) has integrated the required permissions. Therefore, you do not need to apply for these permissions. <br />

**android.permission.ACCESS_NETWORK_STATE:** Checks whether the current network is available.   <br/>

**android.permission.ACCESS_WIFI_STATE:** Obtains the current Wi-Fi connection status and the information about WLAN hotspots. <br />

**android.permission.BLUETOOTH:** Obtains the statuses of paired Bluetooth devices. (The permission can be removed if not necessary.) <br />

**android.permission.CAMERA:** Displays AR ads in the Camera app. (The permission can be removed if not necessary.) <br />

**android.permission.READ_CALENDAR:** Reads calendar events and their subscription statuses. (The permission can be removed if not necessary.) <br />

**android.permission.WRITE_CALENDAR:** Creates a calendar event when a user clicks the subscription button in an ad. (The permission can be removed if not necessary.) <br />

## **Configuring Obfuscation Scripts**
Before building the APK, configure the obfuscation configuration file to prevent the HUAWEI Ads SDK () from being obfuscated.

Open the obfuscation configuration file proguard-rules.pro in the app-level directory of your Android project, and add configurations to exclude the HUAWEI Ads SDK from obfuscation.

```groovy
-keep class com.huawei.openalliance.ad.** { *; }
-keep class com.huawei.hms.ads.** { *; }
```

## **Configuring Network Permissions**
To allow HTTP and HTTPS network requests on devices with targetSdkVersion 28 or later, configure the following information in the AndroidManifest.xml file :

```groovy
<activity
    ...
    android:usesCleartextTraffic="true"
    >
    ...
</activity>
```



# Version Change History

## 2.6.6
Latest version




# Platforms

## Native

This section demonstrates how to use AdMost mediation feature with Huawei Ads Kit on Native android app.

Firstly, integrate the AdMost Mediation SDK for Android

[AdMost Mediation SDK](https://admost.github.io/amrandroid/) can be used for all ad types.

**Note** : 
1) Developers can find app level build.gradle in their project from __**"app-folder/app/build.gradle"**__
2) If you use the native ad format in your application, please submit a ticket [here](https://developer.huawei.com/consumer/en/support/feedback) to get support from Huawei. 

### **Banner Ad**

To use _Banner_ ads in Native android apps, please check the AdMost Mediation SDK. Click [here](https://admost.github.io/amrandroid/#banner-ads) to get more information about  AdMost Mediation SDKs Banner Ad development.

### **Interstitial Ad**

To use _Interstitial_ ads in Native android apps, please check the AdMost Mediation SDK. Click [here](https://admost.github.io/amrandroid/#interstitial-ads) to get more information about  AdMost Mediation SDKs Interstitial Ad development.

### **Rewarded Ad**

To use _Rewarded_ ads in Native android apps, please check the AdMost Mediation SDK. Click [here](https://admost.github.io/amrandroid/#rewarded-ads) to get more information about  AdMost Mediation SDKs Rewarded Ad development.

### **Native Ads**

To use _Native_ ads in Native android apps, please check the AdMost Mediation SDK. Click [here](https://admost.github.io/amrandroid/#native-ads) to get more information about  AdMost Mediation SDKs Native Ad development.



 
# Screenshots

<table>
<tr>
<td>
<img src="https://user-images.githubusercontent.com/44730864/196098529-83b1a65b-cdc4-48a2-9dbd-7a92108e68d5.jpg" width="200">

Banner Ad
</td>

<td>
<img src="https://user-images.githubusercontent.com/44730864/196098547-bf8373c5-5bf7-4e52-9bd6-2e5d88b544ee.jpg" width="200">


Interstitial Ad
</td>

<td>
<img src="https://user-images.githubusercontent.com/44730864/196098564-36308139-ae12-4a4e-bece-ebf894a17b6f.jpg" width="200">

Rewarded Ad
</td>

<td>
<img src="https://user-images.githubusercontent.com/44730864/196098726-0239cc25-e17a-4f96-b592-c51d77d992ea.jpg" width="200">

Native Ad
</td>

</tr>
</tr>
</table>









