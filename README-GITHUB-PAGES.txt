CSI Shanthi Church Sunday School — GitHub Pages PWA

Upload/replace these files in the same GitHub Pages folder as your existing styles.css and seed-data.js:

- index.html
- manifest.webmanifest
- service-worker.js
- icon-192.png
- icon-512.png

KEEP your existing:
- styles.css
- seed-data.js

Announcements:
- Admins can create, edit and delete announcements.
- Announcements can be scheduled for a future post time.
- Announcements can target all classes or selected classes.
- Active announcements are visible on the public Sunday School overview.
- Expired announcements disappear immediately from the website.
- Expired announcement documents are automatically deleted from Firestore the next time an administrator signs in.
- Firestore TTL is NOT required, so no billing upgrade is needed for this feature.

After uploading, commit the changes and allow GitHub Pages a short time to redeploy.
