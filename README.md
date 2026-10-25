# Workshop, Maintenance Request System

Workshop is a factory maintenance request system. Production logs a machine stop, maintenance handles the repair, and finished work feeds the dashboard.

## Features

- **Role-based access and permissions**
  - Production: opens work orders (WOs), views requests and WO details. Cannot start, finish or reject WOs, and has no access to Dashboard or Management.
  - Maintenance: opens WOs, starts repairs, finishes repairs with diagnosis, fix and parts, and rejects WOs. Has access to Requests and Dashboard.
  - Administrator: full access to Requests, Dashboard and Management. Can open, start, finish and reject WOs, manage machines, downtime reasons and users, and connect Firebase.
- **Work order lifecycle** with Open, In Progress, Finished and Rejected statuses; Corrective, Predictive and Preventive types; High, Medium and Low urgency; a non-quality flag; timestamps and wait, repair and total times.
- **Requests list** with search, status filters, live time counters and a Recent repairs panel.
- **One active WO per machine**: selecting a machine that already has an Open or In Progress WO blocks submission, shows a clear notice with a View action for the existing WO, and the rule is checked again when the form is submitted.
- **Clear all data** in local mode: asks for confirmation, deletes every WO, resets the sequence so the next WO is WO-0001, and keeps machines, reasons, users and settings.
- **Restore demo** in local mode: resets requests, machines, reasons and users to the initial demo state.
- **CSV export** of work orders with type, reason, urgency, status, timestamps, wait, repair, total times, description, diagnosis, fix and parts.
- **CSV catalog import** for machines and downtime reasons from pasted rows or a file, using type,name,id rows. Importing WOs is not supported.
- **Dashboard** with KPI cards, a reason Pareto with cumulative share, urgency distribution, maintenance type distribution, machines with most requests, a time by WO table and 7-day, 30-day and all-time period filters.
- **Firebase Realtime Database** connection from Management: validates and saves the database URL in the browser, reads and writes data, uses live updates with polling fallback, can send local data to Firebase and can disconnect.
- **Local persistence** in browser storage when Firebase is not connected.

## How to use

1. Open `index.html` in a browser. No build step is required.
2. Sign in with one of the demo accounts below.
3. Use Requests to open and handle WOs, Dashboard for metrics, and Management as an administrator for the catalog, data tools and Firebase connection.

## Demo

Live demo: https://maintenancews.netlify.app

Demo logins:

- production / production123
- maintenance / maintenance123
- admin / admin123

## Stack

- Plain HTML with embedded CSS and JavaScript
- Firebase Realtime Database
- Netlify

## License

MIT. See [LICENSE](LICENSE).
