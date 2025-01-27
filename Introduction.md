# Architecture (B2B) 

## Overview

Understanding your application is key to understanding how Auth0 can be leveraged to meet your needs. From experience, our most successful customers start with a visualization of their proposed - or in many cases existing - architecture and use this as a basis for reference as they progress. Understanding where your application fits within your organization is also important; Auth0 Accounts and Tenants form the basis for the grouping and structuring of Auth0 assets, and it may be that you’ll need to leverage an existing Auth0 deployment in order to integrate with Single Sign-on (SSO), centralized user Profile Management, consolidated billing, or the like.

## Best Practices

- **Multiple Applications and SSO**: If you have multiple applications and need to leverage SSO, check out Auth0's How to Implement Single Sign-On training guidance.
- **Landscape of Architecture**: Invest time in understanding the landscape of your architecture upfront to reap long-term benefits.
- **URL Structure**: Consider what the URL should look like when Auth0 needs to present a web page to a user.
- **SDLC Support**: Structure Auth0 to support your Software Development Lifecycle (SDLC).
- **Tenant Association**: Ensure your Auth0 tenants are appropriately associated with your contract.
- **Future Projects**: Consider other projects or future requirements when designing your architecture.
## Tenant Provision

Everything starts with an Auth0 tenant. This is where you will be configuring your use of Auth0, and where Auth0 assets - such as Applications, Connections, and user profiles - are defined, managed, and stored. Access to an Auth0 tenant is performed via the Auth0 Dashboard, and via the Dashboard, you can also create additional, associated tenants.

## Custom Domains

When you set up your Auth0 tenant, the URL for accessing that tenant will be of the form `https://{yourTenant}.auth0.com`. Providing a Custom Domain (also known as a vanity URL) for your Auth0 tenant is important for supporting your branding requirements and provides security benefits.

## SDLC Support

Every company has some form of Software Development Life Cycle (SDLC), and throughout the development process, you will want to align with that strategy. Structure Auth0 tenants to support your SDLC, and follow best practices associated with tenant layout.

## Project Planning Guide

Auth0 provides planning guidance in PDF format that you can download and refer to for details about recommended strategies.

## Multiple Organization Architecture (Multitenancy)

Many B2B platforms implement some form of isolation and/or branding for their customers' organization, adding complexity to any Identity and Access Management (IAM) system. Auth0 provides guidance and best practice advice for this type of environment.
