# Peliyagoda Operations Dashboard

A browser-based operations dashboard for Access Engineering's Peliyagoda concrete plant. It tracks daily production plans, delivery actuals, plan-versus-actual variance, delays, and operational records.

## Requirements

- Node.js 24 or newer
- Corepack-enabled pnpm

## Run Locally

From the repository root:

```powershell
corepack pnpm install
npm run dev
```

Open [http://localhost:5173](http://localhost:5173).

The development server uses port `5173` by default. To use another port in PowerShell:

```powershell
$env:PORT=5174
npm run dev
```

## Available Commands

```powershell
npm run dev
corepack pnpm --filter @workspace/peliyagoda-dashboard typecheck
corepack pnpm --filter @workspace/peliyagoda-dashboard build
```

The production build is written to `artifacts/peliyagoda-dashboard/dist/public`.

## Features

- Daily production plan creation, editing, duplication, and deletion
- Delivery actual capture with timing and volume variance calculations
- Plan-versus-actual comparison views
- Delay reason and project performance analysis
- CSV export/import and JSON backup/restore
- Browser-local record storage for the local dashboard

## Project Layout

- `artifacts/peliyagoda-dashboard`: Main dashboard application
- `artifacts/mockup-sandbox`: UI mockup sandbox
- `api-server`: API service workspace
- `lib`: Shared API, database, and schema packages

## Data

Dashboard records are stored in the browser's local storage. Use the Records page to export a CSV or JSON backup before clearing browser data.
