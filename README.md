# Meridian World Clock

Live clocks for the cities you work with, grouped by region, plus a planner that converts a date and time in one city to every other city.

**Live site:** https://justinross58.github.io/world-time-zone/

## Pages

- **Clocks**: the current time in each selected city. Cities in your own time zone are highlighted.
- **Cities**: pick cities by region (USA/Canada, Central America/Caribbean, South America, Europe, Asia, Australia).
- **Planner**: choose a city, date and time (or use the Now / 9 AM / 2 PM / 9 PM shortcuts) and see it everywhere, color-coded:

| Band | Hours |
|---|---|
| Early Morning | 7–8 AM |
| Working | 8 AM–5:30 PM |
| Late afternoon | 5:30–8 PM |
| Evening | 8–10 PM |
| Night | 10 PM–7 AM |

Default cities: Montreal, Winston-Salem NC, Perris CA, Santo Domingo, San Salvador, San Pedro Sula, Bangkok, Huế, Dhaka, Sydney, Melbourne. To change the defaults, edit the `DEFAULTS` list in `index.html`. To add a city, add it to the right region in `REGIONS`.

## Publishing with GitHub Pages

1. In the repo, open **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**, branch **main**, folder **/ (root)**, and save.
3. After a minute or two the site is live at the address above.

## Adding it to Microsoft Teams

The `teams/` folder holds the Teams app package source, and `teams/meridian-world-clock-teams.zip` is the ready-to-upload package.

1. Make sure the GitHub Pages site above is live. Teams loads the app from that address.
2. Download `teams/meridian-world-clock-teams.zip`.
3. In Teams, go to **Apps → Manage your apps → Upload an app → Upload a custom app** and choose the zip.
4. Select **Add**, then right-click the app icon in the left sidebar and choose **Pin**.

If **Upload a custom app** isn't available, your organization has turned off custom app uploads. Send the zip to your Teams admin and ask them to add it to the org app catalog (Teams admin center → **Teams apps → Manage apps → Upload new app**). That also makes it available to your coworkers.

Inside Teams the app follows the Teams light/dark theme and hides its large heading.

### Rebuilding the zip

If you change `manifest.json` (bump `version` each time) or the icons:

```sh
cd teams
zip -j meridian-world-clock-teams.zip manifest.json color.png outline.png
```

The three files must be at the top level of the zip, not inside a folder.
