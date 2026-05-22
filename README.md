I’m a cross-platform developer, and I’ve built an accountability system that does the following:

* Miss your habit → lose money or automatically send an embarrassing photo to your friends
* Walk into a location → distracting apps get blocked automatically
* Leave early → verification fails
* Try deleting the app mid-session → you can’t
* Lose internet → enforcement still continues offline
* Random check-ins verify you stayed the full session
* Commitments become immutable once a session starts

To build this system, I’ve worked with:

* A monolithic architecture organized inside a Turborepo monorepo
* React Native, Expo, TypeScript, Zustand, Reanimated, Expo SQLite
* Kotlin, Accessibility Services, AlarmManager, WakeLocks, WindowManager overlays
* Native Android app enumeration using PackageManager + QUERY_ALL_PACKAGES permissions
* High-accuracy foreground GPS enforcement using Google Fused Location Provider
* Convex, Node.js, SQLite, saga orchestration pipelines
* React, Vite, Tauri
* Bun, Turborepo, Google Maps API, Google Places API

→ Demo

→ [Architecture Docs](https://committ.mintlify.app)

→ [Documentation / Proof of Work](https://committ.mintlify.app/2025/december/day-05)
