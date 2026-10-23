# School Timetable Builder

Live site: https://vivaankumarsingh8-source.github.io/SchoolTimetable/

Everyone with the link sees and edits the **same** timetable. Data is stored in a public GitHub Gist (no Firebase / no Google account needed).

## One-time setup (ask a parent — about 2 minutes)

GitHub already works on this project. Someone 13+ who can open the GitHub account should:

1. Open: https://github.com/settings/tokens/new?scopes=gist&description=SchoolTimetable  
2. Leave **only** the `gist` scope checked.  
3. Click **Generate token** and copy it.  
4. Open the live site (or this project locally). The first time you save, paste the token when asked.  
   Or paste it into `GIST_TOKEN` in `index.html` and `timetable.html`, then commit and push so every visitor can save without the prompt.

The token can only update gists. It cannot change your main repositories if you only enable `gist`.

## How sharing works

- The site loads shared JSON from the Gist.
- Saves write back to that same Gist.
- The page also checks for updates every few seconds, so other people’s changes appear live.
