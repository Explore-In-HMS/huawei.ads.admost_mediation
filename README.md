 <h1 align="center">Huawei-AdMost Mediation Github Documentation</h3>
 
 
 ![Latest Version](https://img.shields.io/badge/latestVersion-2.6.6-yellow)
<br>
![Supported Platforms](https://img.shields.io/badge/Supported_Platforms:-Native_Android_,_Unity_-orange)


# Introduction

In this documentation we explained how to use Huawei-AdMost mediation plugin developed by AdMost. 
AdMost repository link is [here](https://github.com/admost)


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
4. Click on the "**Placements**"tab next yo tour app, then click on  "**+New Placement**". These actions are all taken on the My Apps page.
5. After that, Users can list, edit,  anddelete all of your placements from  "**Placements**" tab next to the app
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

## 13.4.49.301.3
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




 ## Unity
 
 This section demonstrates how to use AdMost mediation feature with Huawei Ads Kit on Unity.
 
 **Supported Ad Formats are:** Banner Ads, Interstitial Ads, Rewarded Vide Ads and Offerwall Ads.
 
 Firstly, integrate the AdMost Unity SDK to Unity.

 For more details on AdMost Unity SDK visit [here](https://admost.github.io/amrunity/)
 
 ### **Banner Ads**
To use Banner ads in Unity , please check the AdMost Unity SDK. Click [here](https://admost.github.io/amrunity/#banner-ads) to get more information about AdMost Unity SDKs Banner Ad development. 

### **Interstitial Ads**
To use Interstitial ads in Unity , please check the AdMost Unity SDK. Click [here](https://admost.github.io/amrunity/#interstitial-ads) to get more information about AdMost Unity SDKs Interstitial Ad development. 

### **Rewarded Ads**
To use Rewarded ads in Unity , please check the AdMost Unity SDK. Click [here](https://admost.github.io/amrunity/#rewarded-ads) to get more information about AdMost Unity SDKs Rewarded Ad development. 

### **Offerwall Ads**
To use Offerwall ads in Unity , please check the AdMost Unity SDK. Click [here](https://admost.github.io/amrunity/#offerwall-ads) to get more information about AdMost Unity SDKs Offerwall Ad development. 

#### **Step 1:** 
Make sure to switch to the Android Platform from **Build Settings -> Android -> Switch Platform**
#### **Step 2:**
**Edit -> Project Settings ->  Player -> Other Settings**<br>
In Other Settings set minimum API level to at least **21**.
#### **Step 3:**
**Edit -> Project Settings ->  Player -> Publishing Settings**<br>
In Publishing Settings select **“Custom Main Gradle Template”** , **“Custom Base Gradle Template”** and **“Custom Greadle Properties Template”** <br>
This will let you override **mainTemplate.gradle** , **baseProjectTemplate.gradle** and **gradleTemplate.properties** files in the project.
#### **Step 4:**
**baseProjectTemplate.gradle** is equal to **project-level gradle** so you have to include **Huawei's Maven repositories** from the Integrate the Huawei Mediation SDK section from [**here**](#integrate-huawei-sdk) <br>
**mainTemplate.gradle** is equal to **app-level build.gradle** so you have to include **dependencies** from the Integrate the Huawei Mediation SDK section from [**here**](#app-level).
#### **Step 5:**
Open **gradleTemplate.properties** and add the following lines
```groovy
android.useAndroidX=true
android.enableJetifier=true
```

**After these configurations is completed you can display Huawei Ads.**

**Note:** 
In case of any error on aaptOptions you can add the following line to aaptOptions in **launcherTemplate.gradle** which you override it by enabiling it from **Edit -> Project Settings ->  Player -> Publishing Settings**

```groovy
aaptOptions {
        noCompress = ['.ress', '.resource', '.obb'] + unityStreamingAssets.tokenize(', ')
        ignoreAssetsPattern = "!.svn:!.git:!.ds_store:!*.scc:.*:!CVS:!thumbs.db:!picasa.ini:!*~"
    }
```

 This section demonstrates how to use AdMost mediation feature with Huawei Ads Kit on Unity android app.
 
 



# Screenshots
 <table>
<tr>
<td>
<img src="" width="200">

Banner Ad
</td>
 <td>
<img src="" width="200">

Interstitial Ad
</td>

<td>
<img src="" width="200">

Rewarded Ad
</td>
<td>
<img src="" width="200">

Native Ad
</td>
 

</tr>
</tr>
</table>








