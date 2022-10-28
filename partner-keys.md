<!-- START_METADATA
---
title: Partner keys
sidebar_position: 10
---
END_METADATA -->

# Partner keys

<!-- START_COMMENT -->

ℹ️ Please use the new documentation:
[Vipps Technical Documentation](https://vippsas.github.io/vipps-developer-docs/).

<!-- END_COMMENT -->

<!-- START_TOC -->

## Table of Contents

* [Partner keys](#partner-keys)
* [Authentication](#authentication)
* [HTTP headers](#http-headers)
* [Partner keys must be kept secret for merchants](#partner-keys-must-be-kept-secret-for-merchants)
* [Partner keys for different APIs](#partner-keys-for-different-apis)
* [Important information](#important-information)
* [Merchant requirements](#merchant-requirements)
* [Questions](#questions)

<!-- END_TOC -->

As a partner, you manage transactions on behalf of Vipps merchants.
Vipps provides you with _partner keys_, which allow you to use your own API credentials to
make API calls on behalf of your merchants (i.e., the sales units that are linked to you as a partner).

There are two ways to use partner keys:
1. To use the
   [Partner API](https://vippsas.github.io/vipps-developer-docs/docs/APIs/partner-api)
   to create and manage merchants' sale units.
2. To make API calls to Vipps APIs on behalf of merchants (including moving money).

All partners (with a signed contract) can use partner keys for (1),
but (2) requires more - see the rest of this document.

For partners making API calls on behalf of merchants:
* The partner uses its own API keys (the partner keys) for all its merchants.
* The partner specifies the MSN of the sale unit its acting on behalf of.

## Authentication

With the partner keys you authenticate in the normal way,
using the `client_id`, `client_secret` and `Ocp-Apim-Subscription-Key` that are
part of your partner keys.

When making API calls on behalf of a merchant:
You must also send the required `Merchant-Serial-Number` HTTP header to identify
which of your merchants you are acting on behalf of (e.g.,
`Merchant-Serial-Number: 123456`).

See
[Get an access token](https://github.com/vippsas/vipps-developers/blob/master/vipps-getting-started.md#get-an-access-token)
in the Getting Started guide, for more details.

## HTTP headers

In the Partner API, you must use your partner keys instead of the merchant's keys.
In addition, you must send the `Merchant-Serial-Number` header.
Note that the partner keys must be used to get the access token, sent in the
`Authorization` header shown above.

The following is an example Partner API request including the `Merchant-Serial-Number` header, partner keys, and the required
[Vipps HTTP headers](https://github.com/vippsas/vipps-ecom-api/blob/master/vipps-ecom-api.md#vipps-http-headers).

```json
Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1Ni <snip>
Ocp-Apim-Subscription-Key: 0f14ebcab0ec4b29ae0cb90d91b4a84a
Merchant-Serial-Number: 123456
Vipps-System-Name: Acme Enterprises Ecommerce DeLuxe
Vipps-System-Version: 3.1.2
Vipps-System-Plugin-Name: acme-webshop
Vipps-System-Plugin-Version: 4.5.6
```

See [Vipps HTTP headers](https://github.com/vippsas/vipps-developers/blob/master/vipps-getting-started.md#vipps-http-headers)
in the Getting started guide for more details.

## Partner keys must be kept secret for merchants

**Important:** The partner keys _*must never be shared in any readable way with
the merchants*_, as that will let one merchant perform API calls (including
making payments, refunds, etc) on behalf of another merchant.

:bomb: **Potential pitfalls:**
If you answer _YES_ to any of the following questions, partner keys is **_not_** for your solution.'
- [ ] Your merchants can see the partner keys (`client_id`, `client_secret`, `Ocp-Apim-Subscription-Key`) in your solution.
- [ ] Your merchants have the ability to _change_ their MSN (Merchant Serial Number) in your solution.
- [ ] The keys and secrets are stored on the merchant system's (in a way that allows them to access and see it).

## Partner keys for different APIs

The same set of partner keys can be used for all your merchants' sale units, for both the
[Vipps eCom API](https://github.com/vippsas/vipps-ecom-api)
and the
[Vipps Recurring API](https://github.com/vippsas/vipps-recurring-api),
including the
[Userinfo](https://github.com/vippsas/vipps-developers/blob/master/common-topics/userinfo.md)
endpoints for both.

**_NOTE:_**  Partner keys cannot yet be used for Vipps Login.
You need to use the merchant's own keys in the Vipps Login API.
We are working on solving this.

## Important information

**Please note:**

* If you are already using the same, identical API keys for multiple
  merchants, you are _already_ using partner keys.
* You _must not_
  use partner keys if the merchants can, in any way, see or access the API keys.
  That would be security problem that would make it possible for someone to act on behalf of all your merchants.
* Partner keys only work in the production environment. In the
  [test environment](https://github.com/vippsas/vipps-developers/blob/master/developer-resources/test-environment.md,
  you must merchant API keys. If you are not a Vipps merchant and do not have these keys, you will need to use the merchant keys belonging to one of your merchants.
* Vipps can not send the merchant's API keys to you. You must get them from the merchant in a secure way (if partner keys are not used).
  See:
  [Getting started: Get credentials](https://github.com/vippsas/vipps-developers/blob/master/vipps-getting-started.md#get-credentials)
  for more details.
* If the merchant is unable to provide the API keys to you in a secure
  way, the merchant _can_ create a user for you,
  [as described in detail with screenshots](add-portal-user.md).
* Vipps cannot assist a partner in getting the API keys from the merchant,
  other than by improving the documentation for how to do it.
* Partner keys can be used for all sale units that are registered with the partner.
  It does not matter if the sale unit is several years old, or one day old.

See:

* [Partner keys for eCom](https://github.com/vippsas/vipps-ecom-api/blob/master/vipps-ecom-api.md#partner-keys)
* [Partner keys for Recurring](https://github.com/vippsas/vipps-recurring-api/blob/master/vipps-recurring-api.md#partner-keys)
* [Getting started: Quick overview of how to make an API call](https://github.com/vippsas/vipps-developers/blob/master/vipps-getting-started.md#quick-overview-of-how-to-make-an-api-call)

## Merchant requirements

**Please note:** Vipps payments can only be made to merchants that have a
customer relationship with Vipps, and that have gone through the required
compliance checks, etc after ordering Vipps on
[portal.vipps.no](https://portal.vipps.no).
It is not possible to pay the partner instead of the merchant. See also:
[Can I create a marketplace with multiple merchants?](https://github.com/vippsas/vipps-ecom-api/blob/master/vipps-ecom-api-faq.md#can-i-create-a-marketplace-with-multiple-merchants)

## Questions

Please contact your partner manager.

We're always happy to help with code or other questions you might have!
Please create an [issue](https://github.com/vippsas/vipps-developers/issues),
a [pull request](https://github.com/vippsas/vipps-developers/pulls),
or contact us by email: partnerbestilling@vipps.no.

Sign up for our [Technical newsletter for developers](https://vippsas.github.io/vipps-developer-docs/docs/vipps-developers/newsletters).
