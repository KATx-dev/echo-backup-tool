Echo Music Backup Fixer
========================

Files:
- index.html: the complete single-page tool.

How to test:
1. Open index.html in a modern browser with an internet connection (it loads JSZip from jsDelivr).
2. Select the old backup and clean backup.
3. Click Repair backup.
4. Download EchoMusic_Fixed.backup.

How to publish:
- Upload index.html to a static host such as GitHub Pages, Netlify, or Cloudflare Pages.
- No backend/server is needed. JSZip is loaded from a CDN, so the first visit needs internet access.
- Before public release, test with copies of real backups and confirm Echo Music accepts the generated archive.

Important:
- This implements the described beta workaround: output contains only root-level song.db from the old backup and setting.preferences_pb from the clean backup.
- It accepts files nested under a directory when finding inputs, but always writes the two output files at the archive root.
- It does not upload the selected backup files.
- Keep original backups. The workaround is community-provided and not guaranteed.
