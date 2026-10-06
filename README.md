# Turkish Plate Lookup

A small, self-contained, offline-capable web app that decodes a Turkish vehicle
registration number (VRN): civilian province code, commercial (taxi/minibüs/
dolmuş/servis), diplomatic, gendarmerie, national police, state protocol, and
military plates.

No build step, no dependencies, no server — it's one `index.html` file with
inline CSS/JS. For privacy, the app never requires the plate's trailing serial
digits; only the province code and letter group matter for the lookup, and a
random number fills the displayed plate purely for looks.

## Live demo

Once this repo is pushed to GitHub and Pages is enabled (see below), the app
is served at:

```
https://<your-github-username>.github.io/<this-repo-name>/
```

## Hosting it on GitHub Pages

**Option A — web upload, no git needed:**

1. Create a new repository at <https://github.com/new> (public, any name — e.g. `tr-plate-lookup`).
2. On the new repo's page, choose "uploading an existing file" and drag in `index.html` (and this `README.md` if you like).
3. Commit the upload to the `main` branch.
4. Go to **Settings → Pages**, and under "Build and deployment" set **Source: Deploy from a branch**, **Branch: main**, folder **/(root)**. Save.
5. Wait ~1 minute, then refresh — GitHub shows the live URL at the top of that Pages settings screen.

**Option B — git CLI:**

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cp index.html <repo-name>/
cd <repo-name>
git add index.html
git commit -m "Add Turkish plate lookup app"
git push
```

Then enable Pages the same way as step 4 above.

## Notes

- `index.html` is the filename GitHub Pages serves automatically as the site's homepage — keep that name.
- Everything is inlined (no external fonts/scripts), so the page also works completely offline if you just open the file directly, or save it to your phone's home screen.
- The province code table and official/commercial plate conventions are cross-checked against Wikipedia and several Turkish traffic-law explainer sources (see the in-app footer); treat the protocol-number and commercial-letter details as indicative rather than an official gazette.
