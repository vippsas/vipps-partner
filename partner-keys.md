---
title: Partner keys
sidebar_label: Partner keys
sidebar_position: 20
pagination_next: null
pagination_prev: null
---

# Partner keys

As a partner, you manage transactions on behalf of Vipps merchants.
Vipps provides you with _partner keys_, which allow you to use your own API credentials to
make API calls on behalf of _all_ your merchants
(i.e., all the sales units that are linked to you as a partner).

The partner keys work for the sales units regardless linked to you as a partner,
whether the keys are used in a POS integration, in a webshop, or something else.

There are two ways to use partner keys:

1. To use the
   [Partner API](https://developer.vippsmobilepay.com/docs/APIs/partner-api)
   to create and manage your merchants' sales units.
2. To make API calls to Vipps APIs on behalf of your merchants (including moving money).

All partners (with a signed contract) can use partner keys for (1),
but (2) requires more - see the rest of this document.

For partners making API calls on behalf of merchants:

* The partner uses the partner keys (the partner's own "special" API keys) for all its merchants.
* The partner specifies the MSN of the sales unit its acting on behalf of in the HTTP header.

## Types of partner keys

We respect that different partners have different requirements, and we are
working to offer different type of partner keys:

| Name          | Description | Status |
| ------------- | ----------- | ------ |
| Partner keys | Give access to the [Partner API](https://developer.vippsmobilepay.com/docs/APIs/partner-api). Let the partner initiate payments and move money on behalf of its merchants - with the [ePayment API](https://developer.vippsmobilepay.com/docs/APIs/epayment-api), etc. | Available |
| Accounting partner keys | Give access to the [Report API](https://developer.vippsmobilepay.com/docs/APIs/report-api). Cannot be used to move money. | Development in process, no release date. |
| Management partner keys | Give access to the [Partner API](https://developer.vippsmobilepay.com/docs/APIs/partner-api). Cannot be used to move money. | Planned, not started. |

The _Partner keys_ do not automatically give access to the Report API, since the
Report API reveals information about prices and fees, and the merchant must
give explicit consent to the partner retrieving that information.

The _Management partner keys_ will be useful for partners that need the
Partner API to manage its merchants, but can not use the _Partner keys_
because they can not be kept secret from the merchants - or the partner is
not at a
[level](partner-level-up.md)
where they can make payments on behalf of merchants.

## Authentication

With the partner keys you authenticate in the normal way,
using the `client_id`, `client_secret` and `Ocp-Apim-Subscription-Key` that are
part of your partner keys.

When making API calls on behalf of a merchant:
You must also send the required `Merchant-Serial-Number` HTTP header to identify
which of your merchants you are acting on behalf of (e.g.,
`Merchant-Serial-Number: 123456`).

See
[Get an access token](https://developer.vippsmobilepay.com/docs/APIs/access-token-api#get-an-access-token), for more details.

## HTTP headers

In the Partner API, you must use your partner keys instead of the merchant's keys.
In addition, you must send the `Merchant-Serial-Number` header.
Note that the partner keys must be used to get the access token, sent in the
`Authorization` header shown above.

The following is an example Partner API request including the `Merchant-Serial-Number` header, partner keys, and the required
[Vipps HTTP headers](https://developer.vippsmobilepay.com/docs/vipps-developers/common-topics/http-headers).

```json
Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1Ni <snip>
Ocp-Apim-Subscription-Key: 0f14ebcab0ec4b29ae0cb90d91b4a84a
Merchant-Serial-Number: 123456
Vipps-System-Name: Acme Enterprises Ecommerce DeLuxe
Vipps-System-Version: 3.1.2
Vipps-System-Plugin-Name: acme-webshop
Vipps-System-Plugin-Version: 4.5.6
```

## Partner keys must be kept secret for merchants

_Important:_ The partner keys _must never be shared in any readable way with
the merchants_, as that will let one merchant perform API calls (including
making payments, refunds, etc.) on behalf of another merchant.

:bomb: **Potential pitfalls:**
If you answer _YES_ to any of the following questions, partner keys is **_not_** for your solution.

- [ ] Your merchants can see the partner keys (`client_id`, `client_secret`, `Ocp-Apim-Subscription-Key`) in your solution.
- [ ] Your merchants have the ability to _change_ their MSN (Merchant Serial Number) in your solution.
- [ ] The keys and secrets are stored on the merchant system's (in a way that allows them to access and see it).

## Partner keys for different APIs

The same set of partner keys can be used for all your merchants' sales units, for both the
[Vipps eCom API](https://developer.vippsmobilepay.com/docs/APIs/ecom-api)
and the
[Vipps Recurring API](https://developer.vippsmobilepay.com/docs/APIs/recurring-api),
including the
[Userinfo](https://developer.vippsmobilepay.com/docs/APIs/userinfo-api)
endpoints for both.

## Important information

**Please note:**

* If you are already using the same, identical API keys for multiple
  merchants, you are _already_ using partner keys.
* You _must not_
  use partner keys if the merchants can, in any way, see or access the API keys.
  That would be security problem that would make it possible for someone to act
  on behalf of all your merchants.
* Partner keys only work in the production environment. In the
  [test environment](https://developer.vippsmobilepay.com/docs/vipps-developers/test-environment),
  you must use the merchant's API keys.
  If you are not a Vipps merchant in the production environment and do not have
  these keys, you will need to use the merchant keys belonging to one of your
  merchants.
* Vipps can not send the merchant's API keys to you. You must get them from the
  merchant securely (if partner keys are not used).
  See:
  [Common topics: API Keys](https://developer.vippsmobilepay.com/docs/vipps-developers/common-topics/api-keys#getting-the-api-keys)
  for more details.
* If the merchant is unable to provide the API keys to you in a secure
  way, the merchant _can_ create a user for you,
  [as described in detail with screenshots](add-portal-user.md).
* Vipps cannot assist a partner in getting the API keys from the merchant,
  other than by improving the documentation for how to do it.
* Partner keys can be used for all sales units that are registered with the partner.
  It does not matter if the sales unit is several years old, or one day old.

See:

* [Getting started](https://developer.vippsmobilepay.com/docs/vipps-developers/getting-started)

## Merchant requirements

**Please note:** Vipps payments can only be made to merchants that have a
customer relationship with Vipps, and that have gone through the required
compliance checks, etc. after ordering Vipps on
[portal.vipps.no](https://portal.vipps.no).
It is not possible to pay the partner instead of the merchant. See also:
[Can I create a marketplace with multiple merchants?](https://developer.vippsmobilepay.com/docs/vipps-developers/faqs/users-and-payments-faq#can-i-create-a-marketplace-with-multiple-merchants)
