# Tab Snooze

A Firefox extension that closes a tab now and brings it back when you want it, like snoozing an email.

## Use

1. Click the moon icon in the toolbar.
2. Pick a time: Later Today, This Evening, Tomorrow, 7 Days, a month, "someday", or **Pick a Date** for a calendar and exact time.
3. The tab closes and reopens at that time, with a notification. If Firefox was closed at the time, it reopens on next start.

**Repeatedly** snoozes a tab daily, weekly, monthly or yearly. **View Snoozed** lists everything waiting, split into one-time and recurring, with options to open a tab now or delete it.

In **Settings** you can change what "later" and "evening" mean, set the date format, choose which buttons appear and in what order, add your own preset buttons, pick how notifications behave, and export or import your snoozed tabs as JSON.

## Install

Requires Firefox. Grab the signed `.xpi` from the [latest release](../../releases/latest) and open it in Firefox, or load the source temporarily:

1. Open `about:debugging#/runtime/this-firefox`.
2. Click **Load Temporary Add-on** and choose `manifest.json`.

A temporary add-on is removed when Firefox restarts and keeps its own separate storage.

## Privacy

Snoozed tabs (title, URL, favicon and time) are stored locally in the browser's extension storage and never leave your device. Only your settings sync between devices, through Firefox Sync if you are signed in; to move snoozed tabs to another device use the JSON export and import. The extension makes no network requests of its own and has no analytics. Permissions: `tabs` (read and close tabs, reopen them), `alarms` (wake-up times), `storage`, `notifications`.

## Development

Vanilla JavaScript, Manifest V2, no build step. `./upgrade.sh --help` bumps the version, lints with `web-ext`, packages to `dist/` and can sign through AMO's unlisted channel (set `AMO_JWT_ISSUER` and `AMO_JWT_SECRET`).

The add-on ID `tab-snooze@ffaddons.local` is kept so existing installs retain their stored snoozes.

Built with Claude Code.

## License

[MIT](LICENSE)
