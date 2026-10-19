ZENOVA EDUCATIONS — LOGIN-FREE ALARM PORTAL
Firebase project: znvapp-2a26f

FILES (all kept flat, no nested folders in this package):
- admin.html: no-login alarm scheduling panel
- alarm_index.html: student portal UI; no student login/profile/UID
- firebase-config.js: config reference for the existing Firebase project
- loud.mp3: ringtone
- firestore-alarm-rules-addition.txt: rule fragment to merge

HOSTING:
1. Host using HTTPS. Firebase modules will not work from file://.
2. Upload admin.html to the location where you want the admin page.
3. Upload alarm_index.html as the student page. If you want the exact URL /alarm/index.html, rename it to index.html and place it in an /alarm/ directory on your hosting server. In that case, update its audio src from loud.mp3 to ../loud.mp3 (or copy loud.mp3 into the alarm directory).
4. Merge the match block from firestore-alarm-rules-addition.txt INSIDE your existing documents match block. Do not replace the existing rules.
5. Open the student portal on devices and tap Enable alarm sound once. Keep the page open for reliable in-page ringing.

IMPORTANT LIMITATIONS:
- No admin login is included, as requested.
- No student login/profile/UID is used.
- Admin and student pages sync schedule data via Firestore collection alarmSchedules.
- This version triggers the ringtone in an open portal. It does not implement push notifications for closed pages or locked phones.
- Public write rules mean anyone can modify schedules. This is the tradeoff of having no admin authentication; protect the admin URL at your hosting layer if possible.
- This package has not been deployed to Firebase or tested against live Firestore rules.
