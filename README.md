# Smart Attendance

Mark attendance easily — no confusion, no registers. A web app built for classrooms: the **CR** (class representative) marks attendance, and **students**, **teachers**, and **faculty** can view it live.

🌐 **Website:** https://sujithchalla12.github.io/smart-attendance
📱 **Android app:** [Latest APK build](https://github.com/SUJITHCHALLA12/smart-attendance/releases) — the site wrapped in a native app shell for customers who prefer an installable app.

## Features

- **Role-based login** — Student, CR, Teacher, Faculty (email + password via Firebase Auth)
- **One-tap attendance marking** — CRs mark a full day or period-wise in seconds
- **Realtime sync** — everyone sees updates instantly (Firebase Realtime Database)
- **Monthly calendar view** with day-wise breakdown
- **Student dashboard** — today's status, weekly and monthly summaries
- **Excuse / leave management** with approval flow
- **Printable reports** for records
- **Dark / light mode**

## Tech stack

- Vanilla HTML / CSS / JavaScript — the whole app is a single `index.html`
- Firebase: Authentication + Realtime Database
- Android wrapper: native WebView shell (`android/`) that loads the live site

## Android app

The `android/` directory holds a thin native wrapper — a full-screen `WebView` that loads the live website, so site updates reach customers instantly without reinstalling the APK. Push notifications from the web version don't fire inside the wrapper; everything else works as-is.

A GitHub Actions workflow (`.github/workflows/build-apk.yml`) builds a debug-signed APK on every push to `main` and publishes it to a rolling `latest` release.

## Run it locally

Just open `index.html` in a browser — or serve the folder:

```bash
npx serve .
```

The Firebase config is baked into `index.html`. To point the app at your own Firebase project, replace the `firebaseConfig` object in `index.html` and update the database rules accordingly.
