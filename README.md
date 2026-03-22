# tanvrit/commerceui

Compose Multiplatform UI components for commerce flows (product listing, checkout, order history).

## Supported Targets

| Target | Artifact suffix | Notes |
|--------|----------------|-------|
| Android | `-android` | minSdk 24+ |
| iOS arm64 (device) | `-iosarm64` | Native |
| iOS x64 (simulator, Intel) | `-iosx64` | Native |
| iOS Simulator arm64 | `-iossimulatorarm64` | Native |
| JVM (Ktor server / desktop) | `-jvm` | Java 11+ |
| WasmJS | `-wasmjs` | Experimental |
| JS (IR) | `-js` | Experimental |

## Prerequisites

This module depends on: [ui](https://github.com/tanvrit/ui), [commerce](https://github.com/tanvrit/commerce), [core](https://github.com/tanvrit/core).

Add those modules to your build before adding `commerceui`.

## Install

Add the GitHub Packages repository to your `settings.gradle.kts`:

```kotlin
maven {
    url = uri("https://maven.pkg.github.com/tanvrit/commerceui")
    credentials {
        username = (project.findProperty("gpr.user") as String?) ?: System.getenv("GITHUB_ACTOR") ?: ""
        password = (project.findProperty("gpr.key") as String?) ?: System.getenv("GITHUB_TOKEN") ?: ""
    }
}
```

Add the dependency:

```kotlin
// JVM / Ktor server / desktop
implementation("com.tanvrit:commerceui-jvm:0.0.2")

// Android
implementation("com.tanvrit:commerceui-android:0.0.2")

// KMP commonMain
implementation("com.tanvrit:commerceui:0.0.2")
```

## GitHub Packages Authentication

GitHub Packages requires a token even for public packages.

1. Create a [GitHub Personal Access Token](https://github.com/settings/tokens) with `read:packages` scope.
2. Add to `~/.gradle/gradle.properties`:

```properties
# ~/.gradle/gradle.properties
gpr.user=YOUR_GITHUB_USERNAME
gpr.key=YOUR_GITHUB_PAT_WITH_READ_PACKAGES
```

## Setup

`commerceui` is a UI/app module and does not expose a Koin DI module. Wire it up according to the composable entry points documented below.

## Quick Start

Add the `commerceui` artifact to your Compose Multiplatform project and use the provided composable functions directly — no additional initialisation is required.

## Version & Changelog

Current version: **0.0.2**

See [Releases](https://github.com/tanvrit/commerceui/releases) for the full changelog.

---

## Part of the Tanvrit SDK

This module is part of the [Tanvrit Platform](https://tanvrit.com).

All SDK modules: [`core`](https://github.com/tanvrit/core) · [`storage`](https://github.com/tanvrit/storage) · [`auth`](https://github.com/tanvrit/auth) · [`business`](https://github.com/tanvrit/business) · [`commerce`](https://github.com/tanvrit/commerce) · [`communication`](https://github.com/tanvrit/communication) · [`social`](https://github.com/tanvrit/social) · [`ui`](https://github.com/tanvrit/ui) · [`commerceui`](https://github.com/tanvrit/commerceui) · [`commerceapp`](https://github.com/tanvrit/commerceapp)
