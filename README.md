## 🏨 Agoda New/Reno Filter Bookmarklet

https://github.com/user-attachments/assets/edd2bf73-7a1a-4c07-a129-83b649ecef51

### ✨ Project Overview

This tool is a simple JavaScript bookmarklet designed to instantly clean up hotel search results on the **Agoda** website. It specifically filters and hides hotel listings that **do not display a "Newly Renovated" or "Newly Built" badge**. This helps users quickly narrow down options to only modern, updated, or recently constructed accommodations.

> 💡 **How it Works**: The script iterates through every visible hotel card on the page. If a card lacks the specific data-element that indicates a recent renovation or new build, the script applies a CSS class to hide that card, removing it from your view.

---

### 🚀 Installation & Usage

Follow these steps to install and effectively use the bookmarklet in your browser.

#### 1. Copy the Code

Copy the entire minified JavaScript code below. Ensure the `javascript:` prefix is included.

```javascript
javascript:(function(){const hotels=document.querySelectorAll('.PropertyCard');hotels.forEach(hotel=>{if(!hotel.querySelector('div[data-element-name="newly-reno-built-badge"]')){hotel.classList.add('hide');}})})();
````

#### 2\. Create the Bookmarklet

  * **Right-click** on your browser's bookmarks bar and select **"Add Page"** or **"Add Bookmark"**.
  * **Name:** Give it a clear name (e.g., `Agoda New Filter`).
  * **URL/Address:** **Paste the entire copied JavaScript code** into the URL or Address field.
  * **Save** the bookmark.

#### 3\. **Crucial Usage Step: Scroll First\!**

**You MUST scroll to the bottom of the hotel listing page before running the script.**

  * Agoda loads content dynamically as you scroll (lazy loading).
  * The script can only process hotel cards that have been loaded into the page's structure (the Document Object Model, or DOM).
  * Scroll completely down to ensure **all properties** are loaded and available for the script to analyze.

#### 4\. Run the Filter

  * Once all hotels are loaded, click the **'Agoda New Filter'** bookmark on your bookmarks bar.
  * All hotel listings that lack the "Newly Renovated/Built" badge will instantly disappear from the page.

-----

### 💻 Code Analysis

| Code Snippet | Function |
| :--- | :--- |
| `document.querySelectorAll('.PropertyCard')` | Selects all major elements (hotel cards) on the page. |
| `!hotel.querySelector('div[data-element-name="newly-reno-built-badge"]')` | Checks if the current hotel card **does not** contain the specific badge element used for "Newly Renovated/Built" indicators. |
| `hotel.classList.add('hide')` | If the badge is absent, the CSS class `hide` is added to the element, concealing it from view. |

-----

### ⚠️ Compatibility Notes

  * **Action Prerequisite:** The **scroll-down step is mandatory** for the script to process all available listings.
  * **Website Structure:** This bookmarklet is strictly dependent on **Agoda's current HTML structure** (`.PropertyCard` and `data-element-name="newly-reno-built-badge"`). If Agoda changes these class names or data attributes, the bookmarklet will stop functioning.
