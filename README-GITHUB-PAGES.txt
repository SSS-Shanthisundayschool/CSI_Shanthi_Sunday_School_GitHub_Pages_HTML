CSI Shanthi Church Sunday School — GitHub Pages PWA update

Upload/replace these files in the SAME GitHub Pages folder as your existing styles.css and seed-data.js:
- index.html (replace current one)
- manifest.webmanifest
- service-worker.js
- icon-192.png
- icon-512.png

Keep your existing styles.css and seed-data.js files in place.

ANNOUNCEMENTS
- Admins can add, edit and delete announcements from the Dashboard.
- Choose all classes or one/more specific classes.
- Set a future Post from time and an Expires at time.
- Teachers see active announcements relevant to their assigned classes.
- The public Sunday School overview shows all active announcements.
- Announcements disappear from the interface immediately after expiry.
- To physically auto-delete expired Firestore records, enable TTL on announcements.expires_at.
- See FIRESTORE_ANNOUNCEMENTS_SETUP.txt for the rules block and TTL field name.

PWA
- The site can be installed from supported Android browsers.
- On iPhone/iPad, open the GitHub Pages URL in Safari and use Share > Add to Home Screen.
