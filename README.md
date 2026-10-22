# Serenade Wedding Platform

Files:
- `index.html` — guest invitation; no admin/CMS navigation.
- `admin.html` — admin CMS, protected by a demo PIN prompt.
- `database.json` — central content file used by both pages.

## Run locally
`fetch('./database.json')` will not work when opening an HTML file directly via `file://`. Run a local static server from this folder, for example:
- Python: `python -m http.server 8000`
- Then open `http://localhost:8000/index.html` and `http://localhost:8000/admin.html`.

Admin demo PIN: `123456`.

## Saving
This is a static front-end demo. The admin page cannot overwrite `database.json` on a server using browser JavaScript alone. `Save Changes` logs the payload and the `Download database.json` button exports the updated file. Replace the original `database.json` with that downloaded file to update the guest page. RSVP and guestbook entries are stored in the current browser's localStorage only.

## Production security
The PIN is visible in client-side source and is not real authentication. Do not use it to protect sensitive data. Use a backend (e.g. Firebase, Supabase, or a server endpoint) and proper authorization for a production deployment.
