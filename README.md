# Builder JV Opportunities

A branded buy box website for **Queen of Wholesaling Land** by Laraque Capital Group, LLC. The page shows Florida markets where builders need lots this month, with each market's buy box, pricing, underwriting video, and seller list, plus the prefilled vacant land contract.

**Live Page:** [laraquecapitalgroup.net](https://laraquecapitalgroup.net)

## Features

- Pop Up Contract Viewer
- Direct Contract Download
- Seven Florida Market Boxes
- Branded Logo, Colors, And Fonts
- Submit A Deal Link In A New Tab
- Phone Layout Matching The Desktop Design
- Underwriting Videos That Open At Each Market's Timestamp

## Current Markets

| Market | County | Lots Needed | Max Per Lot | Video Starts |
| --- | --- | --- | --- | --- |
| Sebastian Highlands | Indian River | 2 | $93,000 | 01:15 |
| Vero Lake Estates | Indian River | 10 | $60,000 | 04:43 |
| Canaveral Groves | Brevard | 2 | $100,000 | 32:36 |
| Port St John | Brevard | 2 | $77,500 | 57:55 |
| Port St Lucie | Saint Lucie | 1 | $150,000 | 17:59 |
| Palm Bay (Blue Lots) | Brevard | 5 | $58,000 | 07:31 |
| Palm Bay (Unit 49) | Brevard | 8 | $23,000 | 07:31 (Palm Bay replay) |

## Files

- `README.md` explains the project.
- `index.html` is the full website in a single file.

Everything is built into that one file, including the CSS, JavaScript, logos, market photos, and contract PDF, so the page needs no other files to run.

## Publish With GitHub Pages

1. Create a new repository on GitHub.
2. Upload `index.html` and `README.md`.
3. Go to **Settings**, then **Pages**.
4. Under **Build And Deployment**, choose **Deploy From A Branch**.
5. Select the `main` branch and the `/ (root)` folder, then click **Save**.
6. Wait a minute or two, then open the link GitHub shows at the top of the Pages settings.

## Publish On GoHighLevel

1. Open the page in the GoHighLevel website or funnel builder.
2. Add or select a **Custom Code** element.
3. Paste in everything from `index.html`, then save and publish.

If GoHighLevel will not save the code because of its size, upload the photos and contract PDF to the GoHighLevel Media Library and swap the built in data for those links.

## How To Update The Page

All editable content sits near the top of the second `<script>` section in `index.html`.

### Links

```js
const LINKS = {
  contract: "",
  videos: { sebastian: "https://www.loom.com/share/...?t=75", ... },
  sellerLists: { sebastian: "", ... }
};
```

- `videos` holds each Loom link. Add `?t=` followed by the start time in seconds (for example, 4:43 is `?t=283`).
- `sellerLists` holds each Get Seller List link. Until a link is added, the button shows a Link Coming Soon message.

### Markets

Each market is one entry in `MARKETS`:

```js
{ id:"sebastian", city:"Sebastian Highlands", county:"Indian River County", lots:2,
  reqs:["No dirt roads","No flood zone AE"], price:["$93,000 max per lot"],
  video:"Sebastian Highlands", time:"01:15" }
```

- `lots` is the number shown in the badge.
- `time` is the Watch From label on the video card.
- `reqs` lists the buy box rules, ordered shortest to longest.
- The order of entries in `MARKETS` sets the order of the boxes on the page.
- `note` (optional) adds a short message above the video, as used for Palm Bay (Unit 49).
- `variant` (optional) adds a tan label under the city, such as `City Water (Blue Lots)`.

### Photos

`PHOTOS` maps each market `id` to an image. A link to a hosted image works as well as built in image data.

```js
const PHOTOS = { sebastian: "https://your-image-link.jpg" };
```

`FOCUS` controls which part of the photo stays in view, for example `"center 40%"`. Markets without a photo show an illustrated scene.

### Submit A Deal

Both Submit A Deal buttons link to `https://laraquecapitalgroup.net/jv` and open in a new tab. Search the file for that address to change it.

## Brand

- **Tan:** `#b5a793`
- **White:** `#ffffff`
- **Dark Teal:** `#223d3c`
- **Body And Numbers:** Poppins
- **Headings:** Cormorant Garamond
- **Market Box Titles:** Oswald

## Notes

- The contract uses the Florida Realtors Vacant Land Contract form (VAC 15), which carries a notice limiting reproduction. Confirm you are licensed to distribute it before sharing the page publicly.
- The Port St John photo is a Welcome to Florida sign preview that may come from a stock image site. Confirm the license or replace it before public use.
- Page copy avoids dashes, uses title case for headers, and orders list items shortest to longest.

## Contact

**Queen of Wholesaling Land**
[info@wholesalinglandqueen.com](mailto:info@wholesalinglandqueen.com)

© 2026 Laraque Capital Group, LLC
