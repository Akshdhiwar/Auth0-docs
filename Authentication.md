# Authentication (B2B)

## Overview

User Authentication is the process of identifying who users are. There are various ways to perform authentication, such as via social media accounts, username and password, or passwordless methods. It's often recommended to go beyond a first factor for authenticating the user by enabling multi-factor authentication (MFA).

## Best Practice

Consider both security and user experience when designing how you will authenticate your users. Providing multiple primary factors and/or enforcing more than one factor during authentication are ways to enhance both.

## Key Considerations

- Where will users enter their credentials?
- How will you keep user credentials safe?
- How will you maintain your authentication system?
- How can you provide password authentication for your users?
- How can you prevent hackers from trying to log in as your users?
- How will you implement authentication in different kinds of applications?
- How can you make login easy for users from different language backgrounds?
- How will you provide a good user experience as you migrate away from any legacy authentication system?
- What should you consider when integrating applications with Auth0?
- Do you need to provide multi-factor authentication?
- What do you do if you have a service that doesn’t have a way for the user to log in ahead of time?
- Can you pass the same user access token from one API to another?
- What do you do if you need to isolate users by organization?
- How will you handle identifying which organization users belong to?
- What’s the benefit of providing enterprise connections for your organizations?
## Universal Login

Auth0 Universal Login provides users with a safe and secure experience, whether you choose to provide user ID/password credentials sign-in or allow Bring Your Own Identity scenarios via Social Login. There are brand recognition benefits to centralizing the login experience with Universal Login, even if you have product-specific branding requirements.

## Home Realm Discovery (HRD)

HRD is the process of identifying which identity provider (or which connection in Auth0) the user belongs to before authenticating them. There are two ways HRD can occur:

- Provide a way for the decision to be made at the application.
- Have HRD happen on the Universal Login page.
## Application Integration

Once you've figured out how you want to authenticate your users, the next step is to determine how you will initiate that authentication. Each application will typically have its own starting point. Native mobile applications (and desktop applications) should use the system browser for authentication to avoid additional security risks.

## Anonymous Access

Consider the user experience when someone first comes to your application. If your application supports anonymous user access, there are different scenarios to consider:

- Are they returning to the application after having already logged in?
- Is this the first time they are accessing the application?
- Have they already accessed a different application that uses the same Auth0 tenant?
- Have they ever (or perhaps not in a long time) authenticated on this device or browser?
## Deep Linking to Protected Endpoints

If your application allows deep linking to protected endpoints, you should automatically redirect your user to Auth0 if they are not authenticated. Once they authenticate and the authorization server returns them to your application, you can redirect them to where they intended to go initially.

## Multi-Factor Authentication (MFA)

Providing users with the ability to configure a second factor for protecting their account is one of the most effective ways to ensure that only a valid user can access their account, even if their username and password have been compromised.

## Project Planning Guide

We provide planning guidance in PDF format that you can download and refer to for details about our recommended strategies.

## Multiple Organization Architecture (Multitenancy)

Many B2B platforms implement some form of isolation and/or branding for their customers’ organization, adding complexity to any Identity and Access Management (IAM) system. We recommend taking time to read through our guidance and best practice advice for this type of environment.
