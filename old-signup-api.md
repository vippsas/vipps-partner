<!-- START_METADATA
---
draft: true
---
END_METADATA -->

<!-- START_COMMENT -->

💥 Preview the new documentation pages here: <https://vippsas.github.io/vipps-developer-docs/>.
See the disclaimer: <https://vippsas.github.io/vipps-developer-docs/docs/examples/>.

<!-- END_COMMENT -->

# Old signup API

The deprecated legacy
[Vipps Signup API](https://github.com/vippsas/vipps-signup-api),
also called "partial signup", is no longer available,
and partners should use the more efficient
[partner keys](#partner-keys)
(and the
[Vipps Partner API](#vipps-partner-api)
when available).

For more details:
* [Old signup API](old-signup.api)

The Vipps Signup API in short:
1. Partners sent some basic info about a new merchant to Vipps.
2. The merchant got a URL to the old, outdated signup form, with a few pre-filled fields.
3. The merchant completed the form and signed with BankID.
4. Vipps processed the application and did customer control (KYC, PEP, AML, etc).
5. Vipps made a callback to the partner's API with the merchant's new API keys.

The Vipps Signup API was phased out because:
* The signup process is now on
  [portal.vipps.no](https://portal.vipps.no)
  and has _many_ improvements over the old signup form that is used in steps 2
  and 3 above as part of the Signup API.
* [Partner keys](#partner-keys)
  eliminate the need for merchant-specific API keys, so step 5 is no longer needed.
* Partners can soon use the
  [Vipps Partner API](#vipps-partner-api)
  to "pre-fill" applications for their merchants.

See: [Why was the Signup API phased out?](#why-was-the-signup-api-phased-out).

### Why was the Signup API phased out?

In short: It is no longer needed, as there are better solutions that are
continuously improved.

1. The Signup API uses the old, outdated signup form, where merchants make mistakes.
2. Applications from merchants that have used the old signup form take longer
   to process, and often require  manual follow-up on email for clarifications.
3. New products, such as
   [Vipps Checkout](https://vipps.no/produkter-og-tjenester/bedrift/ta-betalt-paa-nett/vipps-checkout/),
   can not be ordered using the Signup API.
   The old signup forms will not be updated to support new products.
4. The signup on portal.vipps.no already contains a _lot_ of improvements over the
   signup used by the Signup API, and is being continuously improved - practically
   every day. The Signup API gets none of these improvements.   
5. The callbacks to the partner (with API keys and MSN) often fail because of
   problems on the partner's side, and Vipps has an unacceptable amount of manual
   work to handle this by manually sending API keys with encrypted Excel files with
   passwords on SMS, etc.
6. Merchants that already have another Vipps product get a difficult user experience,
   where they have to provide the same information they have already provided
   (company details, etc), and sign again with BankID.
7. Vipps is making significant changes to the underlying data model for how
   merchants are represented, and we can not continue to maintain both the
   old Signup API and the current signup on portal.vipps.no.
8. The Signup API has no authentication or other security. Anyone can send
   requests. There is no validation of data, and when a partner sends
   incorrect data (which happens quite often), it requires manual correction by Vipps.

See:
[Deprecation of the Vipps Signup API](https://github.com/vippsas/vipps-signup-api/blob/master/vipps-signup-api-deprecation.md).

### When will there be a replacement for the Signup API?

It's available now: Please use the [Vipps Partner API](#vipps-partner-api).

# Questions

Please contact your partner manager.

We're always happy to help with code or other questions you might have!
Please create an [issue](https://github.com/vippsas/vipps-developers/issues),
a [pull request](https://github.com/vippsas/vipps-developers/pulls),
or contact us by email: partnerbestilling@vipps.no.

Sign up for our [Technical newsletter for developers](https://github.com/vippsas/vipps-developers/tree/master/newsletters).
