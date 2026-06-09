# 📋 GBN Tracker
**Guest Booking Network — Author Schedule Tracker**

A fully client-side, single-file web application for tracking and managing guest author bookings, schedules, and statuses across all GBN hosts. No backend, no database server, no installation required — just open `index.html` in any browser.

---

## 🌐 Live Demo
> _Add your live URL here after deploying_
> Example: `https://gbn-tracker.netlify.app`

---

## ✨ Features

| Feature | Description |
|---|---|
| 📊 **Stats Dashboard** | Live count of Total, Completed, Pending, Rescheduled, and Refunded entries |
| 🔍 **Search** | Real-time search across all fields (author, host, notes, dates) |
| 🔽 **Filters** | Filter by GBN Host, PR Status, Assignee, and Schedule Date |
| 📅 **Date Picker Filter** | Calendar icon to filter entries by any specific schedule date |
| ↕️ **Sortable Columns** | Click any column header to sort ascending/descending |
| ➕ **Add Entry** | Add new bookings via a modal form with calendar date picker |
| ✏️ **Edit Entry** | Edit any existing entry directly |
| 🗑️ **Delete Entry** | Delete entries with a confirmation prompt |
| 📤 **Export to Google Sheets** | Downloads CSV and opens a new Google Sheet for import |
| 🌙 **Dark Mode** | Toggle dark/light mode — preference saved across sessions |
| 📄 **Pagination** | 25 entries per page with smart page navigation |
| 💾 **Persistent Storage** | All data saved in browser localStorage |

---

## 🗂️ Data Structure

Each entry contains the following fields:

| Field | Description | Example |
|---|---|---|
| `dateAdded` | Date the booking was added | `04/10/2025` |
| `gbn` | GBN Host name | `Logan Crawford` |
| `guest` | Author / Guest name | `Dr. Anthony J. Emmett` |
| `schedDate` | Scheduled appearance date | `Wed Apr 23, 2025` |
| `time` | Scheduled time slot | `4:30pm - 5pm EST` |
| `prStatus` | PR Status | `COMPLETED` or `REFUNDED` |
| `status` | Assignee name | `Samantha Smith` |
| `notes` | Additional notes | `RESCHED`, `waiting for website` |

---

## 🎙️ GBN Hosts

These are the booking hosts shown in the **GBN Host** column:

- Logan Crawford
- Paul Ryden
- Zach Feldman
- Flobo Boyce
- Judith McKenzie
- Christine Blanchette

---

## 👤 Assignees

These are the team members shown in the **Assignee** column:

- Daisy Brown
- Emily Clark
- Helen Grace
- Joe Bays
- Liza Parker
- Lyle Quinn
- Mary Harper
- Monica Compton
- Rose Cecily
- Samantha Smith
- Vera Estelle
- Zach Shepard

---

## 📌 Status Legend

| Badge | Color | Meaning |
|---|---|---|
| **Completed** | 🟢 Green | Appearance confirmed and done |
| **Pending** | ⚪ Gray | Scheduled but not yet completed |
| **Rescheduled** | 🟡 Amber | Appearance moved to a new date |
| **Refunded** | 🔴 Red | Booking cancelled and refunded |

---

## 🚀 Deployment

### ✅ Option 1 — Netlify (Recommended, Free, 2 minutes)

1. Go to [netlify.com](https://netlify.com) and sign up for free
2. On the dashboard, find the **"Drag and drop your site folder here"** area
3. Drag and drop the `index.html` file
4. Your site is **instantly live** at a URL like `https://gbn-tracker.netlify.app`
5. Optional: connect a custom domain (e.g. `gbntracker.com`)

### ✅ Option 2 — GitHub Pages (Free)

1. Create a new repository on [github.com](https://github.com) named `gbn-tracker`
2. Upload `index.html` and `README.md` to the repository
3. Go to **Settings → Pages → Source → Deploy from branch → main**
4. Click **Save** — your site will be live at:
   ```
   https://yourusername.github.io/gbn-tracker
   ```

### ✅ Option 3 — Vercel (Free)

1. Go to [vercel.com](https://vercel.com) and sign up
2. Click **"Add New Project"** → import your GitHub repository
3. Vercel auto-detects it as a static site and deploys instantly
4. Auto-deploys on every GitHub push ✅

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **HTML5** | Page structure |
| **CSS3** | Styling, dark mode via CSS variables |
| **Vanilla JavaScript** | All logic — filtering, sorting, pagination, CRUD |
| **localStorage** | Client-side data persistence (no backend needed) |
| **Google Fonts** | Inter + DM Mono typography |

> ⚡ **Zero dependencies. Zero frameworks. Zero build tools.**
> The entire application is a single `index.html` file.

---

## 📁 Repository Structure

```
gbn-tracker/
│
├── index.html        ← Complete application (HTML + CSS + JS + Data)
└── README.md         ← This documentation file
```

---

## 💡 How localStorage Works

All entries are saved in your browser under the key `gbn_tracker_v7`:

```
Browser localStorage
└── "gbn_tracker_v7" → JSON array of 829+ entries
```

**Important notes:**
- ✅ Data persists after closing the browser
- ✅ Works completely offline
- ⚠️ Data is tied to **one browser on one device**
- ⚠️ Clearing browser data will reset entries to the original 829 seed entries
- 💡 Use **Export CSV** regularly to back up any new entries you add

---

## 📤 Exporting Data

Click the **Export CSV** button in the top right to:
1. Download a `.csv` file of the current filtered/sorted view
2. Automatically open a new **Google Sheet** (`sheets.new`)
3. In Google Sheets: **File → Import → Upload** → select the downloaded CSV

---

## 🌙 Dark Mode

Click the **moon icon** (🌙) in the top right to toggle dark mode.
- The sun icon (☀️) appears when dark mode is active
- Your preference is saved automatically in localStorage

---

## 📅 Date Filter

Click the **calendar icon** in the toolbar to filter entries by a specific schedule date.
- The icon turns **blue** when a date filter is active
- Click **Clear** to remove the date filter

---

## 🔧 Customization

### Adding a new GBN Host
In `index.html`, find the `<select id="f-gbn">` element and add:
```html
<option value="New Host Name">New Host Name</option>
```

### Adding a new Assignee
Find the `<select id="f-status">` element and add:
```html
<option value="New Assignee">New Assignee</option>
```
Also update the `allAssignees` array in the `populateFilters()` function.

---

## 📝 License

This project is for internal use by the **Guest Booking Network (GBN)** team.
All data and content © GBN. All rights reserved.

---

*Built for the GBN Team · Single-file · No backend · Works everywhere*
