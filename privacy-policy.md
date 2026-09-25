# Rivo — Privacy Policy

**Last updated: 25 September 2026**

Rivo is an expense tracker for Android. It reads the transaction SMS your bank
already sends you and turns them into a spending record.

This policy describes what Rivo does with your information. It is short because
Rivo does very little with it.

---

## The short version

**Nothing you put into Rivo, and nothing Rivo reads from your phone, ever leaves
your device.**

Rivo does not have permission to access the internet. This is not a promise
about our intentions — it is a property of the app you install. The Android
package does not request the `INTERNET` permission, so the operating system
will refuse any attempt by Rivo to open a network connection, including by any
library inside it. You can verify this yourself: the permission list on the
Google Play listing, and in Android's own app-info screen, will not include it.

There is no Rivo account, no Rivo server, and no sign-in.

---

## What Rivo reads

### Transaction SMS

With your permission, Rivo reads the SMS messages on your phone in order to find
transaction alerts from banks and payment apps — the messages that say an amount
was debited or credited.

- Rivo asks for this permission on a screen that explains it first. You can
  decline, and the app still works — you can record transactions by hand.
- Parsing happens entirely on your device. The message text is never uploaded,
  because Rivo cannot upload anything.
- From each transaction message, Rivo stores the amount, date, merchant or payer
  name, transaction type, and the last four digits of the account or card where
  the message includes them. It also stores the message text so you can check a
  transaction against what your bank actually said.
- Rivo ignores messages that are not transaction alerts. OTPs, promotions and
  personal messages are read during scanning and discarded — they are not stored.
- You can revoke SMS access at any time in Android's Settings, or turn the
  feature off inside Rivo.

### What you enter yourself

Transactions you add by hand, budgets, savings goals, groups and shared
expenses, cards you add, your display name, and any notes you write.

### What Rivo does not collect

Rivo does not collect or store: your contacts, your location, your photos, your
device identifiers, advertising IDs, or any usage analytics. There is no
crash-reporting service and no analytics SDK in the app.

---

## Where your information is kept

On your phone, in a database encrypted with SQLCipher (AES-256). The encryption
key is held in the Android Keystore, which is backed by your device's secure
hardware where the device provides it.

Android's automatic cloud backup is **switched off** for Rivo
(`android:allowBackup="false"`). Your financial history is therefore not copied
to Google Drive or anywhere else as part of a device backup.

If you set a PIN or enable biometric unlock, Rivo asks for it before showing
your data. Rivo also asks Android to keep its screens out of the app-switcher
preview and to block screenshots, so your balances are not captured in
thumbnails.

---

## Sharing

Rivo does not share your information with anyone. There are no third-party
services in the app, no advertising, no trackers, and no data sold or
transferred to any party. Because Rivo has no internet access, there is no
mechanism by which it could.

The only way information leaves your phone is if **you** deliberately export it,
described next.

---

## Export and backup

Rivo can write a backup file to a location you choose using Android's own file
picker. This is entirely under your control:

- It happens only when you ask for it.
- The file is encrypted with a passphrase you set, using AES-256-GCM with a key
  derived by PBKDF2 (600,000 iterations).
- Rivo does not keep your passphrase. **If you lose it, the backup cannot be
  recovered — not by us, not by anyone.**
- Once you save that file somewhere, what happens to it is up to you. If you
  place it in a cloud folder, it goes to that cloud provider under their terms,
  encrypted.

---

## Rivo Pro, and what a subscription does not give us

Rivo has a paid tier. It changes what the app shows you; it changes nothing
about where your money information lives or who can see it.

**What we receive: nothing.** Google Play takes the payment. Rivo never sees
your card, your name, your email or your Google account. There is no Rivo
account to create, because there is no Rivo server to hold one.

**What is stored on your phone:** a timestamp recording when Google Play last
confirmed an active subscription, and the product id. That is all. It lives in
the same encrypted storage as everything else and is bound to this device.

**How it is checked:** every purchase Google Play issues is signed. Rivo
verifies that signature on your phone against a public key built into the app.
No request leaves your device, and there is no server to ask.

**Your transactions are untouched either way.** Nothing is uploaded when you
subscribe, and nothing is deleted if you stop. The free tier shows the recent
months; subscribing reveals the rest of the history that was always there, on
your phone, the whole time.

**Encrypted backup and restore stay free.** Getting your own data out of Rivo
is not something we will ever charge for.

**Cancelling** happens in Google Play, not in Rivo — only Google can actually
stop a subscription, so Rivo sends you there rather than showing a button that
cannot do what it says.

---

## Deleting your data

Uninstalling Rivo removes its database with it.

Inside the app, **You → Delete all data** erases everything Rivo holds:
transactions, budgets, goals, groups, cards and your profile. You must type
`DELETE` to confirm. The deletion is immediate and permanent, and there is no
copy anywhere else to restore from.

---

## Permissions, and why each exists

| Permission | Why |
|---|---|
| `READ_SMS`, `RECEIVE_SMS` | To find transaction alerts in your messages and to notice new ones as they arrive. This is Rivo's core function. Optional — decline and enter transactions by hand |
| `POST_NOTIFICATIONS` | To tell you a transaction was recorded, or that a bill is due |
| `USE_BIOMETRIC`, `USE_FINGERPRINT` | To unlock the app with your fingerprint or face, if you turn that on |
| `RECEIVE_BOOT_COMPLETED` | To resume scheduled reminders after your phone restarts |
| `FOREGROUND_SERVICE`, `WAKE_LOCK` | To finish processing a batch of messages without being interrupted |
| `ACCESS_NETWORK_STATE` | Required by a scheduling library Rivo uses. It reports whether a network exists; it cannot open one, and Rivo has no internet permission |
| `com.android.vending.BILLING` | To offer the Rivo Pro subscription through Google Play. It permits Rivo to talk to the Play Store app on your phone; it is not internet access |

Rivo does **not** request internet access, location, contacts, camera,
microphone, or storage beyond the file you pick yourself when exporting.

Google Play Billing asks for internet permission in its own right, and Rivo
**removes it again** when the app is built. You can check this yourself on the
installed app — it is a property of the file, not a promise.

---

## Children

Rivo is not directed at children under 13 and does not knowingly collect
information from them. Since Rivo collects nothing to a server, there is nothing
for us to hold or delete.

---

## Changes to this policy

If this policy changes, the date at the top changes and the new version is
published at this same address. If a future version of Rivo ever adds network
access, that will be stated here plainly and before the feature ships — not
discovered afterwards.

---

## Contact

Questions about this policy or about Rivo's handling of your data:

**quillmatick@gmail.com**

---

*Rivo stores your financial life on your own phone and nowhere else. If any part
of this policy turns out not to match what the app does, that is a bug — please
report it and it will be fixed or the policy corrected.*
