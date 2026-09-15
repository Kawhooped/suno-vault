# SUNO VAULT

Live site after Pages is on: **https://kawhooped.github.io/suno-vault/**

One-file music deck. Paste Suno song links, upload audio, sort, like, make playlists.

## Publish

1. Repo → **Settings → Pages**
2. Source: **GitHub Actions** (workflow already in `.github/workflows/pages.yml`)
   or **Deploy from branch** → `main` / `/ (root)`
3. Wait a minute. Open the Pages URL.

## What is stored where

| Thing | Where |
|---|---|
| The website | this repo / GitHub Pages |
| Shared catalog (titles, Suno IDs, playlist names) | `data/library.json` |
| Audio you drop in the browser | **your phone only** (IndexedDB) |
| Big WAV/MP3 library | Google Drive or similar — **not GitHub** (file size + ToS) |

GitHub is the code + catalog backend. It is a bad hard drive for a music collection.

## Connect Drive later

Google Drive is not connected to Grok in this account yet. When it is, the flow is:

1. Folder `SUNO-VAULT` on Drive
2. Drop WAV/MP3/covers there
3. A small worker writes public-or-signed URLs into `data/library.json`
4. The Pages site loads that JSON and plays

Until then: paste Suno links, or upload files in the page (stays on that device).

## I work with this repo

Push catalog updates to `data/library.json`. I can read the repo from GitHub and edit the site from here.
