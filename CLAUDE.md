# Crate

Single-file vinyl catalog app (`index.html`), hosted on GitHub Pages. No build step.

## Protecting saved data — read before changing anything

People's whole collections live in their browser's `localStorage`. An update that can't read what an
older version saved looks to the user exactly like a deleted catalog. So:

- **Never rename `crate.records.v1`** (or `crate.records.snapshot`, `crate.backup`, `crate.country`,
  `crate.view`, `crate.sort`). Users on every older version have data under these keys.
- **Never remove or rename fields on saved records.** Add new fields freely; treat them as optional
  when reading. Unknown fields must survive a load → edit → save round trip.
- **Changing the shape of a record?** Do it in `migrate()`, which runs on every record on load and on
  restore. It must accept every format any earlier version saved (e.g. `genres` was once a string),
  and must keep fields it doesn't know about.
- **Never let a failed read turn into an empty crate that gets saved.** `load()` sets damaged data aside
  and recovers from the automatic copy; if it can't, `storageLocked` blocks every write. Keep it that way.
- **Backup files** (`{ app, version, exportedAt, settings, records }`) must stay restorable forever.
  If the format changes, bump `SCHEMA` and keep reading older files.
- **Don't change the hosting address** (repo name / Pages URL / custom domain) without warning: storage
  belongs to the origin, so a new address starts with an empty crate. Users would need to back up first.

## Checking a change

Serve the folder (`python3 -m http.server`) and test in a browser. Before shipping anything touching
storage, check: older saved data still loads, edits keep unknown fields, and a backup restores exactly.
