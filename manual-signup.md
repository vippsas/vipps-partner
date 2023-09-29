<!-- START_METADATA
---
title: Manual signup
sidebar_label: Manual signup
description: Vipps MobilePay partner manual signup
sidebar_position: 35
pagination_next: null
pagination_prev: null
---
END_METADATA -->

# Manual signup

We recommend that you use the
[Management API's pre-fill functionality](https://developer.vippsmobilepay.com/docs/APIs/management-api/management-api-guide/#pre-fill-a-product-order) to sign up a new merchant because it is much faster and easier to get all the details correct because you can pre-fill the product order information.

If you aren't able to do this, the merchant manually sign up as follows:

1. The merchant logs in to
   [portal.vipps.no](https://portal.vipps.no) using BankID.

2. The merchant must have a customer relationship with Vipps MobilePay, if they don't already have this.

    Sign up by going to:
   [`https://portal.vipps.no/register/{organisation-number-goes-here}`](https://portal.vipps.no)

   There, they can fill in details for the company, including
   real rights holders, politically exposed people, etc.
   This application must be signed with BankID by a person that has
   signatory rights for the company.

   **Please note:** It is possible for the partner, or simply a person helping the merchant,
   to *fill out* the form, but the *signing* of the form must be done
   by a person with signing rights for the merchant.

3. Once the merchant has a customer relationship with Vipps MobilePay, they can apply for the relevant Vipps MobilePay product(s) on
   [portal.vipps.no](https://portal.vipps.no).

   It is possible to give merchants a direct link to the right product:
   * [Vipps på nett](https://portal.vipps.no/register/vippspaanett)
   * [Vipps Checkout](https://portal.vipps.no/register/vippscheckout)
   * [Vipps i kassa](https://portal.vipps.no/register/vippsikasse)
   * [Vipps Login](https://portal.vipps.no/register/vippslogginn)

   It's the partner's responsibility to make sure the merchant has all necessary
   information to fill out the application correctly.

   When the merchant applies for a product, they must select:
   * The product (or use a direct link as above)
   * The partner
   * The price package, typically "Price 1", "Price 2" or "Price 3".
      Although it's not ideal to let merchants select the price package,
      this is needed when not using the Management API.

4. We process the application and perform customer control (KYC, PEP, AML, etc.).
   This may take a few days, depending on the information provided and the workload
   and the quality and completeness of the application.
   See the
   [Typical reasons for delays](https://developer.vippsmobilepay.com/docs/partner#typical-reasons-for-delays).
5. The merchant can check the status of the application on
   [portal.vipps.no](https://portal.vipps.no)
   at any time.
   We don't have the capacity to answer emails with status inquiries.
   If the partner wants to know the status, they can check with the merchant.
6. We notify the merchant **and the partner** by email that the application is approved,
   with the new MSN, and that the merchant can now use the Vipps MobilePay products.
   Both the merchant and the partner receive exactly the same information.
   **Please note:** If the application is declined, only the merchant is notified,
   as we may not be allowed to share the reason for declining.

The partner can now use their [partner keys](./partner-keys.md)
and the merchant's new MSN to make payments.

**Please note:**

* If the partner doesn't want to use partner keys, the merchant can [create a user for them](add-portal-user.md). Then, they will get access to the merchant's MSN.

  For more about user permissions, see:
    [I can't log into the portal (in Norwegian)](https://vipps.no/hjelp/vipps/kundeforholdet-mitt/hvilke-tilganger-kan-vi-opprette-i-vippsportalen/) and
  [Portal: Permissions and users](https://developer.vippsmobilepay.com/docs/developer-resources/portal#permissions-and-users).

