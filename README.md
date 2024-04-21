# Flutter Web App Builder

Automates the build and deployment of your Flutter web app on GitHub Pages.

## Usage

```yml
name: Build Flutter App (APK/AAB/IPA), Deploy Flutter web app to GitHub Pages

on:
  push:
    branches:
      - main

jobs:
  build:
    name: Build and Deploy
    runs-on: ${{ matrix.os }}
    strategy:
      matrix:
        os: [macos-latest, ubuntu-latest, windows-latest] # No NEED OF Matrix Choose any SIngle But remember Choose as per BUILD
        include:
          - os: macos-latest
            runner: macos-latest
          - os: ubuntu-latest
            runner: ubuntu-latest
          - os: windows-latest
            runner: windows-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v4
      - name: Set up Java
        uses: actions/setup-java@v1
        with:
          java-version: '12.x'
      - name: Set up Flutter
        uses: subosito/flutter-action@v2
        # with:
        #   flutter-version: '2.x' # any version
      
      # Additional steps as needed
      - name: Build and deploy Flutter web app
        uses: antinna/fa@v1
        id: build
        with:
          release: true
          gh_pages: true
          webRenderer: auto
          baseHref: "/"
          aab_generation: true
          apk_generation: true
      - name: Archive APK
        uses: actions/upload-artifact@v2
        with:
          name: release-apk
          path: ${{ steps.build.outputs.apk-path }}
      - name: Archive AAB
        uses: actions/upload-artifact@v2
        with:
          name: release-aab
          path: ${{ steps.build.outputs.aab-path }}
```

## Inputs

| Name                  | Description                                     | Default        |
|-----------------------|-------------------------------------------------|----------------|
| release               | If set to `true`, it will run release builds, otherwise debug builds | `false` |
| keystore              | Base64 encoded keystore.jks, required if release is true | "" |
| keystore-pwd          | Keystore password, required if release is true | "" |
| key-pwd               | Key password, required if release is true | "" |
| aab_generation        | Generate AAB | `false` |
| apk_generation        | Generate APK | `false` |
| ipa_generation        | Generate IPA (iOS) | `false` |
| dmg_generation        | Generate DMG (macOS) | `false` |
| appImage_generation   | Generate LINUX APPIMAGE (Linux) | `false` |
| exe_generation        | Generate EXE (Windows) | `false` |
| gh_pages              | Deploy to GitHub Pages | `false` |
| build_runner_build    | Build Runner Build | `false` |
| change_splash         | Change Splash | `false` |
| i18n_generation       | Generate i18n | `false` |
| generate_launcher_icons | Generate Launcher Icons | `false` |
| custom_app_name       | Custom App Name (Leave empty to skip) | "" |
| custom_package_name   | Custom Package Name (Leave empty to skip) | "" |
| webRenderer           | Which web renderer to be used, default is auto | "auto" |
| workingDir            | The directory where the project is (default .) | "." |
| targetBranch          | Target branch for GitHub Pages deployment | "gh-pages" |
| baseHref              | Base href (if applicable) | "/" |
| customArgs            | Custom args like: --dart-define="key=value" | "" |

## Outputs

| Name           | Description                               |
|----------------|-------------------------------------------|
| apk-path       | Path to built APK if build-type was set to APK or AAB | 
| aab-path       | Path to built AAB if build-type was set to AAB or AAB | 
| ipa-path       | Path to built IPA file if build-type was set for iOS | 
| dmg-path       | Path to built DMG file if build-type was set for macOS | 
| appImage-path  | Path to built APPIMAGE file if build-type was set for Linux | 
| exe-path       | Path to built EXE file if build-type was set for Windows | 

## Platform Support

- **macOS**: Apple supported builds can be generated on macOS runner.
- **Windows**: Windows supported builds can be generated on Windows runner.
- **Linux**: Linux supported builds can be generated on Linux runner.

## Examples

### Build APK and deploy web app to GitHub Pages

```yml
uses: antinna/fa@v1
with:
  release: true
  apk_generation: true
  gh_pages: true
```

### Generate AAB and deploy web app to GitHub Pages

```yml
uses: antinna/fa@v1
with:
  release: true
  aab_generation: true
  gh_pages: true
```

### Build IPA for iOS and deploy web app to GitHub Pages

```yml
uses: antinna/fa@v1
with:
  release: true
  ipa_generation: true
  gh_pages: true
```

### Generate DMG for macOS and deploy web app to GitHub Pages

```yml
uses: antinna/fa@v1
with:
  release: true
  dmg_generation: true
  gh_pages: true
```

### Generate Linux AppImage and deploy web app to GitHub Pages

```yml
uses: antinna/fa@v1
with:
  release: true
  appImage_generation: true
  gh_pages: true
```

### Generate EXE for Windows and deploy web app to GitHub Pages

```yml
uses: antinna/fa@v1
with:
  release: true
  exe_generation: true
  gh_pages: true
```

### Customize app name and package name

```yml
uses: antinna/fa@v1
with:
  release: true
  custom_app_name: "MyCustomAppName"
  custom_package_name: "com.example.custom"
  gh_pages: true
```

### Specify additional custom arguments

```yml
uses: antinna/fa@v1
with:
  release: true
  customArgs: "--dart-define=KEY=VALUE"
  gh_pages: true
```

## License

This action is licensed under the [BSD License](LICENSE).
```
