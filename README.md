# Introduction
Define firstmeetgames mservice grpc api : 
- hello : [hello sample api](hello-grpc-java/README.md)
- zommon : is a share library for all above api projects

## API Design Guide
- Refer to [Google API Design Guide](https://cloud.google.com/apis/design/) 
- Refer to  [Google real life example servicemanager.proto](https://github.com/googleapis/googleapis/blob/master/google/api/servicemanagement/v1/servicemanager.proto)
- And [local copy of Google real life example servicemanager.proto](apiexample.txt)


# How to use mservice-grpc-apis in your JAVA application 
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
com.github.firstmeetgames.mservice-grpc-apis:uidgenerator-grpc-java:V1.0.1.RELEASE
com.github.firstmeetgames.mservice-grpc-apis:hello-grpc-java:V1.0.1.RELEASE
com.github.firstmeetgames.mservice-grpc-apis:zommon-grpc-java:V1.0.1.RELEASE
com.github.firstmeetgames.mservice-grpc-apis:mservice-grpc-apis:V1.0.1.RELEASE
```
## Step 3. Add dependencies as needed To your build.gradle
```gradle
dependencies {
    implementation 'com.github.firstmeetgames.mservice-grpc-apis:hello-grpc-java:master-SNAPSHOT'
    implementation 'com.github.firstmeetgames.mservice-grpc-api:uidgenerator-grpc-java:master-SNAPSHOT'
    implementation 'com.github.firstmeetgames.mservice-grpc-apis:zommon-grpc-java:master-SNAPSHOT'
}
```
	
# Building ahead of time for firstmeetgames.mservice-grpc-apis 
You can also build snapshots on each commit if you add GitHub Webhooks.

To add, head to repository Settings -> Webhooks & Services -> Add webhook.

Webhook URL: https://jitpack.io/api/webhooks

Content type: application/json

The webhook will trigger a build for branches that you have previously used with JitPack. So make sure you have requested master-SNAPSHOT from JitPack before adding a webhook.

# Design 
1. [https://cloud.google.com/apis/design/](https://cloud.google.com/apis/design/)
2. [Envoy and gRPC-Web: a fresh new alternative to REST](https://blog.envoyproxy.io/envoy-and-grpc-web-a-fresh-new-alternative-to-rest-6504ce7eb880)
3. [Seamless Cloud-Native Apps with gRPC-Web and Istio](https://venilnoronha.io/seamless-cloud-native-apps-with-grpc-web-and-istio)

## Reference 
My team has been using gRPC + Improbable's grpc-web + Typescript for a green field project and it has been amazing.
- Typing all the way to the frontend.

- gRPC/protobuf forces you to describe your interfaces and are self-documenting.

- gRPC semantics like error codes and deadlines (if you propagate them through your stack, they're particularly useful - for instance, we cancel database transactions across service boundaries if a request times out).

- Performance is great (but we're far from seeing bottlenecks with JSON, it's not the reason we choose gRPC).

- We use grpc-gateway which auto-generates a REST proxy for our customers. We sometimes use it for interactive debugging. 

- Rather than importing database models for our management tools and one-off scripts, using the API is so frictionless that we even use it inside our backend code and for CLI utilities.

The Google API design guide is helpful: [https://cloud.google.com/apis/design](https://cloud.google.com/apis/design)

One piece of advice: Treat your gRPC calls like you would treat a GraphQL resolver - if you squint your eyes, they're very similar concepts.

Rather than specifying a GraphQL query, you specify a Field Mask.

https://developers.google.com/protocol-buffers/docs/referenc...

Happy to answer questions on our experience.

1: [https://github.com/improbable-eng/grpc-web](https://github.com/improbable-eng/grpc-web)

2: [https://github.com/grpc-ecosystem/grpc-gateway](https://github.com/grpc-ecosystem/grpc-gateway)


# Pagination
## [Paginating Real-Time Data with Cursor Based Pagination](https://www.sitepoint.com/paginating-real-time-data-cursor-based-pagination/)
## [Pagination: You're (Probably) Doing It Wrong.](https://coderwall.com/p/lkcaag/pagination-you-re-probably-doing-it-wrong)
