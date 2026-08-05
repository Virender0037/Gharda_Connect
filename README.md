# Gharda Connect — employee platform

Static frontend for the Gharda Connect intranet prototype, deployed on Zoho Catalyst Slate.

`index.html` is a single self-contained file: all styles, scripts, fonts and assets are inlined,
so it needs no build step and works offline.

## Deploying

This repository is connected to Slate. Pushing to `main` triggers an automatic deploy.

- Project: `gharda-intranet`
- Service: Catalyst Slate
- Build command: none
- Output directory: repository root
- Entry file: `index.html`

Pull requests get their own preview URL. To roll back, redeploy an earlier commit from the
Slate console.

## Updating

`index.html` is generated from the design source — do not edit it by hand, because the next
export overwrites it. The update cycle is:

1. Make the change in the design project.
2. Export a fresh standalone HTML file.
3. Replace `index.html` here and commit.

```bash
git add index.html
git commit -m "Update Gharda Connect build"
git push
```

## Current state

Front-end prototype. All data is in-memory, so sign-in accepts any credentials and changes
reset on reload.

Screens: Home, Announcements, Department hubs (HR, Finance, EHS, IT, Supply Chain, CSR),
Community, Documents, Conversations, Leader's Desk, Knowledge Centre, Quick links, plus
admin views for the approval queue, users and roles, and analytics.

## Wiring up real data

When this moves past prototype, the natural Catalyst mapping is:

| Need | Catalyst service |
|------|------------------|
| APIs | Advanced I/O Functions |
| Announcements, documents, users, posts | Data Store (queried with ZCQL) |
| File and image uploads | Stratus |
| Sign-in and roles | Catalyst Authentication |
| Spine HR / SAP / Ariba integration | Signals |
| Scheduled digests and reminders | Job Scheduling |
