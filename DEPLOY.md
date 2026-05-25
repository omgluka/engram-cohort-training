# Deploy this site

Two steps. ~10 minutes total.

## 1 · Push to GitHub (one-time)

The repo is local at `C:\Claude\engram-cohort-training\`. To put it on GitHub:

```bash
cd C:\Claude\engram-cohort-training

git init
git add .
git commit -m "initial commit · engram cohort training"
git branch -M main
```

Then create an empty repo on GitHub (no README, no .gitignore, no license — we already have them), and push:

```bash
# Replace <your-account> with your GitHub username or org
git remote add origin https://github.com/<your-account>/engram-cohort-training.git
git push -u origin main
```

If you want it under an `engram-media` GitHub org, create that org first at https://github.com/organizations/new, then use the org name in the remote URL above.

## 2 · Deploy on Vercel

1. Go to https://vercel.com/new
2. Click **Import Git Repository**
3. Authorize Vercel to access your GitHub account if it isn't already
4. Pick `engram-cohort-training`
5. Vercel detects it as a static site automatically (no framework). Leave all settings at defaults.
6. Click **Deploy**

Within a minute or two the site is live at:

```
https://engram-cohort-training.vercel.app
```

That's the link you share with the team. Every future `git push origin main` triggers an automatic redeploy.

## Optional · custom domain

If you want it on `learn.engram.media` or similar:

1. In the Vercel project → **Settings** → **Domains** → add `learn.engram.media`
2. Vercel shows you the DNS record to add (typically a CNAME to `cname.vercel-dns.com`)
3. Add that record in your DNS provider (wherever `engram.media` is registered)
4. Wait ~5 minutes for DNS propagation. SSL is automatic.

## Adding a new workshop later

1. Author `topics/<new-workshop>/index.html` (use `topics/skills/index.html` as the template)
2. Flip the card in the root `index.html` from `class="topic upcoming"` to `class="topic"` and `status coming` to `status live`
3. Update `README.md`'s status table
4. `git add . && git commit -m "live · workshop NN" && git push`

Vercel auto-deploys on push. Your team sees the new workshop within a minute.

## Rolling back

In the Vercel project → **Deployments** → find the previous deployment → click the three-dot menu → **Promote to Production**. Done in 10 seconds.
