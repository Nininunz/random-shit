# ChatGPT Nativefier App for macOS


**Note:** The official ChatGPT app does not support Intel Macs. This method works on both Intel and Apple Silicon Macs.

**No API key required!** This is a native web wrapper, so you simply log in with your OpenAI account as you would in a browser.

This guide explains how to create a macOS desktop app for [ChatGPT](https://chat.openai.com/) using [Nativefier](https://github.com/nativefier/nativefier).

## Prerequisites
- [Node.js](https://nodejs.org/) installed
- [Nativefier](https://github.com/nativefier/nativefier) installed globally:
  ```sh
  npm install -g nativefier
  ```
- The `chatgpt.icns` icon file (place it in the working directory). You can find more ChatGPT icons at [macosicons.com](https://macosicons.com/#/ChatGPT)

## Command
Run the following command in your terminal:

```sh
cd <your-working-directory>
nativefier \
  --lang "en-US" \
  --darwin-dark-mode-support \
  --name "ChatGPT" \
  --conceal \
  --single-instance \
  --disable-dev-tools \
  --fast-quit \
  --user-agent chrome \
  --title-bar-style hiddenInset \
  --icon "chatgpt.icns" \
  --inject inject.css \
  --browserwindow-options '{"titleBarStyle":"hiddenInset","fullscreenable":true,"simpleFullscreen":true,"trafficLightPosition":{"x":12,"y":12},"thickFrame":true}' \
  https://chat.openai.com/ /Applications/
```

## Options Explained
- `--lang "en-US"`: Sets the app language to English (US).
- `--darwin-dark-mode-support`: Enables dark mode support on macOS.
- `--name "ChatGPT"`: Sets the app name.
- `--conceal`: Hides the menu bar for a cleaner look.
- `--single-instance`: Prevents multiple app windows.
- `--disable-dev-tools`: Disables developer tools for security.
- `--fast-quit`: Allows the app to quit instantly.
- `--user-agent chrome`: Uses a Chrome user agent for compatibility.
- `--title-bar-style hiddenInset`: Uses a modern macOS title bar style.
- `--icon "chatgpt.icns"`: Sets a custom app icon (must be in the directory).
- `--inject inject.css`: Injects custom CSS from `inject.css` into the app. This is used to fix double tap to zoom and enable proper drag for the title bar.
- `--browserwindow-options`: Customizes window appearance and behavior.
- `https://chat.openai.com/`: The URL to wrap as an app.
- `/Applications/`: Output location for the app (macOS Applications folder).

## Result
After running the command, you will find a `ChatGPT.app` in your `/Applications/` folder. Launch it like any other Mac app for a native ChatGPT experience.

---

For more customization, see the [Nativefier documentation](https://github.com/nativefier/nativefier/blob/master/API.md).
