# Quick Reference: Ad & SEO Updates

## 🚀 Quick Start

### Enable Ads (Post-AdSense Approval)
```bash
# 1. Create .env.local
echo "VITE_ADS_ENABLED=true" > .env.local

# 2. Rebuild
npm run build

# 3. Deploy
```

### Disable Ads
```bash
# Remove or comment out:
# VITE_ADS_ENABLED=true

npm run build
```

### Admin Mode (Test Ads Without Env)
```bash
# In .env.local
VITE_ADS_ADMIN=true

# Then visit:
https://yoursite.com/?adsToggle=1  # Enable
https://yoursite.com/?adsToggle=0  # Disable

# Persists to localStorage
```

---

## 📝 Page Structure Reference

### SEO Component
```tsx
import SEO from "@/components/SEO";

<SEO
  title="Your Page - Converter | ConvertAll"
  description="Short description (150-160 chars) about the tool."
  canonical="/your-page"
  schema={{
    "@context": "https://schema.org",
    "@type": "WebPage",
    name: "Tool Name",
    description: "Description of the tool.",
    url: "https://convertall.com/your-page",
  }}
/>
```

### AdWrapper Component
```tsx
import AdWrapper from "@/components/ui/AdWrapper";

<AdWrapper slot="Top Banner">
  <div style={{ textAlign: "center", margin: "1rem 0" }}>
    {/* AdSense placeholder - Top Banner */}
  </div>
</AdWrapper>
```

---

## 📂 File Locations

| File | Purpose |
|------|---------|
| `src/components/ui/AdWrapper.tsx` | Ad toggle component |
| `src/components/SEO.tsx` | SEO meta tags + schema |
| `public/robots.txt` | Search engine crawl rules |
| `public/sitemap.xml` | URL sitemap for SEO |

---

## 🧪 Testing

### Verify Ads Are Hidden
```javascript
// Browser console
localStorage.getItem("adsEnabled")  // Should be null or "false"
```

### Enable Ads Via Console
```javascript
localStorage.setItem("adsEnabled", "true");
location.reload();
```

### Check Meta Tags
```javascript
// In DevTools Console
document.querySelector("title").textContent
document.querySelector('meta[name="description"]').content
```

### Validate Sitemap
Visit: `https://yoursite.com/sitemap.xml`
Should be valid XML with all URLs

### Validate robots.txt
Visit: `https://yoursite.com/robots.txt`
Should include sitemap reference

---

## 📊 Checklist: Adding a New Converter Page

When adding a new converter:

1. **Create page file** in `src/pages/NewToolPage.tsx`
2. **Add SEO component:**
   ```tsx
   import SEO from "@/components/SEO";
   
   <SEO
     title="New Tool - Description | ConvertAll"
     description="Unique description for this tool."
     canonical="/new-tool"
     schema={{
       "@context": "https://schema.org",
       "@type": "WebPage",
       name: "New Tool Name",
       description: "Tool description.",
       url: "https://convertall.com/new-tool",
     }}
   />
   ```

3. **Add 3 AdWrappers:**
   - Top Banner (after title)
   - Inline (between content sections)
   - Footer (end of content)

4. **Update sitemap.xml:**
   ```xml
   <url>
     <loc>https://convertall.com/new-tool</loc>
     <changefreq>monthly</changefreq>
     <priority>0.9</priority>
   </url>
   ```

5. **Update routes in `src/App.tsx`:**
   ```tsx
   <Route path="/new-tool" element={<NewToolPage />} />
   ```

6. **Update Navbar/Footer links**

---

## 🔍 SEO Checklist Per Page

- [ ] Unique, descriptive title (50-60 chars)
- [ ] Unique meta description (150-160 chars)
- [ ] Canonical URL set correctly
- [ ] JSON-LD schema with `@context`, `@type`, `name`, `description`, `url`
- [ ] `<h1>` present and unique
- [ ] `<h2>` sections for content
- [ ] Open Graph tags included
- [ ] Twitter Card meta tags included

---

## 🚀 Deployment Checklist

Before going live:

```bash
# 1. Test build locally
npm run build

# 2. Verify no TypeScript errors
npm run type-check  # if available

# 3. Verify sitemap
cat public/sitemap.xml

# 4. Verify robots.txt
cat public/robots.txt

# 5. Run in prod mode locally
npm run preview

# 6. Test URL structure
# - All pages accessible
# - Ads hidden by default
# - Meta tags present
```

---

## 📡 Submit to Search Engines

### Google Search Console
1. Add property
2. Upload sitemap: `/sitemap.xml`
3. Request indexing
4. Monitor crawl stats

### Bing Webmaster Tools
1. Add site
2. Upload sitemap
3. Submit URLs for crawling
4. Monitor indexing status

---

## 🎯 Important Notes

### Ads
- ⚠️ **Disabled by default** until AdSense approval
- ⚠️ Use `AdWrapper` for all ad slots
- ⚠️ Never hardcode ad code; use AdWrapper

### SEO
- ⚠️ Each page **must** have unique title & description
- ⚠️ Always include canonical URL
- ⚠️ Always include JSON-LD schema
- ⚠️ Use proper heading hierarchy

### Deployment
- ⚠️ Run full build test before deploying
- ⚠️ Verify sitemap.xml is accessible
- ⚠️ Verify robots.txt is accessible
- ⚠️ Submit sitemap to Google & Bing

---

## 💡 Pro Tips

1. **Use rel="canonical"** to avoid duplicate content issues
2. **Keep descriptions under 160 chars** for Google snippets
3. **Use schema.org types** for better rich results
4. **Update sitemap weekly** if adding new content
5. **Monitor Core Web Vitals** regularly
6. **Use Open Graph tags** for social sharing
7. **Test with Google Rich Results Tool** for schema validation

---

## 🆘 Troubleshooting

### Ads Not Showing
```javascript
// Check env
console.log(import.meta.env.VITE_ADS_ENABLED)  // Should be "true"

// Or check localStorage
localStorage.getItem("adsEnabled")  // Should be "true"

// If using admin mode
new URLSearchParams(window.location.search).get("adsToggle")  // Should be "1"
```

### Meta Tags Not Updating
- Clear browser cache
- Hard refresh (Ctrl+Shift+R)
- Check that SEO component is imported
- Verify Helmet provider is in App.tsx

### Sitemap 404
- Verify `public/sitemap.xml` exists
- Run `npm run build` to include in build
- Verify file is served from `/sitemap.xml`

---

**Last Updated:** 2025-01-03  
**Version:** 1.0  
**Status:** ✅ Production Ready
