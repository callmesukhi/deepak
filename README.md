# BoardReady English — Classes IX to XII

A single-file CBSE English revision app: chapter notes, quiz drills and progress tracking for Classes 9, 10, 11 and 12, served straight from `index.html`.

Live at **[deepak.mellaven.app](https://deepak.mellaven.app)**.

## What's inside

| Class | Books | Chapters | Quiz questions |
|---|---|---|---|
| IX | Beehive + Moments | 31 | 83 |
| X | First Flight + Footprints Without Feet | 32 | 80 |
| XI | Hornbill + Snapshots | 21 | 53 |
| XII | Flamingo + Vistas | 21 | 42 |

Every chapter carries a one-line theme, a short summary, 6–8 study notes, a six-step story arc or poem flow, key terms, core quotes and a line-art doodle. Quizzes shuffle their options on every attempt and review each miss afterwards.

## Class passwords

Students land on a class picker and unlock their own class with a password their teacher shares. A Class 9 student can't wander into the Class 10 notes, and each class keeps its own separate progress.

| Class | Password |
|---|---|
| IX | `peacock9` |
| X | `falcon10` |
| XI | `sparrow11` |
| XII | `eagle12` |

Passwords are stored as SHA-256 hashes rather than plain text, and an unlocked class is remembered on that device. This keeps classes tidily separated between students; it is not a security boundary, since anything shipped to a browser can be read by a determined student.

To change a password, open the site, open the browser console and run:

```js
BR.hash("c10", "new password here")
```

Paste the resulting hash into the matching `passHash` field in the `CLASSES` object in `index.html`.

## Progress

Progress saves automatically in the browser, separately per class. The Progress tab can export it to a file or a backup code and import it on another phone, laptop or browser. Nothing is sent anywhere — there is no server and no account.

## Running it

No build step, no dependencies. Open `index.html` directly, or serve the folder:

```sh
python3 -m http.server 8000
```

Deployment is GitHub Pages from the repository root. On a phone: open the site, tap Share, then Add to Home Screen for a full-screen app that works offline.

## Editing content

Chapter and quiz data lives in `index.html` as `C9_CHAPTERS` / `C9_QUIZ` through `C12_CHAPTERS` / `C12_QUIZ`. A quiz question attaches to a chapter by matching its `chapter` field to that chapter's `title` exactly, and a chapter is filed under Poetry when its `type` is `"Poetry"`.
