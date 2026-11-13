# Install, offline use and updates

Power DevBox Review is an installable web app. Installation gives you an app window or home-screen entry; it does not turn the product into a server-side solution store.

## Install

1. Open the hosted app using HTTPS in a supporting browser. Localhost also supports installation during local use.
2. Open **Settings → Install Power DevBox Review**.
3. If **Install app** is offered, choose it and complete the browser's prompt.
4. If it is not offered, use your browser's own install-app command where available. On iPhone/iPad, use Safari's **Share → Add to Home Screen**.

The button is hidden when the app is already installed, running standalone, or the browser has not offered installation. Lack of a button does not mean standard browser review is unavailable.

## Prepare for offline review

While online, open the workspace **and each reviewer you intend to use** so its public assets can be cached. Only app assets are cached as they are used. Keep your solution ZIP on the device: uploaded solution files are not stored in the offline cache.

Offline availability depends on what has been cached and on browser storage retention. It is not a guarantee that a never-opened reviewer or newly released asset will work offline. Reload your local solution file when needed.

## Pro still needs the network

{% hint style="info" %}
**Custom flags and comparison need a validated Power DevBox Pro license.** [Buy a license](https://power-devbox.lemonsqueezy.com/checkout/buy/729d48f6-cc59-477e-a601-ca99100ffeb3). Installation does not unlock these features or remove online validation.
{% endhint %}

License validation requires an internet connection. Do not rely on custom flags or comparison remaining available throughout an offline session: there is no supported offline-unlock mechanism, and saved credentials alone do not grant access.

## Updates

New app updates activate after **all app windows are closed**, so a loaded review is not interrupted by an immediate replacement. Export any review evidence you need, close the browser/app windows for this app, then reopen online to receive the update.

If you suspect old assets, first check the version in Settings and close/reopen all app windows. Avoid clearing site data as a first step: it can remove your custom rules, remembered credentials, recent list and preferences. [Export rules](flags/custom-flags/import-export.md) before doing that.
