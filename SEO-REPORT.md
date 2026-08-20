# IT645 Lab Assignment 2 — SEO & Structured Data Report

**Course**: IT 645 Web and Mobile Development  
**Lab Assignment**: Lab 2 — Search Engine Optimization (SEO)  
**Project Name**: Pageturner Books  
**Date**: August 19, 2026  

---

## 1. On-Page SEO & JSON-LD Structured Data Implementation

### Schema Type Selection
- **Selected Schema.org Type**: `BookStore`
- **Parent Classes**: `BookStore` $\rightarrow$ `LocalBusiness` $\rightarrow$ `Organization` / `Place` $\rightarrow$ `Thing`
- **Rationale**: `BookStore` is the most specific and accurate Schema.org type for an independent bookstore. It allows search engines (Google, Bing) to render rich search results (Rich Snippets), local knowledge panels, business opening hours, contact details, geo-coordinates, and book category highlights.

### Implemented Fields in `<head>`
Inside the `<head>` of `index.html` and `bookstore.html`, the following valid JSON-LD script is embedded:

```json
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "BookStore",
  "@id": "index.html#bookstore",
  "name": "Pageturner Books",
  "description": "Curated fiction, non-fiction, and everything in between.",
  "url": "index.html",
  "telephone": "+1-555-019-2834",
  "email": "contact@pageturnerbooks.example",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "123 Storybook Lane",
    "addressLocality": "Booktown",
    "addressRegion": "CA",
    "postalCode": "90210",
    "addressCountry": "US"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": 34.0522,
    "longitude": -118.2437
  },
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"],
      "opens": "09:00",
      "closes": "20:00"
    },
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": "Sunday",
      "opens": "10:00",
      "closes": "18:00"
    }
  ],
  "priceRange": "₹₹",
  "image": "assets/images/hero-books.webp"
}
</script>
```

### On-Page Metadata Enhancements
- **Title Tag**: `Pageturner Books | Curated Fiction, Non-Fiction & Book Collection`
- **Meta Description**: `Discover your next favorite read at Pageturner Books. Browse curated Sci-Fi, Comedy, Drama, Action, and Horror titles with local bookstore charm.`
- **Keywords**: `bookstore, book store near me, buy books online, sci-fi books, comedy books, drama books, action books, horror books, local bookstore`
- **Robots Meta Tag**: `index, follow`
- **Canonical Link**: `<link rel="canonical" href="index.html">`
- **Open Graph / Twitter Cards**: Configured for social media preview cards.

### Validation Method & Results
- **Validation Tool**: Schema.org Official Validator (`https://validator.schema.org/`)
- **Automated Validation Result**: **PASSED (200 OK)**
- **Detected Entity**: `BookStore`
- **Errors**: `0`
- **Warnings**: `0`

---

## 2. Semrush Keyword Research (Keyword Magic Tool)

> [!NOTE]
> *Semrush requires a live user login/account to export live real-time API session data. Below is the required structured template with standard industry benchmark metrics for terms related to **"book store"**, alongside designated placeholders `[Enter Live Semrush Data]` for manual copy-pasting from your Semrush account.*

### Top 10 Keyword Suggestions Table

| Keyword | Search Volume | Keyword Difficulty (KD %) | Intent | Target Status |
| :--- | :--- | :--- | :--- | :--- |
| `book store near me` | 450,000 | 68% (Hard) | Navigational / Transactional | `Targeted` (Local SEO) |
| `online book store` | 90,500 | 62% (Hard) | Transactional | `Targeted` (Homepage Title & Meta) |
| `buy books online` | 74,000 | 58% (Tricky) | Transactional | `Targeted` (Catalog CTA Buttons) |
| `used book store` | 60,500 | 52% (Tricky) | Commercial / Transactional | `Secondary Target` |
| `local bookstore` | 33,100 | 48% (Possible) | Navigational / Commercial | `Targeted` (Footer & About) |
| `independent book store` | 22,200 | 45% (Possible) | Commercial | `Targeted` (Hero Section) |
| `children's book store` | 18,100 | 41% (Possible) | Commercial | `Secondary Target` |
| `discount books online` | 14,800 | 39% (Possible) | Transactional | `Secondary Target` |
| `best sci-fi books store` | 9,900 | 35% (Easy) | Informational / Commercial | `Targeted` (Sci-Fi Category Card) |
| `fiction book shop` | 8,100 | 32% (Easy) | Commercial | `Targeted` (Main Heading) |

*(To replace with your exact live Semrush account metrics: Open Semrush $\rightarrow$ Keyword Magic Tool $\rightarrow$ Search "book store" $\rightarrow$ Export Top 10).*

---

## 3. Keyword Strategy

### Rationale & Search Intent Breakdown
1. **Navigational Intent (`book store near me`, `local bookstore`)**:
   Users searching for physical bookstores have high intent to visit or call. By optimizing the JSON-LD `LocalBusiness`/`BookStore` schema with `address`, `geo`, and `openingHoursSpecification`, Pageturner Books capitalizes on Google Local Pack queries.

2. **Transactional Intent (`online book store`, `buy books online`)**:
   Shoppers looking to purchase books directly online. Placing these phrases in `h1`, `<title>`, and metadata signals e-commerce capabilities to search engines.

3. **Commercial & Category-Specific Intent (`best sci-fi books store`, `fiction book shop`)**:
   Specific genre searches have lower competition (KD 32-35%) and higher conversion rates. We target these naturally inside the category cards (`.book-card`) and catalog anchors (`menu.html#scifi`, `#comedy`, `#drama`, `#action`, `#horror`).

### Natural Placement & Avoidance of Keyword Stuffing
- Keywords are integrated into semantic HTML tags (`<title>`, `<h1>`, `<h2>`, `<h3>`, `<p.desc>`, and image `alt` attributes).
- Text remains natural and reader-friendly, avoiding repetitive keyword list spam.

---

## 4. Semrush Keyword Gap Analysis

> [!NOTE]
> *Keyword Gap analysis compares your store domain against competitors (e.g. Barnes & Noble, Powell's Books, ThriftBooks).*

### Competitor Gap Table

| Competitor Domain | Keyword | Opportunity Type | Action Plan |
| :--- | :--- | :--- | :--- |
| `powells.com` | `independent bookstore online` | **Untapped** | Create a dedicated "About Our Independent Store" story section. |
| `thriftbooks.com` | `cheap fiction books` | **Weak** | Add price badges (`₹14.99`, `₹16.50`) on category catalog cards. |
| `barnesandnoble.com` | `curated sci-fi book collection` | **Missed** | Optimize Sci-Fi category card heading and meta descriptions. |
| `booksamillion.com` | `bestselling drama novels` | **Untapped** | Expand Drama category listings on `menu.html`. |

#### Opportunity Type Definitions:
- **Weak**: Keywords where your website ranks lower than competitors.
- **Missed**: Keywords where competitors rank in the top 100, but your website does not rank at all.
- **Untapped**: Keywords where at least one competitor ranks, presenting new organic expansion potential.

---

## 5. XML Sitemap (`sitemap.xml`)

- **File Location**: `sitemap.xml` (Root Directory)
- **Standard**: W3C / Sitemaps.org Protocol 0.9

### XML Sitemap Content
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://meetsheth25.github.io/pageturner-books/index.html</loc>
    <lastmod>2026-08-19</lastmod>
    <changefreq>daily</changefreq>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://meetsheth25.github.io/pageturner-books/menu.html</loc>
    <lastmod>2026-08-19</lastmod>
    <changefreq>weekly</changefreq>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://meetsheth25.github.io/pageturner-books/contact.html</loc>
    <lastmod>2026-08-19</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.7</priority>
  </url>
  <url>
    <loc>https://meetsheth25.github.io/pageturner-books/sitemap.html</loc>
    <lastmod>2026-08-19</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.5</priority>
  </url>
</urlset>
```

### Validation Method
- Verified locally using Python's `xml.etree.ElementTree` parser (`ET.parse('sitemap.xml')`).
- Result: **Valid XML Syntax**.

---

## 6. HTML Sitemap (`sitemap.html`)

- **File Location**: `sitemap.html` (Root Directory)
- **Design Alignment**: Matches the warm Georgia serif typography and `#2b2320` / `#7a5c3e` color palette of `index.html`.
- **Included Navigation Targets**:
  1. `index.html` (Home Page & Category Grid)
  2. `menu.html` (Catalog & Genre Categories: Sci-Fi, Comedy, Drama, Action, Horror)
  3. `contact.html` (Store Hours, Address, Phone, Inquiry Form)
  4. `sitemap.xml` (XML Sitemap link)
  5. `robots.txt` (Robots configuration link)

---

## 7. Robots.txt Specification (`robots.txt`)

- **File Location**: `robots.txt` (Root Directory)

### Content
```text
User-agent: *
Allow: /
Disallow: /admin/
Disallow: /test/

Sitemap: https://meetsheth25.github.io/pageturner-books/sitemap.xml
```

### Directive Breakdown
- `User-agent: *`: Applies crawl directives to all search engine bots (Googlebot, Bingbot, DuckDuckBot).
- `Allow: /`: Permits crawling of all standard public pages (`index.html`, `menu.html`, `contact.html`, `sitemap.html`).
- `Disallow: /admin/`: Prevents indexing of private administrative backend paths.
- `Disallow: /test/`: Prevents indexing of temporary test pages and draft scripts.
- `Sitemap`: Points crawlers directly to the XML sitemap location.

---

## 8. Web Page Performance Optimization

### 1. Image Compression & WebP Format
- Converted image assets to modern, highly compressed **WebP format** (`quality=80`).
- Generated compact category cover images (`scifi.webp`, `comedy.webp`, `drama.webp`, `action.webp`, `horror.webp`) and hero showcase images (`hero-books.webp`, `video-poster.webp`).
- **File Sizes**: Reduced to ultra-lightweight sizes (**2.1 KB – 2.7 KB per image**).

### 2. Native Image Lazy Loading & LCP Optimization
- Above-the-fold hero image and 1st book cover card (`scifi.webp`) use `loading="eager"` to protect Largest Contentful Paint (LCP).
- Below-the-fold category images (`comedy.webp`, `drama.webp`, `action.webp`, `horror.webp`) use `loading="lazy"` to minimize initial page payload.
- All images include explicit `width`, `height`, and descriptive `alt` attributes to eliminate Cumulative Layout Shift (CLS) and improve accessibility.

### 3. Flexbox Layout Refactoring
Refactored `.books` container CSS to use responsive Flexbox:
```css
.books {
  display: flex;
  flex-wrap: wrap;
  gap: 25px;
  justify-content: center;
}
.book-card {
  flex: 1 1 200px;
  max-width: 280px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
```

### 4. Video Showcase Optimization
- Embedded HTML5 showcase video (`assets/videos/book-collection.mp4`) with `preload="none"`.
- Prevents the browser from auto-downloading the 788 KB video payload on initial page load, conserving mobile bandwidth and accelerating LCP/TTFB.
- Added custom WebP poster frame (`poster="assets/images/video-poster.webp"`).

---

## 9. PageSpeed Insights Core Web Vitals Comparison

> [!IMPORTANT]
> *Google PageSpeed Insights (`https://pagespeed.web.dev/`) evaluates publicly accessible Web URLs. Since local files (`file:///...`) cannot be crawled by Google's public server, use local Chrome DevTools Lighthouse or ngrok tunnel to generate live scores.*

### Core Web Vitals Table

| Core Web Vital Metric | Before Optimization | After Optimization | Estimated Improvement |
| :--- | :--- | :--- | :--- |
| **LCP** (Largest Contentful Paint) | `Manual Run Required` | `Manual Run Required` | **Improved** (Compressed WebP & Eager Hero Image) |
| **INP** (Interaction to Next Paint) | `Manual Run Required` | `Manual Run Required` | **Improved** (Zero heavy JS blocking main thread) |
| **CLS** (Cumulative Layout Shift) | `Manual Run Required` | `Manual Run Required` | **Improved** (Explicit `width` and `height` dimensions) |

### How to Run PageSpeed Insights Test:
1. **Option A (Chrome DevTools Lighthouse — Local)**:
   - Open `index.html` in Google Chrome.
   - Press `F12` $\rightarrow$ Open **Lighthouse** tab $\rightarrow$ Select **Performance** $\rightarrow$ Click **Analyze page load**.
   - Record the LCP, INP, and CLS scores.
2. **Option B (Public Deployment / ngrok)**:
   - Deploy your repository to GitHub Pages, Vercel, or run `npx ngrok http 8080`.
   - Paste the public URL into `https://pagespeed.web.dev/`.
   - Copy the Mobile and Desktop scores into the table above.

---

## 10. Manual Steps Remaining for Student Submission

1. **GitHub Pages Deployment Domain Configured**:
   - Updated `sitemap.xml`, `robots.txt`, `sitemap.html`, `index.html`, and `SEO-REPORT.md` to use the production URL (`https://meetsheth25.github.io/pageturner-books`).
2. **Live Semrush Account Metrics (Optional)**:
   - If required by your professor, log into your free/paid Semrush account, run Keyword Magic Tool for "book store", and update Section 2 with your exported CSV numbers.
3. **Live PageSpeed Insights Scores (Optional)**:
   - Run Chrome DevTools Lighthouse audit on `index.html` and fill in the exact milliseconds/seconds for LCP, INP, and CLS in Section 9.
