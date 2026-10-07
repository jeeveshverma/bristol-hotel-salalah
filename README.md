# Bristol Hotel Salalah: website

A static website (HTML, CSS and a little JavaScript) for **Bristol Hotel Salalah**, a 3-star hotel on As Saadah Street in Salalah, Oman, in English (`/`) and Arabic (`/ar/`, right to left).
It needs no build step, no server code and no database. Bookings go straight to WhatsApp (+968 9726 0111) with a pre-filled message.

## Files

```
index.html            English home page
ar/index.html         Arabic home page (right to left)
404.html              "Page not found" page
assets/css/style.css  All styles (colours and fonts are set at the top in :root)
assets/css/fonts.css  Self-hosted fonts (no Google requests)
assets/js/main.js     WhatsApp booking form, mobile menu, animations
assets/img/           favicon.svg, apple-touch-icon.png (the hotel's own B logo), og-image.jpg, map.svg, pattern.svg
assets/img/photos/    Hotel photos, recompressed (originals from the hotel's listing photos)
robots.txt, sitemap.xml, .nojekyll
```

## Preview locally

Open `index.html` in a browser. To test the way it will run online, start a local web server:

```
python3 -m http.server 8000   # then open http://localhost:8000
```

## Publish (GitHub Pages, free)

The repository is published at **https://jeeveshverma.github.io/bristol-hotel-salalah/** (Settings → Pages → Deploy from branch → `main` / root).

To put it on the hotel's own domain (`bristolhotelsalalah.com`, currently a GoDaddy placeholder page):
under Settings → Pages → Custom domain, add `www.bristolhotelsalalah.com`, then point the domain's DNS at GitHub Pages:
four A records (185.199.108.153, .109.153, .110.153, .111.153) plus a `www` CNAME to `jeeveshverma.github.io`.

Netlify and Cloudflare Pages also work: drag and drop the folder.

## Where the facts came from

| Fact | Source |
|---|---|
| Name, Arabic name, phone +968 23 321666, Instagram, check-in/out, Google 4.0 (364) | Google Maps listing |
| Second phone 97260111, licence MHT L1169594, tagline "جوهرة في قلب السعادة", Laylati Hall, offers | Instagram bio and highlights (@bristol_hotel_salalah) |
| Room types, sizes, beds, prices, facilities, review score 7.9 (172), category scores, quotes, house rules, Silk Road Restaurant | Booking.com listing, 7 Oct 2026 |
| 42 rooms, opened 2019, breakfast 7:00–10:30 | Trip.com, Expedia |
| 53 rooms (conflicts with 42), 2 meeting rooms, smoke-free | topomanhotels.com |
| Coordinates 17.0526615, 54.1570177 | Google Maps / Wanderlog |
| Distances | Booking.com (airport 6–7 km, Dahariz 6 km, Al Haffa 8 km), Google (Al Baleed 8 km); Wadi Darbat and the mosque from the map |

## Before going live: confirm with the hotel

| Item | Current value on the site | Why it needs checking |
|---|---|---|
| WhatsApp number | +968 9726 0111 (`wa.me/96897260111`) | From the Instagram bio ("للإستفسار والحجز 23321666 / 97260111"). Confirm it is on WhatsApp and who answers it |
| Domain | `www.bristolhotelsalalah.com` (in canonical, og, sitemap, robots) | The hotel owns the domain (GoDaddy builder placeholder). Replace if they use another |
| Prices | Deluxe $32, Junior Suite $39, Superior Suite $42, Executive Suite $44, breakfast $5 pp | Booking.com, 8–9 Oct 2026, before taxes (about +20%). The hotel may prefer OMR |
| Number of rooms | 42 | Booking/Expedia/Trip.com say 42, topomanhotels says 53 |
| Check-in / out | 2:00–11:00 pm / before 12:00 noon | Booking.com house rules |
| Payment | "At the hotel, cash accepted; ask about card" | Booking.com lists cash only, Trip.com says cash and cards |
| Suite occupancy | "King + sofa bed", Executive "family of five" | Booking showed max 2 for a 2-adult search; bed counts suggest more |
| Events hall name | "Laylati Hall" (قاعة ليلتي) | Taken from an Instagram highlight title; confirm the name and what it hosts |
| Cancellation | "We'll explain the terms on WhatsApp" | Not published for direct bookings |
| Massage / spa prices | "charged separately" | Not published |
| Languages | Arabic & English | Reviews mention Omani, Egyptian and Indian staff |
| Accessibility | "Wheelchair accessible, accessible bathrooms" | Booking.com accessibility filters; lift not confirmed |
| Email | not shown | Add one if the hotel wants it |

## Editing

* **Prices:** search both HTML files for `$32` / `$39` / `$42` / `$44`, and update the `<option>` labels in the booking form.
* **WhatsApp number:** change `PHONE` in `assets/js/main.js` and the `wa.me/96897260111` links in both pages.
* **Photos:** replace files in `assets/img/photos/` with the same names. Photos are 1080 px wide; larger originals from the hotel will improve the site, especially `hero.jpg`.
* **Reviews:** verbatim quotes from verified Booking.com reviews (English page: Khalid, Prasath, Marwan; Arabic page: Asim, Mohamed, Khuwar, Rashedi) and Google (Renny J, Ophel V). Keep the attribution if you change them.
* **Arabic page:** `ar/index.html` is written by hand; keep it in step with `index.html` when you change facts.

Fonts: Cormorant Garamond, Manrope, Tajawal and Noto Kufi Arabic, all under the SIL Open Font License.
