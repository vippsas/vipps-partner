# Vipps Partners

Technical information for Vipps partners.

Document version: 1.2.6.

# Table of Contents

- [How to become a Vipps partner](#how-to-become-a-vipps-partner)
  * [Partner types](#partner-types)
  * [Apply on vipps.no](#apply-on-vippsno)
  * [Integrate with the Vipps APIs](#integrate-with-the-vipps-apis)
  * [Finishing the integration and going live](#finishing-the-integration-and-going-live)
- [Technical information for partners](#technical-information-for-partners)
  * [Developer documentation](#developer-documentation)
  * [Vipps API Lifecycle](#vipps-api-lifecycle)
  * [Partner keys](#partner-keys)
  * [Plugin development](#plugin-development)
- [How to sign up new merchants](#how-to-sign-up-new-merchants)
  * [Typical reasons for delays](#typical-reasons-for-delays)
  * [Vipps Partner API PoC](#vipps-partner-api-poc)
  * [Vipps Signup API](#vipps-signup-api)
    - [If you are using the Signup API](#if-you-are-using-the-signup-api)
    - [Why is the Signup API being phased out?](#why-is-the-signup-api-being-phased-out)
    - [When will there be a replacement for the Signup API?](#when-will-there-be-a-replacement-for-the-signup-api)
- [FAQ for partners](#faq-for-partners)
- [Questions?](#questions)

# How to become a Vipps partner

If you and your merchants have a good volume and great potential, we would like
to have you on the team as a partner. The goal of the partner program is to
find areas where we can work closely together and experience good growth - together.
The collaboration will give you good exposure and opportunities for even better
solutions for our customers.

## Partner types

Vipps has three types of partners:

1. **Platform partners:** Provide a "closed" ready-to-use platform for their merchants,
   do all integration with the Vipps APIs,
   do all development and maintenance on their platform,
   and also provide all support for the merchants.

   Platform partners use the Vipps APIs _on behalf of_ merchants
   (initiate payments, do captures, do refunds, etc).

   Merchants that use a platform partner
   _never need to see their API keys_,
   since the platform partner uses partner keys.

2. **Integration partners:** Assist merchants in development of the merchants'
   integration. Typically a consultancy firm doing development for the merchant.
   An integration partner does not use the Vipps APIs on behalf of the merchant.

   If the integration partner continue to run, manage and develop the
   _everything_ related to the Vipps integration, and also manage the API
   credentials _on behalf of_ the merchant, the partner is similar to a
   platform partner and should use partner keys.

   Merchants that use an integration partner must
   _provide the API keys to the integration partner_.
   See [Getting started: Getting the API keys](https://github.com/vippsas/vipps-developers/blob/master/vipps-getting-started.md#getting-the-api-keys).

3. **Plugin partners:** Develop Vipps' official
   [open source plugins](https://github.com/vippsas/vipps-plugins)
   on contract for Vipps.

   If a partner uses official Vipps plugins to implement a Vipps integration
   for a merchant, the API credentials for the merchant must be used, and
   the partner use the Vipps APIs on behalf of the merchant.

A partner may act as a different type of partner in different situation.
It is possible for a partner to both develop an official Vipps plugin and
to be a platform partner.

This document is mainly for platform partners, that act _on behalf of_ merchants,
using one set of API keys for all merchants: Partner keys.
Other partners must rely on each merchant's individual API keys.

Information for PSP (Payment Service Providers) is here:
[Vipps PSP API](https://github.com/vippsas/vipps-psp-api),
including
[PSP Signup API](https://github.com/vippsas/vipps-psp-api/blob/master/vipps-psp-api.md#psp-signup-api).

## Apply on vipps.no

Please visit the
[partner page at Vipps.no]( https://vipps.no/developer/bli-partner/),
read through our FAQ, and fill out the form.

## Integrate with the Vipps APIs

See: [Developer documentation](#developer-documentation).

When you application is aproved you will receive an email with details about access to the
[test environment](https://github.com/vippsas/vipps-developers/blob/master/vipps-test-environment.md).

If you already have a pilot merchant that has access to the Vipps APIs,
you can also use the merchant's API keys for the test environment for development.

**Please note:** Access to the production environment requires thorough
checks required by law. For most partners this is not relevant, as
it is the partner's _merchants_ that will need production access.
The partner only needs access to the test environment to complete an integration.

## Finishing the integration and going live

An integration is considered complete when all the elements of the
relevant API's checklist are done. See the checklists:
- [ ] [Vipps eCom API](https://github.com/vippsas/vipps-ecom-api/blob/master/vipps-ecom-api-checklist.md)
- [ ] [Vipps Recurring API](https://github.com/vippsas/vipps-recurring-api/blob/master/vipps-recurring-api-checklist.md)
- [ ] [Vipps Login API](https://github.com/vippsas/vipps-login-api/blob/master/vipps-login-api-checklist.md)

In addition to the checklists mentioned above, all partners are required to complete the following:
- [ ] As a partner you accept the [Partner terms and conditions](https://github.com/vippsas/vipps-partner/blob/main/partner-terms.md)
- [ ] Technical documentation for merchants
     - [ ] Documentation for merchants regarding how to apply for Vipps products
     - [ ] Documentation for merchants regarding how to configure and use the module
     - [ ] FAQ for merchants
- [ ] Provide one pilot customer to verify the integration in production environment (send organization number and name)
- [ ] Describe how your integration have been set up with a link to a demo, or provide screenshots.

When the integration checklist is completed, notify Vipps Integration
[integration@vipps.no](integration@vipps.no)
as described in the checklist with `orderId` examples from test environment,
pilot customer info and description of the implemented solution.

Vipps Integration will verify the integration, and contact the partner.

Vipps then adds the partner to vipps.no, including the signup forms on
[portal.vipps.no](https://portal.vipps.no)
where the merchants can sign up and select the partner as their partner.

# Technical information for partners

## Developer documentation

All developer documentation and tools is available on
[GitHub](https://github.com/vippsas/vipps-developers).

## Vipps API Lifecycle

See the
[Vipps API Lifecycle](https://github.com/vippsas/vipps-developers/blob/master/vipps-api-lifecycle.md)
for information about deprecation notices, etc.

## Partner keys

As a partner you manage transactions on behalf of Vipps merchants.
Vipps provide you with _partner keys_, which allows you to use your own API credentials to
make API calls on behalf of your merchants (only for the sale units that are linked to you as a partner, though).
Please note that partner keys can not be used for Vipps Login, here you need to use the merchant's own keys.

With the partner keys you authenticate in the normal way, and then send
the required `Merchant-Serial-Number` header to identify which of your merchants you are
acting on behalf of: `Merchant-Serial-Number: 123456`.

Example of headers in an API request _without_ using partner keys
(including the required
[Vipps HTTP headers](https://github.com/vippsas/vipps-ecom-api/blob/master/vipps-ecom-api.md#vipps-http-headers)
):

```
Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1Ni <snip>
Ocp-Apim-Subscription-Key: 0f14ebcab0ec4b29ae0cb90d91b4a84a
Vipps-System-Name: Acme Enterprises Ecommerce DeLuxe
Vipps-System-Version: 3.1.2
Vipps-System-Plugin-Name: acme-webshop
Vipps-System-Plugin-Version: 4.5.6
```

With the `Merchant-Serial-Number` header, using partner keys:

```
Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1Ni <snip>
Ocp-Apim-Subscription-Key: 0f14ebcab0ec4b29ae0cb90d91b4a84a
Merchant-Serial-Number: 123456
Vipps-System-Name: Acme Enterprises Ecommerce DeLuxe
Vipps-System-Version: 3.1.2
Vipps-System-Plugin-Name: acme-webshop
Vipps-System-Plugin-Version: 4.5.6
```

It's just one extra line.
And: You must of course first get an access token (to send in the `Authorization` header), using the same partner keys, as documented in
[Getting started: Get an access token](https://github.com/vippsas/vipps-developers/blob/master/vipps-getting-started.md#get-an-access-token).

Partners must always send the `Merchant-Serial-Number` header, and we recommend
that _everyone_ sends it, also when using the merchant's own API keys.
The `Merchant-Serial-Number` header can be used with all API keys, and can
speed up any trouble-shooting of API problems quite a bit.

The same set of partner keys can be used for all your merchants' sale units, for both the
[Vipps eCom API](https://github.com/vippsas/vipps-ecom-api)
and the
[Vipps Recurring API](https://github.com/vippsas/vipps-recurring-api),
including the
[Userinfo](#use-userinfo)
endpoints for both.

**Please note:**
* If the merchant can, in any way, see or access the API keys you _must not_
  use partner keys, as that will make it possible to act on behalf of all your
  merchants.
* If you are already using the same, identical API-keys for multiple
  merchants, you are _already_ using partner keys. That's good.

See:
* [Partner keys for eCom](https://github.com/vippsas/vipps-ecom-api/blob/master/vipps-ecom-api.md#partner-keys)
* [Partner keys for Recurring](https://github.com/vippsas/vipps-recurring-api/blob/master/vipps-recurring-api.md#partner-keys)
* [Getting started: Quick overview of how to make an API call](https://github.com/vippsas/vipps-developers/blob/master/vipps-getting-started.md#quick-overview-of-how-to-make-an-api-call)

**Please note:** Vipps payments can only be made to merchants that have a
customer relationship with Vipps, and that have gone through the required
compliance checks, etc after ordering Vipps on
[portal.vipps.no](https://portal.vipps.no).
It is not possible to pay the partner instead of the merchant. See also:
[Can I create a marketplace with multiple merchants?](https://github.com/vippsas/vipps-ecom-api/blob/master/vipps-ecom-api-faq.md#can-i-create-a-marketplace-with-multiple-merchants)

## Plugin development

All official plugins are open source, free to use, and available in our
[plugin section](https://github.com/vippsas/vipps-plugins), as well as on
the platforms they are designed for.

We encourage submitting issues and PRs to improve the plugins.

If you have developed, or plan to develop, a plugin for Vipps, and you think
it may be a candidate for becoming an official plugin: See
[How to become a Vipps partner](#how-to-become-a-vipps-partner)
and let us know what your plans are.

# How to sign up new merchants

The below is for platform partners.
Merchants that do not use a platform partner sign up on their own on
[portal.vipps.no](https://portal.vipps.no).

All merchants must have a customer relationship with Vipps,
in addition to the one with the partner.

A merchant that already has a customer relationship with Vipps still needs
to apply for a new product (sale unit) to use with a new partner.

1. The merchant applies for Vipps on
   [portal.vipps.no](https://portal.vipps.no)
   and selects:
   1. The correct product
   2. The partner
   3. The price package, typically "Pris 1", "Pris 2" or "Pris 3".
      We are aware that it's not ideal to let merchants select the price package,
      but right now this must be done - and it works quite well for most partners.
      Talk to your partner contact in Vipps about the current plans and status.
2. Vipps processes the application and does customer control (KYC, PEP, AML, etc).
   This may take a few days, depending on the information provided and the workload.
3. The merchant can check the status of the application on
   [portal.vipps.no](https://portal.vipps.no)
   at any time.
   Vipps does not have the capacity to answer emails with status inquiries.
4. Vipps notifies the merchant **and the partner** by email that the application is approved,
   with thew new MSN, and that the merchant can now use Vipps.
   If the application is declined, only the merchant is notified.

The partner uses their
[partner keys](#partner-keys)
and the new MSN to make Vipps payments.

**Please note:**
- Partners can ask the mercant to create a user for them so they get access
  to the MSN on
  [portal.vipps.no](https://portal.vipps.no).
  See:
  [Getting started: Permissions and users](https://github.com/vippsas/vipps-developers/blob/master/vipps-getting-started.md#permissions-and-users).
- We are working on direct URLs that will let merchants go directly to the
  right page on
  [portal.vipps.no](https://portal.vipps.no)
  with as much information as possible information pre-filled.
- We have started on a proof of concept for a
  [Vipps Partner API PoC](#vipps-partner-api-poc),
  which will improve the process above. Please bear with us in the meantime.

## Typical reasons for delays

The application solution on
[portal.vipps.no](https://portal.vipps.no)
contains a lot of help and tips, as well as links to more information.

There are still some common problems that cause delays:

* The application is not signed by a person that has signatory rights.
  Merchants can check who can sign at
  [Brønnøysundregistrene](https://www.brreg.no).
* The merchant's website does not have the
  [legally required terms and conditions](https://www.forbrukertilsynet.no/lov-og-rett/veiledninger-og-retningslinjer/standard-salgsbetingelser-for-forbrukerkjop-av-varer-over-internett).
* The merchant's website does not have the organization number clearly visible.
* The merchant has not provided enough information about what they want to use
  Vipps for ("Spesifiser kort hvilke varer/tjenester dere selger").
* Vipps has sent an email requesting additional information, but has not received a reply.
  Merchants should check their "spam" and try to search their email for "vipps".
* The application has been declined. Vipps only informs the merchant about this, not the partner.

**Please note:** Partners should always check with the merchant for an updated status before contacting Vipps.

## Vipps Partner API PoC

An early draft of the Vipps Partner API is available on GitHub:
https://github.com/vippsas/vipps-partner-api

The plan for the Vipps Partner API will let partners, banks and large corporations manage their merchants and sale units. See the GitHub repository for background and priorities.

## Vipps Signup API

The soon-to-be-deprecated legacy
[Vipps Signup API](https://github.com/vippsas/vipps-signup-api),
also called "partial signup",
is still available _for a short while_ for partners that have already started
using it, but new partners should use the more efficient
[partner keys](#partner-keys)
(and the
[Vipps Partner API PoC](#vipps-partner-api-poc)
when available).

The Vipps Signup API in short:
1. Partners sendt some basic info about a new merchant to Vipps.
2. The merchant gets a URL to the old, outdated signup form, with a few pre-filled fields.
3. The merchant completes the form and signs with BankID.
4. Vipps processes the application and does customer control (KYC, PEP, AML, etc).
5. Vipps makes a callback to the partner's API with the merchant's new API keys.

We are phasing out the Vipps Signup API because:
* The signup process is now on
  [portal.vipps.no](https://portal.vipps.no)
  and has _many_ improvements over the old signup form that is used in steps 2
  and 3 above as part of the Signup API.
* [Partner keys](#partner-keys)
  eliminate the need for merchant-specific API keys, so step 5 is no longer needed.

See: [Why is the Signup API being phased out?](#why-is-the-signup-api-being-phased-out).

### If you are using the Signup API

You should _as quickly as possible_ stop using it and instead follow the
guidelines described in
[How to sign up new merchants](#how-to-sign-up-new-merchants).

Merchants will then get the _much improved_ new signup solution,
applications will be processed much faster, and by using
[partner keys](#partner-keys)
there is no need for callbacks with the merchant's API keys.

The new
[Vipps Partner API PoC](#vipps-partner-api-poc)
will be simple in the beginning, but our goal is to offer as much
self-service to partners as possible.

### Why is the Signup API being phased out?

In short: It is no longer needed, as there are better solutions that are
continuously improved.

1. The Signup API uses the old, outdated signup form, where merchants make mistakes.
2. Applications from merchants that have used the old signup form takes longer to
   to process, and often require  manual follow-up on email for clarifications.
3. New products, such as
   [Vipps Checkout](https://vipps.no/produkter-og-tjenester/bedrift/ta-betalt-paa-nett/vipps-checkout/),
   can not be ordered using the Signup API.
   The old signup forms will not be updated to support new products.
4. The signup on portal.vipps.no already contains a _lot_ of improvements over the
   signup used by the Signup API, and is being continuously improved - practically
   every day. The Signup API gets none of these improvements.   
5. The callbacks to the partner (with API keys and MSN) often fail because of
   problems on the partner's side, and Vipps has an unacceptable amount of manual
   work to handle this by manually sending API keys with encrypted Excel files with
   passwords on SMS, etc.
6. Merchants that already have another Vipps product get a difficult user experience,
   where they have to provide the same information they have already provided
   (company details, etc), and sign again with BankID.
7. Vipps is making significant changes to the underlying data model for how
   merchants are represented, and we can not continue to maintain both the
   old Signup API and the current signup on portal.vipps.no.

See:
[Deprecation of the Vipps Signup API](https://github.com/vippsas/vipps-signup-api/blob/master/vipps-signup-api-deprecation.md).

### When will there be a replacement for the Signup API?

We are working on a new and better solution. See:
[Vipps Partner API PoC](#vipps-partner-api-poc).

The Partner API will be available as soon as possible, but we can not give
a date. We will make the most important features available first, and
welcome feedback. See:
[Questions?](#questions).

Vipps is making fundamental changes to the data model for representing
merchants, partners, prices, payments, etc. This is a huge effort, with
numerous dependencies, and has in practice already been in process for years.
It is a continuous effort to improve and adapt our systems, and at the time
of writing there is a lot going on with how _merchants_ are handles internally.

Vipps is able to handle these changes in the backend services in the signup solution on
[portal.vipps.no](https://portal.vipps.no),
as we have complete control, and can make related changes at the same time.
When we make a backend change, we make the necessary change in the frontend too.

An external API is different. We can not make a stable API while we are making
big changes in our backend, as that would require partners to frequently
update their integration with our API.

Again: The Signup API is no longer needed, as there are better solutions that are
continuously improved - and we are working hard to provide even better solutions.

# FAQ for partners

You may find answers to your questions on our FAQ section on the bottom of the
[partner page on vipps.no](https://vipps.no/developer/bli-partner/)

# Questions

Please contact your partner manager.

We're always happy to help with code or other questions you might have!
Please create an [issue](https://github.com/vippsas/vipps-developers/issues),
a [pull request](https://github.com/vippsas/vipps-developers/pulls),
or contact us by email: partnerbestilling@vipps.no.

Sign up for our [Technical newsletter for developers](https://github.com/vippsas/vipps-developers/tree/master/newsletters).
