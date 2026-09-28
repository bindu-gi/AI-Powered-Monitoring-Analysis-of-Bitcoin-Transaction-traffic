# Bitcoin Forensics Dashboard — Frontend Skeleton

This is the empty folder/file structure for the React frontend, matching the
step-by-step build plan we agreed on. All files are currently blank stubs —
code will be filled in one step at a time.

## Flow this structure supports
Dashboard (CSV upload) -> Suspicious Wallets List -> click wallet ->
Wallet Detail (risk breakdown, graph, tx chart, CSV/PDF export) -> Alerts section

## Next steps (not done yet)
1. `npm create vite@latest . -- --template react` (or copy package.json deps in)
2. Install dependencies:
   ```
   npm install react-router-dom @tanstack/react-query @tanstack/react-table axios zustand recharts react-cytoscapejs cytoscape lucide-react clsx
   npm install -D tailwindcss postcss autoprefixer
   ```
3. Fill in tailwind.config.js / postcss.config.js / index.css (Tailwind setup)
4. Wire up src/App.jsx + src/main.jsx (routing skeleton)
5. Build layout (Sidebar/Topbar/AppLayout)
6. Build api/client.js + hooks (useUploadCsv, useWalletDetail, useWalletGraph, useAlerts)
7. Build Dashboard.jsx (CsvUploadZone + SuspiciousWalletsTable)
8. Build WalletDetail.jsx (RiskBreakdown, GraphCanvas, WalletTxChart, DownloadCsvButton)
9. Build Alerts.jsx / AlertDetail.jsx
10. Final polish + offline production build

## Folder map
```
src/
├── api/            -> axios client
├── hooks/           -> React Query hooks per data type
├── store/            -> zustand global state (uploaded wallets, filters)
├── components/
│   ├── layout/         -> Sidebar, Topbar, AppLayout
│   ├── common/           -> RiskBadge, LoadingSpinner, ErrorState, DownloadCsvButton
│   ├── dashboard/          -> CsvUploadZone, SuspiciousWalletsTable
│   ├── wallet/              -> RiskBreakdown, WalletTxChart
│   ├── alerts/               -> AlertsTable, FlagTags
│   ├── graph/                  -> GraphCanvas (Cytoscape)
│   └── charts/                  -> TrendChart (Recharts)
└── pages/
    ├── Dashboard.jsx    -> home: upload + suspicious wallet list
    ├── WalletDetail.jsx  -> per-wallet investigation view
    ├── Alerts.jsx          -> full alerts table
    └── AlertDetail.jsx      -> single alert explanation + graph
```
