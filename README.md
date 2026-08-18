# aseprite-build

🛠️ GitHub Actions workflow that builds Aseprite for macOS. See the official [install](https://github.com/aseprite/aseprite/blob/main/INSTALL.md) instructions.

## Build

1. Go to **Actions** → **Build Aseprite for macOS** → **Run workflow**.
2. Choose the [aseprite](https://github.com/aseprite/aseprite) branch or tag, the macOS runner (`macos-latest` or `macos-13`), and the CMake build type.
3. Download the `aseprite-macos-...` artifact from the workflow run.

### Architecture

The default `macos-latest` runner builds an Apple Silicon (arm64) `.app`. If your Mac uses an Intel processor, use the `macos-13` runner and download the artifact that contains `x64` in its name.

If opening the app shows the message:

> You can’t open the application “Aseprite” because this application is not supported on this Mac.

The build’s architecture doesn’t match your Mac. Rerun with the appropriate runner.

## Open the unsigned app

The built `.app` is not code-signed, so macOS will warn you the first time it is opened:

- Open **System Settings** → **Privacy & Security** and click **Allow Anyway** under **Security**, then open `Aseprite.app` again.
- Or remove the quarantine flag from the terminal:

```bash
xattr -rd com.apple.quarantine /path/to/Aseprite.app
```
