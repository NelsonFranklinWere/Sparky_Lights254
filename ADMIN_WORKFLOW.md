# Admin Panel Workflow for GitHub Pages

## How It Works

1. **Admin Panel** (`admin.html` or `/admin`)
   - Add/edit/delete products
   - Upload images from phone
   - Products stored in browser localStorage

2. **Export Products**
   - Click "Export JSON" button
   - Downloads `products.json` file

3. **Upload to GitHub**
   - Upload `products.json` to your GitHub repo root
   - Commit and push

4. **Collection Page**
   - `collection.html` automatically loads from `products.json`
   - If file doesn't exist, uses fallback hardcoded data

## Step-by-Step Guide

### Adding/Updating Products

1. Go to `/admin` (or `admin.html`)
2. Login with password (default: `admin123` - change in `admin.html` line 67)
3. Click "Add Product" or edit existing
4. Fill in product details
5. Upload image from phone (optional - auto-fills filename and URL)
6. Click "Save Product"

### Publishing to GitHub

1. Click "Export JSON" button in admin panel
2. Save `products.json` file
3. Upload `products.json` to your GitHub repo:
   ```
   - Upload to root directory
   - Commit changes
   - Push to GitHub
   ```
4. GitHub Pages will serve the updated `products.json`
5. Visitors will see updated products on `collection.html`

### Image Upload Notes

- Images uploaded in admin are stored as base64 in localStorage
- When exporting JSON, base64 data is included for preview
- **Important**: Upload actual image files to your server (`https://sparklights.co.ke/`)
- Update `imageUrl` field with full URL to hosted image
- The `image` field should be just the filename

## File Structure

```
/
├── admin.html (or /admin/index.html)
├── collection.html
├── products.json (exported from admin)
└── images/ (your product images)
```

## Troubleshooting

**Products not showing on collection page?**
- Check browser console for errors
- Verify `products.json` exists in repo root
- Check JSON format is valid
- Ensure image URLs are correct

**Admin panel not saving?**
- Check browser localStorage is enabled
- Try exporting JSON manually
- Clear browser cache and retry

