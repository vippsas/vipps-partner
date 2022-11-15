<!-- START_METADATA
---
title: How to add a user on the portal
sidebar_position: 2
---
END_METADATA -->

# How to add a user on portal.vipps.no

<!-- START_COMMENT -->

ℹ️ Please use the new documentation:
[Vipps Technical Documentation](https://vippsas.github.io/vipps-developer-docs/).

<!-- END_COMMENT -->

Partners should use
[partner keys](https://vippsas.github.io/vipps-developer-docs/docs/vipps-partner/partner-keys).

If the partner has not implemented partner keys, there will be some manual work:
The merchant must retrieve the API keys on portal.vipps.no and send them to the
partner in a secure way.

If the merchant is unable to provide the API keys to the partner in a secure
way, the merchant _can_ create a user for the partner, so the partner can
retrieve the API keys.

This is a step by step guide for that.

Document version: 0.0.1.

<!-- START_TOC -->

# Table of contents

* [1. Log in on portal.vipps.no](#1-log-in-on-portalvippsno)
* [2. See the list of users](#2-see-the-list-of-users)
* [3. Enter the new user's phone number](#3-enter-the-new-users-phone-number)
* [4. Select permissions](#4-select-permissions)
* [5. Select sale units the new user will get access to](#5-select-sale-units-the-new-user-will-get-access-to)
* [6. Confirmation](#6-confirmation)
* [Questions](#questions)

<!-- END_TOC -->

# 1. Log in on portal.vipps.no

The merchant logs in with BankID on
[portal.vipps.no](https://portal.vipps.no)
and sees the main page.

Click "Brukertilganger" in the left menu:

![1](images/portal-add-user-1.png)

# 2. See the list of users

The list of users is now shown.

Click "Legg til bruker":

![2](images/portal-add-user-2.png)

# 3. Enter the new user's phone number

A panel for adding a new user is shown.

Enter the phone number of the new user that will be added.

The name of the person will automatically be displayed.

Click "Neste".

![3](images/portal-add-user-3.png)

# 4. Select permissions

The partner's user should have "Lese" and "Utvikler" permissions.

Click "Neste".

![4](images/portal-add-user-4.png)

# 5. Select sale units the new user will get access to

There merchant may have one or several sale units.

Choose the one(s) that the new user will get access to.

Click "Ferdig".

![5](images/portal-add-user-5.png)

# 6. Confirmation

That's it.

The confirmation screen looks like this:

![6](images/portal-add-user-6.png)

# Questions

Please contact your partner manager.

See: [Vipps Partners](README.md).

We're always happy to help with code or other questions you might have!
Please create an [issue](https://github.com/vippsas/vipps-developers/issues),
a [pull request](https://github.com/vippsas/vipps-developers/pulls),
or contact us by email: partnerbestilling@vipps.no.

Sign up for our [Technical newsletter for developers](https://vippsas.github.io/vipps-developer-docs/docs/vipps-developers/newsletters).
