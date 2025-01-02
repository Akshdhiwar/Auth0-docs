# Architecture (B2B)

## Overview

Understanding your application is key to understanding how Auth0 can be leveraged to meet your needs. From experience, our most successful customers start with a visualization of their proposed - or in many cases existing - architecture and use this as a basis for reference as they progress. Understanding where your application fits within your organization is also important; Auth0 Accounts and Tenants form the basis for the grouping and structuring of Auth0 assets, and it may be that you’ll need to leverage an existing Auth0 deployment in order to integrate with Single Sign-on (SSO), centralized user Profile Management, consolidated billing, or the like.

## Best Practice

If you do have multiple applications, and you need to leverage SSO, then we recommend you check out our How to Implement Single Sign-On training guidance before continuing. The value of investing time on the landscape of the architecture up-front is something that we have found pays dividends in the long run, and there are a number of things you will want to consider when looking at functionality and workflow:

- What should the URL look like when Auth0 needs to present a web page to a user?
- How can Auth0 be structured to support your SDLC (Software Development Lifecycle)?
- How can you ensure that your Auth0 tenants are appropriately associated with your contract?
- What do you need to consider if there are other projects in your organization integrating with Auth0? Particularly projects that target their own, or a different domain of users (for example, applications that only employees will use)?
- How can you align the structure and domain of your customers’ organization with your Auth0 deployment?
## Organizations and Domains

Organizations often service more than one domain of user - customers, employees, and affiliates being the most frequently encountered, with typically little to no cross-over: employees, say, don’t use the same applications as customers and vice-versa. In some cases there can also be a need to partition further within a domain - separate groups of customers, say, who use different and unconnected products. Auth0 provides a way to segregate your users and the associated collateral, and tenant provision covers this in more detail. If you need to provision an independent tenant then you’ll also want to associate this with your existing Auth0 account, so that you can take full advantage of the benefits provided at your organization’s contracted subscription level.

## Best Practice

It’s not uncommon for companies to have identity requirements that address multiple user communities: customers, partners, employees, etc. So be sure to consider other projects or future requirements when designing your architecture. In addition, you’ll undoubtedly have an established set of processes and procedures as part of your Software Development Lifecycle (SDLC). So you’ll want to check out our SDLC support guidance regarding Auth0 Tenant provision in support of that too.

## Customer-Facing Applications

For customer-facing applications, we typically see OpenID Connect (OIDC) as being the most frequently used protocol. OIDC makes use of web-based workflows with browser URLs that are presented to the user. Out-of-the-box, client-facing URLs as part of Auth0 OIDC support are Auth0 branded, however we recommend using the Auth0 custom domain capability to provide for consistent corporate identity and to also address potential user confidence concerns before they arise.

## Best Practice

Other groups within your organization may also be working with Auth0; it’s not uncommon for our customers to have disparate departments that serve different user communities. Identifying these will potentially influence your design choices, and doing so early could mitigate decisions that might prove costly later on. If some or all of your customer organizations each need their own custom URL or they are using social providers that need a custom consent page branded to the organization, then we recommend that you create separate Auth0 tenants for those organizations; see Tenant provision for complex organizations for further details.

## Tenant Provision

Everything starts with an Auth0 tenant. This is where you will be configuring your use of Auth0, and where Auth0 assets - such as Applications, Connections, and user profiles are defined, managed, and stored. Access to an Auth0 tenant is performed via the Auth0 Dashboard, and via the Dashboard you can also create additional, associated tenants; you’re allowed to create more than one Auth0 tenant so that you can structure your tenants in a way that will isolate different domains of users and also support your Software Development Life Cycle (SDLC). Tenant names cannot be changed, nor reused once deleted. So, make sure you’re happy with your name(s) before you create your Auth0 tenants.

## Tenant Provision for Complex Organizations

In most cases, provisioning separate Auth0 tenants for your customer’s organizations is not necessary. This has become even easier with the release of our new Organizations feature. However, in certain circumstances, this can be something that is valuable for reducing the complexity of your setup. For instance, we recommend provisioning a separate Auth0 tenant for your customers’ organization as a best practice if:

- Your customer organizations need a custom login URL that is unique to the organization. This is generally the case only if you allow your organizations to have their own vanity URL instead of using a common login URL. Auth0 supports one custom domain per tenant.
- Your customer organizations use social providers for login. In this case, it is often desirable for the organization to have a custom consent page for the social provider that is branded to their organization.
If either of these situations is true, we recommend creating a separate Auth0 tenant for each organization that has one of the above criteria. Maintaining multiple Auth0 tenants can add complexity to your system and should not be done unless absolutely necessary.

## Tenant Association

To ensure that your tenants are all associated with your Auth0 contractual agreement and have the same features, ensure all your tenants are associated with your company account. If you have individual developers that want to create their own sandboxes for testing, make sure they get associated with your account so they have the same permissions too. To do this you should contact your Auth0 representative or the Auth0 Support Center.

## Custom Domains

When you set up your Auth0 tenant, the URL for accessing that tenant will be of the form https://{yourTenant}.auth0.com. Providing a Custom Domain (also known as a vanity URL), for your Auth0 tenant is not only an important factor for supporting your Branding requirements, but more importantly will also provide you with security benefits too:

- Some browsers will, by default, make it difficult to communicate in an iFrame if you don’t have a shared domain.
- It’s harder to phish your domain if you have a vanity URL, as the phisher must also create a vanity URL to mimic yours. For example, with a custom domain you can use your own certificate to get an “Extended Validation”, making phishing even harder.
You are allowed only one custom domain per Auth0 Tenant. This is because a tenant in Auth0 is intended to represent a “domain” of users. If you need more than one vanity URL, then you likely have more than one domain of users and should be using multiple tenants. Your custom domain name should also give the user confidence that this is the appropriate place to enter their credentials, and we recommend that you create your custom domain in all environments early on to ensure that you are testing consistently between environments. It’s extremely important to train your users to look for suspicious URLs when entering their credentials!

## Best Practice

Create a custom domain (a.k.a. CNAME) for your Auth0 tenant, and also create one in development too so you can ensure you have managed the CNAME correctly. For example, you could create a CNAME which maps login.mycompany.com to mycompany-prod.auth0.com. In almost all cases, customers have been most successful when adopting a strategy of a centralized domain for authentication across multiple product or service brands. This strategy provides users with a consistent UX, and also mitigates the complexity of deploying and maintaining multiple Auth0 tenants in a production environment. If you are considering having multiple domains for different brands, please refer to the Branding guidance before you begin implementing.

## SDLC Support

Every company has some form of Software Development Life Cycle (SDLC), and throughout the development process you will want to align with that strategy. For instance, you need to be able to test your integration with Auth0 in a similar fashion as you test the applications themselves. It is therefore important to structure Auth0 tenants to support your SDLC, and there is a consistent pattern which our customers typically follow when it comes to the best practices associated with tenant layout for doing so:

| Environment | Sample Tenant Name | Description |
| --- | --- | --- |
| Development | company-dev | A shared environment where most of your development work occurs |
| QA/Testing | company-qa or company-uat | An environment for formal testing of the changes you’ve made |
| Production | company-prod | The production tenant |

In some cases, you may also want to create one or more sandboxes (e.g., company-sandbox1, company-sandbox2) so that you can test changes without compromising your development environment. This might be where you test deployment scripts and the like.

## Best Practice

You can also take advantage of our Implementation Checklists that you can download and customize to meet your implementation project needs. Customers with an Enterprise subscription should ensure tenants set up to support their SDLC are properly linked to their subscription. This will ensure each tenant has a consistent set of features enabled.

## Project Planning Guide

We provide planning guidance in PDF format that you can download and refer to for details about our recommended strategies.

## Multiple Organization Architecture (Multitenancy)

Many B2B platforms implement some form of isolation and/or branding for their customers’ organization, and this can add complexity to any Identity and Access Management (IAM) system. If this applies to you, then we recommend you take some time to read through our guidance and best practice
