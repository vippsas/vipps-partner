# Vipps Partners

Technical information for Vipps partners.

Document version: 1.2.17.

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
  * [Merchants sign up on portal.vipps.no](#merchants-sign-up-on-portal.vipps.no)
    - [How to check if a merchant is signed up with the partner as partner](#how-to-check-if-a-merchant-is-signed-up-with-the-partner-as-partner)
  * [Typical reasons for delays](#typical-reasons-for-delays)
  * [Vipps Partner API PoC](#vipps-partner-api-poc)
  * [How to change partners for a merchant](#how-to-change-partners-for-a-merchant)
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

   If the integration partner continues to run, manage and develop
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
   the partner uses the Vipps APIs on behalf of the merchant.

A partner may act as a different type of partner in different situations.
It is possible for a partner to both develop an official Vipps plugin and
to be a platform partner.

This document is mainly for platform partners that act _on behalf of_ merchants,
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

When your application is approved you will receive an email with details about access to the
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
- [ ] Describe how your integration has been set up with a link to a demo, or provide screenshots.

When the integration checklist is completed, notify Vipps Integration
[integration@vipps.no](integration@vipps.no)
as described in the checklist with `orderId` examples from the test environment,
pilot customer info and description of the implemented solution.

Vipps Integration will verify the integration, and contact the partner.

Vipps then adds the partner to vipps.no, including the signup forms on
[portal.vipps.no](https://portal.vipps.no)
where the merchants can sign up and select the partner as their partner.

# Technical information for partners

## Developer documentation

All developer documentation and tools are available on
[GitHub](https://github.com/vippsas/vipps-developers).

## Vipps API Lifecycle

See the
[Vipps API Lifecycle](https://github.com/vippsas/vipps-developers/blob/master/vipps-api-lifecycle.md)
for information about deprecation notices, etc.

## Partner keys

As a partner you manage transactions on behalf of Vipps merchants.
Vipps provides you with _partner keys_, which allows you to use your own API credentials to
make API calls on behalf of your merchants (only for the sales units that are linked to you as a partner, though).
Please note that partner keys can not be used for Vipps Login, here you need to use the merchant's own keys.

With the partner keys you authenticate in the normal way, and then send
the required `Merchant-Serial-Number` header to identify which of your merchants you are
acting on behalf of: `Merchant-Serial-Number: 123456`.

Example of headers in an API request _without_ using partner keys
(including the required
[Vipps HTTP headers](https://github.com/vippsas/vipps-ecom-api/blob/master/vipps-ecom-api.md#vipps-http-headers)):

```
Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1Ni <snip>
Ocp-Apim-Subscription-Key: 0f14ebcab0ec4b29ae0cb90d91b4a84a
Vipps-System-Name: Acme Enterprises Ecommerce DeLuxe
Vipps-System-Version: 3.1.2
Vipps-System-Plugin-Name: acme-webshop
Vipps-System-Plugin-Version: 4.5.6
```

With the `Merchant-Serial-Number` header, using partner keys
(including the required
[Vipps HTTP headers](https://github.com/vippsas/vipps-ecom-api/blob/master/vipps-ecom-api.md#vipps-http-headers)):

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
* Vipps can not send the merchant's API keys to the partner. The partner must get
  the API keys from the merchant in a secure way (if partner keys are not used).
  See:
  [Getting started: Get credentials](https://github.com/vippsas/vipps-developers/blob/master/vipps-getting-started.md#get-credentials)
  for more details.
* If the merchant is unable to provide the API keys to the partner in a secure
  way, the merchant _can_ create a user for the partner,
  [as described in detail with screenshots here](add-portal-user.md):
  1. Log in with BankID on portal.vipps.no
  2. Click "Brukertilganger"
  3. Click "Legg til bruker"
  4. Enter the phone number of the person at the partner, click "Neste"
  5. Check the "Lese" and "Utvikler" checkboxes, click "Neste"
  6. Check the sale unit the new user will get access to, click "Ferdig"

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
See: [How to change partners for a merchant](#how-to-change-partners-for-a-merchant).

## Merchants sign up on portal.vipps.no

1. The merchant logs in on
   [portal.vipps.no](https://portal.vipps.no) using BankID
2. If the merchant does not have an existing customer relationship with Vipps, they need to first set this up. They can find the necessary form by going to:
`https://portal.vipps.no/register/{organisation number}`

   There, they need to fill in details for the company, including
   "reelle rettighetshaverer", politically exposed persons, etc.
   This application is signed with BankID by a person that has
   signatory rights for the company.

3. If the merchant already has a customer relationship or the above step has been done, the merchant then needs to apply for the relevant Vipps product(s) on
   [portal.vipps.no](https://portal.vipps.no)
   and select:
   1. The correct product
   2. The partner
   3. The price package, typically "Pris 1", "Pris 2" or "Pris 3".
      We are aware that it's not ideal to let merchants select the price package,
      but right now this must be done - and it works quite well for most partners.
      Talk to your partner contact in Vipps about the current plans and status.
3. Vipps processes the application and does customer control (KYC, PEP, AML, etc).
   This may take a few days, depending on the information provided and the workload.
4. The merchant can check the status of the application on
   [portal.vipps.no](https://portal.vipps.no)
   at any time.
   Vipps does not have the capacity to answer emails with status inquiries.
5. Vipps notifies the merchant **and the partner** by email that the application is approved,
   with the new MSN, and that the merchant can now use Vipps.
   If the application is declined, only the merchant is notified.

The partner uses their
[partner keys](#partner-keys)
and the new MSN to make Vipps payments.

**Please note:**
- Partners can ask the merchant to create a user for them so they get access
  to the MSN on
  [portal.vipps.no](https://portal.vipps.no).
  The user permissions are described (in Norwegian)
  [here](https://vipps.no/hjelp/vipps/kundeforholdet-mitt/hvilke-tilganger-kan-vi-opprette-i-vippsportalen/).
  See:
  [Getting started: Permissions and users](https://github.com/vippsas/vipps-developers/blob/master/vipps-getting-started.md#permissions-and-users).
- We are working on direct URLs that will let merchants go directly to the
  right page on
  [portal.vipps.no](https://portal.vipps.no)
  with as much information as possible pre-filled.
- We have started on a proof of concept for a
  [Vipps Partner API PoC](#vipps-partner-api-poc),
  which will improve the process above. Please bear with us in the meantime.
- Partner keys can not be used for Vipps Login, here you need to use the merchant's own keys.

### How to check if a merchant is signed up with the partner as partner

A workaround until
[Vipps Partner API PoC](#vipps-partner-api-poc)
is available:

Partners can use the partner keys and try to retrieve a fictional `orderId` with
the merchant's MSN with
[`GET:/ecomm/v2/payments/{orderId}/details`](https://vippsas.github.io/vipps-ecom-api/#/Vipps_eCom_API/getPaymentDetailsUsingGET).

If the MSN does not have the partner as partner, this will be the error:
```
[
    {
        "errorCode": "Unauthorized",
        "errorMessage": "Invalid MSN: 123. This MSN is not valid for the provided super merchant id. Check that you are using the correct credentials for the right environment.",
        "contextId": "87f70e69-5649-458f-a3cc-39acbec0d4ba",
        "errorGroup": "Merchant"
    }
]
```

If the MSN is set up correctly for the partner, the fictional `orderId`
will result in this error:
```
[
    {
        "errorGroup": "Merchant",
        "errorCode": "35",
        "errorMessage": "Requested Order not found",
        "contextId": "b829cb3f-2abd-4eb4-a425-68a173fd630a"
    }
]
```

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
* The application has been declined. Vipps only informs the merchant about this,
  not the partner. The reason for declining may be related to risk and
  compliance, and thus sensitive.

**Please note:** Partners should always check with the merchant for an updated status before contacting Vipps.

## Vipps Partner API PoC

An early draft of the Vipps Partner API is available on GitHub:
https://github.com/vippsas/vipps-partner-api

The plan for the Vipps Partner API will let partners, banks and large corporations manage their merchants and sale units. See the GitHub repository for background and priorities.

## How to change partners for a merchant

If the merchant changes partners, the merchant's sale unit (identified with MSN,
the Merchant Serial Number) must be reconfigured so the new partner's
[partner keys](https://github.com/vippsas/vipps-partner#partner-keys)
can be used for the same MSN.

The MSN can only be used with one set of partner keys at a time,
so in the transition period this requires some effort from
both the merchant and the two partners.

This is the recommended way:

1. The merchant logs in on
  [portal.vipps.no](https://portal.vipps.no)
  and retrieves the API keys for the MSN, as documented in
  [Getting started](https://github.com/vippsas/vipps-developers/blob/master/vipps-getting-started.md#getting-the-api-keys).
2. The merchant securely provides the MSN's API keys to _both_ the
  old partner and the new partner. This ensures that both partners can
  make API calls for the MSN, regardless of each partner's
  [partner keys](https://github.com/vippsas/vipps-partner#partner-keys).
3. The new partner contacts
  [Partnerbestilling](https://github.com/vippsas/vipps-developers/blob/master/contact.md#we-help-with-technical-issues)
  and orders a reconfiguration of the MSN: Link it to the new partner instead
  of the old one.
  When this is done, the MSN has the new partner as partner.
4. The new partner's partner keys now work for the MSN,
  and the old partner's partner keys have stopped working for this MSN.
5. The new partner uses its partner keys.
  The old partner (if it needs to make API calls) must use the merchant's own API keys,
  which they got in step 2.

Both partners can use the MSN's own API (from step 2) keys if there are "special"
API calls to make in the transition period.
The new partner should _always_ use the partner keys.
Vipps offers a
[Postman collection](https://github.com/vippsas/vipps-recurring-api/blob/master/vipps-recurring-postman.md)
that can be used if needed.

When the merchant wants to remove the old partner's access to the MSN,
the merchant can log in on
[portal.vipps.no](https://portal.vipps.no)
and regenerate the MSN's API keys.
That will make the MSN's old API keys invalid and unusable.

**Please note:** Vipps has previously handled the above by creating a new MSN to use with the
new partner. We no longer offer this, as it creates a lot of additional work,
and it results in a confusing user experience for Vipps users - and partners.

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
2. Applications from merchants that have used the old signup form take longer
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
8. The Signup API has no authentication or other security. Anyone can send
   requests. There is no validation of data, and when a partner sends
   incorrect data (which happens quite often), it requires manual correction by Vipps.

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
of writing there is a lot going on with how _merchants_ are handled internally.

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
