# philipalcorn.github.io

Personal academic website for Phil Alcorn, built with the [Academic Pages](https://github.com/academicpages/academicpages.github.io) Jekyll template and deployed to GitHub Pages by `.github/workflows/jekyll.yml`.

## Where things live

| Content | Location |
| --- | --- |
| Home / about page | `_pages/about.md` |
| Sidebar, site title, links | `_config.yml` (`author:` section) |
| Header menu | `_data/navigation.yml` |
| Research projects | `_portfolio/` (sorted by `order:`) |
| Publications | `_publications/` |
| Talks | `_talks/` |
| Teaching | `_teaching/` |
| Profile photo | `images/profile.png` |

## CV

The CV is **not** stored in this repo. During each deploy, the workflow checks out `alcorn_phil_cv.pdf` from the private `philipalcorn/Resume` repo and copies it to `files/alcorn_phil_cv.pdf`; the `/cv/` page embeds it.

The site rebuilds on every push to `master`, once a day (09:00 UTC), and when triggered manually from the Actions tab, so CV changes show up within a day.

### One-time setup

1. Create a [fine-grained personal access token](https://github.com/settings/personal-access-tokens/new) with:
   - Repository access: only `philipalcorn/Resume`
   - Permissions: **Contents: Read-only**
2. In this repo: Settings → Secrets and variables → Actions → New repository secret, named `RESUME_REPO_TOKEN`, containing the token.
3. Settings → Pages → Source: **GitHub Actions**.

### Optional: update immediately when the resume changes

Add `.github/workflows/notify-site.yml` to the Resume repo, plus a secret `SITE_DISPATCH_TOKEN` there: a fine-grained token scoped to `philipalcorn/philipalcorn.github.io` with **Contents: Read and write** (required for repository_dispatch).

```yaml
name: Rebuild website
on:
  push:
    paths: ["alcorn_phil_cv.pdf"]
jobs:
  dispatch:
    runs-on: ubuntu-latest
    steps:
      - run: |
          curl -sf -X POST \
            -H "Authorization: Bearer ${{ secrets.SITE_DISPATCH_TOKEN }}" \
            -H "Accept: application/vnd.github+json" \
            https://api.github.com/repos/philipalcorn/philipalcorn.github.io/dispatches \
            -d '{"event_type":"resume-updated"}'
```

## Local preview

```sh
bundle install
cp ../resume/alcorn_phil_cv.pdf files/   # ignored by git
bundle exec jekyll serve -l -H localhost
```
