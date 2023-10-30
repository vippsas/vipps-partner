<!-- START_METADATA
---
title: How to change partners
sidebar_label: How to change partners
description: How to change partners in Vipps MobilePay
sidebar_position: 25
pagination_next: null
pagination_prev: null
---
END_METADATA -->

# How to change partners for a merchant

**Please see:**
[How to sign up new merchants](README.md#how-to-sign-up-new-merchants)
for general information about signing up new merchants.

Merchants can change partners. This is always initiated by the merchant. The
merchant is responsible, as *data controller*, for which partner(s) can access the
merchant's data as *data processor*.

If the merchant changes partners, the merchant's sales unit (identified with MSN,
the Merchant Serial Number) must be reconfigured, so the new partner's
[partner keys](partner-keys.md)
can be used for the same MSN.

The new partner will get access to all the payments made to the MSN.
There is no way we can restrict the new partner's access, so it cannot see
payments made before the partner change.

The MSN can only be used with one set of
[partner keys](partner-keys.md)
at a time,
so, in the transition period, this requires some effort from
both the merchant and the two partners.

This is the recommended way:

1. The merchant logs in on
   [portal.vipps.no](https://portal.vipps.no)
   and retrieves the API keys for the MSN, as documented in
   [Knowledge base: API Keys](https://developer.vippsmobilepay.com/docs/knowledge-base/api-keys#getting-the-api-keys).
2. The merchant securely provides the MSN's API keys to *both* the
   old partner and the new partner. This ensures that both partners can
   make API calls for the MSN, regardless of each partner's
   [partner keys](partner-keys.md).
3. The new partner [contacts the partner support team](README.md#questions)
   and orders a reconfiguration of the MSN. Link it to the new partner instead
   of the old one.
   When this is done, the MSN has the new partner as partner.
4. The new partner's
   [partner keys](partner-keys.md)
   now work for the MSN,
   and the old partner's partner keys have stopped working for this MSN.
5. The new partner uses its partner keys.
   The old partner (if it needs to make API calls) must use the merchant's own API keys,
   which they got in step 2.

Both partners can use the MSN's own API (from step 2) keys if there are "special"
API calls to make in the transition period.
The new partner should *always* use the partner keys.
We offer a
[Postman collection](https://developer.vippsmobilepay.com/docs/APIs/recurring-api/vipps-recurring-api-quick-start)
that can be used to make manual API calls if needed.

The new partner should use the
[Management API](https://developer.vippsmobilepay.com/docs/APIs/management-api/)
to verify that the MSN is set up correctly.

**Important:** When or if the merchant wants to remove the old partner's access
to the MSN, the merchant can log in on
[portal.vipps.no](https://portal.vipps.no)
and regenerate the MSN's API keys.
That will make the MSN's old API keys invalid and unusable for both Partners,
but the new partner's
[partner keys](partner-keys.md)
will continue to work.
This is also the recommended way to manage API keys when *not* using partner keys:
Generate new API keys for the merchant, so the keys used by the old partner no
longer can be used.

**Please note:** We have previously handled the above by creating a new MSN to use with the
new partner. We no longer offer this, as it creates a lot of additional work,
and it results in a confusing user experience for our users - and partners.
