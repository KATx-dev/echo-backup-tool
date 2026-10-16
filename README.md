Echo Music Backup Fixer
========================

Files:
- index.html: the complete single-page tool.

How it works:
1. If an old backup is not working, keep it as your **old/corrupt backup**; it contains the original `song.db` with your library data.
2. Clear Echo Music's app data, start from the clean state, and make a fresh backup. This is your **new/fresh backup**; it contains the working `settings.preferences_pb`.
3. Open `index.html`, select both backups, and click **Repair backup**.
4. The tool takes `song.db` from the old backup and `settings.preferences_pb` from the new backup, then packages those two files together.
5. Download the result and rename its extension to `.backup` if needed before restoring it in Echo Music.

How to test:
1. Open index.html in a modern browser with an internet connection (it loads JSZip from jsDelivr).
2. Follow the recovery steps above using copies of your backups.
3. Confirm the generated archive contains exactly `song.db` and `settings.preferences_pb`.

How to publish:
- Upload index.html to a static host such as GitHub Pages, Netlify, or Cloudflare Pages.
- No backend/server is needed. JSZip is loaded from a CDN, so the first visit needs internet access.
- Before public release, test with copies of real backups and confirm Echo Music accepts the generated archive.

Important:
- This implements the described beta workaround: output contains only root-level song.db from the old backup and settings.preferences_pb from the clean backup.
- It accepts files nested under a directory when finding inputs, but always writes the two output files at the archive root.
- It does not upload the selected backup files.
- Keep original backups. The workaround is community-provided and not guaranteed.
