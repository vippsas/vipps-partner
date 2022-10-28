<!-- START_METADATA
---
title: Introduction
sidebar_position: 1
pagination_next: null
pagination_prev: null
---
END_METADATA -->

# Vipps Partners

<!-- START_COMMENT -->

ℹ️ Please use the new documentation:
[Vipps Technical Documentation](https://vippsas.github.io/vipps-developer-docs/).

<!-- END_COMMENT -->

Technical information for Vipps partners.

Document version: 2.1.2.

<!-- START_TOC -->

## Table of contents

* [How to become a Vipps partner](#how-to-become-a-vipps-partner)
  * [Partner types](#partner-types)
  * [Apply on vipps.no](#apply-on-vippsno)
  * [Integrate with the Vipps APIs](#integrate-with-the-vipps-apis)
  * [Finishing the integration and going live](#finishing-the-integration-and-going-live)
* [Technical information for partners](#technical-information-for-partners)
  * [Developer documentation](#developer-documentation)
  * [Vipps Partner API](#vipps-partner-api)
  * [Partner keys](#partner-keys)
  * [Plugin development](#plugin-development)
  * [How to get access to portal.vipps.no](#how-to-get-access-to-portalvippsno)
* [How to sign up new merchants](#how-to-sign-up-new-merchants)
  * [Partners use the Partner API to pre-fill the signup form](#partners-use-the-partner-api-to-pre-fill-the-signup-form)
  * [Merchants can also sign up on portal.vipps.no](#merchants-can-also-sign-up-on-portalvippsno)
  * [How to check if a merchant is signed up with the partner as partner](#how-to-check-if-a-merchant-is-signed-up-with-the-partner-as-partner)
  * [Typical reasons for delays](#typical-reasons-for-delays)
  * [How to change partners for a merchant](#how-to-change-partners-for-a-merchant)
  * [The deprecated Vipps Signup API](#the-deprecated-vipps-signup-api)
* [FAQ for partners](#faq-for-partners)
* [Questions](#questions)

<!-- END_TOC -->

## How to become a Vipps partner

If you and your merchants have a good volume and great potential, we would like
to have you on the team as a partner. The goal of the partner program is to
find areas where we can work closely together and experience good growth - together.
The collaboration will give you good exposure and opportunities for even better
solutions for our customers.

### Partner types

Vipps has three types of partners:

1. **Platform partners:** Provide a "closed" ready-to-use platform for their merchants,
   do all integration with the Vipps APIs,
   do all development and maintenance on their platform,
   and also provide all support for the merchants.

   Platform partners use the Vipps APIs _on behalf of_ merchants:
   Initiate payments, do captures, do refunds, etc.

   Merchants that use a platform partner
   _never need to see their API keys_,
   since the platform partner uses
   [partner keys](#partner-keys).

2. **Integration partners:** Assist merchants in development of the merchants'
   integration. Typically, a consultancy firm doing development for the merchant.
   An integration partner does not use the Vipps APIs on behalf of the merchant.

   Merchants that use an integration partner must
   _provide the API keys to the integration partner_.
   See [Getting started: Getting the API keys](https://github.com/vippsas/vipps-developers/blob/master/vipps-getting-started.md#getting-the-api-keys).

   If the integration partner continues to run, manage, and develop
   _everything_ related to the Vipps integration, and also manage the API
   credentials _on behalf of_ the merchant, the partner is similar to a
   platform partner and should use
   [partner keys](#partner-keys).

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
using one set of API keys for all merchants:
[Partner keys](#partner-keys).
Other partners must rely on each merchant's individual API keys.

Information for PSP (Payment Service Providers) is here:
[Vipps PSP API](https://github.com/vippsas/vipps-psp-api),
including
[PSP Signup API](https://github.com/vippsas/vipps-psp-api/blob/master/vipps-psp-signup-api.md).

### Apply on vipps.no

Please visit the
[partner page at Vipps.no]( https://vipps.no/developer/bli-partner/),
read through our FAQ, and fill out the form.

### Integrate with the Vipps APIs

See: [Developer documentation](#developer-documentation).

When your application is approved, you will receive an email with details about access to the
[test environment](https://github.com/vippsas/vipps-developers/blob/master/developer-resources/test-environment.md.

If you already have a pilot merchant that has access to the Vipps APIs,
you can also use the merchant's API keys for the test environment for development.

**Please note:** Access to the production environment requires thorough
checks required by law. For most partners this is not relevant, as
it is the partner's _merchants_ that will need production access.
The partner only needs access to the test environment to complete an integration.

### Finishing the integration and going live

An integration is considered complete when all the elements of the
relevant API checklists are done. See the checklists:

- [ ] [Vipps eCom API](https://github.com/vippsas/vipps-ecom-api/blob/master/vipps-ecom-api-checklist.md)
- [ ] [Vipps Recurring API](https://github.com/vippsas/vipps-recurring-api/blob/master/vipps-recurring-api-checklist.md)
- [ ] [Vipps Login API](https://github.com/vippsas/vipps-login-api/blob/master/vipps-login-api-checklist.md)

**Important:** Please make sure to read and understand the checklist.
You must provide the required information, such as orderId and the HTTP headers.
If you simply send a copy of the checklist with "OK" for each item,
we will have to ask you again to complete the checklist.

In addition to the checklists mentioned above, all partners are required to complete the following:

- [ ] As a partner, you accept the [Partner terms and conditions](https://github.com/vippsas/vipps-partner/blob/main/partner-terms.md)
- [ ] Provide technical documentation for merchants regarding:
     - [ ] How to apply for Vipps products (a URL, plain text or PDF is preferred)
     - [ ] How to configure and use the module (a URL, plain text or PDF is preferred)
     - [ ] Frequently Asked Questions (FAQs) for merchants (a URL, plain text or PDF is preferred)
- [ ] Provide one pilot customer to verify the integration in the production environment (send organization number and name)
- [ ] Describe how your integration has been set up, with a link to a demo, or provide screenshots (PDF is preferred).

When the integration checklist is completed, notify Vipps Integration
[integration@vipps.no](mailto:integration@vipps.no)
as described in the checklist, with `orderId` examples from the test environment,
pilot customer info, and a description of the implemented solution.

Vipps Integration will verify the integration and take contact with you.

Vipps then adds you to vipps.no, including the signup forms on
[portal.vipps.no](https://portal.vipps.no)
where the merchants can sign up and select you as their partner.

## Technical information for partners

### Developer documentation

See: [Developer documentation](https://vippsas.github.io/vipps-developer-docs/).

### Vipps Partner API

See: [Partner API](https://vippsas.github.io/vipps-developer-docs/docs/APIs/partner-api).

### Partner keys

As a partner, you manage transactions on behalf of Vipps merchants.
Vipps provides you with _partner keys_, which allow you to use your own API credentials to
make API calls on behalf of your merchants (i.e., the sales units that are linked to you as a partner).

See: [Partner keys](partner-keys.md).

### Plugin development

All official plugins are open source, free to use, and available in our
[plugin section](https://github.com/vippsas/vipps-plugins), as well as on
the platforms they are designed for.

We encourage submitting issues and PRs to improve the plugins.

If you have developed, or plan to develop, a plugin for Vipps, and you think
it may be a candidate for becoming an official plugin: See
[How to become a Vipps partner](#how-to-become-a-vipps-partner)
and let us know what your plans are.

## How to get access to portal.vipps.no

Partners can order Vipps Logg Inn on
[portal.vipps.no](https://portal.vipps.no).
The requirements for customer control are simpler than other products, since
Vipps Logg Inn does not allow for payments.

When the partner's order for Vipps Logg Inn is approved, the partner can log
in on
[portal.vipps.no](https://portal.vipps.no)
and manage their own sale units in
[the test environment](https://github.com/vippsas/vipps-developers/blob/master/developer-resources/test-environment.md.

**Please note:** Partners can also ask the merchant to create a user for them so
they get access to the merchant's MSN on
[portal.vipps.no](https://portal.vipps.no)
as described
[in detail with screenshots here](add-portal-user.md).
The user permissions are described (in Norwegian)
[here](https://vipps.no/hjelp/vipps/kundeforholdet-mitt/hvilke-tilganger-kan-vi-opprette-i-vippsportalen/).
See:
[Getting started: Permissions and users](https://github.com/vippsas/vipps-developers/blob/master/vipps-getting-started.md#permissions-and-users).

## How to sign up new merchants

The information below is for platform partners.

All merchants must have a customer relationship with Vipps,
in addition to the one with the partner.

A merchant that already has a customer relationship with Vipps still needs
to apply for a new product (sale unit) to use with a new partner.
See: [How to change partners for a merchant](#how-to-change-partners-for-a-merchant).

Merchants that do not use a platform partner must sign up on their own on
[portal.vipps.no](https://portal.vipps.no).

### Partners use the Partner API to pre-fill the signup form

The Vipps Partner API lets a partner "prefill" the product order form on
[portal.vipps.no](https://portal.vipps.no)
on behalf of a merchant, so the merchant can log in,
check the data, and submit the product order.

See: [Submit a product order for a merchant](https://github.com/vippsas/vipps-partner-api/blob/main/vipps-partner-api.md#submit-a-product-order-for-a-merchant).

**Please note:** A partner that only rarely needs to onboard a new merchant can
have the merchant order Vipps on
[portal.vipps.no](https://portal.vipps.no)
instead of using the Partner API's prefill functionality.

### Merchants can also sign up on portal.vipps.no

See: [Manual signup](manual-signup.md).

### How to check if a merchant is signed up with the partner as partner

**Please note:** Vipps can not share information about the status of a
merchant's agreement or product orders.
The partner must always check with the merchant.
The merchant can check the status on
[portal.vipps.no](https://portal.vipps.no)
any time.

The
[Vipps Partner API](https://vippsas.github.io/vipps-developer-docs/docs/APIs/partner-api)
lets a partner look up MSNs based on the merchant's
organization number, and also retrieve details of a specific sale unit based
on the sale unit's MSN.

### Typical reasons for delays

The application solution on
[portal.vipps.no](https://portal.vipps.no)
contains a lot of help and tips, as well as links to more information.

There are still some common problems that cause delays:

* The merchant has signed a merchant agreement, but has not ordered any
  Vipps products.
* The application is not signed by a person that has signatory rights.
  Merchants can check who can sign at
  [Brønnøysundregistrene](https://www.brreg.no).
* The merchant's website does not have the
  [legally required terms and conditions](https://www.forbrukertilsynet.no/lov-og-rett/veiledninger-og-retningslinjer/standard-salgsbetingelser-for-forbrukerkjop-av-varer-over-internett).
* The merchant's website does not have the organization number clearly visible.
* The merchant has not provided enough information about what they want to use
  Vipps for ("Spesifiser kort hvilke varer/tjenester dere selger", in English: "Briefly specify which goods/services you sell").
* Vipps has sent an email requesting additional information, but has not received a reply.
  Merchants should check their "spam" and try to search their email for "vipps".
* The application has been declined. Vipps only informs the merchant about this,
  not the partner. The reason for declining may be related to risk and
  compliance, and thus sensitive.

## How to change partners for a merchant

See: [How to change partners](how-to-change-partners.md).

## The deprecated Vipps Signup API

The deprecated legacy
[Vipps Signup API](https://github.com/vippsas/vipps-signup-api),
also called "partial signup", is no longer available,
and partners should use the more efficient
[partner keys](#partner-keys)
(and the
[Vipps Partner API](#vipps-partner-api)
when available).

## FAQ for partners

You may find answers to your questions on our FAQ section on the bottom of the
[partner page on vipps.no](https://vipps.no/developer/bli-partner/)

## Questions

Please contact your partner manager.

We're always happy to help with code or other questions you might have!
Please create an [issue](https://github.com/vippsas/vipps-developers/issues),
a [pull request](https://github.com/vippsas/vipps-developers/pulls),
or contact us by email: partnerbestilling@vipps.no.

Sign up for our [Technical newsletter for developers](https://vippsas.github.io/vipps-developer-docs/docs/vipps-developers/newsletters).
