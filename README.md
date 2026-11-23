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

## Publishing (GitHub Pages)

The live site is https://bennis45.github.io/RememberWhere/ and it serves whatever is on the `main` branch.

### One-time setup

Run these from this folder. They need the GitHub CLI (`gh`), signed in.

1. Create the public repository and push the local commits:

   ```bash
   gh repo create RememberWhere --public --source=. --remote=origin --push
   ```

2. Turn on GitHub Pages for the `main` branch:

   ```bash
   gh api -X POST repos/bennis45/RememberWhere/pages -f "source[branch]=main" -f "source[path]=/"
   ```

3. About a minute later, check that the site is built (it should print `built`):

   ```bash
   gh api repos/bennis45/RememberWhere/pages --jq .status
   ```

### Updating

```bash
git commit -am "Add <trip>"
git push
```

Pages rebuilds automatically, usually within a minute or two. A hard refresh in the browser makes sure you aren't seeing a cached copy.

## Running locally

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.
