# Marvey Studios site

Menu/landing page for Marvey Studios, with placeholder pages for SweatSlot and
Runway. BrickLog and StrideLog stay on `bricklog.app` for now and are linked
externally.

## Publishing this with GitHub Desktop

1. Unzip this folder somewhere on your Mac.
2. In GitHub Desktop: **File → Add Local Repository**, choose the unzipped
   `marvey-studios-site` folder.
3. It'll offer to initialize a git repo if there isn't one yet — accept that.
4. Make your first commit (e.g. "Initial site structure").
5. **Publish repository** — keep it public (GitHub Pages on the free plan
   needs a public repo unless you're on GitHub Pro/Team).
6. On github.com, go to the repo's **Settings → Pages**. Under "Build and
   deployment", set Source to **Deploy from a branch**, branch `main`,
   folder `/ (root)`.

At this point the site is live at `https://<your-username>.github.io/marvey-studios-site/`
— check it loads before touching domains.

## Once you've bought the domain (marveystudios.dev or similar)

1. Add a file called exactly `CNAME` (no extension) to the repo root,
   containing just the domain, e.g.:
   ```
   marveystudios.dev
   ```
2. At your domain registrar, add DNS records:
   - Apex domain → four `A` records pointing to:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `www` (optional) → `CNAME` record pointing to `<your-username>.github.io`
3. Back in Settings → Pages, the custom domain field should pick up the
   `CNAME` file. Wait for the DNS check to go green, then enable
   **Enforce HTTPS**.

Happy to walk through the DNS records with you once the domain's bought —
they vary slightly by registrar's dashboard.

## Folder naming

Keep all folder names lowercase (`sweatslot`, `runway`, not `SweatSlot`) —
GitHub Pages URLs are case-sensitive even though macOS's Finder isn't, and
mismatches there are an easy silent 404.

## When StrideLog is ready to move over

1. Add a `stridelog` folder here with its HTML/CSS.
2. Update the StrideLog card link in `index.html` from
   `https://bricklog.app/Stridelog` to `stridelog/`.
3. Once bricklog.app is retired, do the same for BrickLog itself.
