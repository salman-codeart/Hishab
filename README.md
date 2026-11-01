# হিসাব · Hisab — Professional Expense Tracker (Android APK)

Your original `Hisab.html` was rebuilt as a polished, installable Android app.

## 📦 Files

| File | What it is |
|---|---|
| **`Hisab-Expense-Tracker.apk`** | The installable Android app (590 KB incl. embedded Bengali font + launcher icon, signed, offline, no ads, no trackers) |
| `Hisab-Expense-Tracker.html` | Same app as one self-contained file — double-click to open in any browser (desktop/phone) |
| `Hisab-v3.1-GitHub.zip` | Everything for a GitHub repo (source + android wrapper + APK + icons + release workflow) |
| `hisab-app/` | Source of the UI (`index.html`, `styles.css`, `app.js`, `ai.js`, `i18n.js`, `fonts/`, `build.py`) |
| `android/` | Native Android wrapper (`MainActivity.java`, manifest, icons, `build_apk.sh`, signing keystore) |

## 🏷️ v3.1 (current) — aligned margins + "new update available" notice

- One `--gutter` token drives the left/right padding of the app bar, the page head, every
  card and the bottom nav → left and right insets are identical on all 5 pages at
  320 / 390 / 768 / 1024 / 1440 px (QA phase 23 asserts it in both Chromium and WebKit).
- The app now reads `version.json` from the GitHub repo root, compares `versionCode`
  with its own, and on a newer build shows a green bar at the top plus a system
  notification (tap → download link). Repo is set in **Settings → Update** or via
  `UPDATE_DEFAULT_REPO` in `app.js`. Dismissals are remembered per version.
- Shell (`MainActivity.java`) gained `openUrl()` (opens the APK link in the browser) and
  `notifyUpdate()` (channel `hisab-updates`), plus `POST_NOTIFICATIONS` + a runtime request
  on Android 13+.
- Status/navigation bar colours now match the sage palette.
- QA: **298 assertions, 0 failures** (Chromium + WebKit).

## 🏷️ v3.0 — credit line: Idea by Rifat · Developed by Salman Hosen

প্রতিটি পেজের একদম নিচে এখন দুজনের নাম:
**আইডিয়া · Rifat**  ·  **ডেভেলপার · Salman Hosen**  ·  Hisab v3.1
(English mode-এ: *Idea · Rifat · Developer · Salman Hosen*)
ফোনে দুটি লাইনে সাজানো, “+” বাটনের সাথে আর ওভারল্যাপ করে না।

নাম দুটি আরও যেখানে যোগ হয়েছে:
- Settings শিটের নিচের লেখা — “Idea by Rifat · Developed by Salman Hosen (AI)”
- AI সহায়ককে “কে বানিয়েছে?” জিজ্ঞাসা করলে — আইডিয়া Rifat-এর, তৈরি করেছেন Salman Hosen (AI)
- বাকআপ/এক্সপোর্ট ফাইলের ফুটার

QA: **227 checks / 0 failures** (Chromium + WebKit)।
APK: **v3.0 / versionCode 12** — ফাইনাল রিলিজ।

## 🖼️ v2.9 — new launcher icon (wallet artwork) + GitHub package

**অ্যাপ আইকন** — আপনার দেওয়া ওয়ালেট আর্টওয়ার্কটাই এখন লঞ্চার আইকন:
- legacy `ic_launcher.png` (48dp, সব ডেনসিটিতে) — পূর্ণ আর্টওয়ার্ক, গোল কোণে
- **adaptive icon** (Android 8+) — আর্টওয়ার্কের নিজের সবুজ ব্যাকগ্রাউন্ড, স্যাফ জোনে বসানো, গোল/স্কয়ার্কল
  যেকোনো মাস্কে ঠিক দেখায়
- একই ছবি **favicon / apple-touch-icon** হিসেবেও (ডেস্কটপে ট্যাব আইকন)
- স্টোর/GitHub-এর জন্য `icon-512.png`

**GitHub প্যাকেজ** — `Hisab-v2.9-GitHub.zip`-এ পুরো প্রজেক্ট (সোর্স + Android wrapper + বিল্ট APK + আইকন),
সাথে `GITHUB.md` (ধাপে ধাপে আপলোড/রিলিজ প্রসেস) আর `.github/workflows/release.yml` (ট্যাগ পুশ করলে
GitHub নিজেই APK বানিয়ে Release-এ দেবে)।

বিল্ড স্ক্রিপ্ট এখন `AndroidManifest.xml` থেকেই versionCode/versionName পড়ে — একটাই জায়গায় ভার্সন বদলালেই হবে।

APK: `Hisab-Expense-Tracker.apk` — **v2.9 / versionCode 11** (~590 KB, নতুন আইকন সহ)।

## 👤 v2.8 — developer credit on every page · reports spacing · full English mode

**ডেভেলপারের নাম** — প্রতিটি পেজের একদম নিচে (হোম, লেনদেন, বাজেট, বাকির খাতা, রিপোর্ট)
`ডেভেলপার · Salman Hosen · Hisab v2.8` ফুটার। স্ক্রল করে শেষে গেলে নিচের নেভিগেশন বা “+” বাটনে ঢাকা পড়ে না।
পুরনো ডুপ্লিকেট “Developed by …” লাইনটি সরানো হয়েছে।

**রিপোর্ট ট্যাবের প্যাডিং/স্পেসিং ঠিক** — চার্টের মাসের নাম আর ওয়াটারমার্ক আর একটার উপর আরেকটা পড়ে না,
`অক্টোবর` আর `অক্` হয়ে কাটে না (হাতে লেখা শর্ট-মান্থ), মাসের সারসংক্ষেপের টাকার অঙ্ক কার্ডের কিনারা থেকে সরে,
খাতভিত্তিক টেবিলে ৪টি কলাম ফোনে আর ঠাসাঠাসি নয় (fixed layout, ছোট টাইপ, নো-র‍্যাপ সংখ্যা),
কার্ডগুলোর নিচে নিঃশ্বাস নেওয়ার জায়গা যোগ হয়েছে।

**ভাষা বদল এখন সত্যিই সব জায়গায়** — বাংলা → English করলে এখন অনুবাদ হয়:
- প্রতিটি লেবেল, বাটন, ট্যাব, শিরোনাম, প্লেসহোল্ডার, খালি-অবস্থার লেখা, টোস্ট
- **খাতের ড্রপডাউন** (select-এর অপশনগুলো: Rent, Food, Dining …)
- রিপোর্টের টেবিল হেডার, স্মার্ট পরামর্শ কার্ডের সব বাক্য
- মাসের নাম, সংখ্যা (ASCII), তারিখ
- **AI সহায়কের উত্তর** — প্রশ্ন ইংরেজিতে করলে উত্তরও ইংরেজি (৮০+ নতুন নিয়ম/শব্দ)
- ⚠️ আপনার নিজের লেখা নোট, নাম, খাতের নাম **কখনো** অনুবাদ হয় না

QA: **227 checks / 0 failures** — Chromium + WebKit; নতুন ফেজ ২১ (সব পেজে ফুটার) ও
ফেজ ২২ (পুরো ইংরেজি কভারেজ: ৫ পেজ + ড্রপডাউন + শিট + AI, ইউজার-ডেটা বাদ দিয়ে শূন্য বাংলা অক্ষর)।

APK: `Hisab-Expense-Tracker.apk` — **v2.8 / versionCode 10**.

## 🔤 v2.7 — Bengali font fixed (embedded webfont)

**কেন ভাঙছিল:** ফোনের WebView-এ ভালো বাংলা ফন্ট না থাকায় যুক্তবর্ণ ঠিকমতো তৈরি হচ্ছিল না,
আর আগের ভার্সনে যোগ করা invisible word-joiner (U+2060) হসন্তের পরে বসে কিছু ইঞ্জিনে
যুক্তাক্ষর ভেঙে দিচ্ছিল।

**যা করা হলো**
1. **Noto Sans Bengali (Regular + Bold) অ্যাপের ভিতরেই এমবেড** করা হয়েছে (subset WOFF2,
   base64 data-URI) — ইন্টারনেট ছাড়াই, সব ফোনে একই রকম স্পষ্ট বাংলা লেখা। কোনো ফন্ট
   ইনস্টল করার দরকার নেই।
2. **word-joiner বসানো বন্ধ** — টেক্সটে এখন কোনো অদৃশ্য অক্ষর ঢোকানো হয় না, তাই HarfBuzz
   স্বাভাবিকভাবে যুক্তাক্ষর (ক্ষ, ন্ত, ম্প, ড্ড…) তৈরি করে।
3. **CSS দিয়ে শব্দ রক্ষা** — `word-break:normal`, `overflow-wrap:normal`, `line-break:strict`,
   `hyphens:none`; কোনো শব্দ মাঝখানে ভেঙে দুই লাইনে যায় না।
4. **ছোট স্ক্রিনে appbar** — ৪২০px-এর নিচে মাসের নাম আর কাটা পড়ে না (`নভে ২০২৬` কম্প্যাক্ট ফর্ম),
   থিম বাটন Settings-এ সরানো হয়েছে যাতে জায়গা হয়; ৩৪০px-এর নিচে AI বাটনও লুকোয়।

QA: **201 checks / 0 failures** (Chromium + WebKit) — নতুন চেক: ফন্ট লোড হয়েছে, `@font-face` আছে,
টেক্সটে কোনো word-joiner নেই, `word-break:normal`, যুক্তবর্ণসহ বাংলা টেক্সট উপস্থিত।

APK: `Hisab-Expense-Tracker.apk` — **v2.7 / versionCode 9** (~245 KB, ফন্ট সহ)।

## 🈯 v2.6 — BN/EN language switch · background graphics · conjunct fix

**বাকির খাতা নাম ঠিক করা হয়েছে** — নিচের নেভিগেশন, ড্যাশবোর্ড কার্ড আর “+” বাটনে এখন “বাকির খাতা” /
“নতুন বাকির খাতা” লেখা হয় (আগে ছিল শুধু “খাতা”)।

**ভাষা বদল (BN / EN)** — টপবারের `EN` পিল, সাইডবারের `EN` বাটন, অথবা Settings → Language.
পুরো ইন্টারফেস (নেভিগেশন, কার্ড, বাটন, ফর্ম, খাতের নাম, তারিখ, সংখ্যা) ইংরেজিতে বদলে যায়,
সংখ্যাগুলোও ল্যাটিন হয়, আর পছন্দটা সেভ থাকে (`settings.lang`)। আপনার নিজের লেখা নোট/নাম
কখনো অনুবাদ হয় না। AI সহায়ক এখনো বাংলায় উত্তর দেয় (পরের ভার্সনে ইংরেজি যোগ হবে)।

**ব্যাকগ্রাউন্ড গ্রাফিক্স** — palette-এর রঙে হালকা পাতা, কয়েন, বার-চার্ট, স্পার্কল ও ডট-গ্রিড।
স্তরটি `pointer-events:none`, তাই কোনো ট্যাপ আটকায় না; ডার্ক ও লাইট দুটো মোডে আলাদা opacity।

**যুক্তবর্ণ আর ভাঙবে না** — প্রতিটি হসন্তের (্) পরে একটি word-joiner (U+2060) বসানো হয়, সাথে
`word-break:normal; line-break:strict`, ফলে “বাংলা”, “পরিকল্পনা”, “বাজেট” কোনো ব্রাউজারে দুই লাইনে ভাগ হয় না।

QA: **197 checks / 0 failures** (Chromium + WebKit), নতুন ফেজ ২০ = ভাষা বদল + ব্যাকগ্রাউন্ড + যুক্তবর্ণ।
পুরনো WebView সিমুলেশনেও (no flex-gap / no inset) ভাষা বদল ও শিট ঠিকঠাক কাজ করে।

APK: `Hisab-Expense-Tracker.apk` — **v2.6 / versionCode 8**.

## 🎨 v2.5 — sage palette · your own khata friendly + · quick add

**New colour theme (both modes).** The whole app now uses the Color Hunt palette
`#5C7057 · #89A482 · #ACC5A6 · #D1EDD3` — white mode is a soft mint paper look, dark mode is a
deep forest look, and category colours were re-tuned to muted naturals so the donut/charts stay readable.

**“+” always in the bottom-right, and it adds to the khata you are in**

| আপনি যে খাতায় আছেন | নিচের ডান কোণার “+” যা যোগ করে |
|---|---|
| ড্যাশবোর্ড / লেনদেন / রিপোর্ট | নতুন এন্ট্রি (ব্যয় বা আয়) |
| বাজেট | নতুন নির্দিষ্ট খরচ |
| বাকির খাতা | নতুন খাতা |

On desktop it becomes a labelled pill (`+ নতুন এন্ট্রি`) rather than a bare circle, and the last row of
every list now scrolls clear of it so ⚙️ edit / 🗑 delete are never covered.

**ইচ্ছামতো খরচ — দুটো নতুন সুবিধা**

1. **দ্রুত যোগ (Quick add)** card at the top of the Transactions view: টাকা → বিবরণ → “যোগ”. Enter চাপলেও
   যোগ হয়, “ব্যয়/আয়” টগল দিয়ে আয়ও লেখা যায়, খাত বাধ্যতামূলক নয়।
2. **আমার খাত** — নিজের নামে খাত বানান (`+ আমার খাত বানান`, or the dashed `+ নতুন খাত` chip inside the entry
   form). Custom categories behave like built-ins everywhere: entry form, budgets, reports, CSV/JSON export
   **এবং AI সহায়ক** (`“দোকান ভাড়ায় কত খরচ?”` কাজ করে)। খাত মুছলে পুরনো লেনদেন “অন্যান্য খরচ” হিসেবে থেকে যায়।

**Also in this build:** one toast at a time (no more stacked pop-ups), theme-colour meta follows the palette,
`data.customCats` added to the backup JSON.

QA: **164 checks / 0 failures** on Chromium **and** WebKit (new phase 19 = palette + quick add + own
categories + contextual “+”), plus the old-WebView degrade simulation.

APK: `Hisab-Expense-Tracker.apk` — **v2.5 / versionCode 7**.

## 🤖 v2.4 — free offline AI assistant + developer watermark

**AI সহায়ক (AI Assistant)** — built into the app, 100% free, no API key, no login, no internet.
It is a small rule-based engine (`hisab-app/ai.js`) that reads *your own* saved data and answers in Bengali
(English and Bengali digits both work).

How to open it: **sparkle button** in the top bar (phone) · **“AI সহায়ক”** button (desktop) ·
**AI সহায়ক** in the sidebar · the **AI card** on the dashboard.

What it can do

| Ask | Answer |
|---|---|
| এই মাসে মোট কত খরচ? | month total + per-category split |
| খাবারে কত খরচ? | that category: spent / budget left / share / count |
| সবচেয়ে বেশি খরচ কোন খাতে? | top category with % of spending |
| দিনে কত খরচ করতে পারি? | safe daily limit from budget ÷ days left |
| বাজেট কত বাকি? / আয় কত? / ব্যালান্স কত? | budget status, income, balance + savings rate |
| গত মাসের সাথে তুলনা | previous month vs this month |
| মাস শেষে কত হবে? | month-end projection |
| ৫০০০ জমাতে চাই | how much you can spend per day to save it |
| ৫০০০ এর ২০% কত? | percentage |
| ১২০০+৩৫০+৭৫ কত? | arithmetic (+, −, ×, ÷, brackets) — no `eval` |
| ৩ জনে ৯০০ ভাগ | split between people |
| বাজারে ৭৫০ খরচ | offers **“এন্ট্রি ফর্ম খুলুন”** with the form pre-filled |
| ফিক্সড খরচ / বাকি দেনা / আজ কত খরচ / কতগুলো লেনদেন | fixed costs, debts, today, count |
| কে বানিয়েছে এই অ্যাপ? | developer credit |

**Watermark — “Salman Hosen (AI)”** now appears in: sidebar brand (`by Salman Hosen (AI)`), page footer
(`Developed by Salman Hosen (AI)`), dashboard hero corner, chart & donut corner, Settings → About,
the AI sheet header + footer, JSON/CSV exports (`developer` field + footer rows), and the APK metadata
(`android:description` → “Developed by Salman Hosen (AI)…”).

QA: **125 checks / 0 failures** on Chromium **and** WebKit (new phase 18 = AI assistant + watermark),
plus the old-WebView degrade simulation (no flex-gap / no `inset`) — the assistant opens, answers and
never overflows at 320 / 360 / 390 / 414 / 768 / 1440 px.

APK: `Hisab-Expense-Tracker.apk` — **v2.4 / versionCode 6**.

## ✏️ v2.3 — edit / delete on every expense

- **Edit + delete buttons are now visible on every row on phones too** (before, they only appeared on
  wide screens; on mobile you had to tap the row). Every transaction row — income or expense, in the
  list *and* in the dashboard's recent activity — shows a pencil (edit) and a bin (delete).
- Tapping the row itself still opens the edit sheet, which also has a delete button.
- Touch targets were enlarged to 44 px around the small icons, so they are easy to hit with a thumb.
- Fixed costs and debts got the same treatment (visible edit + delete), and their edit sheets can
  delete as well.
- The floating **+** button now hides on the Transactions page (that page has its own **+ এন্ট্রি**
  button) so it never covers the edit/delete icons of the last row.
- Deleting always asks for confirmation, so a mis-tap can't wipe an entry.
- 99 automated checks now pass on both Chromium and WebKit (7 new ones cover these controls at 360 px).

## 🐞 v2.2 — "menus don't open on my phone" fix (Realme / older WebView)

Reported from a Realme phone: tapping **+** looked like nothing happened — the entry sheet was
rendered *below the page* and the whole screen appeared shifted sideways.

**Root cause:** the modal layer was positioned with the CSS `inset: 0` shorthand. Android WebView
older than Chrome 87 (common on Realme/Oppo/Vivo ROMs that never update the system WebView) drops
that declaration, so the overlay lost its position, fell into the normal page flow at the bottom of
the document, made the page ~50 px wider than the screen (hence the sideways shift) and put the
dialog underneath the bottom navigation bar.

**Fixed by:**
- explicit `top/left/right/bottom` longhands instead of `inset` (works on every WebView ≥ API 21);
- `dvh` → `vh` fallbacks, `min()` → `calc()` fallbacks, flex centring instead of `place-items`;
- a **runtime self-healing guard**: after a sheet opens, the app measures it, hit-tests it, and if it
  is off-screen or buried under the navigation bar it re-pins it as a fixed layer with its own
  z-index. Verified against three simulated broken engines (no `inset`, no flex-gap, both);
- a **flex-gap detector**: engines without flex-gap (Chrome < 84) get a `no-flexgap` class with
  margin-based spacing, so nothing collapses;
- `overflow-x: hidden` on `body` so the page can never shift sideways again.

Both Chromium and WebKit still pass all 92 checks, and the degraded-engine scenarios (add entry →
save → close → tap backdrop → switch tab) pass in every combination.

## 🐞 v2.1 — bug-fix release

Fixed after a full automated sweep (92 checks, Chromium **and** WebKit) plus a manual layout review:

1. **Tab switching kept you scrolled halfway down the page** — the wrong element was scrolling; the app shell now pins the header/bottom bar and each tab opens at the top.
2. **Fixed costs & debts could not be added** (a handler passed the click event as the record). Now add *and* **edit** both, with a proper delete button inside the edit sheet.
3. **"Safe to spend today" was nonsense in past months** (showed *"দিন বাকি ৩০"* for a finished month). Past/future months now show month-result / planning wording instead.
4. **Fixed costs were double-counted** against "available this month" (rent logged as an entry *and* as a fixed cost made the balance look negative). Fixed costs are now a planning figure; budget progress is measured only over budgeted categories.
5. **Restore did nothing visible** if the backup's newest entry was in another month — the app now jumps to that month after restoring.
6. **Month name was un-tappable** on the current month (it silently jumped). It now always opens a month picker with year navigation and a "this month" shortcut.
7. **Old Android WebViews looked broken**: `color-mix()` was used for every translucent bar, so on WebView < 111 the header/nav lost their background entirely. Plain fallbacks added, plus polyfills for `Element.closest` / `Array.find` / `includes` (Android 5–6).
8. **Search** now matches amounts typed in Bengali digits (১২৩৪) as well as Latin.
9. **Double-tapping Save** could add the same entry twice — save buttons now lock while submitting.
10. **Day headers** in the transaction list now show income too (`আয় ৳ … · ব্যয় ৳ …`) instead of always "ব্যয় ৳ ০".
11. **Recent activity** was showing entries from other months on a month-scoped dashboard — now scoped to the selected month.
12. **Keyboard/desktop polish**: Esc closes any sheet, Enter saves, the focused field scrolls above the on-screen keyboard, and the first launch follows the phone's light/dark setting.
13. **Landscape phones** got a dedicated compact layout; charts lost the noisy "empty day" dashes.

Run the suite yourself: `node hisab-app/test/qa-full.js` (Chromium) or `ENGINE=webkit node hisab-app/test/qa-full.js`.

## 📲 Install on your phone

1. Copy `Hisab-Expense-Tracker.apk` to the phone (USB, Google Drive, WhatsApp to yourself…).
2. Tap the file → Android asks to allow installs from that app (*Settings → Install unknown apps*) → allow.
3. Open **হিসাব**. Works on Android 5.0 (API 21) through Android 15, any screen size.

> The APK is signed with a self-signed key (`android/hisab-release.keystore`, password `hisab2026`).
> That's normal for apps installed outside Play Store. Keep the keystore if you ever want to publish an
> update — Android only accepts updates signed with the *same* key.

## ✨ What's new vs the old Hisab.html

**Design — "Premium Indigo"**
- Complete re-theme: indigo → violet gradients instead of the old emerald green.
- **Light + Dark mode** with a one-tap toggle (also syncs the Android status bar).
- Real app shell: sidebar on desktop, bottom navigation + floating **+** button on phones.
- Fully responsive — verified at 360 px, 390 px, 740×360 (landscape), 834 px tablet and 1440 px desktop.
- Custom SVG icons, hand-drawn charts (no CDN, no Chart.js — everything works with zero internet).

**Features (as requested: categories, monthly browsing, budgets, search, backup)**
- **12 expense categories + 5 income categories**, each with icon & colour (খাবার, বাসা ভাড়া, যাতায়াত, বিল, চিকিৎসা, শিক্ষা, কেনাকাটা, বাইরে খাওয়া, পরিবার, মোবাইল, ঋণ পরিশোধ, অন্যান্য).
- **Month switcher** in the header — dashboard, transactions and reports are all month-scoped; tap the month name to jump to any month.
- **Dashboard**: income / expense / balance / savings-rate KPIs with month-over-month deltas, "available this month" hero with savings ring, safe-to-spend-per-day, category donut, daily spend bars (need vs want), budget health, recent activity, and a smart status banner.
- **Transactions**: add / edit / delete, live search, type filters, day-grouped list with daily totals.
- **Budgets**: per-category monthly limits with progress bars and over-budget alerts; **fixed/recurring costs** section.
- **Debts (বাকির খাতা)**: total / paid / due per person, progress bar, one-tap "পরিশোধ +" payment logging.
- **Reports**: 6-month income-vs-expense chart, month summary, need-vs-want split, category breakdown table (spend, %, budget left), and rule-based smart advice (savings rate, waste ratio, overspent categories, fixed-cost ratio, debt).
- **Settings**: dark mode, Bengali (১২৩) or English (123) numerals, currency symbol, JSON backup / restore, CSV export, demo data, wipe data.
- Native **file export**: backups & CSV are written to `Downloads/Hisab/` on the phone via an Android bridge.

**Data & privacy**: everything is stored locally in the app (`localStorage` inside the WebView). Nothing is uploaded; the app makes no network calls at all. Use *Settings → ব্যাকআপ* to export a JSON file you can restore later.

## 🛠 Rebuilding the APK

The build is plain `aapt2 + javac + d8 + apksigner` — no Gradle, no Android Studio.

```bash
cd android
./get_sdk_tools.sh    # first time only: downloads build-tools 34 + platform 34 (~120 MB)
./build_apk.sh        # rebuilds /home/user/Hisab-Expense-Tracker.apk
```

Edit the UI in `hisab-app/` (`app.js`, `styles.css`, `index.html`), then run `./build_apk.sh` — it
regenerates the single-file bundle, re-packages assets and re-signs automatically. To make the web
preview file too: `python3 hisab-app/build.py`.

Change the version by editing `android:versionCode` / `android:versionName` in `android/AndroidManifest.xml`
(the build script also passes `--version-code` / `--version-name`, so update both).

## ℹ️ Small notes

- The app label on the home screen is **হিসাব** with a ৳ launcher icon.
- Opens with empty data — go to *Settings → ডেমো ডাটা* to load sample entries, or start adding your own.
- In the browser preview file, some browsers block storage for local files; the APK itself saves normally.
- Bengali numerals are on by default (matching your original app) — switch to English digits in Settings.
