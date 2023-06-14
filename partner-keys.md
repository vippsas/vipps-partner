<!-- START_METADATA
---
title: Partner keys
sidebar_label: Partner keys
sidebar_position: 20
pagination_next: null
pagination_prev: null
---
END_METADATA -->

# Partner keys

<!-- START_COMMENT -->
ℹ️ Please use the website:
[Vipps MobilePay Technical Documentation](https://developer.vippsmobilepay.com/docs/vipps-partner/).
<!-- END_COMMENT -->

As a Partner Plus or Partner Premium partner ([see partner levels](https://developer.vippsmobilepay.com/docs/vipps-partner/partner-level-up/)), you manage transactions on behalf of Vipps merchants.
Vipps provides you with *partner keys*, which allow you to use your own API credentials to
make API calls on behalf of *all* your merchants
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
| Partner keys | Provide access to the [Management API](https://developer.vippsmobilepay.com/docs/APIs/management-api/) (and the [Partner API](https://developer.vippsmobilepay.com/docs/APIs/partner-api)). Allow partners to initiate payments and move money on behalf of their merchants (for example, by using the [ePayment API](https://developer.vippsmobilepay.com/docs/APIs/epayment-api)). | Available now, see [Partner levels](https://developer.vippsmobilepay.com/docs/vipps-partner/partner-level-up/). |
| Management keys | Provide access to the [Management API](https://developer.vippsmobilepay.com/docs/APIs/management-api/) (and the [Partner API](https://developer.vippsmobilepay.com/docs/APIs/partner-api)). Cannot be used to move money. Both partners and merchants may use management keys. | Planned availability in Q3. |
| Accounting keys | Provide access to the [Report API](https://developer.vippsmobilepay.com/docs/APIs/report-api). Cannot be used to move money. | Planned availability in Q3. |

*Partner keys* For partners who will make payments on behalf of their merchants.
However, since the [Report API](https://developer.vippsmobilepay.com/docs/APIs/report-api) can
reveal information about a merchant's prices and fees,
*partner keys* don't automatically give access to it. The merchant must
[explicitly give consent](https://developer.vippsmobilepay.com/docs/APIs/report-api/api-guide/overview/#give-access-to-an-accounting-partner)
 for the accounting partner to get access to this information.

*Management keys* are useful for partners who need to manage their merchants,
but are allowed to use *partner keys*. For example, a partner can't use *partner keys*
to make payments on behalf of merchants if:

* their [partner level](partner-level-up.md) is not high enough
* the *partner keys* are available (visible) to the merchants (if they are, one merchant can make payments on behalf of another merchhant)

On overview of which type of APi keys give access to what:

| API keys        | Manage sales units | Make payments | Use the Report API |
| --------------- | ------------------ | ------------- | ------------------ |
| Partner keys    | ✅                 | ✅             | ❌                 |
| Management keys | ✅                 | ❌             | ❌                 |
| Accounting keys | ❌                 | ❌             | ✅                 |

**Please note:** If a partner is both an accouting partner and a "normal" partner, 
the partnwe will have two sets of API keys: Accounting keys and either Partner keys
or Management keys.

### An explanation for humans

#### Partner keys

You can think about it this way:

- All sales units are apartments in a large building block
- Every apartment has its own keys to its own door
- The janitor has special janitor keys that work in the doors of all the apartments

The *partner keys* are the janitor keys: A partner with partner keys can
act on behalf of all the sales units that has that partner as partner
(the janitor keys work for all the apartmens in the building that the janitor is janitor for).

#### Management keys

The _management keys_ are similar to partner keys, but they do not allow moving money.
They can be used to manage sales units, but not to make payments.
Think of them as the postman's keys that gives access to the entrance where the mailboxes are,
but not to the apartments.

#### Accounting keys

The _accounting keys_ only allow access to the
[Report API](https://developer.vippsmobilepay.com/docs/APIs/report-api),
for retrieval of data about payments that have been made.
They cannot be used to manage sales units or to make payments.

## Authentication

With the partner keys, you authenticate in the normal way,
using the `client_id`, `client_secret` and `Ocp-Apim-Subscription-Key` that are
part of your partner keys.

When making API calls on behalf of a merchant,
you must also send the required `Merchant-Serial-Number` HTTP header to identify
which of your merchants you are acting on behalf of (e.g.,
`Merchant-Serial-Number: 123456`).

See
[Get an access token](https://developer.vippsmobilepay.com/docs/APIs/access-token-api#get-an-access-token),
for more details.

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
Vipps-System-Name: Acme Commerce
Vipps-System-Version: 3.1.2
Vipps-System-Plugin-Name: acme-webshop
Vipps-System-Plugin-Version: 4.5.6
```

## Partner keys must be kept secret for merchants

*Important:* The partner keys *must never be shared in any readable way with
the merchants*, as that will let one merchant perform API calls (including
making payments, refunds, etc.) on behalf of another merchant.

:bomb: **Potential pitfalls:**
If you answer *YES* to any of the following questions, partner keys is **not** for your solution.

* [ ] Your merchants can see the partner keys (`client_id`, `client_secret`, `Ocp-Apim-Subscription-Key`) in your solution.
* [ ] Your merchants have the ability to *change* their MSN (Merchant Serial Number) in your solution.
* [ ] The keys and secrets are stored on the merchant system's (in a way that allows them to access and see it).

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
  merchants, you are *already* using partner keys.
* You *must not*
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
* If the merchant is unable to provide the API keys to you securely, the merchant *can* create a user for you,
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
