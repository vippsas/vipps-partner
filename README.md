# Vipps Partners

Document version: 1.1.1.

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
  * [Merchant Management API](#merchant-management-api)
  * [The Vipps Signup API](#the-vipps-signup-api)
- [Questions?](#questions-)

# How to become a Vipps partner

If you and your merchants have a good volume and great potential, we would like
to have you on the team as a partner. The goal of the partner program is to
find areas where we can work closely together and experience good growth - together.
The collaboration will give you good exposure and opportunities for even better
solutions for our customers.

## Partner types

Vipps has three types of partners:

1. Platform partners: Provide a ready-to-use platform for their merchants, do all
   integration, development and maintenance on their platform, and also
   provide all support for the merchants.
2. Integration partners: Assist merchants in development of the merchants'
   integration. Typically a concultancy firm doing development for the merchant.
3. Plugin partners: Develop Vipps' official
   [open source plugins](https://github.com/vippsas/vipps-plugins)
   for Vipps.
   
This document is mainly for platform partners.

## Apply on vipps.no

Please visit the
[partner page at Vipps.no]( https://vipps.no/developer/bli-partner/),
read through our FAQ, and fill out the form.

## Integrate with the Vipps APIs

See: [Developer documentation](#developer-documentation).

You will receive an email with details about access to the
[test environment](https://github.com/vippsas/vipps-developers/blob/master/vipps-test-environment.md).

**Please note:** Access to the production environment requires thorough
checks required by law. For most partners this is not relevant, as
it is the partner's _merchants_ that will need production access.
The partner only needs access to the test environment to complete an integration.

## Finishing the integration and going live

An integration is considered finished when all the elements of the
relevant API's checklist are done (see the checklists for the
[eCom API](https://github.com/vippsas/vipps-ecom-api/blob/master/vipps-ecom-api-checklist.md)
and the
[Recurring API](https://github.com/vippsas/vipps-recurring-api/blob/master/vipps-recurring-api-checklist.md)).

In addition, all partners are required to complete the following:
- [ ] As a partner you accept the [Partner terms and conditions](https://github.com/vippsas/vipps-partner/blob/main/partnerterms.md)
- [ ] Technical documentation for merchants
     - [ ] Documentation for merchants regarding how to apply for Vipps products
     - [ ] Documentation for merchants regarding how to configure and use the module
     - [ ] FAQ for merchants
- [ ] Provide one pilot customer to verify the integration in production environment

When the integration checklist is completed, notify Vipps as described in the checklist.
The Vipps Integration team will verify the integration, and contact the partner.

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

With the partner keys you authenticate in the normal way, and then send
the required `Merchant-Serial-Number` header to identify which of your merchants you are
acting on behalf of.

The same set of partner keys can be used for all your merchants' sale units, for both the
[Vipps eCom API](https://github.com/vippsas/vipps-ecom-api)
and the
[Vipps Recurring API](https://github.com/vippsas/vipps-recurring-api),
including the
[Userinfo](#use-userinfo)
endpoints for both.

See:
[Partner keys for eCom](https://github.com/vippsas/vipps-ecom-api/blob/master/vipps-ecom-api.md#partner-keys)
and
[Partner keys for Recurring](https://github.com/vippsas/vipps-recurring-api/blob/master/vipps-recurring-api.md#partner-keys)

**Please note:** Vipps payments can only be made to merchants that have a customer relationship with Vipps,
and that have gone through the required compliance checks, etc after ordering Vipps on
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

All merchants must have a customer relationship with Vipps,
in addition to the one with the partner.

A merchant that already has a customer relationship with Vipps still needs
to apply for a new product (sale unit) to use with a new partner.

1. The merchant applies for Vipps on
   [portal.vipps.no](https://portal.vipps.no)
   and selects:
   1. The correct product
   2. The partner
   3. The price package, typically "Small", "Medium" or "Large"
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

We have started on the
[Merchant Management API](#merchant-management-api),
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

## Merchant Management API

An early draft of the Vipps Merchant Management API is available on GitHub:
https://github.com/vippsas/vipps-merchant-management-api

The Vipps Merchant Management API will let partners, banks and large corporations
manage their merchants and sale units. See the GitHub repository for
background and priorities.

## The Vipps Signup API

The soon-to-be-deprecated legacy
[Vipps Signup API](https://github.com/vippsas/vipps-signup-api),
also called "partial signup",
is still available for partners that have already started using it, but new partners
should use the more efficient
[partner keys](#partner-keys)
(and
[Merchant Management API](#merchant-management-api)
when available).

The Vipps Signup API in short:
1. Partners sendt some basic info about a new merchant to Vipps.
2. The merchant get a URL to a form with a few pre-filled fields.
3. The merchant completes the form and signs with BankID.
4. Vipps processes the application and does customer control (KYC, PEP, AML, etc).
5. Vipps makes a callback to the partner's API with the merchant's new API keys.

We are phasing out the Vipps Signup API because:
* The signup process is now on
  [portal.vipps.no](https://portal.vipps.no)
  and has _many_ improvements over the old signup form that is used in steps 2 and 3 above as part of the Signup API.
* [Partner keys](#partner-keys) eliminate the need for merchant-specific API keys, so step 5 is no longer needed.

# Questions?

We're always happy to help with code or other questions you might have!
Please create an [issue](https://github.com/vippsas/vipps-developers/issues),
a [pull request](https://github.com/vippsas/vipps-developers/pulls),
or contact us by email: partnerbestilling@vipps.no.

Sign up for our [Technical newsletter for developers](https://github.com/vippsas/vipps-developers/tree/master/newsletters).
