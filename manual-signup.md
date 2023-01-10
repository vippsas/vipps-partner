<!-- START_METADATA
---
title: Manual signup
sidebar_position: 30
pagination_next: null
pagination_prev: null
---
END_METADATA -->

# Manual signup

<!-- START_COMMENT -->

ℹ️ Please use the new documentation:
[Vipps Technical Documentation](https://vippsas.github.io/vipps-developer-docs/docs/vipps-partner/manual-signup).

<!-- END_COMMENT -->

Partners that can, for some reason, not use the Partner API to
[submit a product order for a merchant](https://vippsas.github.io/vipps-developer-docs/docs/APIs/partner-api/vipps-partner-api#submit-a-product-order-for-a-merchant)
must use manual signup: The merchant must fill out the form on its own.

1. The merchant logs in to
   [portal.vipps.no](https://portal.vipps.no) using BankID
2. If the merchant does not have an existing customer relationship with Vipps,
   they need to first set this up. They can find the necessary form by going to:
   `https://portal.vipps.no/register/{organisation-number-goes-here}`

   There, they need to fill in details for the company, including
   "reelle rettighetshavere", politically exposed people, etc.
   This application must be signed with BankID by a person that has
   signatory rights for the company.

3. If the merchant already has a customer relationship or the above step has
   been done, the merchant then needs to apply for the relevant Vipps product(s) on
   [portal.vipps.no](https://portal.vipps.no)
   and select:
   1. The correct product
   2. The partner
   3. The price package, typically "Pris 1", "Pris 2" or "Pris 3".
      We are aware that it's not ideal to let merchants select the price package,
      but right now this must be done - and it works quite well for most partners.
      Talk to your partner contact in Vipps about the current plans and status.
4. Vipps processes the application and does customer control (KYC, PEP, AML, etc).
   This may take a few days, depending on the information provided and the workload.
5. The merchant can check the status of the application on
   [portal.vipps.no](https://portal.vipps.no)
   at any time.
   Vipps does not have the capacity to answer emails with status inquiries.
6. Vipps notifies the merchant **and the partner** by email that the application is approved,
   with the new MSN, and that the merchant can now use Vipps.
   If the application is declined, only the merchant is notified.

The partner uses their
[partner keys](./partner-keys.md)
and the new MSN to make Vipps payments.

**Please note:**

- Partners can ask the merchant to create a user for them, so they get access
  to the MSN on
  [portal.vipps.no](https://portal.vipps.no)
  as described
  [in detail with screenshots here](add-portal-user.md).
  The user permissions are described (in Norwegian)
  [here](https://vipps.no/hjelp/vipps/kundeforholdet-mitt/hvilke-tilganger-kan-vi-opprette-i-vippsportalen/).
  See:
  [Developer resources: Vipps Portal: Permissions and users](https://vippsas.github.io/vipps-developer-docs/docs/vipps-developers/developer-resources/portal#permissions-and-users).
- Partner keys can not be used for the Vipps Login API, here you need to use the merchant's own keys.

# Questions

Please contact your partner manager.

We're always happy to help with code or other questions you might have!
Please create an [issue](https://github.com/vippsas/vipps-developers/issues),
a [pull request](https://github.com/vippsas/vipps-developers/pulls),
or contact us by email: [partnerbestilling@vipps.no](mailto:partnerbestilling@vipps.no).

Sign up for our [Technical newsletter for developers](https://vippsas.github.io/vipps-developer-docs/docs/vipps-developers/newsletters).
