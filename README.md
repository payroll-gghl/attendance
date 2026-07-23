# GGHL Attendance Console — hosted version

This folder is a ready-to-publish website. Once it's on GitHub Pages, the app
**automatically loads `Attendance_Report_GGHL.xlsx` from the same folder every time
it opens.** To push an update to everyone, you replace that one Excel file. Nothing
else changes.

## What's in here
- `index.html` — the app (loads the Excel file next to it on open)
- `Attendance_Report_GGHL.xlsx` — the live data file (this is the one you replace)
- `.nojekyll` — tells GitHub Pages to serve files as-is (leave it alone)

---

## One-time setup (about 5 minutes, no coding)

1. Go to https://github.com and sign in (create a free account if needed).
2. Click **+** (top right) → **New repository**.
   - Repository name: `gghl-attendance` (any name is fine)
   - Set it to **Public** (Pages needs this on free plans)
   - Do NOT add a README — click **Create repository**.
3. On the new repo page, click **uploading an existing file** (or **Add file → Upload files**).
4. Drag in all three items from this folder: `index.html`,
   `Attendance_Report_GGHL.xlsx`, and `.nojekyll`. Click **Commit changes**.
5. Go to **Settings → Pages** (left menu).
   - Under **Source**, choose **Deploy from a branch**.
   - Branch: **main**, folder: **/ (root)**. Click **Save**.
6. Wait about a minute, then refresh. Pages shows your live link, like:
   `https://<your-username>.github.io/gghl-attendance/`

That link is your app. Share it with anyone. On iPhone/iPad they open it in Safari
→ **Share → Add to Home Screen**. On Windows they open it in Edge/Chrome and click
**Install** in the address bar.

---

## To update the data (do this whenever attendance changes)

1. Export the latest report from SAP as `Attendance_Report_GGHL.xlsx`
   (same columns as now: SAP Id, Name, Company, Date, Day, Time In, Time Out,
   Hours Worked, Duty Hours, OT Hours, Remarks).
2. In your GitHub repo, click **Add file → Upload files**.
3. Drag in the new `Attendance_Report_GGHL.xlsx` (keep the exact same name).
4. Click **Commit changes**.

That's it. Next time anyone opens the app it pulls the new file automatically.
They can also tap **Update data → Reload from shared link** to refresh on the spot.

> Keep the filename exactly `Attendance_Report_GGHL.xlsx` — the app looks for that name.

---

## Notes

- The app already shows data the instant it opens (a built-in copy), then quietly
  refreshes from the Excel file in the repo. So it's never blank, even offline.
- Times, dates, hours and OT are read straight from Excel's own cell values, so
  formatting in the sheet doesn't matter.
- If you ever want to stop the auto-refresh, open **Update data** in the app and
  untick "Refresh from this link every time the app opens".
- A private SharePoint/OneDrive link can't be used here — browsers block reading
  those from another site. GitHub serves the file from the same address as the app,
  which is why the auto-refresh works.
