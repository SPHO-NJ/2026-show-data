# 2026 National Standardbred Horse Show — vendor & adoptable-horse data

This repo is the live data source for the "Vendors" and "Adoptable Horses"
pages at [nationalshow.sphonj.org](https://nationalshow.sphonj.org). The site
fetches `vendors.json` and `horses.json` from here directly — **editing a
file here and committing updates the live site within a minute or two, with
no Netlify deploy involved.**

## How to add a vendor or horse

1. Open [vendors.json](vendors.json) or [horses.json](horses.json) above.
2. Click the pencil (edit) icon.
3. Copy an existing `{ ... }` entry, paste a new one below it (don't forget
   the comma between entries), and fill in the fields — see the schemas
   below.
4. For a logo or photo: upload the image file to the [images](images)
   folder first (Add file → Upload files), then reference it in the JSON as
   `images/whatever-you-named-it.jpg`.
5. Commit directly to `main`.

That's it — no build step, no Netlify involved.

## vendors.json

One object per vendor:

```json
{
  "name": "Example Tack & Feed",
  "logo": "images/example-tack-and-feed.png",
  "description": "One or two sentences about the vendor / booth.",
  "website": "https://example.com"
}
```

- `logo` — path to a file in `images/`, or a full image URL. Optional — leave `""` if there's no logo yet.
- `website` — optional. Leave `""` to hide the "Visit website" link.

## horses.json

One object per adoptable horse:

```json
{
  "name": "Example Horse",
  "age": "8",
  "gender": "Gelding",
  "height": "15.2 hh",
  "price": "$2,500",
  "photo": "images/example-horse.jpg",
  "infoUrl": "https://www.purplehazestandardbreds.org/"
}
```

- `photo` — path to a file in `images/`, or a full image URL.
- `infoUrl` — where "More info" links to (a Purple Haze page, a Facebook post, etc).
