+++
title = 'Flutter Post'
date = 2024-07-21T20:42:41+02:00
draft = true
+++

# Flutter

$$ \sum_{n=1000}^{2000}n  $$

```bash
flutter doctor
flutter create first_project
cd first_project/

# run in debug (dev)
flutter run
flutter run --web-hostname 0.0.0.0 --web-port 8888
```

This will open Chrome with your app inside.


Compile to apk:

```bash
flutter build apk --split-per-abi
scp build/app/outputs/flutter-apk/* rpi:/ave/www/md/apk
```

This command results in three APK files:

    [project]/build/app/outputs/apk/release/app-armeabi-v7a-release.apk
    [project]/build/app/outputs/apk/release/app-arm64-v8a-release.apk
    [project]/build/app/outputs/apk/release/app-x86_64-release.apk

## Build for web

```
flutter build web --base-href /md/apk_web/
```

Wynik jest tu: avendi_app\build\web 

Strona pod adresem: http://192.168.5.5/md/apk_web/

## Build for Windows


```ps
flutter build windows
```

Wynik jest tu: avendi_app\build\windows\runner\Release 


## Add dependency

```bash
flutter pub add flutter_map
flutter pub add latlong2
flutter pub add flutter_radio_player
flutter pub add latlong2
flutter pub add latlong2
```

## Install on Windows


```ps
$env:JAVA_HOME="C:\Android\openjdk"
$env:ANDROID_HOME="C:\Android"
$env:ANDROID_NDK="C:\Android\ndk-bundle"

$env:path=$env:Path+";C:\Android\cmdline-tools;C:\Android\cmdline-tools\tools;C:\Android\cmdline-tools\tools\bin;C:\Android\flutter\bin;C:\Android\cmake\3.22.1\bin"

flutter config --android-sdk C:\Android\
dir env:
sdkmanager "system-images;android-29;default;x86_64"
sdkmanager "build-tools;29.0.3"
.\sdkmanager --install "cmdline-tools;latest"
flutter doctor --android-licenses
flutter doctor
.\sdkmanager.bat ndk-bundle
.\sdkmanager.bat --install "cmake;3.22.1"
```

## rust

```ps
cargo install cbindgen
dart pub global activate ffigen
cargo install flutter_rust_bridge_codegen
```

- https://github.com/flutter-rs/flutter-rs
- C:\Users\rav\.cargo\

```ps
cargo install cargo-flutter
flutter create first_project
cd .\first_project\
cargo new rust --vcs=none --lib
<!-- Cargo.toml edycje -->
cargo install flutter_rust_bridge_codegen
dart pub global activate ffigen
flutter pub add flutter_rust_bridge
flutter pub add -d build_runner
flutter pub add -d freezed
flutter pub add -d freezed_annotation
cargo install cargo-ndk
dart pub add --dev ffigen
dart pub add ffi
flutter_rust_bridge_codegen --rust-input .\rust\src\lib.rs --dart-output .\lib\bridge_generated.dart
```

```bash
flutter run -d windows
```

# Flutter

```dart
void main() {
  print("Hello, World!");
}
```


## Kompilacja

do exe, js, jit

```bash
flutter upgrade

dart compile exe hello.dart
./hello.exe

dart compile js hello.dart
node out.js

dart compile jit-snapshot hello.dart
dart run hello.jit
```



## Tutorials
- https://www.youtube.com/watch?v=iuGNFhxz4ZQ
- https://www.youtube.com/watch?v=C-fKAzdTrLU

