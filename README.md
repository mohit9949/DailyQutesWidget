# Daily Quotes Widget

A minimal Android app with a home-screen widget that shows one saying each
morning, and a screen where you paste in your own list of 50.

## Why the defaults are placeholders

I couldn't pre-load the actual lines from H. Jackson Brown Jr.'s
*Life's Little Instruction Book* — that text is copyrighted, and shipping
someone else's full curated list inside an app crosses a line even for
personal use. The app ships with 50 original placeholder sayings so it
works immediately. Open the app, select all the text in the box, and
paste in your own 50 (one per line), then tap **Save quotes**.

## What it does

- Home screen widget shows one saying, changes automatically once a day.
- Tap the widget any time to cycle to the next saying (e.g. after work,
  to get a second dose).
- In-app editor to view/replace/reset your list, no re-installing needed.
- Everything is stored locally on-device (SharedPreferences) — no
  network, no account.

## How to build it

You'll need [Android Studio](https://developer.android.com/studio)
(free). This project doesn't include the Gradle wrapper files, so:

1. Unzip this project.
2. Open Android Studio → **Open** → select the `DailyQuotes` folder.
3. Android Studio will detect it's missing the wrapper and offer to
   generate one automatically — accept that, or go to
   **File → Sync Project with Gradle Files**.
4. Once synced, click **Run ▶** with your phone connected (USB
   debugging on) or an emulator selected.
5. On your phone: long-press the home screen → **Widgets** →
   **Daily Quotes** → drag the "Morning Quote" widget onto your home
   screen.
6. Open the app once to paste in your real list of sayings.

## Files of note

- `QuoteStore.kt` — where quotes are stored and how "today's" quote is
  picked (rotates by day-of-year, so it's stable all day and changes at
  midnight).
- `QuoteWidgetProvider.kt` — the widget itself; handles tap-to-cycle.
- `MainActivity.kt` + `activity_main.xml` — the editor screen.
- `strings.xml` → `default_quotes` array — replace this list, or just use
  the in-app editor (simpler, no rebuild needed).
