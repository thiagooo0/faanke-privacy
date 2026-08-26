# faanke-privacy

Public site for [Faanke](https://github.com/thiagooo0/Faanke), a macOS pomodoro
timer. It exists because the App Store requires a publicly reachable Privacy
Policy URL and Support URL, and the app's own repository is private.

Served by GitHub Pages from the `main` branch:

| Page | URL | Used in App Store Connect as |
|---|---|---|
| `index.html` | `https://thiagooo0.github.io/faanke-privacy/` | Support URL |
| `privacy.html` | `https://thiagooo0.github.io/faanke-privacy/privacy.html` | Privacy Policy URL |

Both pages pick a language from the browser, and accept a `?lang=` override
(`en`, `zh-Hans`, `zh-Hant`, `ja`, `es`, `fr`, `de`) so each App Store
storefront can be pointed at its own language.

## The header icon

The `<svg class="mark">` in both pages is a verbatim copy of
`Faanke/Resources/IconSource/AppIcon.svg` in the app repo, which is the single
source of truth for the icon. If the icon changes there, re-copy it here —
don't redraw it.

## Keeping the policy honest

The privacy policy claims Faanke cannot reach the network. That holds only as
long as the app has no network code and, crucially, does not add
`com.apple.security.network.client` to `Faanke.entitlements`. If that ever
changes, this policy has to change with it — before the release ships.
