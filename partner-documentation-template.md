# Vipps partner documentation template

This document is an example that partners can use for documentation to their
merchants of how to get started with Vipps.

The ""**ℹ️ Please note:**"" is for the partners, and must not be in the finished
documentation for the partner's merchants. See
[Vipps Partners](https://github.com/vippsas/vipps-partner)
for more information.

Document version: 0.0.2.

# How to order Vipps

**ℹ️ Please note:** Partners should use the
[Partner API](https://github.com/vippsas/vipps-partner-api)
to pre-fill product orders for merchants.
If the Partner API is not used, the merchants must order Vipps on
[portal.vipps.no](https://portal.vipps.no).

1. Log in with BankID
   (everyone with BankID can log in)
2. Search for your company's name or organization number.
3. Fill in the required information.
   Most fields have a small `i`: Click that for help.
   If you need help: Contact us (your parter) first,
   and we will contact Vipps if needed.
4. Sign the application with BankID on the company's behalf.
5. Order "Vipps på nett" with the settings required by the partner.

You may get follow-up questions from Vipps. Please check your email,
including the "spam" folder, and search for "vipps".

You can check the status of your Vipps order on
[portal.vipps.no](https://portal.vipps.no)
at any time.

# API keys

**ℹ️ Please note: Select one of the alternatives below, depending on whether you use partner keys or not:**

1. We use "partner keys" so there is no need for you to do anything.

   When the Vipps application is complete, you will get an email.
   We, your partner, receive the same email.
   The email contains the "Merchant Serial Number" (MSN),
   a six-digit number identifying your new Vipps sale unit.
   There is nothing more you need to do, we then have everything we need.

2. Describe how to use the API keys in the partner's solution,
   complete with screenshots with added arrows, text, etc.
   Link to
   [Getting Started: Get credentials](https://github.com/vippsas/vipps-developers/blob/master/vipps-getting-started.md#get-credentials)
   if relevant.

# Configuration of Vipps on our (the partner) side

**ℹ️ Please note:** Describe in detail how to configure Vipps, with screenshots, etc.
Link to
[Getting Started](https://github.com/vippsas/vipps-developers/blob/master/vipps-getting-started.md)
if relevant.

Topics to cover:

* Installation
* Configuration
  - Autorization
  - Shortcodes
  - Webhooks
* Additional info (support)

Consider linking to the Vipps API FAQs.

# Frequently asked questions

**ℹ️ Please note:** All partners must offer a FAQ for their merchants.
Link to the
[Vipps eCom API FAQ](https://github.com/vippsas/vipps-ecom-api/blob/master/vipps-ecom-api-faq.md)
if relevant.

Topics to cover:

* Order handling
  - How do I capture an order
  - How do I partial capture an order
  - How do I cancel an order
  - How do I refund an order
  - How do I partial refund an order
  - How do I debug a failed order
* Additional info (support)

# Questions

Please contact us and we will help as soon as possible.
We will contact Vipps if needed, so you should not contact Vipps directly.

**ℹ️Please note: Add partner name, address, website, phone, email, etc here.**
