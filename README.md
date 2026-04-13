# Rudi's Bakery — Route Planner App

A mobile-first Progressive Web App (PWA) for Rudi's Bakery delivery drivers. Shows recommended drop quantities per store and SKU for each route.

## How Drivers Use It

1. Open the app URL in their phone browser
2. Tap **"Add to Home Screen"** when prompted (or manually via browser menu)
3. Select their route number
4. See recommended drop quantities for each stop

Works on iPhone and Android. No app store required.

---

## How to Update Recommendations Weekly

1. Run the Colab notebook to generate fresh recommendations
2. Download `powerbi_recommendations.csv` from Google Drive
3. Rename it to `recommendations.csv`
4. Come to this GitHub repository
5. Click on `recommendations.csv` in the file list
6. Click the pencil (edit) icon in the top right
7. Click **"Upload files"** or drag the new CSV over the existing one
8. Click **"Commit changes"**
9. App updates automatically within 1-2 minutes

---

## Column Format for recommendations.csv

The CSV must have these columns (order doesn't matter):

| Column | Description |
|---|---|
| Route | Route name e.g. ROUTE 759 |
| Store | Store number e.g. 631 |
| City | City name |
| Product | Product description |
| Item | UPC or item code |
| Predicted Demand | Raw model prediction |
| Recommended Qty | Final recommended drop quantity |
| 4-Week Avg Sold | Simple baseline |
| Return Rate | Recent return rate (decimal) |
| Confidence | ✅ High Confidence / 👀 Moderate Confidence / ⚠️ Low Confidence |
| Action | ✅ Maintain / 🔻 Reduce Drop / 🔺 Increase Drop |
| Last Drop Qty | What was dropped last delivery |
| Last Return Qty | What was returned last delivery |

---

## App URL

Once GitHub Pages is enabled your app will be live at:
`https://YOUR-GITHUB-USERNAME.github.io/rudis-delivery-app/`

---

## Transferring This Repository

To hand off to Rudi's Bakery:
1. Go to repository Settings
2. Scroll to the bottom — Danger Zone
3. Click **Transfer**
4. Enter the new owner's GitHub username
5. They accept the transfer and own the repo going forward

---

## Technical Notes

- No backend or server required
- App reads directly from `recommendations.csv` in this repository
- PWA manifest enables "Add to Home Screen" on iOS and Android
- Works offline for last loaded data (service worker optional)
