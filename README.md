# Fire Owl bookmarks

Public bookmark list for the [Fire Owl](https://github.com/new-meta-monkey/fire-owl) TV browser.

The app fetches this file on the home screen and adds the entries to **Bookmarks**.
Edit `bookmarks.json` and commit; the app picks up the change on its next sync
(at most once every 6 hours, or immediately with **Settings → Refresh remote bookmarks**).

## Format

```json
{
  "version": 1,
  "bookmarks": [
    { "title": "CineHive", "url": "https://cinehive.watch/" },
    { "title": "Example", "url": "https://example.com/" }
  ]
}
```

A top-level array is also accepted, and each entry may be a plain URL string:

```json
[
  "https://cinehive.watch/",
  "https://example.com/"
]
```

Rules:

- Only `http://` and `https://` URLs are used.
- Duplicate URLs are ignored.
- At most 40 bookmarks are kept.
- `title` is optional; the domain is shown when it is missing.

## Deleting and resetting in the app

- **Delete** one remote bookmark on the home screen: focus it, then press **MENU**
  (or long-press OK). It is hidden locally and will not come back on the next sync.
- **Reset** the remote list: **Settings → Reset remote bookmarks**. Hidden entries
  come back and the list is fetched again.

Your own bookmarks (added from the browser) are kept separately and are not affected
by a remote reset.
