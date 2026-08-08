# deadbeat0nline — link page + control panel

Your bio link page with a built-in "backend": a control panel page that
updates the song title and links without touching any code.

## What's in here

- `index.html` — the arcade high-score page (your main bio link)
- `bios.html` — the BIOS setup page (lives at `/bios.html` on the same site)
- `config.json` — the data both pages read: NOW PLAYING song + all your links
- `admin.html` — your control panel. Open it in a browser, edit, hit PUBLISH
- `README.md` — this file

Want the BIOS page as the main one instead? Just swap the two filenames
(rename `index.html` → `arcade.html` and `bios.html` → `index.html`).

## Going live (one-time, ~10 minutes, free)

1. **Make a GitHub account** at github.com if you don't have one.
2. **Create a new repository.** Name it exactly `YOURUSERNAME.github.io`
   (using your actual username) — that makes the URL clean. Set it to Public.
3. **Upload these files.** On the repo page: "Add file" → "Upload files" →
   drag in everything in this folder → Commit.
4. **Turn on Pages.** Repo → Settings → Pages → under "Build and deployment"
   set Source to "Deploy from a branch", Branch: `main`, folder `/ (root)` → Save.
5. Wait a minute or two. Your page is live at:

   **https://YOURUSERNAME.github.io**

   That's the link for your bio. The BIOS version is at
   `https://YOURUSERNAME.github.io/bios.html`, and your control panel at
   `https://YOURUSERNAME.github.io/admin.html`.

## Setting up the control panel (one-time, ~3 minutes)

The panel needs a token so it's allowed to update YOUR repo (and nobody
else can). Make one that only works on this single repo:

1. GitHub → click your avatar → **Settings** → **Developer settings**
   → **Fine-grained personal access tokens** → **Generate new token**.
2. Name: `link page panel`. Expiration: up to you (you'll paste a new one
   when it expires).
3. Repository access: **Only select repositories** → pick `YOURUSERNAME.github.io`.
4. Permissions → Repository permissions → **Contents** → **Read and write**.
   Leave everything else on "No access".
5. Generate, and copy the token (starts with `github_pat_`).

## Updating your page (any time, ~30 seconds)

1. Open `https://YOURUSERNAME.github.io/admin.html` (works on your phone too).
2. Fill in username, repo name, and paste the token
   (tick "remember on this device" so you only do this once per device).
3. Hit **LOAD CURRENT CONFIG** → edit the song title / links → **PUBLISH**.
4. The live page updates within a minute or so.

Dropped a new track? Change "song title" + "song link", publish, done —
the blinking NOW PLAYING line on your page now points at the new song.

## Notes

- The token never leaves your browser except to go directly to
  api.github.com. Don't commit it anywhere or share it.
- Anyone can *view* admin.html but without your token it can't do anything.
- You can also just edit `config.json` directly on GitHub (pencil icon)
  if you ever prefer that.
