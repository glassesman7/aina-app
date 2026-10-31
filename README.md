# aina-app

The two web pages Google's sign-in screen points to for Aina, the personal
assistant in `C:\dev\aina`: a homepage (`index.html`) and a privacy policy
(`privacy.html`), styled by `style.css`. Plain static HTML, no build step.

## Where it is published

GitHub Pages, from the `main` branch, root folder, of
`github.com/glassesman7/aina-app` (checked with the GitHub API on 2026-10-31:
Pages is on, built, HTTPS enforced). The addresses are:

- homepage: https://glassesman7.github.io/aina-app/
- privacy policy: https://glassesman7.github.io/aina-app/privacy.html

A push to `main` publishes. Nothing is built or deployed from this machine.

## What Google has

The OAuth consent screen (Google Cloud console, APIs & Services, OAuth consent
screen, in the project Aina's OAuth clients belong to) asks for the
**Application home page** and the **Application privacy policy link**. They
should be the two addresses above. This README cannot see what is typed into
that console; if Google asks for re-verification, or the Pages address ever
changes (a renamed repo or account, a custom domain), compare the console with
this list first. The steps for setting the screen up are in Aina's
`docs/PHONE_GOOGLE_SIGNIN.md`, step 6.

## Keep it true

`privacy.html` is a statement about what Aina does with Gmail and Calendar
data. It must match the code, or Google can refuse or revoke the app's access:

- the scopes Aina asks for are `GOOGLE_SCOPES` in Aina's `mcp_auth.py`; what
  they allow is under "What Aina accesses";
- everywhere the text can go is under "Where the data goes": the model
  providers the owner can pick (`ONLINE_PROVIDERS` in Aina's `models.py`),
  the notification services (`phone/notify.py`), and the optional Cloudflare
  tunnel (`phone/reach.py`).

Change the page in the same piece of work as any change to those, and bump the
"Last updated" date.
