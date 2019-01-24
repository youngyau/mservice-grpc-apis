# Introduction
Define firstmeetgames mservice grpc api : 
- hello : [hello sample api](hello-grpc-java/README.md)
- zommon : is a share library for all above api projects

## API Design Guide
- Refer to [Google API Design Guide](https://cloud.google.com/apis/design/) 
- Refer to  [Google real life example servicemanager.proto](https://github.com/googleapis/googleapis/blob/master/google/api/servicemanagement/v1/servicemanager.proto)
- And [local copy of Google real life example servicemanager.proto](apiexample.txt)


# How to use guo-micro-apis in your JAVA application 
## Step 1. Add the JitPack repository to your build file
Add it in your root build.gradle at the end of repositories:
```gradle
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}
```
	
## Step 2. Find the dependencies
### master 分支
> If you want to trigger the build immediately, you may click the below link:
1. [https://jitpack.io/com/github/firstmeetgames/mservice-grpc-apis/master-SNAPSHOT/build.log](https://jitpack.io/com/github/firstmeetgames/mservice-grpc-apis/master-SNAPSHOT/build.log)
### release 分支
> If you want to trigger the build immediately, you may click the below link:
2. [https://jitpack.io/com/github/firstmeetgames/mservice-grpc-apis/V1.0.0.RELEASE/build.log](https://jitpack.io/com/github/firstmeetgames/mservice-grpc-apis/V1.0.0.RELEASE/build.log)

```angular2html
Build artifacts:
com.github.firstmeetgames.mservice-grpc-apis:hello-grpc-java:V1.0.1.RELEASE
com.github.firstmeetgames.mservice-grpc-apis:zommon-grpc-java:V1.0.1.RELEASE
com.github.firstmeetgames.mservice-grpc-apis:mservice-grpc-apis:V1.0.1.RELEASE
```
## Step 3. Add Dependencies As Needed To Your build.gradle
```gradle
dependencies {
    implementation 'com.github.firstmeetgames.mservice-grpc-apis:hello-grpc-java:master-SNAPSHOT'
    implementation 'com.github.firstmeetgames.mservice-grpc-apis:zommon-grpc-java:master-SNAPSHOT'
}
```
	
# Building ahead of time for firstmeetgames.mservice-grpc-apis 
You can also build snapshots on each commit if you add GitHub Webhooks.

To add, head to repository Settings -> Webhooks & Services -> Add webhook.

Webhook URL: https://jitpack.io/api/webhooks

Content type: application/json

The webhook will trigger a build for branches that you have previously used with JitPack. So make sure you have requested master-SNAPSHOT from JitPack before adding a webhook.


# Pagination
## [Paginating Real-Time Data with Cursor Based Pagination](https://www.sitepoint.com/paginating-real-time-data-cursor-based-pagination/)
## [Pagination: You're (Probably) Doing It Wrong.](https://coderwall.com/p/lkcaag/pagination-you-re-probably-doing-it-wrong)
