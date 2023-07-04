<!-- START_METADATA
---
title: Vipps Partners
sidebar_label: Introduction
sidebar_position: 1
description: Technical information for Vipps partners
pagination_next: null
pagination_prev: null
---
END_METADATA -->

# Vipps Partners

<!-- START_COMMENT -->
ℹ️ Please use the website:
[Vipps MobilePay Technical Documentation](https://developer.vippsmobilepay.com/docs/vipps-partner/).
<!-- END_COMMENT -->

Technical information for Vipps partners.

## How to become a Vipps partner

If you and your merchants have a good volume and great potential, we would like
to have you on the team as a partner. The goal of the partner program is to
find areas where we can work closely together and experience good growth - together.
The collaboration will give you good exposure and opportunities for even better
solutions for our customers.

## Partner types

Vipps has four types of partners:

### Platform partner

Provide a "closed" ready-to-use platform for their merchants,
do all integration with the Vipps APIs,
do all development and maintenance on their platform,
and also provide all support for the merchants.

Vipps Partner Plus and Vipps Partner Premium can and should use partner keys.
Platform partners on these partner levels use the Vipps APIs *on behalf of* merchants:
Initiate payments, do captures, do refunds, etc.

Merchants that use a platform partner with Vipps Partner Plus and Vipps Partner Premium
*never need to see their API keys*,
since the partner uses
[partner keys](#partner-keys).

Partner keys can be used with the
[Management API](https://developer.vippsmobilepay.com/docs/APIs/management-api/).

### Reseller partner

Assist merchants in development of the merchants'
integration. Typically, a consultancy firm doing development for the merchant.
A reseller partner does not use the Vipps APIs on behalf of the merchant.

Merchants that use a reseller partner must
*provide the API keys to the integration partner*.
See [Common topics: API Keys](https://developer.vippsmobilepay.com/docs/vipps-developers/common-topics/api-keys#getting-the-api-keys).

If the reseller partner continues to run, manage, and develop
*everything* related to the Vipps integration after it has been developed,
and also manage the API credentials *on behalf of* the merchant, the partner
is similar to a platform partner and should use
[partner keys](#partner-keys).

### Plugin supplier

Develops Vipps' official
[open source plugins](https://developer.vippsmobilepay.com/docs/vipps-plugins)
on contract for Vipps.

If a partner uses official Vipps plugins to implement a Vipps integration
for a merchant, the API credentials for the merchant must be used, and
the partner uses the Vipps APIs on behalf of the merchant.

### PSP partner

Uses the
[Vipps PSP API](https://developer.vippsmobilepay.com/docs/APIs/psp-api)
to offer Vipps to its merchants.

Information for PSP (Payment Service Providers) is here:
[Vipps PSP API](https://developer.vippsmobilepay.com/docs/APIs/psp-api),
including
[PSP Signup API](https://developer.vippsmobilepay.com/docs/APIs/psp-api/vipps-psp-signup-api).

### More about partner types

A partner may act as a different type of partner in different situations.
It is possible for a partner to both develop an official Vipps plugin and
to be a platform partner.

This document is mainly for platform partners that act *on behalf of* merchants,
using one set of API keys for all merchants:
[Partner keys](#partner-keys).
Other partners must rely on each merchant's individual API keys.

## Partner levels

See:
[Partner levels](partner-level-up.md).

## Apply on vipps.no

Please visit the
[partner page at Vipps.no](https://www.vipps.no/developer/become-a-partner/),
read through our FAQ, and fill out the form.

## Integrate with the Vipps APIs

See: [Developer documentation](#developer-documentation).

When your application is approved, you will receive an email with details about access to the
[test environment](https://developer.vippsmobilepay.com/docs/vipps-developers/test-environment).

If you already have a pilot merchant that has access to the Vipps APIs,
you can also use the merchant's API keys for the test environment for development.

**Please note:** Access to the production environment requires thorough
checks required by law. For most partners this is not relevant, as
it is the partner's *merchants* that will need production access.
The partner only needs access to the test environment to complete an integration.

## Finishing the integration and going live

An integration is considered complete when all the elements of the
relevant API checklists are done. See the checklists:

* [ ] [Vipps ePayment API](https://developer.vippsmobilepay.com/docs/APIs/epayment-api/checklist/)
  (the [ePayment API](https://developer.vippsmobilepay.com/docs/APIs/epayment-api/)
  supersedes the
  [eCom API](https://developer.vippsmobilepay.com/docs/APIs/ecom-api/))
* [ ] [Vipps Recurring API](https://developer.vippsmobilepay.com/docs/APIs/recurring-api/vipps-recurring-api-checklist)
* [ ] [Vipps Login API](https://developer.vippsmobilepay.com/docs/APIs/login-api/vipps-login-api-checklist)

**Important:** Please make sure to read and understand the checklist.
You must provide the required information, such as
[`reference`](https://developer.vippsmobilepay.com/docs/vipps-developers/common-topics/orderid/),
[`paymentDescription`](https://developer.vippsmobilepay.com/docs/vipps-developers/common-topics/transactiontext/)
and
[HTTP headers](https://developer.vippsmobilepay.com/docs/vipps-developers/common-topics/http-headers/).
If you simply send a copy of the checklist with "OK" for each item,
we will have to ask you again to complete the checklist.

In addition to the checklists mentioned above, all partners are required to complete the following:

|  Required to become a partner   |
| ----     |
| As a partner, you accept the [Partner terms and conditions](partner-terms.md)   |
| Provide technical documentation for merchants regarding: |
| - How to apply for Vipps products (a URL, plain text or PDF is preferred)   |
| - How to configure and use the solution (a URL, plain text or PDF is preferred)   |
| - Frequently Asked Questions (FAQs) for merchants (a URL, plain text or PDF is preferred)   |
| Provide one pilot customer to verify the integration in the production environment (send organization number and name)   |
| Describe how your integration has been set up, with a link to a demo, or provide screenshots (PDF is preferred).    |

When the integration checklist is completed, notify Vipps MobilePay Integration Service
([developer@vippsmobilepay.com](mailto:developer@vippsmobilepay.com))
as described in the checklist, with `reference` examples from the test environment,
pilot customer info, and a description of the implemented solution.

Vipps MobilePay Integration Service will verify the integration and contact you.

After the checklist is approved, you will receive all necessary information from
[partnerbestilling@vipps.no](mailto:partnerbestilling@vipps.no).  

Vipps then adds you to the partner page(s) on vipps.no, and in the signup forms on
[portal.vipps.no](https://portal.vipps.no)
where the merchants can sign up and select you as their partner.

## Technical information for partners

### Developer documentation

See:
[Developer documentation](https://developer.vippsmobilepay.com/docs/vipps-developers).

### Vipps Management API

See:
[Management API](https://developer.vippsmobilepay.com/docs/APIs/management-api/).

### Partner keys

As a partner, you manage transactions on behalf of Vipps merchants.
Vipps provides you with *partner keys*, which allow you to use your own API
credentials to make API calls on behalf of your merchants (i.e., the sales units
that are connected to you as a partner).

This means that you don't need to use the merchant's own API keys.

See: [Partner keys](partner-keys.md).

**Please note:** Partner keys are only available for
[Vipps Partner Plus and Vipps Partner Premium](partner-level-up.md).

### Plugin development

All official plugins are open source, free to use, and available in our
[plugin section](https://developer.vippsmobilepay.com/docs/vipps-plugins),
as well as on the platforms they are designed for.

We encourage submitting issues and pull requests to improve the plugins.

If you have developed, or plan to develop, a plugin for Vipps, and you think
it may be a candidate for becoming an official plugin: See
[How to become a Vipps partner](#how-to-become-a-vipps-partner)
and let us know what your plans are.

## How to get access to portal.vipps.no

Partners that have a Norwegian organization number and Norwegian BankID can
order Vipps Logg Inn on
[portal.vipps.no](https://portal.vipps.no).
The requirements for compliance are simpler than other products, since
[Vipps Login API](https://developer.vippsmobilepay.com/docs/APIs/login-api)
does not allow for payments.

**Please note:**

* The partner must have a website.
* The partner's Norwegian organization number must be clearly visible on the website.
* The partner must mention in the application that the application is for a
  partner and that it's for access to the API for development.

When the partner's order for Vipps Logg Inn is approved, the partner can log
in on
[portal.vipps.no](https://portal.vipps.no)
and manage their own sales units in the
[test environment](https://developer.vippsmobilepay.com/docs/vipps-developers/test-environment).

For information about the test environment, see:
[Developer resources: Test environment](https://developer.vippsmobilepay.com/docs/vipps-developers/test-environment).

**Please note:** Partners can also ask the merchant to create a user for them, so
they get access to the merchant's MSN on
[portal.vipps.no](https://portal.vipps.no)
as described
[in detail with screenshots here](add-portal-user.md).
The user permissions are described (in Norwegian)
[here](https://vipps.no/hjelp/vipps/kundeforholdet-mitt/hvilke-tilganger-kan-vi-opprette-i-vippsportalen/).

See:
[Developer resources: Vipps Portal: Permissions and users](https://developer.vippsmobilepay.com/docs/vipps-developers/developer-resources/portal#permissions-and-users).

## How to sign up new merchants

The information below is for platform partners.

All merchants must have a customer relationship with Vipps,
in addition to the one with the partner.

A merchant that already has a customer relationship with Vipps still needs
to apply for a new product (sales unit) to use with a new partner.
See: [How to change partners for a merchant](#how-to-change-partners-for-a-merchant).

Merchants that do not use a platform partner must sign up on their own on
[portal.vipps.no](https://portal.vipps.no).

### Management API

The
[Management API](https://developer.vippsmobilepay.com/docs/APIs/management-api/)
enables a partner to "pre-fill" the product order form on
[portal.vipps.no](https://portal.vipps.no)
on behalf of a merchant, so the merchant can log in,
check the data, and submit the product order.

See:
[Pre-fill a product order](https://developer.vippsmobilepay.com/docs/APIs/management-api/management-api-guide/#pre-fill-a-product-order).

**Please note:** A partner that only rarely needs to onboard a new merchant can
have the merchant order Vipps on
[portal.vipps.no](https://portal.vipps.no)
instead of using the Management API's "pre-fill" functionality.
The partner may also log in on
[portal.vipps.no](https://portal.vipps.no)
and manually fill in the form, which will be similar to using the
Management API's "pre-fill" functionality.

### Manual signup

See: [Manual signup](manual-signup.md).

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
  Vipps for (*Spesifiser kort hvilke varer/tjenester dere selger*, in English:
  *Briefly specify which goods/services you sell*).
* If the merchant website is not the distribution channel, the requirements outlined above shall also apply to the partner platform.  
* Vipps has sent an email requesting additional information, but has not received a reply.
  Merchants should check their "spam" and try to search their email for "vipps".
* The application has been declined. Vipps only informs the merchant about this,
  not the partner. The reason for declining may be related to risk and
  compliance, and thus sensitive.

### How to check if a merchant is signed up with the partner as partner

**Important:** For partners: Vipps has limited capacity to handle partners' requests to
"just check something", even though it may be trivial. We therefore recommend
the following priority:

1. Integrate with the
   [Management API](https://developer.vippsmobilepay.com/docs/APIs/management-api/),
   so the functionality is made available in the partner's own admin interface.
2. Use the Management API manually with the Postman collection.
3. Ask the merchant to create a user for the partner on portal.vipps.no,
   so the partner can check on behalf of the merchant:
   [How to add a user on portal.vipps.no](https://developer.vippsmobilepay.com/docs/vipps-partner/add-portal-user).
4. See the Vipps FAQ for how to check if a sales unit
   [has skipLandingPage](https://developer.vippsmobilepay.com/docs/vipps-developers/faqs/reserve-and-capture-faq#how-can-i-check-if-i-have-reserve-capture-or-direct-capture)
   or
   [which capture type it has](https://developer.vippsmobilepay.com/docs/vipps-developers/faqs/reserve-and-capture-faq#how-do-i-turn-direct-capture-on-or-off).

**Please note:** Vipps can not share information about the status of a
merchant's agreement or product orders.
This is because we need explicit consent from the merchant to share the
information with the partner, and the consent must also be possible to withdraw.
We have not been able to prioritize implementing this consent management.
Also: Some applications may be declined due to too high risk, suspicion of fraud, etc.
We can not "leak" this information about the merchant.
The partner must always check with the merchant.

The merchant can check the status on
[portal.vipps.no](https://portal.vipps.no)
any time.

When a new merchant gets their Vipps application approved, an email is sent
to both the merchant and the partner with information about:

* The merchant's organization number
* The merchant's name
* The sales unit's MSN
* The sales unit's name

The
[Management API](https://developer.vippsmobilepay.com/docs/APIs/management-api/)
lets a partner look up MSNs based on the merchant's
organization number, and also retrieve details of a specific sales unit based
on the sales unit's MSN.

## How to change partners for a merchant

See: [How to change partners](how-to-change-partners.md).

## The deprecated Vipps Signup API

The deprecated legacy
[Vipps Signup API](https://github.com/vippsas/vipps-signup-api),
also called "partial signup", is no longer available,
and partners should use the more efficient
[partner keys](#partner-keys)
(and the
[Management API](#vipps-partner-api)
when possible).

## FAQ for partners

You may find answers to your questions on our FAQ section on the bottom of the
[partner page on vipps.no](https://www.vipps.no/developer/become-a-partner/)

## Questions

Please contact your partner manager.
If you do not have a partner manager, please contact
[partnerbestilling@vipps.no](mailto:partnerbestilling@vipps.no).

We're always happy to help with code or other questions you might have!
Please create an [issue](https://github.com/vippsas/vipps-developers/issues),
a [pull request](https://github.com/vippsas/vipps-developers/pulls),
or contact us by email:
[partnerbestilling@vipps.no](mailto:partnerbestilling@vipps.no).
