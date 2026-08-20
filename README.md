# 🏨 Agoda New Filter

Filter Agoda results to show only new & newly renovated stays.

> A tiny bookmarklet that hides every listing without the "Newly Built / Renovated" badge.

https://github.com/user-attachments/assets/edd2bf73-7a1a-4c07-a129-83b649ecef51

## Features

- One-click filtering on Agoda search results
- Keeps only places with the New / Newly Renovated badge
- No extension, no setup — just a bookmark

## Usage

**1. Copy the bookmarklet**

```javascript
javascript:(function(){const hotels=document.querySelectorAll('.PropertyCard');hotels.forEach(hotel=>{if(!hotel.querySelector('div[data-element-name="newly-reno-built-badge"]')){hotel.classList.add('hide');}})})();
```

**2. Create a bookmark**

Right-click your bookmarks bar → Add Bookmark → Paste the code into the URL field → Save as `Agoda New Filter`

**3. Scroll first (important)**

Scroll to the very bottom of the Agoda results page before running it. Agoda lazy-loads listings, so the script can only filter what’s already loaded in the DOM.

**4. Click to filter**

Click the bookmark. Listings without the badge disappear instantly.

## How it Works

- `document.querySelectorAll('.PropertyCard')` — finds all hotel cards
- `hotel.querySelector('div[data-element-name="newly-reno-built-badge"]')` — checks for the badge
- `hotel.classList.add('hide')` — hides cards without it

## Notes

- You need to scroll and load all results before running it
- Depends on Agoda's current markup (`.PropertyCard` / `newly-reno-built-badge`). May break if Agoda changes its HTML.
