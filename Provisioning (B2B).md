# Provisioning (B2B)

## Overview

Determining how users get signed up is important to address early, and the decisions you make here will influence many of the decisions you will need to make going forward. We've found there are a typical set of patterns for how users will get added to your system, and things to take note of when considering workflow design too.

## Best Practice

While Auth0 supports numerous workflows, web-based workflows using Auth0 Universal Login for sign-up are considered both industry and Auth0 best practice as they provide for optimal functionality and the best security. Auth0 supports user sign-up via a number of different identity providers. During sign-up, Auth0 provisions the user profile so that it contains the user's account information.

## Key Considerations

- Does a user get added to your company's domain or do they belong to or remain in their organizationÃ¢ÂÂs domain?
- If the user stays in their own domain, do they belong to a single organization or can they belong to multiple organizations?
- How do you provision the organization itself in your system?
- Should you use Auth0 as an identity store?
- Can you use your own (legacy) identity store with Auth0?
- How do you migrate user identities from your identity store to Auth0?
- Can your users sign up using their organizationÃ¢ÂÂs identity provider?
- Can your users be invited or self-register?
## Provisioning Organization Users

One of the first determinations to make when providing your service(s) to other businesses is identifying to which domain users belong. Based on the answer to that question, there are a couple of different approaches you can take to provision those users.

### Isolated to the Organization

Every user belongs to exactly one organization. It would not make sense for that user to be a part of more than one organization, and even if they were, it would make sense for them to have a separate Ã¢ÂÂidentityÃ¢ÂÂ for that other organization.

### Shared Between Organizations

Users either create credentials in your company, or they can access other organizations' instances of your application using credentials from their own organization. A user may be authorized to access more than one organizationÃ¢ÂÂs instance of the application.

## Provisioning Organizations

When provisioning organizations, you need to consider the following:

- Add the organization to your own application configuration and/or database.
- Make changes to your Auth0 configuration, which may include creating a unique tenant for the organization, creating a new Organization in your Auth0 Tenant, adding a new database connection for that Organization, enabling the existing shared database connection for that Organization, and adding an enterprise connection for this Organization.
- Provision an administrator for the organization.
- Create an Organization Admin Portal to make it easier to provision new organizations.
- Create a Self-Signup portal for your Organizations.
## User Migration

Auth0 provides capabilities to both proxy your own legacy identity store and provide a secure Auth0 hosted replacement. You can migrate users either all at once with bulk migration or progressively with automatic migration.

## Best Practice

Customers often opt for a two-stage approach to user migration, using Automatic Migration first to migrate as many users as possible, then using Bulk Migration for the users that remain. Automatic Migration is preferred as it allows users to be migrated individually and also allows them to retain their existing passwords in almost all situations.

## Identity Store Proxy

Auth0 Database Connection types can also be configured to proxy an existing (legacy) identity store. If you need to keep user identities defined in your own legacy store, you can easily integrate with Auth0.

## User Invite

In most B2B scenarios, only particular individuals are allowed access to the application. Provisioning can often be done in an automated fashion when users are added to a centralized system.

## Enterprise Sign Up

Enterprise sign-up is synonymous with sign-in via enterprise login. User profile creation happens automatically upon first enterprise login.

## Best Practice

Allowing your customers to use their own IdP is advantageous as they can administer their users and assign roles and access in their own IdP setup instead of forcing you to build administration for them.

## Project Planning Guide

We provide planning guidance in PDF format that you can download and refer to for details about our recommended strategies.

## Multiple Organization Architecture (Multitenancy)

Many B2B platforms implement some form of isolation and/or branding for their customer's organization, and this can add complexity to any Identity and Access Management (IAM) system. We recommend you take some time to read through our guidance and best practice advice for this type of environment.
