---
title: Native authentication
description: Learn how you can use native authentication to take greater control over the user interface and experience for your customer-facing mobile and desktop apps.
 
author: csmulligan
manager: celestedg
ms.service: entra-external-id 
ms.subservice: customers
ms.topic: concept-article
ms.date:  03/08/2024
ms.author: cmulligan

#Customer intent: As a developer, devops, I want to learn more how to host the user interface (UI) within the client app by using native authentication so that I can take greater control over the UI and experience of my customer apps.
---
# Native authentication (preview)

Microsoft Entra ID for customers' native authentication empowers you to take complete control over the design of the sign-in experience of your mobile applications. It allows you to craft stunning, pixel-perfect authentication screens that are seamlessly integrated into your apps, rather than relying on browser-based solutions.  
 
In the standard, browser-delegated mobile app sign-in process, users often experience a disruptive jump during authentication. They're taken to a browser for authentication and then redirected back to the app when the sign-in is complete. This leads to a diluted experience and branding can be compromised. While browser-delegated methods can reduce attack vectors and support single sign-on (SSO), they suffer from limited UI customization and poor user experience.

Native authentication is the solution for app developers looking for solutions that give them full control over the user interface and experience.

[!INCLUDE [preview-alert](../customers/includes/preview-alert/preview-alert-ciam.md)]

## Available authentication methods

Currently, native authentication supports local account identity provider for two authentications methods: 

- Email with one-time passcode sign-in (OTP).
- Email and password sign-in with support for self-service password reset (SSPR). 

Native authentication doesn't yet support federated identity providers such as social or enterprise identities. 

## When to use native authentication

When it comes to implementing authentication for mobile apps on External ID for customers, you have two options: 

- Microsoft-hosted browser-delegated authentication.
- Fully custom SDK based native authentication. 

The approach you choose depends on your app’s specific requirements. While each app has unique authentication needs, there are some common considerations to keep in mind. Whether you choose native authentication or browser-delegated authentication, Microsoft Entra ID for customers supports both of them.

The following table compares the two authentication methods to help you decide then right option for your app.

|   | Browser-delegated authentication | Native authentication | 
| ---- | --- |  --- |
| **User authentication experience** | Users are taken to a system browser or embedded browser for authentication only to be redirected back to the app when the sign-in is complete. This is recommended if the redirection doesn't negatively impact the end user experience. | Users have a rich, native mobile-first sign-up and sign-in journey without ever leaving the app. |
| **Customization experience** |Managed [branding and customization options](how-to-customize-branding-customers.md) are available as an out-of-the-box feature.  | This API-centric approach offers a high level of customization, providing extensive flexibility in design and the ability to create tailored interactions and flows. |
| **Applicability**  | Suitable for workforce, B2B, and B2C apps, it can be used for native apps, single-page applications, and web apps. | For customer first-party mobile apps, when the authorization server and app are operated by the same entity and the user perceives them both as the same entity.|
| **Go live effort** |  Low. Use it straight out of the box.  |High. The developer builds, owns, and maintains the authentication experience. |
| **Maintenance effort** | Low. |High. For each feature that Microsoft releases, you need to update the SDK to use it.  |
| **Security** | Most secure option. |Security responsibility is shared with developers, and best practices need to be followed. It's prone to phishing attacks. |
| **Supported languages and frameworks** | <ul><li>ASP.NET Core</li><li>Android (Kotlin, Java)</li><li>iOS (Swift, Objective-C)</li><li>JavaScript</li><li>React</li><li>Angular</li><li>Nodejs</li><li>Python</li><li>Java</li></ul>  |<ul><li>Android (Kotlin, Java)</li><li>iOS (Swift, Objective-C)</li></ul> For other languages and platforms, you can use our [native authentication API](../../identity-platform/reference-native-authentication-overview.md?bc=/entra/external-id/customers/breadcrumb/toc.json&toc=/entra/external-id/customers/toc.json).  |


## Feature availability

The following table shows the availability of features for browser-delegated and native authentication. 

|   | Browser-delegated authentication | Native authentication | 
| ---- | --- |  --- |
| **Sign-up and sign-in with email one-time passcode (OTP)** | :heavy_check_mark:  | :heavy_check_mark:  |
| **Sign-up and sign-in with email and password** | :heavy_check_mark:  | :heavy_check_mark:  |
| **Self-service password reset (SSPR)** | :heavy_check_mark:  | :heavy_check_mark:  |
| **Social identity provider sign-in** | :heavy_check_mark:  | :x: |
| **Multifactor authentication with email one-time passcode (OTP)**| :heavy_check_mark:  | :x:  |
| **Single sign-on (SSO)** | :heavy_check_mark:  | :x:  |

## How to use native authentication

You can build your customer-facing apps that use native authentication by using our native authentication APIs or Microsoft Authentication Library (MSAL) SDK for Android and iOS. Whenever possible, we recommend you use the MSAL to add native authentication to your apps. 

If you're planning to create a mobile app on a framework currently not supported by MSAL, you may use our authentication API.  For more information, explore our [Android](how-to-run-native-authentication-sample-android-app.md) and [iOS](how-to-run-native-authentication-sample-ios-app.md) tutorials. 

## Related content 

- [Android native authentication tutorials](how-to-run-native-authentication-sample-android-app.md).
- [iOS native authentication tutorials](how-to-run-native-authentication-sample-ios-app.md).
- [Native authentication API documentation](../../identity-platform/reference-native-authentication-overview.md).