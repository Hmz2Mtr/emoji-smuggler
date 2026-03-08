# 🕵️‍♂️ Emoji Smuggler

**Zero-Width Character Steganography Engine**

Emoji Smuggler is a powerful, client-side steganography tool that allows you to hide secret text within innocent-looking emoji strings (or any text). By utilizing zero-width characters (ZWC), the injected payload remains completely invisible to the naked eye and bypasses standard content filters.

## ✨ Features

- **Local Processing:** 100% of the encoding, encryption, decoding, and extraction processes happen locally in your browser. No data is ever sent to a server.
- **Advanced Steganography:** Weaves your secret payload between characters using Unicode Zero-Width Characters (`U+200B`, `U+200C`, and `U+200D`).
- **Encrypted Payload:** Contents are encrypted using an XOR cipher and Base64 encoded before being converted to binary bits, ensuring the underlying data isn't plain text if extracted without the tool.
- **Password Protected:** Includes a built-in passcode gate to prevent unauthorized access to the application.

## 🚀 Usage

### Injecting a Payload
1. Unlock the application using your passcode.
2. Enter an innocent **Emoji carrier string** (e.g., `😀😎🚀`).
3. Type your **Secret payload** in the designated box.
4. Click **INJECT PAYLOAD**.
5. Copy the resulting text and paste it anywhere! Unsuspecting viewers will only see the carrier text/emojis.

### Extracting a Payload
1. Paste the suspicious text containing the hidden payload into the **EXTRACT** module.
2. Click **ANALYZE & EXTRACT**.
3. The engine will scan for ZWC signatures, decode the 8-bit segments, decrypt them, and reveal the hidden payload.

## 🛠️ Technical Details

Each character of the payload is converted to 8-bit ASCII binary:
- `Bit 0` is represented by `U+200C` (Zero-Width Non-Joiner - ZWNJ)
- `Bit 1` is represented by `U+200B` (Zero-Width Space - ZWS)
- Characters are separated by `U+200D` (Zero-Width Joiner - ZWJ)

These invisible codepoints are then meticulously woven into the carrier text.

## 🌐 Hosting on GitHub Pages

This project is fully static and can be hosted directly on GitHub Pages!

1. Go to your repository **Settings**.
2. Navigate to the **Pages** section on the left sidebar.
3. Under **Build and deployment** > **Source**, select `Deploy from a branch`.
4. Select the `master` or `main` branch.
5. Save, and your site will be live! Simply navigate to the provided URL, appending `/emoji-smuggler.html` if the default file isn't named `index.html`.
