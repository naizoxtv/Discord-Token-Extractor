# Discord Token Extractor

## Description
This script allows you to retrieve your own Discord token directly from the browser console. This can be useful for debugging, bot development, or educational purposes. Always ensure you are extracting your own token and not violating Discord's Terms of Service.

**Watch [this video](https://www.youtube.com/watch?v=aPoRQ0hxvc4) for a step-by-step visual guide on how to extract your Discord token.**  

## Step-by-Step Guide

### 1. Open the Discord Web App
- Go to the [Discord website](https://discord.com/app) and log in to your account.

### 2. Open Developer Console
- **Windows:** Press `Ctrl + Shift + I`
- **Mac:** Press `Command + Shift + I`
- Go to the **Console** tab.

### 3. Enter the Following Command
You can view the script directly on GitHub: [extract_discord_token.js](https://github.com/naizoxtv/Discord-Token-Extractor/blob/main/extract_discord_token.js)

Copy and paste the following command into the **Console**:

```js
(webpackChunkdiscord_app.push([[''],{},e=>{m=[];
for(let c in e.c)m.push(e.c[c])}]),m).find(m=>m?.exports?.default?.getToken!==void 0).exports.default.getToken()
```

### 4. Run the Command
- Press **Enter** to execute it.
- You should see a result similar to the following:

```
'OTMA1DNMc0MwzUNTUTyE2Njw.GhOsnE.aXrR0SIp9wK4k1in8_OEjT-3svTSPIA-cw'
```

- **Right-click** on the token and select **Copy String Contents**.
- Paste the token into a text editor and save it for later use.

## Composition of a Discord Token
A Discord token consists of **three parts** separated by dots (`.`):

1. **User ID (Base64 Encoded)**
   - This is the Discord **User ID**, encoded in Base64.
   - Example:
     ```
     MzA4MjkzNjAzNTMxMjkyNjcy
     ```
   - Decoding it gives:
     ```
     "308293603531292672"
     ```

2. **Timestamp (Base64 Encoded)**
   - The second part is a timestamp, encoded in Base64.
   - Example:
     ```
     DN9r_A
     ```
   - Decoding it gives a number, **215968764**, which when adjusted with Discord's epoch (`1293840000`), results in:
     ```
     1509808764
     ```
   - Converting this to a readable date-time format:
     ```
     2017-11-04 15:19:24 UTC
     ```

3. **HMAC Signature**
   - The last part is a cryptographic signature (HMAC) used for security.
   - This ensures the token is valid and has not been tampered with.
   - Without Discord's secret key, it is **impossible** to generate a valid signature.

## Reset Your Token
If you want to reset your token, follow these steps:

1. Open your **Discord settings**.
2. Change your password to automatically generate a new token.

---

**⚠ Disclaimer:** Extracting your Discord token should only be done for educational and personal use. Misuse of tokens or unauthorized access to accounts violates Discord’s Terms of Service and can result in account termination. Use this script responsibly and only with your own account.

