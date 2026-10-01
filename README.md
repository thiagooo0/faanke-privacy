# faanke-privacy

Public site for [Faanke](https://github.com/thiagooo0/Faanke), a pomodoro timer
for Mac and iPhone. It exists because the App Store requires a publicly reachable Privacy
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

One Privacy Policy URL serves both platforms on the App Store, so every claim in
`privacy.html` has to hold for the Mac app and the iPhone app at once.

- **Mac**: the policy says Faanke for Mac cannot reach the network. That holds
  only while the Mac app has no network code and `Faanke.entitlements` does not
  contain `com.apple.security.network.client`.
- **iPhone**: the only network traffic is weather — approximate location sent
  to Apple's WeatherKit and Apple's geocoder, and only after the user turns
  weather on. The latest forecast and the coordinates it was fetched for are
  cached on the device. Photos come through the system picker (no library
  permission). Purchases go through StoreKit. No account, analytics, ads or
  third-party SDKs.

If either app's behaviour changes, this policy has to change with it — before
the release ships.
