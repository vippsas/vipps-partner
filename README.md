# Vipps Partners

💥 Work in progress! We will update this page frequently. "Star" it to get notifications. 💥

Document version: 0.14.3.

If you and your merchants have a good volume and great potential, we would like
to have you on the team as a partner. The goal of the partner program is to
find areas where we can work closely together and experience good growth - together.
The collaboration will give you good exposure and opportunities for even better
solutions for our customers.

# Table of Contents

- [How to become a Vipps partner](#how-to-become-a-vipps-partner)
  * [Apply on vipps.no](#apply-on-vippsno)
  * [Integrate with the Vipps APIs](#integrate-with-the-vipps-apis)
  * [Finishing the integration and going live](#finishing-the-integration-and-going-live)
- [Technical information for partners](#technical-information-for-partners)
  * [Partner keys](#partner-keys)
  * [Merchant Management API](#merchant-management-api)
  * [Plugin development](#plugin-development)
- [How to sign up new merchants](#how-to-sign-up-new-merchants)
- [Questions?](#questions-)

# How to become a Vipps partner

## Apply on vipps.no

Please visit our
[partner page at Vipps.no]( https://vipps.no/developer/bli-partner/),
read through our FAQ, and fill out the form.

## Integrate with the Vipps APIs

You will receive an email with detail about access to our
[test environment](https://github.com/vippsas/vipps-developers/blob/master/vipps-test-environment.md).

All developer resources are available on
[GitHub](https://github.com/vippsas/vipps-developers).

**Please note:** Access to the production environment requires thorough
checks required by law, and for most partners this is not relevant, as
it is the partner's _merchants_ that will need production access.

## Finishing the integration and going live

An integration is considered finished when all the elements of the
relevant APIs checklist are done (see the checklists for the
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

When the integration checklist is completed, send a notification to integration@vipps.no.
Vipps Integration team will verify the implemented solution, the partner receives an email from Vipps saying that the implementation is OK.

Vipps adds the partner to vipps.no, including the signup forms for merchants.

# Technical information for partners

## Partner keys

As a partner you can manage transactions on behalf of other Vipps merchants.
Vipps will provide you with _partner keys_, which allows you to use your own API credentials to
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

## Merchant Management API

An early version of the
[Vipps Merchant Management API](https://github.com/vippsas/vipps-merchant-management-api)
is available on GitHub.

The Vipps Merchant Management API will let partners, banks and large corporations
manage their merchants and sale units. See the GitHub repository for
background and priorities.

## Plugin development

If you’re an integration partner we have a number of plugins for different open
source plattforms you can (and should) use to integrate Vipps.
[See our plugin section](https://github.com/vippsas/vipps-plugins).

# How to sign up new merchants

1. The merchant applies for Vipps on
   [portal.vipps.no](https://portal.vipps.no)
   and selects the correct product and partner.
2. Vipps completes customer control (KYC, PEP, AML, etc).
3. The merchant is notified by Vipps that their application is approved and can use Vipps.
4. The merchant notifies the partner that the application is approved and also sends the new MSN to the partner.

The merchant can check the status of their application on
[portal.vipps.no](https://portal.vipps.no)
at any time.

**Important: The merchant must notify the partner when
the Vipps application is processed, and provide the MSN to the partner**. 

The partner uses their partner keys and the new MSN to make Vipps payments.

We are working on the Merchant Management API (MMAPI, see above), which will improve the
process above. Please bear with us in the meantime.

The legacy [Signup API](https://github.com/vippsas/vipps-signup-api)
is still available for partners that have already started using it, but new partners
should use partner keys and MMAPI when available.

# Questions?

We're always happy to help with code or other questions you might have!
Please create an [issue](https://github.com/vippsas/vipps-developers/issues),
a [pull request](https://github.com/vippsas/vipps-developers/pulls),
or contact us by email: partnerbestilling@vipps.no.

Sign up for our [Technical newsletter for developers](https://github.com/vippsas/vipps-developers/tree/master/newsletters).
