---
layout: default
title: Privacy policy
description: How AdShield handles your data. Short version, it stays on your phone.
permalink: /legal/privacy-policy/
---

# Privacy policy

<p class="meta">Effective date: November 1, 2026 (updated: optional usage analytics) · App: AdShield (<code>com.aps.adshield</code>) · Developer: Apoorv Soni</p>

## Summary

- AdShield blocks ads and trackers **on your device**. Your DNS history, statistics and rules
  are stored only on your phone.
- AdShield has **no accounts, no advertising SDKs and no crash-reporting services**. We do not sell,
  rent or share your personal data.
- **Usage analytics are optional and off by default.** Only if you turn on "Share anonymous usage
  statistics" does AdShield send app usage events and daily totals to Mixpanel. They never include
  the domains, sites or apps you use. See [Optional usage analytics](#optional-usage-analytics).
- Otherwise, the only network requests AdShield makes itself are **DNS lookups** to the DNS provider
  you choose and **blocklist downloads** from the list sources you enable.

## How AdShield works

AdShield uses Android's `VpnService` to create a **local** VPN on your device. This VPN does not
connect to a remote server, and it does not see your web traffic. It only receives DNS lookups
(the step where an app asks "what is the address of example.com?"). Requests to public DNS
resolvers are also routed to it so that apps can't bypass filtering.

Each lookup is checked on your device against the blocklists you enable and your own rules:

- **Blocked** lookups are answered locally and never leave your device.
- **Allowed** lookups are forwarded to your chosen DNS provider, and the answer is returned to the app.

AdShield does not decrypt HTTPS, install certificates, read the content of your communications,
or collect the pages you visit.

## Information processed and stored on your device

| Data | Why | Where | How long |
|---|---|---|---|
| DNS query log: domain name, time, record type, result (blocked/allowed), response time, and which app made the request (from Android's app identifier) | Lets you see what was blocked in the Query log and allow anything that broke | App's private storage on your device | 1, 7 (default) or 30 days, as you choose in Settings |
| Daily statistics: request and block counts, and per-domain block counts | Statistics screen and charts | On your device | Per-domain counts 90 days; daily totals about 13 months |
| Your settings, custom allow/block rules and custom blocklist addresses | Making the app work as configured | On your device | Until you change or delete them |
| Downloaded blocklists | Filtering | On your device | Replaced at each update |
| List of installed apps (name and icon of launchable apps) | The "App filtering" screen, where you choose which apps AdShield filters | Read on demand, not stored except the apps you choose to exclude/include | Until you change the choice |

None of this information is sent to us or to Mixpanel. We have no server that receives it.

## Information that leaves your device

**DNS lookups to your DNS provider.** Allowed lookups (the domain name being looked up, sent from your
device's IP address) go to the provider selected in Settings:

- **Network default:** the DNS servers of your Wi-Fi or mobile network (usually your internet provider).
- **Cloudflare (1.1.1.1):** see the [Cloudflare 1.1.1.1 privacy policy](https://developers.cloudflare.com/1.1.1.1/privacy/public-dns-resolver/).
- **Google Public DNS (8.8.8.8):** see the [Google Public DNS privacy page](https://developers.google.com/speed/public-dns/privacy).
- **Custom:** the servers you enter.

This is the same information your phone would send without AdShield. If you turn on encrypted DNS,
lookups to Cloudflare or Google are sent over HTTPS (DNS-over-HTTPS) so others on the network can't read them.

**Blocklist downloads.** AdShield downloads the filter lists you enable over HTTPS from their publishers,
for example AdGuard (`adguardteam.github.io`), Peter Lowe's list (`pgl.yoyo.org`), StevenBlack hosts
(`raw.githubusercontent.com`) and malware-filter (`malware-filter.gitlab.io`), or any custom list address
you add. Like any web request, these servers can see your IP address and the time of the download.
No personal data is included in these requests.

**Android backup.** If Android backup is enabled on your device, only AdShield's **settings** may be
included in your Google backup or device-to-device transfer. Your query log, statistics and rules are
excluded from backup.

**Rules export.** If you use "Export rules", AdShield writes a file to the location you pick. Where that
file goes is up to you.

## Optional usage analytics

AdShield can send anonymous usage statistics to help us understand how the app is used and improve it.
This is **off unless you turn it on** in Settings → Application → "Share anonymous usage statistics",
and you can turn it off at any time. Until you opt in, the analytics library is not even started.

**Service:** [Mixpanel](https://mixpanel.com) (Mixpanel, Inc.), acting as our analytics processor. See the
[Mixpanel privacy policy](https://mixpanel.com/legal/privacy-policy/).

**What is sent when it's on:**

- App events, such as the app being opened, protection being started, stopped or failing to start,
  the VPN permission being granted or denied, a built-in blocklist being turned on/off or updated, and
  a setting being changed (for example the theme or the DNS provider type).
- Counts and totals, such as the number of DNS requests, blocked ads and blocked trackers per day, or
  how many domains you added to your own rules.
- App and device context: app version and build, Android version, phone or tablet, and the device
  model and manufacturer, plus a random analytics ID that Mixpanel creates for this installation.

**What is never sent:** domain names, websites, DNS queries or answers, your query log, the names of
apps on your device or which apps you exclude, custom DNS server addresses, names of custom blocklists,
anything you type, or your email or account details (AdShield has no accounts). We also tell Mixpanel not
to use your IP address to estimate your location.

**Turning it off** stops all further events and discards any that are still waiting to be sent from your
device. Mixpanel keeps received events according to its data-retention settings for our project. To ask
for deletion of events already received, contact us at the address below.

## Permissions

| Permission | Why it's needed |
|---|---|
| VPN (`BIND_VPN_SERVICE`, with your consent) | Run the local DNS-filtering VPN |
| Internet, network state | Forward DNS lookups, download blocklists, follow network changes |
| Foreground service | Keep protection running, with a visible notification |
| Notifications (optional) | Show the "Protection is on" notification and alerts if protection stops |
| Run at startup | Turn protection back on after a reboot or app update, if you had it on |

## Your choices and deleting your data

- Change how long the query log is kept in **Settings → Application → Keep detailed request log for**.
- Delete statistics and the query log in **Settings → Application → Clear statistics**.
- Turn usage analytics on or off in **Settings → Application → Share anonymous usage statistics**.
- Remove custom rules and lists from their screens at any time.
- Clearing the app's storage in Android settings, or uninstalling AdShield, permanently deletes all of
  its data from your device.

We don't hold your filtering data, so there is nothing of it for us to access, export or delete on our
side. If you used optional analytics, contact us to delete the events Mixpanel received.

## Children

AdShield is not directed at children under 13 and does not knowingly collect personal information
from anyone.

## Security

Data is kept in AdShield's private app storage, which other apps can't read. Blocklists are only
downloaded over HTTPS. Encrypted DNS is available for supported providers.

## Changes to this policy

If this policy changes, the new version will be posted on this page with a new effective date.
Significant changes will also be noted in the app's release notes.

## Contact

Apoorv Soni · [apoorvsoni587@gmail.com](mailto:apoorvsoni587@gmail.com)
