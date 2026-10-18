# OpenClaw Mail information site

Public, static information for a privately operated Gmail integration. This directory is separate from the private OpenClaw runtime and contains no runtime source, OAuth credentials, tokens or mailbox contents. It is not a public application, login service or OAuth callback handler.

Gmail authorization is not active yet. Publishing this site does not connect Gmail or make the private assistant public.

## Files to publish

- `index.html` — application overview and privacy link.
- `privacy/index.html` — intended Gmail data handling and operator contact.
- `assets/site.css` — shared styles; no external assets or JavaScript.
- `.nojekyll` — publish these files directly rather than using a site generator.
- `.gitignore` — excludes common credential-file names; this is not a substitute for reviewing uploads.
- `README.md` — this handoff, also safe to publish.

No build, package installation or application server is required. Relative links support both a root site and a project site such as the `openclaw-mail-info` repository's Pages URL.

## Publish using your existing GitHub account

Git operations and remote publication are deliberately left to the operator. This directory has not been initialized as a Git repository.

1. In GitHub, use **New repository**. Choose your existing account, name it **openclaw-mail-info**, and make it **Public**. Do not change the private runtime repository's visibility. A new GitHub account is not needed.
2. Upload **the contents of this directory**, not an enclosing `openclaw-mail-info` directory. Preserve the `assets/` and `privacy/` folders. On macOS, Command-Shift-period shows `.nojekyll` and `.gitignore` in Finder. Review the upload: only the six files listed above belong in the initial publication.
3. Commit the uploaded files using GitHub's web interface.
4. Open **Settings → Pages → Build and deployment**. Set **Source** to **Deploy from a branch**, select the uploaded branch (normally `main`), choose **/(root)**, and click **Save**.
5. Wait for the Pages deployment to succeed. Copy the actual URL shown under **Visit site**; do not guess it. GitHub's supplied HTTPS hostname is sufficient—no DuckDNS, purchased domain, DNS updates or Headscale changes are selected.
6. Open that URL in a signed-out/private browser window. Check that the overview loads, its Privacy link opens the full policy, the Home link returns correctly, and the contact link uses the intended operator inbox. Retain HTTPS.

GitHub Free requires the Pages source repository to be public. Only this information site is public; the runtime and homeserver repositories stay private. See [GitHub's publishing instructions](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site).

## Continue Google OAuth

1. In the dedicated mail project's **Google Auth Platform → Branding**, use the actual published overview URL as the homepage and the actual Privacy link target as the privacy-policy URL. Keep the app name consistent with the site and select the intended support email.
2. Under **Authorized domains**, use the site's top private domain, normally your account's `github.io` hostname—not the shared `github.io` suffix. Enter no protocol or path in this field.
3. If Google requires ownership verification, use [Search Console](https://search.google.com/search-console) while signed into an Owner or Editor of the mail project. Add the site's actual HTTPS URL as a **URL-prefix** property and follow its offered HTML-file or HTML-meta-tag verification method. Supply the requested public verification file/tag so it can be added to this site; do not remove it after verification. A verification tag is not an OAuth client secret.
4. Return to Branding/Audience and resolve Google's actual validation messages. Production publishing and brand/data-access verification are distinct. Personal-use verification exemptions do not justify using fake URLs or ignoring the publishing block.
5. Before a permanent Gmail grant, confirm the desired production status and only `gmail.readonly` plus `gmail.send`. Do not add Calendar, Drive, full-mail, modification or settings-management scopes to work around a warning.
6. Finish the protected runtime connection and human-owned Google consent separately. Never publish OAuth JSON, authorization callback URLs/codes, refresh tokens, SOPS data, private conversation history or mailbox contents here.

Google may still require an additional ownership or verification step; the public pages are not a guarantee of approval. Testing-mode Gmail grants expire after seven days and are not the permanent configuration.

## Activation and maintenance

The privacy policy describes the integration's permitted use when enabled. Before allowing Gmail contents into an AI provider, verify compatible training, retention and human-access controls under Google's Limited Use rules. Also verify protected token persistence and appropriate encryption/access controls for retained Google data, safeguards for untrusted mail, and prominent in-product disclosure with affirmative owner consent. Publishing this policy is not proof that those controls or consent exist; it does not add a per-email approval requirement.

Keep the policy aligned with actual permissions, AI-provider processing, retention and deletion behavior. If the OAuth app name or operator contact changes, update the overview, policy and Google branding together. No analytics, external fonts, third-party scripts, forms or browser storage are used by these pages; GitHub operates the hosting and can retain visitor/security logs.

This repository is not an automatic synchronization path from the private runtime. Review every file before publishing. The `.gitignore` rules do not remove files that have already been committed.

## Local verification

The six-file public artifact manifest and credential-pattern scan passed. Root and project-prefix HTTP paths, stylesheet MIME types, directory redirects, and real-browser overview/privacy/back navigation were exercised in the existing OpenClaw Compose service on its existing local port. Desktop and 390-pixel mobile layouts, light/dark styles, absence of external subresources and absence of page errors were observed. The temporary preview was stopped afterward without deleting persistent runtime state.

This is local site evidence, not GitHub Pages deployment, Google domain verification, OAuth authorization or Gmail delivery proof. No remote repository or Git metadata was created.

