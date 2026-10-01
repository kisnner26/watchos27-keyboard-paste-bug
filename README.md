# Apple Watch remote keyboard: pasted text arrives empty (watchOS 27)

[Leer en español](README.es.md)

> **Status: open.** Reproduced on watchOS 27.2. Last updated: 2026-10-01.

When a text field on an Apple Watch is filled through the iPhone's remote keyboard, text that is **pasted** into the iPhone field looks correct on the iPhone, but arrives **empty** on the watch. Typing the same text character by character works.

It happens in secure (password) fields and in regular text fields, so it does not look like a password-field restriction.

## Reproduce

1. On the watch, open a text field (tested with a password field and a regular field).
2. Open the keyboard on the iPhone when prompted.
3. Copy a short test string (for example `test12345`) from another app.
4. Paste it into the iPhone field. The iPhone shows the text.
5. Confirm on the watch.

**Expected:** the watch receives the pasted text.
**Actual:** the watch field receives empty input.

## What I tested

| Test | Result |
|---|---|
| Type the string by hand on the iPhone | arrives on the watch |
| Paste into a secure (password) field | arrives empty |
| Paste into a regular text field | arrives empty |

The data path itself works, since typed characters arrive. The failure is specific to pasted text.

## Environment

| | |
|---|---|
| iPhone | iPhone 15 Pro Max (`iPhone16,2`), iOS 27.0 |
| Watch | Apple Watch Ultra 2 (`Watch7,5`), watchOS 27.2 (`24S5091f`) |
| Mac | MacBook Pro (`MacBookPro17,1`, Apple M1), macOS 27.2 |

## Workaround

Type the text manually instead of pasting it.

## Related

- [watchos27-pairing-bug](https://github.com/kisnner26/watchos27-pairing-bug): a separate issue on the same watch, where it never reconnects after a successful manual pairing.

## Notes

This is an independent report from one device setup. If you can reproduce it (or cannot), open an issue with your device and OS versions.

MIT licensed. See [LICENSE](LICENSE).
