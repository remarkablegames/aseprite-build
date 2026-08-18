# aseprite-build

🛠️ GitHub Actions workflow that builds Aseprite for macOS. See the official [install](https://github.com/aseprite/aseprite/blob/main/INSTALL.md) instructions.

## Build

1. Go to **Actions** → **Build Aseprite for macOS** → **Run workflow**.
2. Choose the [aseprite](https://github.com/aseprite/aseprite) branch or tag, the macOS runner (`macos-latest` or `macos-13`), and the CMake build type.
3. Download the `aseprite-macos-...` artifact from the workflow run.

## Open the unsigned app

The built `.app` is not code-signed, so macOS will warn you the first time it is opened:

- Open **System Settings** → **Privacy & Security** and click **Allow Anyway** under **Security**, then open `Aseprite.app` again.
- Or remove the quarantine flag from the terminal:

```bash
xattr -rd com.apple.quarantine /path/to/Aseprite.app
```
