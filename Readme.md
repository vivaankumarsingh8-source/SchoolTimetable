# School Timetable Builder

Live site: https://vivaankumarsingh8-source.github.io/SchoolTimetable/

Everyone with the link sees and edits the **same** timetable. Data is stored in Firebase Realtime Database (not in each browser).

## One-time Firebase setup

1. Go to [Firebase Console](https://console.firebase.google.com) and sign in with Google.
2. Create a project (e.g. `SchoolTimetable`). Disable Google Analytics if you do not need it.
3. Click the **Web** icon (`</>`) to add a web app. Register the app and copy the `firebaseConfig` object.
4. In the left menu open **Build → Realtime Database → Create Database**.
   - Pick a region close to you.
   - Start in **test mode** (allows read/write for anyone with the link).
5. Open `index.html` and `timetable.html` and replace the `FIREBASE_CONFIG` object with your config.  
   Make sure `databaseURL` is included (Realtime Database → Data tab shows the URL, like `https://YOUR_PROJECT-default-rtdb.firebaseio.com`).
6. Commit and push:

```bash
git add index.html timetable.html
git commit -m "Add Firebase config for shared timetable"
git push
```

7. Open the live site and confirm edits appear in another browser or private window.

## Notes

- Anyone with the site link can change the data (by design).
- Test-mode rules may expire after 30 days; in Realtime Database → Rules you can keep open access with:

```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```
