# valueamp-status — setup (≈5 min, one-time)

A public, GitHub-only uptime monitor + status page for app.valueamp.co.uk.
No personal access token required.

## 1. Create the repo
GitHub → New repository → owner `camberleyadvisory-droid`, name **`valueamp-status`**,
visibility **Public**, do NOT add a README. Create.

## 2. Push these files
From this unzipped folder:

```bash
git init -b main
git add .
git commit -m "Initial Upptime status page"
git remote add origin https://github.com/camberleyadvisory-droid/valueamp-status.git
git push -u origin main
```

(Or use the repo's "uploading an existing file" link and drag the files in.)

The push auto-triggers **Setup CI**, which builds the site and creates the
`gh-pages` branch. If it 403s, set **Settings → Actions → General → Workflow
permissions → Read and write**, then re-run it.

## 3. Enable Pages
**Settings → Pages → Source: Deploy from a branch → `gh-pages` / `(root)`.**
(Free, because the repo is public.) Site goes live at
`https://camberleyadvisory-droid.github.io/valueamp-status/`.

## 4. Custom domain
**Cloudflare DNS:** CNAME `status` → `camberleyadvisory-droid.github.io`
(DNS only / grey cloud). The page is then served at https://status.valueamp.co.uk.

## 5. Done
`Uptime CI` checks app.valueamp.co.uk every 5 minutes automatically. To add more
sites, edit `.upptimerc.yml` and push.
