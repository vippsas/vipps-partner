<!-- START_METADATA
---
title: Partner documentation template
sidebar_position: 90
pagination_next: null
pagination_prev: null
---
END_METADATA -->

# Vipps partner documentation template

This document is an example that partners can use for documentation to their
merchants of how to get started with Vipps.

The paragraphs prefixed with "ℹ️" is for the partners, and must not be in the
finished documentation for the partner's merchants. See
[Vipps Partners](https://vippsas.github.io/vipps-developer-docs/docs/vipps-partner)
for more information.

<!-- START_COMMENT -->

ℹ️ Please use the new documentation:
[Vipps Technical Documentation](https://vippsas.github.io/vipps-developer-docs/docs/vipps-partner/partner-documentation-template).

## Table of contents

* [How to order Vipps](#how-to-order-vipps)
* [API keys](#api-keys)
* [Configuration of Vipps on our (the partner) side](#configuration-of-vipps-on-our-the-partner-side)
* [Frequently asked questions](#frequently-asked-questions)
* [Order handling](#order-handling)
* [Support](#support)

<!-- END_COMMENT -->

## How to order Vipps

ℹ️ Partners should use the
[Partner API](https://vippsas.github.io/vipps-developer-docs/docs/APIs/partner-api)
to pre-fill product orders for merchants,
and document how the merchant sign up in the partner's interface.
If the Partner API is not used, the merchants must order Vipps on
[portal.vipps.no](https://portal.vipps.no), as described below:

1. Log in with BankID (everyone with BankID can log in).
2. Search for your company's name or organization number.
3. Fill in the required information.
   If you need help, please contact
   [Vipps customer service](https://vipps.no/kontakt-oss/).
4. Sign the application with BankID.
5. Order "Vipps på nett" with the settings required by the partner.
   Try to avoid the
   [typical reasons for delays](https://vippsas.github.io/vipps-developer-docs/docs/vipps-partner/#typical-reasons-for-delays).

You may get follow-up questions from Vipps. Please check your email,
including the "spam" folder, and search for "vipps".

You can check the status of your Vipps order on
[portal.vipps.no](https://portal.vipps.no)
at any time.

## API keys

ℹ️ Select one of the alternatives below, depending on whether you
use
[partner keys](https://vippsas.github.io/vipps-developer-docs/docs/vipps-partner/partner-keys)
or not.

1. Explain that (since you use the Partner API and partner keys) the merchant
   does not have to do anything after ordering Vipps in the partner's interface:

   "When the Vipps application is complete, you will get an email.
   We, your partner, receive the same email.
   The email contains the "Merchant Serial Number" (MSN),
   a six-digit number identifying your new Vipps sale unit.
   There is nothing more you need to do, we then have everything we need.""

2. Explain how to use the Vipps API keys in the partner's solution,
   complete with screenshots with added arrows, text, etc.
   Link to
   [Developer resources: Vipps portal: How to find the API keys](https://vippsas.github.io/vipps-developer-docs/docs/vipps-developers/developer-resources/portal),
   if relevant.

For information about API keys, see
[Common topics: API keys](https://vippsas.github.io/vipps-developer-docs/docs/vipps-developers/common-topics/api-keys).

## Configuration of Vipps on our (the partner) side

ℹ️ Describe _in detail_ how to configure Vipps, with screenshots, etc.
Link to
[Getting Started](https://vippsas.github.io/vipps-developer-docs/docs/vipps-developers/vipps-getting-started)
if relevant.

Topics to cover:

* Installation
* Configuration
  - Authorization
  - Short codes
  - Webhooks
* Additional info (support)

Consider linking to the
[Vipps FAQs](https://vippsas.github.io/vipps-developer-docs/docs/vipps-developers/faqs).

## Frequently asked questions

ℹ️ All partners must offer a FAQ for their merchants.
Link to the
[Vipps FAQs](https://vippsas.github.io/vipps-developer-docs/docs/vipps-developers/faqs),
if relevant.

## Order handling

ℹ️ Document everything required for the merchant to manage their orders.
All order management must be done in the partner's interface, using the Vipps API,
and _not_ on portal.vipps.no.

From the integration checklist:

> Make sure your customer service, etc has all the tools and information they need
> available in your system, through the APIs listed in the first item in this
> checklist, and that they do not need to visit portal.vipps.no for normal work.

Topics to cover:

* Order handling
  - How do I capture an order?
  - How do I partial capture an order?
  - How do I cancel an order?
  - How do I refund an order?
  - How do I partial refund an order?
  - How to I find all the details about an order?
  - How do I debug a failed order?
* Additional info (support)

## Support

ℹ️ All partners must offer all required support for their merchants.
Explain how to get help, how to use the partner's support system, etc.
Document very clearly that the partner's merchants should _never_ contact Vipps directly.

## Questions

Please contact us, your partner, and we will help as soon as possible.
We will contact Vipps if needed, so you should not contact Vipps directly.

**ℹ️Please note: Add partner name, address, website, phone, email, etc here.**
