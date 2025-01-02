# Authentication (B2B)

## Overview

In order to provide services to your users, you must be able to identify who those users are. This process is called User Authentication. There are a number of ways to perform authentication of a user - via social media accounts, username and password, passwordless - and it's often recommended that you go beyond a first factor for authenticating the user by enabling multi-factor authentication (MFA).

## Best Practices

- **Security and User Experience**: Consider both security and user experience when designing how you will authenticate your users. Providing for multiple primary factors, and/or enforcing more than one factor during authentication, are ways that you can provide both.
- **Credential Safety**: Ensure that user credentials are kept safe and maintain your authentication system.
- **Password Authentication**: Provide password authentication for your users and prevent hackers from trying to log in as your users.
- **Application Integration**: Implement authentication in different kinds of applications and provide a good user experience as you migrate away from any legacy authentication system.
- **Multi-Factor Authentication**: Consider providing multi-factor authentication to enhance security.
## Universal Login

Auth0 Universal Login provides users with a safe and secure experience - no matter whether you choose to provide for user ID/password credentials sign in, or allow the so-called Bring Your Own Identity scenarios provided via Social Login. There are also brand recognition benefits to centralizing the login experience with Universal Login, even if you feel you will also have product-specific branding requirements.

## Home Realm Discovery (HRD)

Home realm discovery (HRD) is the process of identifying which identity provider (or which connection in Auth0) the user belongs to before authenticating them. There are two ways HRD can occur:

- Provide a way for the decision to be made at the application.
- Have Home Realm Discovery happen on the Universal Login page.
## Username and Password Authentication

Nearly every B2C application provides the ability for its customers to create a new set of credentials. This is a common form of authentication that all users are familiar with. Username password authentication comes in multiple flavors at Auth0.

## Application Integration

Once you've figured out how you want to authenticate your users, the next step is to determine how you will initiate that authentication. Each application will typically have its own starting point. Native mobile applications (and desktop applications) should use the system browser for authentication, or they open themselves up to additional security risks.

## Anonymous Access

It is important to consider the user experience when someone first comes to your application. If your application supports anonymous user access (quite common for eCommerce applications) there are different scenarios to consider.

## Deep Linking to Protected Endpoints

There are a variety of reasons why someone might link directly to a particular page within your application that is only accessible by authenticated users. If this is possible for your application you should automatically redirect your user to Auth0 if they are not authenticated.

## Multi-Factor Authentication (MFA)

In an era where misuse of user credentials is at an all-time high, protecting your systems when it's so common for hackers to steal users identity information in general is a challenge. One of the most effective ways though is to provide users with the ability to configure a second factor for protecting their account.

## Project Planning Guide

Auth0 provides planning guidance in PDF format that you can download and refer to for details about our recommended strategies.

## Multiple Organization Architecture (Multitenancy)

Many B2B platforms implement some form of isolation and/or branding for their customers' organization, and this can add complexity to any Identity and Access Management (IAM) system.

## Conclusion

Auth0 offers a comprehensive set of tools and best practices for implementing authentication in B2B scenarios, ensuring both security and a seamless user experience.
