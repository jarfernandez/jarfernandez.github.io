# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

The personal GitHub Pages site for José Arturo Fernández Díaz (a DevOps engineer who publishes Android apps), served at `https://jarfernandez.github.io` from the root of the `master` branch. There is **no build system, package manager, test suite, or linter** — the repository is plain static HTML and assets served as-is.

## Deploying

Deployment is a `git push` to `master`. GitHub Pages publishes the branch root directly; there is no CI step, no generated output, and no preview environment. Edits to tracked files are live once pushed.

Commit messages in this repo are written in **Spanish** (e.g. "Se añade la política de privacidad de …"). Match that convention.

Do **not** attribute commits or pull requests to Claude Code: omit any `Co-Authored-By: Claude …` trailer from commit messages and any "Generated with Claude Code" footer from PR descriptions.

## Layout and conventions

- **`index.html`** — the homepage. It is a single **AMP document exported from a site builder**: a self-contained file of minified `i-amphtml-*` boilerplate and inline styles. Treat it as generated output — editing the AMP scaffolding by hand is error-prone. For visible text/link changes, locate the specific human-readable string and change only that; avoid reformatting the surrounding minified markup.
- **`<AppName>/privacy_policy.html`** — one directory per published Android app, each holding a privacy policy. These are all the **same generated template** (App Privacy Policy Generator output) with only the app name swapped in (e.g. "built the **Tip Calculator** app"). Contact email is `jarfernandez@gmail.com`. To add a privacy policy for a new app, copy an existing app's `privacy_policy.html` into a new directory and substitute the app name throughout.
- **`app-ads.txt`** — AdMob/AdSense publisher verification (`app-ads.txt` standard) for the Android apps. The single line authorizes Google as a seller; keep the publisher ID intact when editing.
- **`files/`** — vendored AMP runtime scripts (`v0.js`, `amp-*.js`) and image assets referenced by `index.html`. These are third-party AMP libraries, not project source.
