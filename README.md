# Master Dry Cleaners — weekly sales dashboard

A live dashboard for the weekly 12-week average reports, built from **Average Weekly Sales - All Stores.xlsx**. It replaces the weekly email: every store, the All stores total, the 12-week report, both charts, key insights and services week to week, for any week you pick.

The repository only ever holds two things: `index.html` (the dashboard) and `data.json` (the figures, locked with a passcode). The Excel file never goes to GitHub.

---

## One-time setup (about 10 minutes)

1. **Create the repository.** On GitHub: **New repository** → name it (e.g. `sales-dashboard`) → Public → Create.
2. **Upload the files.** **Add file → Upload files** → drop in `index.html` and `README.md` → Commit.
3. **Turn on GitHub Pages.** **Settings → Pages** → Source: **Deploy from a branch** → Branch: **main**, folder **/ (root)** → Save. After a minute the page shows your link, e.g. `https://yourname.github.io/sales-dashboard/`.
4. **Make an access token** (lets the update page save the figures):
   profile picture → **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token** →
   Repository access: **Only select repositories** → this repository →
   Permissions → Repository permissions → **Contents: Read and write** → choose an expiry → Generate. Copy it.
5. **Publish the first week.** Open your link with `#update` on the end (e.g. `https://yourname.github.io/sales-dashboard/#update`), then:
   - drop in the workbook,
   - set a **passcode** (10+ characters — three or four words works well),
   - check the repository (it fills itself in) and paste the token,
   - click **Publish to dashboard**.
6. **Send David the link and the passcode** (separately is best). He types the passcode once per device.

Bookmark the `#update` link for yourself.

## Every week (2 minutes)

1. Add the new week’s row to each store tab as usual, and the Services rows (below).
2. Open your `#update` bookmark and drop in the workbook.
3. Read the summary. Anything under **Worth a look** is a likely typo in the workbook (a date that doesn’t follow on, a store missing its row, and so on). The dashboard behind the panel shows a preview, so you can check it before it goes live.
4. Click **Publish to dashboard**. It’s live on David’s link within a minute or two — the panel says **Live ✓** when it is.

If a store tab is behind the others, All stores reports on the latest week **every** tab has filled in, so publish once they’re all in.

## The Services tab

The workbook now has a **Services** tab. Each week, add one row per store below the last row:

| Week ending | Store | Dry cleaning | Shirts | Wash & fold | Alterations & repairs | Household | Gowns & leather | Other |
|---|---|---|---|---|---|---|---|---|
| 11.01.26 | Albert Park | dollar amounts from the POS service report … |

- Type the week ending the same way as the store tabs (MM.DD.YY).
- Pick the store from the drop-down so it matches the store tab. **DRYZ** has its own row if you can split it out of Butler.
- Leave a cell blank if there was nothing for that service that week.
- Rename, add or remove service columns whenever you like — the dashboard follows the headings. (A column headed “Total” or “Notes” is ignored.)
- Back-filling a few past weeks from the POS gives the services charts history straight away.

## Passcode

- **Change it:** publish with a new passcode. Anyone who had the old one is asked for the new one next time.
- **Forgotten it:** just publish again with a new one — nothing is lost, the figures come from the workbook each week.
- On a shared computer, use **Forget the passcode on this device** at the bottom of the dashboard.
- GitHub Pages links are public, so the passcode is what keeps the figures private. `data.json` in the repository is unreadable without it.

## How the numbers work

- **12-week average** = average of the last 12 weeks of sales (the workbook’s “Avg - 3 Months” column). Green ▲ / red ▼ means it went up / down on the week before, the same as the workbook’s colouring.
- **Last year** = the same week 52 weeks earlier, taken straight from each store’s own rows (so any typos in the workbook’s “2024 Sales” column don’t carry through).
- **Changes** are measured against the earlier figure (last week or last year), the same as the weekly emails. The workbook’s own % columns divide by this year’s figure instead, so they read slightly differently (Butler, 25 Oct 2026: 5.8% in the workbook, +6.2% here).
- **Butler** is shown excluding DRYZ (the “Butler DRYZ” tab), **DRYZ** is the difference between the Butler and Butler DRYZ tabs, and **All stores** includes both. Wages columns aren’t used or published.

## Good to know

- **New store?** Add a tab laid out like the others (a “week ending” heading with Sales and Discounts beside it) and it appears automatically.
- **Store closed?** Hide its tab.
- **No token, or prefer to do it by hand?** Use **Download data file** in the update panel, then in GitHub **Add file → Upload files** and replace `data.json`.
- **Preview on your own computer:** open `index.html` straight from your folder and drop the workbook on it. Nothing is sent anywhere.

## Troubleshooting

| Message | Fix |
|---|---|
| GitHub didn’t accept the token | It’s expired or wasn’t pasted in full — make a new one (step 4). |
| The token isn’t allowed to change this repository | Give the token **Contents: Read and write** on this repository. |
| GitHub can’t find that repository | Check the owner/repository name, and that the token was given access to it. |
| That passcode didn’t work | It’s been changed since this device last opened the dashboard — use the current one. |
| No figures published yet | Nothing has been published from the update page yet. |
