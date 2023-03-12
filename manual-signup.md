<!-- START_METADATA
---
title: Manual signup
sidebar_position: 35
pagination_next: null
pagination_prev: null
---
END_METADATA -->

# Manual signup

<!-- START_COMMENT -->

ℹ️ Please use the website:
[Vipps MobilePay Technical Documentation](https://vippsas.github.io/vipps-developer-docs/docs/vipps-partner).

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

   **Please note:** It is possible for the partner, or simply a person helping the merchant,
   to _fill out_ the form, but the _signing_ of the form must be done
   by a person with signing rights for the merchant.

3. If the merchant already has a customer relationship or the above step has
   been done, the merchant then needs to apply for the relevant Vipps product(s) on
   [portal.vipps.no](https://portal.vipps.no).

   It is possible to give merchants a direct link to the right product:
   - Vipps på nett: https://portal.vipps.no/register/vippspaanett
   - Vipps Checkout: https://portal.vipps.no/register/vippscheckout
   - Vipps i kassa: https://portal.vipps.no/register/vippsikasse
   - Vipps Logg inn: https://portal.vipps.no/register/vippslogginn

   It's the partner's responsibility to make sure the merchant has all necessary
   information to fill out the application correctly. The
   [Partner API's prefill functionality](https://vippsas.github.io/vipps-developer-docs/docs/vipps-partner#partners-use-the-partner-api-to-pre-fill-the-signup-form)
   eliminates both this and other steps for the merchant.

   When the merchant applies for a Vipps product it must select:
   1. The Vipps product (or use a direct link as above)
   2. The partner
   3. The price package, typically "Pris 1", "Pris 2" or "Pris 3".
      We are aware that it's not ideal to let merchants select the price package,
      but this is needed when not using the Partner API.

4. Vipps processes the application and does customer control (KYC, PEP, AML, etc).
   This may take a few days, depending on the information provided and the workload
   and the quality and completeness of the application.
   See the
   [Typical reasons for delays](https://vippsas.github.io/vipps-developer-docs/docs/vipps-partner#typical-reasons-for-delays).
5. The merchant can check the status of the application on
   [portal.vipps.no](https://portal.vipps.no)
   at any time.
   Vipps does not have the capacity to answer emails with status inquiries.
   If the partner wants to know the status, it must check with the merchant.
6. Vipps notifies the merchant **and the partner** by email that the application is approved,
   with the new MSN, and that the merchant can now use Vipps.
   Both thew merchant and the partner receive exactly the same information.
   **Please note:** If the application is declined, only the merchant is notified,
   as Vipps may not be allowed to share the reason for declining.

The partner can now use their
[partner keys](./partner-keys.md)
and the merchant's new MSN to make Vipps payments.

**Please note:**

- Partners can ask the merchant to create a user for them, so they get access
  to the merchant's MSN on
  [portal.vipps.no](https://portal.vipps.no)
  as described
  [in detail with screenshots here](add-portal-user.md).
  The user permissions are described (in Norwegian)
  [here](https://vipps.no/hjelp/vipps/kundeforholdet-mitt/hvilke-tilganger-kan-vi-opprette-i-vippsportalen/).
  See:
  [Developer resources: Vipps Portal: Permissions and users](https://vippsas.github.io/vipps-developer-docs/docs/vipps-developers/developer-resources/portal#permissions-and-users).
