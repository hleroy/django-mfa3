0.11.0 (2023-04-14)
-------------------

-   Add setting `MFA_FIDO2_USER_VERIFICATION`
-   Allow to use FIDO2 on localhost without HTTPS if DEBUG is True (thanks to
    humphrey)
-   Avoid autocompletion in the code field
-   Fix minimum supported django version (3.2) in the package


0.10.0 (2023-03-19)
-------------------

-   Add french translation (thanks to hleroy)


0.9.0 (2023-02-27)
------------------

-   Autofocus in auth form
-   Work around rendering bug in qrcode (see
    https://github.com/lincolnloop/python-qrcode/issues/317)


0.8.0 (2022-12-08)
------------------

-   Add option to send an email on failed login


0.7.0 (2022-06-24)
------------------

-   Add new setting `MFA_TOTP_VALID_WINDOW` to compensate for clock drifts
    (thanks to Tobias Bölz)


0.6.0 (2022-06-08)
------------------

-   Adapt to fido2 1.0.0


0.5.1 (2022-06-08)
------------------

-   Pin fido2 dependency


0.5.0 (2022-04-15)
------------------

-   Security fix: The admin login was not adapted, so it could be used to
    bypass MFA. As a fix, django-mfa3 will now automatically patch `AdminSite`
    so the admin login redirects to regular login. (CVE-2022-24857)
-   Drop support for django 2.2
-   Use a more efficient string encoding for FIDO2 messages


0.4.0 (2022-01-25)
------------------

-   Drop support for python 3.6, add support for python 3.10
-   Drop support for django 3.1, add support for django 4.0
-   No longer include MFA code in credentials for `user_login_failed`


0.3.0 (2021-08-25)
------------------

-   Add recovery codes. Check the example templates for references to
    "recovery" to see what needs to be changed.
-   Add new setting `MFA_METHODS` to change the set of enabled methods.


0.2.5 (2021-07-18)
------------------

-   Fix usage with custom User models that use a different username field
    (thanks to Ashok Argent-Katwala)


0.2.4 (2021-07-07)
------------------

-   Security fix: Do not allow users to see the names of/delete other user's
    keys (secrets were not leaked)


0.2.3 (2021-07-05)
------------------

-   Fix packaging: include .mo files


0.2.2 (2021-07-05)
------------------

-   Fix packaging: include templatetags


0.2.1 (2021-07-02)
------------------

-   Fix packaging: exclude tests


0.2.0 (2021-07-02)
------------------

-   Convert qrcode to template filter. In templates, change
    `{{ mfa_data.qrcode|safe }}` to `{% load mfa %} {{ mfa_data.url|qrcode }}`.
-   Fix form validation on missing code
-   Add german translation
-   Use `never_cache` and `sensitive_post_parameters` decorators
-   Do not generate a new challenge on validation errors


0.1.0 (2021-06-29)
------------------

-   Trigger `user_login_failed` on failed second factor. This can be used to
    integrating with external rate limiting solutions such as django-axes.
-   Fix: include JS files in python package
-   Render qrcode server-side
-   Convenience: redirect to TOTP auth if no FIDO2 key exists
-   Add optional `MFAEnforceMiddleware`
-   Tweak admin UI
-   Tweak example templates


0.0.0 (2021-06-21)
------------------

initial release
