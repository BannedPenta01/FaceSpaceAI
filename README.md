# Open Source AI app that contains over 50 AI models from Huggingface and a plethora of features and optimizations.

# FaceSpace AI

Android chat and coding agent app powered by [Hugging Face Router](https://huggingface.co/docs/inference-providers) and 50 selectable open models.

## Features

- Standard chat with streaming replies, web search, and file/image attachments
- Coding agent with workspace tools (`LIST_FILES`, `READ_FILE`, `WRITE_FILE`, `EDIT_FILE`)
- Hugging Face, OpenRouter, or custom OpenAI-compatible API hosts
- Budget mode, adaptive layouts (phone, tablet, desktop window)

## Requirements

- Android 8.0+ (API 26)
- JDK 17
- Android SDK (compile SDK 35)

## Build

```bash
./gradlew assembleDebug
```

APK: `app/build/outputs/apk/debug/app-debug.apk`

**Signed release** (certificate CN: **BannedPenta**):

```powershell
.\scripts\create-release-keystore.bat
.\gradlew.bat assembleRelease
```

APK: `app/build/outputs/apk/release/app-release.apk` (signed when `secrets.properties` exists).

**Clean build artifacts** (keeps your release APK; you can delete the APK yourself afterward):

```powershell
.\scripts\clean-for-release.ps1
```

On Windows (debug):

```powershell
.\gradlew.bat assembleDebug
```

## Setup

1. Install the APK or run from Android Studio.
2. Open **Settings** and add your Hugging Face access token.
3. Enable **Inference Providers** for your account at [huggingface.co/settings/inference-providers](https://huggingface.co/settings/inference-providers).
4. Pick a model and start chatting.

Optional: set a SearXNG base URL in Settings for web search.

## Project structure

```
app/src/main/java/com/local/llmandroid/
  agent/       Coding agent + workspace tools
  inference/   Hugging Face / OpenAI-compatible API client
  model/       Model catalog (50 HF Router models)
  ui/          Jetpack Compose UI
  util/        Attachments helpers
  web/         Web search engine
```

## License

Source provided as-is for personal use. Model usage is subject to each provider's license on Hugging Face.
