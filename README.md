# Constellation Globe

An interactive celestial globe of the 88 modern constellations, built to embed in a Tableau Public dashboard.

**Live:** https://luigicicciari.github.io/constellation-globe/

![The globe turned toward the southern sky, with Centaurus highlighted](preview.png)

## What it does

- Spins slowly on load. Drag or swipe to turn it, scroll or pinch to zoom, and use **Pause / Spin** to stop or restart it.
- Hover a star to see its name and brightness, or a constellation name to see its meaning and story.
- **Show as a celestial globe** flips the view to the mirror image used on antique star globes. The default view matches the sky as seen from Earth.
- Respects reduced-motion settings: no spin for visitors who turn motion off.

## URL settings

The page reads optional settings from its address, so a Tableau URL action can control it.

| Setting | Example | What it does |
|---|---|---|
| `focus` | `?focus=Ori` | Turns the globe to a constellation (three-letter IAU abbreviation) and highlights it |
| `lat` | `?lat=33` | Dims the sky that never rises at that latitude and outlines the sky that never sets |
| `month` | `?month=1` | Brightens the constellations best seen in the evening that month (1 to 12) |

Settings combine: `?focus=Cru&lat=33&month=4`

## Using it in Tableau

1. Add a **Web Page** object to a dashboard and paste the live URL.
2. To drive it from a sheet, add a **Go to URL** action that targets the web page object, for example:
   `https://luigicicciari.github.io/constellation-globe/?focus=<Abbreviation>&lat=<Parameters.Latitude>&month=<Month_Num>`

## How it works

A single self-contained `index.html`. The globe is drawn with [D3](https://d3js.org/) using an orthographic projection: each star's right ascension and declination are treated like longitude and latitude on a sphere. The data is embedded in the page, so there is nothing else to host.

## Data and credits

- **Constellation figures:** from the Stellarium modern sky culture (https://stellarium.org), via the Ma-Pe-Ma constellation collection.
- **Star names and magnitudes:** HYG Database by David Nash (astronexus), https://github.com/astronexus/HYG-Database, licensed CC BY-SA 4.0. Four magnitudes with a missing minus sign in the source figures were corrected (Sirius, Canopus, Arcturus, Alpha Centauri).
- **Constellation meanings and descriptions:** written for this project.
- **Typeface:** Gelasio, via Google Fonts (SIL Open Font License).

## License

- **Code:** MIT. See [LICENSE](LICENSE).
- **Data embedded in index.html:** CC BY-SA 4.0 (https://creativecommons.org/licenses/by-sa/4.0/), in keeping with the HYG Database terms. If you reuse or adapt the data, credit the sources above and share it under the same license.

Made by Luigi Cicciari.
