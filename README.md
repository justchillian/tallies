# Tally

Track attendance in Raycast with separate rosters, reusable Markdown templates, and tables you can paste into Excel.

## Get started

1. Open **Template**. Choose **Create new**, add a heading and notes, and save your template.
2. Set an optional default time in, such as `9:00 AM`. It applies to current and future entries in that template, except no shows.
3. Open **Check in**, choose the template in the dropdown, and press **Enter** to add someone. Login receives focus first.
4. Use **Copy as Table** to copy everyone in the selected template except no shows. Paste into Excel or another spreadsheet. **Copy No Shows as Table** copies only no shows.

Switch templates whenever you need a different roster. Each template retains its own people and default time.

## Templates and notes

The attendance detail pane displays the template heading, Markdown notes, and attendance table. The selected person's row is bold. Checklist Markdown in notes is displayed as text; it is not interactive.

The **Template Table** field defines the individual note copied by **Copy Entry Note**, using `{{login}}`, `{{name}}`, `{{time_in}}`, and `{{time_out}}`. Each new entry keeps a snapshot of its template. The spreadsheet table always has these columns: Login, Name, Time in, Time out.

Times use 12-hour format, for example `2:30 PM`. People who have not clocked out display `—`; no shows display `No Show` with a blank time in. Edit an entry to change individual times or turn No Show off.

## Shortcuts in Check in

| Action                  | Shortcut            |
| ----------------------- | ------------------- |
| Add Entry               | Enter               |
| Edit Entry              | Shift + Enter       |
| Clocked Out / Edit Time | Command + Shift + O |
| Mark No Show            | Command + Shift + N |
| Copy as Table           | Command + Shift + C |
| Open Actions            | Command + K         |

The Actions menu also lets you set a template's time in, delete one entry, clear the current roster, or clear entries across all templates. Deletion requires confirmation.

## Move to another computer

1. In **Check in**, open Actions and choose **Export Backup**.
2. Select a folder and save. Tally also copies the backup file to your clipboard so you can paste it into Finder or transfer it.
3. Install Tally on the other Mac.
4. Open **Check in → Actions → Import Backup** and choose the JSON file.

Import replaces all templates and entries after validation and confirmation. Export the destination computer's data first if you want to keep it. Backups contain names, logins, notes, and times in plain text; share them only with intended recipients.

## Moving from an earlier development installation

Renaming the internal extension can create a separate Raycast data store. Before removing the previous installation, use its **Export Backup** action, then **Import Backup** in the renamed Tally installation. Changing the project folder alone does not transfer saved data.

## Storage and privacy

All templates, attendance entries, and time settings are stored locally with Raycast LocalStorage. Tally makes no network requests and does not automatically sync data between computers. Installing the extension on another computer does not transfer your data; use export/import.

## Development

Requires macOS, Raycast, and Node.js/npm.

```sh
npm ci
npm run dev
```

Open **Template** or **Check in** in Raycast. To validate:

```sh
npm test
npm run build
npm run lint
```

`npm run bundle` creates a local `.rayext` package. `npm run publish` starts Raycast's GitHub submission workflow. Store availability follows review and approval by Raycast.
