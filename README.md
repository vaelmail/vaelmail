# VaelMail

<p align="center">
  <a href="https://vaelmail.com">
    <img src="https://vaelmail.com/social/vaelmail-logo.png" alt="VaelMail Logo" width="128" height="128">
  </a>
</p>

<p align="center">
  <strong>Private, lightweight webmail and persistent aliases authenticated via 16-digit account keys.</strong><br>
  Zero phone numbers. Zero KYC. Zero tracking. Hosted in Sweden.
</p>

<p align="center">
  <a href="https://vaelmail.com"><img src="https://img.shields.io/badge/Website-vaelmail.com-00e599?style=flat-square" alt="Website"></a>
  <a href="https://nojs.vaelmail.com"><img src="https://img.shields.io/badge/Mirror-No--JS%20Webmail-141414?style=flat-square" alt="No-JS Mirror"></a>
  <a href="http://5gxnpixptykyv5fchr2qidjbrazjewswx77ddrqowpcmwmmgll57daid.onion"><img src="https://img.shields.io/badge/Tor-v3%20Onion-7D4698?style=flat-square" alt="Tor Onion"></a>
  <a href="https://monerica.com/site/vaelmail"><img src="https://img.shields.io/badge/Monerica-Verified%20Owner-FF6600?style=flat-square" alt="Monerica Verified"></a>
  <img src="https://img.shields.io/badge/Jurisdiction-Sweden%20%F0%9F%87%B8%F0%9F%87%BA-blue?style=flat-square" alt="Sweden">
  <img src="https://img.shields.io/badge/Payments-Monero%20%7C%20Bitcoin-orange?style=flat-square" alt="Crypto Payments">
</p>

---

### Core Philosophy and Architecture

Modern email registration has devolved into an invasive identity audit: mainstream providers mandate mobile numbers, linking mailboxes to telecom registrations and physical locations.

VaelMail eliminates this compromise. Drawing architectural inspiration from Mullvad VPN, accounts authenticate using client-generated **16-digit account keys** processed with **Argon2id** key derivation. No passwords on disk, no SMS verification, and no personal data collection.

```
       [ Client Ingress ]
       /       |        \
( HTTPS )  ( Tor v3 )  ( No-JS SSR )
       \       |        /
    [ Reverse Proxy & Postfix ]
               |
  [ Argon2id Authentication ]
               |
  [ Maildir Storage (AES-256) ]
```

---

### Key Capabilities

* **16-Digit Account Keys**: Non-custodial possession model. Your 16-digit number is your sole authoritative credential.
* **Persistent Aliases (`@vael.pw`)**: Shield your primary address from data breaches and cross-site tracking. Aliases route indefinitely into your main inbox and can be isolated or toggled individually.
* **Multi-Network Ingress**:
  * **Clearnet**: Fast, encrypted webmail at [vaelmail.com](https://vaelmail.com).
  * **Scriptless No-JS Mirror**: Pure server-side rendered HTML webmail at [nojs.vaelmail.com](https://nojs.vaelmail.com) to mitigate browser exploit surfaces and canvas fingerprinting.
  * **Tor Hidden Service**: Direct end-to-end onion routing (`http://5gxnpixptykyv5fchr2qidjbrazjewswx77ddrqowpcmwmmgll57daid.onion`).
  * **I2P Eepsite**: Decentralized garlic routing.
* **Hardware Security Keys**: Optional client-side WebAuthn (FIDO2) Passkey registration (YubiKey, Touch ID, Windows Hello).
* **Zero Telemetry**: 0% Google Analytics, tracking pixels, or remote font/CDN dependencies.
* **Non-Custodial Cryptocurrency Upgrades**: Native Monero (XMR) and Bitcoin (BTC) checkout for VaelMail Plus subscriptions (1 GB storage, outbound sending, custom domains).

---

### Official Resources

* **Webmail**: [https://vaelmail.com](https://vaelmail.com)
* **No-JS Webmail**: [https://nojs.vaelmail.com](https://nojs.vaelmail.com)
* **Technical Specification**: [VaelMail Technical Spec](https://vaelmail.com/privacy)
* **Support Email**: `vael-support@vael.email`
* **PGP Fingerprint**: `0C5A 1CF2 7DC4 F5E6 9C72  D807 E490 17C3 6DED F1E6`
