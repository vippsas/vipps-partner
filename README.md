# Vipps Partners

💥 Work in progress! 💥

Document version: 0.11.0

Vipps wants to make payment and identification liberatingly easy - together with our partners. We believe in the magic that arises through collaboration. 

If you and your merchants have a good volume and great potential, we would like to have you on the team as a partner. The goal of the partner program is to find areas where we can work closely together and experience good growth - together. The collaboration will give you good exposure and opportunities for even better solutions for our customers.


## Phase 1: 

Potential Vipps partners are curious about the partner program.

In this phase potential partners are curious about the Vipps partner program and what it entails. 
We ask our potential partners to visit our [partner page at Vipps.no]( https://vipps.no/developer/bli-partner/), scroll down and read through our FAQ. 
When that is done, we ask you to register yourselves through our form on the same page. 

By becoming a Vipps-partner you accept these [terms and conditions]( https://github.com/vippsas/vipps-partner/blob/main/partnerterms.md). 
However, since you're reading this text on a Github-page you’re probably past this stage.

## Phase 2: Technical integration

In this phase you will integrate one or more of Vipps' eCom APIs in your own system (typically proprietary platform partners) or in your customers systems (typically integration partners). After you register your interest in becoming a [Vipps partner at vipps.no]( https://vipps.no/developer/bli-partner/), you will receive a test account and access to our Merchant Test Environment. 
We strive to provide access within 48 hours. 

The development and integration with Vipps can now start.

### Relevant links

* [Starting point for developers](https://github.com/vippsas/vipps-developers#vipps-developers)
* [Vipps eCom API](https://github.com/vippsas/vipps-ecom-api#vipps-ecommerce-api-version-2) (Single payments and Express Checkout)
* [Vipps Login API](https://github.com/vippsas/vipps-ecom-api#vipps-ecommerce-api-version-2)
* [Vipps Recurring API](https://github.com/vippsas/vipps-recurring-api#vipps-recurring-api)

### Plugins

If you’re an integration partner we have a number of plugins for different open-source plattforms you can (and should) use to integrate Vipps.
[See our plugin section](https://github.com/vippsas/vipps-plugins). 

### Signup-API

If you’ve developed a proprietary platform with more than 20 active merchants, we would recommend that you integrate our Signup-API. This API automates part of the onboarding process and makes it easier for your customers to register as a Vipps eCom-customer. Go to [Signup API documentation](https://github.com/vippsas/vipps-signup-api)

An example of how the API is used optimally, by our [partner 24Nettbutikk](https://support.24nettbutikk.no/nb/articles/2332760-vipps)

All our Github API-pages have extensive Frequently Asked Questions-sections (FAQs). As we receive a high number of emails every day, we urge you to check the FAQs before contacting us. If you still can’t find what you're looking for, you can contact us [using this mail format](https://github.com/vippsas/vipps-developers/blob/master/contact.md#what-to-include-in-the-email)


### Finishing the integration and going live
An integration is considered finished when all the elements of the [integration checklist are done](https://github.com/vippsas/vipps-ecom-api/blob/master/vipps-ecom-api-checklist.md#checklist). 

In addition, as a partner you are required to complete the following:
- [ ] As a partner you accept the [Partner terms and conditions](https://github.com/vippsas/vipps-developers/blob/master/partners/partnerterms.md)
- [ ] Technical documentation for merchants
     - [ ] Documentation for merchants regarding how to apply for Vipps products
- [ ] Find a pilot customer to verify the integration in production environment

When the integration checklist is completed and verified by Vipps Integration team, the partner receives an email from Vipps saying that the implementation is OK.

Vipps adds the partner to vipps.no, including the signup forms for merchants.



## Phase 3 The partner is live and offering Vipps to its customers

Congratulations, you’re officially a Vipps partner and you and your customers can start to reap the benefits of the partnership. The best Vipps partners spend some time familiarizing themselves with our products, how our onboarding process works, our brand, the important elements of our pricing and kick-back models, before diving head first into the partnership. 
Underneath we will give an overview of the most important information you’ll need to help your customers enjoy the benefits of using vipps.


### The partner are now able to activate merchants

1. The merchant signs up from either
   A: Vipps.no, [Vipps på Nett](https://www.vipps.no/produkter-og-tjenester/bedrift/ta-betalt-paa-nett/ta-betalt-paa-nett/) and selects the partner in the form.
   B: From the partner signup form connected to the [signup API](https://github.com/vippsas/vipps-signup-api) 
2. Vipps completes customer control (KYC, PEP, AML, etc).
3. Merchant keys are available for the merchant on [portal.vipps.no](https://portal.vipps.no), or sent directly to partner if [signup API](https://github.com/vippsas/vipps-signup-api) is implemented.


## Partner keys

**Note: This is new functionality currently being rolled out.**

A partner may get API keys that also work for all the partner's merchants.
This means that the partner does noe have to manage the API keys for
every merchant: It is sufficient to use the partner's own API keys.

The partner's API keys only work for merchants that are registered in Vipps as customers of that partner.

Please note that partner keys are currently only available for eCom API. 



## Questions?

We're always happy to help with code or other questions you might have!
Please create an [issue](https://github.com/vippsas/vipps-developers/issues),
a [pull request](https://github.com/vippsas/vipps-developers/pulls),
or contact us by email: partnerbestilling@vipps.no.

Sign up for our [Technical newsletter for developers](https://github.com/vippsas/vipps-developers/tree/master/newsletters).
