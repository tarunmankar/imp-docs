Role: You are a Senior Technical SEO Specialist & Web Architect. Perform a 100% comprehensive, exhaustive SEO Audit for the website.

Audit the entire codebase/website across the following 8 critical pillars and provide a detailed diagnostic report with exact issue locations and actionable fixes:

### 1. 🏗️ Technical SEO & Indexability
- Canonical URL Consistency (strictly enforce single primary domain: www vs non-www, https vs http, no trailing slash mismatches).
- Sitemap.xml (presence, valid XML syntax, proper frequency, priority scores, 0 broken 404 URLs).
- Robots.txt (rules, User-agent directives, disallow paths, host declaration, sitemap link).
- Crawlability & HTTP Status (0 orphan pages, 301 redirects, no 404 broken links, noindex/nofollow checks).

### 2. 📝 On-Page SEO & Content Structure
- Title Tags (50–60 chars, unique per page, primary keyword placed early).
- Meta Descriptions (145–160 chars, compelling CTR copy, unique).
- Heading Hierarchy (Exactly ONE <h1> per page + logical <h2>-<h4> fallback without skipping levels).
- Image Optimization (descriptive alt text, loading="lazy", WebP/AVIF formats).
- Internal Linking (descriptive anchor text, cross-linking, 0 broken internal anchors).
- Content Freshness (dynamic year tokens 2026/[YEAR] in titles/descriptions).

### 3. 🏷️ Structured Data (JSON-LD Schemas)
- Homepage Schema (WebSite & Organization/Person JSON-LD).
- Article Schema (Article/BlogPosting schema on all articles with headline, image, author, datePublished).
- Breadcrumb Schema (BreadcrumbList schema on subpages & categories).
- FAQ Schema (FAQPage schema on Q&A content).

### 4. 📲 Social Sharing Metadata (OpenGraph & Twitter Cards)
- OpenGraph Tags (og:title, og:description, og:url, og:site_name, og:type, og:locale, og:image).
- Twitter Card Tags (twitter:card summary_large_image, twitter:title, twitter:description, twitter:image).
- Asset Verification (verify og:image file path exists in public assets and returns HTTP 200 OK).

### 5. ⚡ Performance & Core Web Vitals
- TTFB (Time to First Byte < 200ms).
- LCP (Largest Contentful Paint < 2.5s).
- CLS (Cumulative Layout Shift < 0.1).
- Asset Delivery (CSS/JS minification, font-display: swap).

### 6. 📱 Mobile UX & Accessibility
- Viewport Tag (<meta name="viewport" content="width=device-width, initial-scale=1.0">).
- Touch Targets (buttons/links > 48x48px clickable area).
- Semantic HTML (proper usage of <header>, <nav>, <main>, <article>, <footer>).
- Accessibility (WCAG AA color contrast, aria-labels on icons).

### 7. 🔗 URL Architecture & Clean Slugs
- Clean Slugs (lowercase, hyphenated, short, keyword-rich, no query string bloat).
- Breadcrumb Trail (visible breadcrumb navigation).

### 8. 📊 Analytics & Search Verification
- Google Analytics (GA4/GTAG script with non-blocking afterInteractive loading).
- Webmaster Verification (Google Search Console meta tag or HTML verification file intact).

Deliver the output as a clean Scorecard Table + List of Specific Critical Bugs + Actionable Fixes.
