# Run It — public pages

Static pages for **Run It: PickUp Soccer**, served over GitHub Pages.

This repo is intentionally separate from the app source, which stays private.
Only these pages need to be publicly reachable:

| Page | Purpose |
|---|---|
| `index.html` | Landing / link hub |
| `privacy.html` | Privacy Policy — required by the App Store |
| `terms.html` | Terms of Service |
| `support.html` | Support + FAQ — required by the App Store |
| `reset-password.html` | Completes a password reset from the emailed link |

## Deploying

GitHub Pages serves from the `main` branch, root folder. Push to `main` and the
change is live within a minute or two.

Settings → Pages → Source: *Deploy from a branch* → Branch: `main` / `/ (root)`.

## Notes

- `reset-password.html` reads the recovery token from the URL fragment and calls
  Supabase directly. The Supabase project's **Redirect URLs** allowlist must
  include this page's full URL, or the link will not carry a token and the page
  will correctly show "Link expired".
- The Supabase publishable (anon) key in `reset-password.html` is safe to expose —
  it is a public client key, already shipped inside the mobile app bundle, and is
  protected by row-level security.
- Content here mirrors the in-app legal screens in the app repo. If you change the
  privacy policy or terms, update both so they don't drift apart.
