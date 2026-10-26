# Crate

Catalog your vinyl. Type in the artist and album, and Crate finds the cover art, genres and release info (date, label, catalog number, country, track count) for you.

## Features

- **Barcode scanning**: point your phone's camera at the barcode on the sleeve (or use a photo, or type the number) to find your exact pressing — label, catalog number, country, year and vinyl format
- Automatic lookup via [MusicBrainz](https://musicbrainz.org) and the [Cover Art Archive](https://coverartarchive.org), with iTunes as a fallback for artwork and genre
- **Choose your pressing**: after picking an album, see every pressing with its country, year, label, catalog number and format — your own country listed first (set it in Settings), with filters for country, vinyl only, and catalog #
- **Catalog number lookup**: type the code from the spine or label (e.g. `XBS 3010`) to find that exact release — handy for older records without a barcode
- **Change pressing** on records you've already saved
- Pick the right match when an album has several versions (live, deluxe, etc.), or enter a record manually
- Track your own copy: format (LP, 2×LP, 7″…), condition grade and notes
- Covers or list view, search, sort and genre filters
- Light and dark mode, works on phone and desktop
- Backup reminders, backup to iCloud/Drive/email from your phone, restore, an automatic daily copy, and CSV export

## Running it

It's a single HTML file with no build step and no API keys. The camera scanner needs the page served over HTTPS (GitHub Pages is fine); on browsers without a built-in barcode reader, such as Safari, it loads the [barcode-detector](https://github.com/Sec-ant/barcode-detector) polyfill on first use. Open `index.html` in a browser, or host it with GitHub Pages (Settings → Pages → Deploy from branch → `main` / root).

## Keeping your catalog safe

Your collection is saved in your browser on that one device. Updating the app never deletes it — but clearing your browser data, or losing the device, would. So:

- **Back up regularly**: Settings → **Back up now**. On a phone this opens the share sheet, so you can save the file to iCloud Drive, Google Drive or Files, or email it to yourself. The app reminds you when you have unsaved changes. A backup holds every detail of every record, and **Restore from backup** brings it all back on any device.
- **On iPhone, add Crate to your Home Screen** (Share → Add to Home Screen). Safari can clear a website's saved data after 7 days without a visit; apps on the Home Screen are exempt.
- The app also keeps an **automatic daily copy** you can restore from Settings, and if the saved data is ever damaged it recovers from that copy instead of starting empty.
