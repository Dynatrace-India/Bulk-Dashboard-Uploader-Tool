# Dynatrace Bulk Dashboard Uploader Tool

This is a Python-based GUI tool that uploads multiple dashboard JSON files to a Dynatrace environment using the Dynatrace Configuration API. It allows users to specify the tenant URL, API token, and assign a new dashboard owner dynamically.

---

## Features

- Uploads multiple dashboards from a local folder (`dashboard_files`)
- Removes top-level `id` field from each dashboard JSON before upload
- Replaces the `dashboardMetadata.owner` field with user input
- GUI with fields for:
  - Dynatrace Tenant URL
  - API Token (hidden for security)
  - Dashboard Owner Username
- Live upload result logs in a scrollable GUI window
- Actions and results logged in:
  - `logs.txt` – Records user actions and inputs
  - `upload_log.txt` – Records success/failure for each dashboard
- Displays Dynatrace logo at the top of the GUI
- Clean footer with developer attribution

---

## Folder Structure

root/
│
├── DT-Bulk_Dashboard_Uploader.exe # Main Python GUI script
├── dashboard_files/ # Folder containing dashboard JSON files
│ ├── dashboard1.json
│ ├── dashboard2.json
│ └── ...
├── logs.txt # Action log file
└── upload_log.txt # Upload result log file


---

## Prerequisites

- Publicly Accessible Tenant URL
- Access Token with Write.Config scope

---

## How to Use

- Place your dashboard JSON files in the folder named dashboard_files located in the same directory as the tool.
- Run the exe
- Fill the required fields in the GUI:
  - Dynatrace Tenant URL (e.g., https://your-env.live.dynatrace.com)
  - API Token with WriteConfig permission
  - Dashboard Owner Username
- Click the Upload Dashboards button.
- Monitor logs in the scrollable window or check logs.txt and upload_log.txt files for a detailed summary.

---

## Notes
- The tool automatically strips the top-level id from the JSON to avoid conflict during dashboard creation.
- Existing dashboards will not be overwritten. This tool always creates new dashboards.
- Ensure your API token has WriteConfig permission.

---

## Developed By
Abhishek Satpathy (abhishek.satpathy@dynatrace.com)
