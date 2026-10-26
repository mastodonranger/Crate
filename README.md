# Crate

Catalog your vinyl. Type in the artist and album, and Crate finds the cover art, genres and release info (date, label, catalog number, country, track count) for you.

## Features

- **Barcode scanning**: point your phone's camera at the barcode on the sleeve (or use a photo, or type the number) to find your exact pressing — label, catalog number, country, year and vinyl format
- Automatic lookup via [MusicBrainz](https://musicbrainz.org) and the [Cover Art Archive](https://coverartarchive.org), with iTunes as a fallback for artwork and genre
- Pick the right match when an album has several versions (live, deluxe, etc.), or enter a record manually
- Track your own copy: format (LP, 2×LP, 7″…), condition grade and notes
- Covers or list view, search, sort and genre filters
- Light and dark mode, works on phone and desktop
- Backup and restore (JSON) and CSV export

## Running it

It's a single HTML file with no build step and no API keys. The camera scanner needs the page served over HTTPS (GitHub Pages is fine); on browsers without a built-in barcode reader, such as Safari, it loads the [barcode-detector](https://github.com/Sec-ant/barcode-detector) polyfill on first use. Open `index.html` in a browser, or host it with GitHub Pages (Settings → Pages → Deploy from branch → `main` / root).

Your collection is saved in your browser's local storage, so it lives on that one device. Use **⋯ → Download backup** to keep a copy or move it to another device.
