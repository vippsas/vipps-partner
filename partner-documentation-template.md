<!-- START_METADATA
---
title: Partner documentation template
sidebar_label: Partner documentation template
description: Vipps MobilePay partner documentation template
sidebar_position: 90
pagination_next: null
pagination_prev: null
---
END_METADATA -->

# Partner documentation template

<!-- START_COMMENT -->
ℹ️ Please use the website:
[Vipps MobilePay Technical Documentation](https://developer.vippsmobilepay.com/docs/partner/).
<!-- END_COMMENT -->

This document provides examples for providing documentation to your merchants.

The paragraphs prefixed with "ℹ️" is for you (the partner), and must not be in the
finished documentation for the partner's merchants.

## How to order products

ℹ️ Partners should use the
[Management API](https://developer.vippsmobilepay.com/docs/APIs/management-api/)
to pre-fill product orders for merchants,
and document how the merchant sign up in the partner's interface.
If the [Management API](https://developer.vippsmobilepay.com/docs/APIs/management-api/) is not used, the merchants must order products on
[portal.vipps.no](https://portal.vipps.no), as described below:

1. Log in with BankID (everyone with BankID can log in).
2. Search for your business' name or organization number.
3. Fill in the required information.
   If you need help, please contact
   [customer service](https://vipps.no/kontakt-oss/).
4. Sign the application with BankID.
5. Order *Vipps på nett* with the settings required by the partner.
   Try to avoid the
   [typical reasons for delays](https://developer.vippsmobilepay.com/docs/partner#typical-reasons-for-delays).

You may get follow-up questions from us. Please check your email,
including the "spam" folder, and search for "vipps".

You can check the status of your order on
[portal.vipps.no](https://portal.vipps.no)
at any time.

## API keys

ℹ️ Select one of the alternatives below, depending on whether you
use
[partner keys](https://developer.vippsmobilepay.com/docs/partner/partner-keys)
or not.

1. As a partner, explain that you are using the Management API and partner keys, so the merchant
   doesn't have to do anything after ordering products in your interface:

   "When the application is complete, you will get an email.
   We, your partner, receive the same email.
   The email contains the "Merchant Serial Number" (MSN),
   a six-digit number identifying your new sales unit.
   There is nothing more you need to do, we then have everything we need."

2. Explain how to use the API keys in your solution,
   complete with screenshots with added arrows, text, etc.
   Link to
   [Knowledge base: API keys](https://developer.vippsmobilepay.com/docs/common-topics/api-keys),
   if relevant.


## Configuration of Vipps or MobilePay on your site

ℹ️ Describe *in detail* how to configure Vipps or MobilePay with screenshots and details.
Link to
[Getting Started](https://developer.vippsmobilepay.com/docs/getting-started),
if relevant.

Topics to cover:

* Installation
* Configuration
  * Authorization
  * Short codes
  * Webhooks
* Additional info (support)

Consider linking to the
[Knowledge base](https://developer.vippsmobilepay.com/docs/common-topics/).

## Frequently asked questions

ℹ️ All partners must offer a FAQ for their merchants.
Link to the
[Knowledge base](https://developer.vippsmobilepay.com/docs/common-topics/),
if relevant.

## Order handling

ℹ️ Document everything required for the merchant to manage their orders.
All order management must be done in your interface, using our API platform,
rather than using [portal.vipps.no](https://portal.vipps.no).

Make sure your customer service has all the tools and information they need
available in your system and that they do not need to visit [portal.vipps.no](https://portal.vipps.no) for normal work.

Topics to cover:

* Order handling
  * How do I capture an order?
  * How do I partially capture an order?
  * How do I cancel an order?
  * How do I refund an order?
  * How do I partially refund an order?
  * How to I find all the details about an order?
  * How do I debug a failed order?
* Additional info (support)

## Support

ℹ️ Offer all required support for your merchants.
Explain how to get help, how to use your support system, and any other necessary details.
Document very clearly that your merchants should contact you instead of Vipps MobilePay.

For example:

> Please contact us, your partner, and we will help as soon as possible.
> We will contact Vipps MobilePay if needed, so you should not contact Vipps MobilePay directly.
> **ℹ️ Please note: Add partner name, address, website, phone, email, etc. here.**
