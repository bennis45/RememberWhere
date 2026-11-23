# RememberWhere

A map of everywhere our family has traveled. It's a static page: `index.html` draws the map with
[Leaflet](https://leafletjs.com) and OpenStreetMap tiles, and `data.js` holds the trips.

## Adding a trip

Edit `data.js`:

1. If it's a new place, add it to `PLACES` with its lat/lng (in Google Maps, right-click the spot to copy the coordinates).
2. Add a row to `TRIPS`.

Commit and push (or edit `data.js` on github.com), and GitHub Pages republishes within a minute or two.
If a trip names a place or initials that don't exist, the page skips it and logs a warning in the browser console.

Only add past trips. The repository is public.

## Running locally

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.
