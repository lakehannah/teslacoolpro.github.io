# Tesla Cool Pro - 30-Day SEO Action Plan

**Start Date:** June 26, 2026  
**End Date:** July 25, 2026  
**Owner:** SEO Specialist  
**Goal:** Establish foundational SEO dominance for Utah Tesla services

---

## Week 1: Foundation & Technical Setup (Days 1-7)

### Day 1 (June 26) - Google Business Profile Setup

**Priority:** 🔴 CRITICAL

**Tasks:**
- [ ] Verify if GBP exists (search "Tesla Cool Pro Utah" on Google Maps)
- [ ] Claim/create GBP at google.com/business
- [ ] Enter exact business info:
  - Name: Tesla Cool Pro
  - Category: Auto Repair Shop (primary), Car Detailing Service (secondary)
  - Phone: (385) 325-1912
  - Website: https://teslacoolpro.com?utm_source=google&utm_medium=organic&utm_campaign=gbp
  - Service areas: Utah County, Salt Lake County, Lehi, Provo, Salt Lake City, Murray, Sandy
  - Hours: "By Appointment" (Mon-Sat 8am-6pm)
- [ ] Write 750-character description with keywords
- [ ] Upload 10+ photos minimum (logo, team, equipment, before/after)
- [ ] Enable messaging feature
- [ ] Add services menu with pricing:
  - Standard Clean: $250
  - BOGO Special: $450
- [ ] Set up Q&A: Seed 5 common questions + answers

**Time Estimate:** 2-3 hours

**Success Metric:** GBP live and verified

---

### Day 2 (June 27) - Technical SEO Fixes

**Priority:** 🔴 CRITICAL

**Tasks:**
- [ ] Update index.html title tag:
  ```html
  <title>Tesla Radiator Cleaning Utah | Model 3/Y AC Repair - Tesla Cool Pro</title>
  ```
- [ ] Update meta description:
  ```html
  <meta name="description" content="Expert Tesla radiator cleaning & AC restoration in Utah. Model 3 & Model Y specialists. Mobile service to your home/office. Save $1,000+ vs Tesla Service Center. Book online: (385) 325-1912">
  ```
- [ ] Add H1 to payment.html: `<h1>Secure Online Booking - Tesla Radiator Cleaning</h1>`
- [ ] Add meta description to payment.html
- [ ] Compress images:
  - logo.png (currently 1.08 MB → target <200 KB)
  - tesla-service-bumper-off.jpg (optimize for web)
  - Use TinyPNG or ImageOptim
- [ ] Add alt text to ALL images:
  ```html
  <img src="logo.png" alt="Tesla Cool Pro Logo - Mobile Radiator Cleaning Service Utah">
  <img src="tesla-service-bumper-off.jpg" alt="Tesla Model 3 with front bumper removed for professional radiator cleaning service in Utah">
  ```

**Time Estimate:** 2 hours

**Success Metric:** All critical on-page elements optimized

---

### Day 3 (June 28) - Schema Markup Implementation

**Priority:** 🔴 CRITICAL

**Tasks:**
- [ ] Add LocalBusiness schema to index.html (JSON-LD format)
- [ ] Add Service schema for radiator cleaning + AC restoration
- [ ] Add Review schema placeholder (for when reviews arrive)
- [ ] Add FAQ schema (prepare for FAQ page)
- [ ] Test schema with Google Rich Results Test tool
- [ ] Validate with Schema.org validator

**Schema Code Template:**
```json
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "AutoRepair",
  "name": "Tesla Cool Pro",
  "image": "https://teslacoolpro.com/logo.png",
  "telephone": "(385) 325-1912",
  "url": "https://teslacoolpro.com",
  "priceRange": "$$",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "Lehi",
    "addressRegion": "UT",
    "postalCode": "84043",
    "addressCountry": "US"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": 40.3916,
    "longitude": -111.8508
  },
  "openingHoursSpecification": {
    "@type": "OpeningHoursSpecification",
    "dayOfWeek": ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"],
    "opens": "08:00",
    "closes": "18:00"
  },
  "areaServed": [
    {"@type": "City", "name": "Lehi"},
    {"@type": "City", "name": "Provo"},
    {"@type": "City", "name": "Salt Lake City"},
    {"@type": "County", "name": "Utah County"},
    {"@type": "County", "name": "Salt Lake County"}
  ],
  "servesCuisine": "Tesla Model 3, Model Y, Model S, Model X"
}
</script>
```

**Time Estimate:** 2-3 hours

**Success Metric:** Schema validates without errors, eligible for rich results

---

### Day 4 (June 29) - Analytics & Tracking Setup

**Priority:** 🔴 CRITICAL

**Tasks:**
- [ ] Create Google Analytics 4 property
- [ ] Install GA4 tracking code on both pages
- [ ] Set up Google Search Console:
  - Verify domain ownership (DNS or HTML file method)
  - Submit sitemap (create sitemap.xml first)
  - Enable enhanced search data
- [ ] Set up Bing Webmaster Tools
- [ ] Create XML sitemap (include index.html, payment.html, future pages)
- [ ] Configure conversion goals in GA4:
  - Payment page visits
  - Phone number clicks
  - Form submissions
- [ ] Set up UTM tracking for all external links

**Sitemap.xml Template:**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://teslacoolpro.com/</loc>
    <lastmod>2026-06-26</lastmod>
    <changefreq>weekly</changefreq>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://teslacoolpro.com/payment.html</loc>
    <lastmod>2026-06-26</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
</urlset>
```

**Time Estimate:** 3 hours

**Success Metric:** GA4 collecting data, GSC verified, sitemap submitted

---

### Day 5 (June 30) - Citation Building (Tier 1)

**Priority:** 🟠 HIGH

**Tasks:**
- [ ] Create/optimize Bing Places listing
- [ ] Create/optimize Apple Maps Connect listing
- [ ] Create Yelp Business page
- [ ] Create Facebook Business page
- [ ] Ensure NAP consistency across all platforms:
  - Name: Tesla Cool Pro (exact match)
  - Phone: (385) 325-1912 (exact format)
  - Website: https://teslacoolpro.com
  - Service areas listed identically

**Time Estimate:** 3-4 hours

**Success Metric:** 5 Tier 1 citations live and consistent

---

### Day 6 (July 1) - Location Pages Creation (Part 1)

**Priority:** 🟠 HIGH

**Tasks:**
- [ ] Create utah-county.html landing page
- [ ] Create salt-lake-county.html landing page
- [ ] Optimize each page for local keywords:
  - Unique title tags
  - Unique meta descriptions
  - Location-specific H1/H2s
  - Local testimonials (if available)
  - Embedded Google Map
  - City-specific content (150+ words each)

**Content Outline for Each Location Page:**
1. H1: "Tesla Radiator Cleaning in [Location]"
2. Intro paragraph with location + service keywords
3. Common Tesla AC problems in [Location] area
4. Why choose mobile service in [Location]
5. Service area map/list of cities covered
6. Local testimonials (or general if none yet)
7. CTA: "Book Service in [Location]"

**Time Estimate:** 4 hours

**Success Metric:** 2 location pages published and indexed

---

### Day 7 (July 2) - Location Pages Creation (Part 2) + Weekly Review

**Priority:** 🟠 HIGH

**Tasks:**
- [ ] Create lehi.html landing page
- [ ] Create provo.html landing page
- [ ] Create slc.html landing page
- [ ] Add internal links from homepage to all location pages
- [ ] Add location pages to navigation menu
- [ ] Submit all new pages to Google Search Console for indexing
- [ ] **Weekly Review:**
  - Check GBP verification status
  - Review GA4 data (traffic, behavior)
  - Check GSC for crawl errors
  - Assess keyword ranking baseline (manual search)

**Time Estimate:** 4 hours + 1 hour review

**Success Metric:** 5 location pages live, internal linking complete

---

## Week 2: Content Launch & Review System (Days 8-14)

### Day 8 (July 3) - Blog Setup + Post #1

**Priority:** 🟠 HIGH

**Tasks:**
- [ ] Create blog index page (/blog or /articles)
- [ ] Publish Blog Post #1: "Why Your Tesla Model 3 AC Stops Working in Summer"
  - Target keyword: "Tesla AC not working cold"
  - Word count: 1,200-1,500 words
  - Include 3-5 internal links
  - Add FAQ section at end
  - Optimize images with alt text
  - Add social sharing buttons
- [ ] Create blog post template for future posts

**Time Estimate:** 4-5 hours

**Success Metric:** First blog post published and submitted for indexing

---

### Day 9 (July 4) - Blog Post #2 + Promotion

**Priority:** 🟠 HIGH

**Tasks:**
- [ ] Publish Blog Post #2: "How to Tell If Your Radiator is Clogged (Model 3/Y)"
  - Target keyword: "Tesla radiator clogged symptoms"
  - Include before/after photos
  - Add checklist/downloadable PDF lead magnet
- [ ] Share both blog posts on:
  - Facebook Business page
  - LinkedIn company page
  - Tesla owner Facebook groups (where allowed)
  - Reddit r/TeslaMotors (value-first, not spammy)

**Time Estimate:** 4 hours

**Success Metric:** 2 blog posts live, initial social promotion complete

---

### Day 10 (July 5) - Review Generation System Setup

**Priority:** 🔴 CRITICAL

**Tasks:**
- [ ] Create Google review direct link (short URL)
- [ ] Set up SMS review request template (send 2 hours after service)
- [ ] Set up email review request template (send 24 hours after service)
- [ ] Create in-person review ask script for technicians
- [ ] Design QR code for review requests (print on invoices/business cards)
- [ ] Add review request link to payment confirmation page
- [ ] Add review link to email signatures

**Templates Created:**
- SMS template (160 chars max)
- Email template (mobile-optimized)
- In-person script (natural, not robotic)
- Follow-up sequence (Day 1, Day 3, Day 7 if no review)

**Time Estimate:** 3 hours

**Success Metric:** Review generation system fully automated

---

### Day 11 (July 6) - Blog Post #3

**Priority:** 🟠 HIGH

**Tasks:**
- [ ] Publish Blog Post #3: "Tesla Radiator Cleaning Cost: DIY vs Professional"
  - Target keyword: "Tesla radiator cleaning cost"
  - Include cost breakdown table
  - Risk comparison (DIY damage vs professional warranty)
  - ROI calculation (preventive vs reactive repair costs)
- [ ] Interlink with Posts #1 and #2
- [ ] Add CTA to book service at end

**Time Estimate:** 3-4 hours

**Success Metric:** 3 blog posts published, interlinked

---

### Day 12 (July 7) - Blog Post #4 + FAQ Page

**Priority:** 🟠 HIGH

**Tasks:**
- [ ] Publish Blog Post #4: "Does Radiator Cleaning Void Tesla Warranty?"
  - Target keyword: "Tesla warranty AC cleaning"
  - Address common fears/misconceptions
  - Quote Tesla warranty guidelines
  - Include customer testimonials about warranty safety
- [ ] Create FAQ page (/faq)
  - 15-20 common questions
  - Add FAQ schema markup
  - Link to relevant blog posts
  - Include video answers where possible

**Time Estimate:** 4-5 hours

**Success Metric:** 4 cornerstone blog posts + FAQ page live

---

### Day 13 (July 8) - Citation Building (Tier 2)

**Priority:** 🟡 MEDIUM

**Tasks:**
- [ ] YellowPages.com listing
- [ ] Manta.com listing
- [ ] Foursquare for Business
- [ ] Better Business Bureau (BBB) profile
- [ ] MapQuest business listing
- [ ] Local Utah directories:
  - Utah Valley Chamber of Commerce
  - Salt Lake Chamber
  - City-specific business directories

**Time Estimate:** 3-4 hours

**Success Metric:** 10+ total citations live

---

### Day 14 (July 9) - Week 2 Review + GBP Optimization

**Priority:** 🟡 MEDIUM

**Tasks:**
- [ ] **Analytics Review:**
  - Organic traffic trends (GA4)
  - Top landing pages
  - Bounce rates
  - Conversion rate (visits to bookings)
- [ ] **Search Console Review:**
  - Index coverage report
  - Search queries (impressions, clicks, CTR)
  - Mobile usability errors
- [ ] **GBP Optimization:**
  - Post first Google Post (tip/educational)
  - Add 5+ new photos to GBP
  - Respond to any reviews received
  - Check Q&A for new questions
- [ ] **Ranking Check:**
  - Manual search for top 10 keywords
  - Document current positions (baseline)

**Time Estimate:** 2-3 hours

**Success Metric:** Performance baseline established, GBP active

---

## Week 3: Link Building & Authority (Days 15-21)

### Day 15 (July 10) - Partner Outreach (Link Building)

**Priority:** 🟡 MEDIUM

**Tasks:**
- [ ] Identify 20 potential partner businesses:
  - Tesla wrap shops
  - Mobile detailers (non-competing)
  - EV charger installers
  - Auto glass shops
  - Tesla photographers
- [ ] Craft partnership outreach email template
- [ ] Send 10 personalized outreach emails
- [ ] Offer reciprocal value (referrals, co-marketing, not just link swaps)

**Outreach Email Template:**
```
Subject: Partnership Opportunity - Tesla Cool Pro x [Their Business]

Hi [Name],

I'm [Your Name] with Tesla Cool Pro, a mobile Tesla radiator cleaning service here in Utah. 

I noticed we both serve the Tesla community, and I think there's a great opportunity for us to help each other out. Our customers often need [their service], and I bet your customers could benefit from our specialized AC/radiator cleaning.

Would you be open to:
- Cross-referring customers?
- Featuring each other on our websites?
- Maybe collaborating on a social media giveaway?

No pressure at all - just think it could be a win-win. Let me know if you'd like to chat!

Best,
[Your Name]
Tesla Cool Pro
(385) 325-1912
```

**Time Estimate:** 3 hours

**Success Metric:** 10 outreach emails sent, 2-3 responses expected

---

### Day 16 (July 11) - Guest Post Pitching

**Priority:** 🟡 MEDIUM

**Tasks:**
- [ ] Identify 10 Tesla/EV blogs accepting guest posts:
  - Teslarati.com
  - Electrek.co
  - InsideEVs.com
  - The Tesla Guide
  - EV Announcements
  - CleanTechnica
- [ ] Pitch 5 guest post ideas:
  - "The Hidden Maintenance Issue Every Tesla Owner Ignores"
  - "Why Your Tesla's AC Fails in Summer (And How to Prevent It)"
  - "Mobile vs. Dealership: Real Cost of Tesla AC Service"
- [ ] Prepare author bio with backlink to teslacoolpro.com

**Time Estimate:** 3-4 hours

**Success Metric:** 5 guest post pitches sent

---

### Day 17 (July 12) - HARO Setup + Response

**Priority:** 🟡 MEDIUM

**Tasks:**
- [ ] Sign up for Help A Reporter Out (HARO) at helpareporter.com
- [ ] Set up daily email alerts for categories:
  - Automotive
  - Small Business
  - Technology/EVs
- [ ] Monitor queries daily
- [ ] Respond to 3-5 relevant queries with expert insights
- [ ] Include Tesla Cool Pro credentials in bio

**HARO Response Template:**
```
Query: [Insert query topic]

Expert Commentary:

[Provide 2-3 paragraphs of valuable, quotable insight]

Key Points:
- [Statistic or surprising fact]
- [Actionable advice for readers]
- [Unique perspective as Tesla specialist]

About the Expert:
[Your Name] is founder of Tesla Cool Pro, Utah's premier mobile Tesla radiator cleaning service. With 20+ years of HVAC experience and 500+ Teslas serviced, [he/she] specializes in preventing costly AC failures in Model 3 and Model Y vehicles.

Contact: (385) 325-1912 | [email] | teslacoolpro.com
```

**Time Estimate:** 2 hours setup + 30 min/day ongoing

**Success Metric:** HARO profile active, 3+ responses sent

---

### Day 18 (July 13) - Local News Pitch

**Priority:** 🟡 MEDIUM

**Tasks:**
- [ ] Identify 5 local Utah news outlets:
  - KSL.com
  - ABC4 Utah
  - Fox13 Now
  - The Salt Lake Tribune
  - Utah Valley Magazine
- [ ] Craft news pitch: "Utah Entrepreneur Solves Common Tesla Problem"
- [ ] Send pitch to business/automotive reporters
- [ ] Offer exclusive first interview + demo service

**News Pitch Angle:**
- Local entrepreneur angle
- Unique solution to widespread Tesla issue
- Summer heatwave timing (newsworthy)
- Human interest: helping families avoid $2,000+ repairs
- Visual: before/after photos, mobile service in action

**Time Estimate:** 3 hours

**Success Metric:** News pitch sent to 5 outlets

---

### Day 19 (July 14) - Content Upgrade + Lead Magnet

**Priority:** 🟡 MEDIUM

**Tasks:**
- [ ] Create downloadable PDF: "Tesla AC Maintenance Checklist"
- [ ] Add opt-in form to blog posts (email capture)
- [ ] Set up email automation for checklist delivery
- [ ] Promote lead magnet on social media
- [ ] Track downloads in GA4 as conversion goal

**Lead Magnet Content:**
- Seasonal maintenance schedule
- DIY inspection checklist (safe tasks only)
- Warning signs requiring professional service
- Cost comparison worksheet
- Exclusive discount code for subscribers

**Time Estimate:** 3-4 hours

**Success Metric:** Lead magnet live, email capture active

---

### Day 20 (July 15) - Social Proof Expansion

**Priority:** 🟡 MEDIUM

**Tasks:**
- [ ] Create testimonials page (/testimonials)
- [ ] Aggregate all existing reviews/testimonials
- [ ] Add aggregate review schema markup
- [ ] Screenshot best social media mentions
- [ ] Record 2-3 video testimonials (offer $20 discount for participation)
- [ ] Add testimonial widgets to homepage

**Time Estimate:** 3 hours

**Success Metric:** Testimonials page live with 10+ reviews

---

### Day 21 (July 16) - Week 3 Review + Optimization

**Priority:** 🟡 MEDIUM

**Tasks:**
- [ ] **Link Building Review:**
  - Count new backlinks (use Ahrefs free checker or similar)
  - Domain authority of linking sites
  - Follow-up on pending guest post pitches
- [ ] **Content Performance:**
  - Most visited blog posts
  - Time on page
  - Social shares
  - Comments/engagement
- [ ] **GBP Activity:**
  - Post second Google Post (before/after transformation)
  - Add 5 new photos
  - Respond to new reviews
  - Check insights (views, clicks, calls)
- [ ] **Adjust Strategy:**
  - Double down on what's working
  - Pivot away from low-performers
  - Plan Week 4 priorities

**Time Estimate:** 2-3 hours

**Success Metric:** Backlink profile growing, content strategy refined

---

## Week 4: Optimization & Scale (Days 22-30)

### Day 22 (July 17) - Technical SEO Audit #2

**Priority:** 🟡 MEDIUM

**Tasks:**
- [ ] Run full site crawl (Screaming Frog free version or similar)
- [ ] Check for:
  - Broken links (404 errors)
  - Duplicate content issues
  - Missing meta tags on new pages
  - Slow-loading pages
  - Mobile usability errors
- [ ] Fix all critical errors found
- [ ] Re-submit updated sitemap to GSC

**Time Estimate:** 3 hours

**Success Metric:** Zero critical technical errors

---

### Day 23 (July 18) - Blog Post #5 + #6

**Priority:** 🟢 ONGOING

**Tasks:**
- [ ] Publish Blog Post #5: "Model Y Overheating Problems: Solutions That Work"
  - Target: "Model Y overheating summer Utah"
  - Include real case studies
  - Add temperature data/efficiency metrics
- [ ] Publish Blog Post #6: "Best Tesla Maintenance Services in Utah [2026]"
  - Target: "best Tesla mechanic Utah"
  - Comprehensive directory/guide format
  - Position Tesla Cool Pro as top choice (naturally)
  - Link to all service/location pages

**Time Estimate:** 5-6 hours

**Success Metric:** 6 total blog posts published

---

### Day 24 (July 19) - Google Posts Batch Creation

**Priority:** 🟢 ONGOING

**Tasks:**
- [ ] Create 4 Google Posts for next month (weekly rotation):
  - **Week 1 (Tip):** "5 Signs Your Tesla AC Needs Cleaning"
  - **Week 2 (Before/After):** Dramatic transformation photo
  - **Week 3 (Offer):** "Summer Flash Sale - $250 Standard Clean"
  - **Week 4 (Update):** "Now Serving [New City/Area]"
- [ ] Schedule posts using GBP dashboard
- [ ] Include CTAs and booking links in each post
- [ ] Use high-quality images (1080x1080 minimum)

**Time Estimate:** 2-3 hours

**Success Metric:** 4 weeks of Google Posts scheduled

---

### Day 25 (July 20) - Review Velocity Push

**Priority:** 🟢 ONGOING

**Tasks:**
- [ ] Contact last 20 customers with review request
- [ ] Offer entry into monthly $100 service giveaway for reviews
- [ ] Share best recent reviews on social media
- [ ] Respond to ALL reviews within 24 hours (positive and negative)
- [ ] Set up review monitoring alerts (Google Alerts for brand name)

**Time Estimate:** 2 hours

**Success Metric:** 10+ new reviews this week

---

### Day 26 (July 21) - Competitor Analysis Update

**Priority:** 🟢 ONGOING

**Tasks:**
- [ ] Re-check top 5 competitor rankings
- [ ] Analyze their new content/backlinks
- [ ] Identify gaps/opportunities
- [ ] Adjust keyword targets if needed
- [ ] Document competitive advantages to emphasize

**Time Estimate:** 2 hours

**Success Metric:** Competitive positioning updated

---

### Day 27 (July 22) - Internal Linking Optimization

**Priority:** 🟢 ONGOING

**Tasks:**
- [ ] Audit internal link structure
- [ ] Ensure all pages have 3+ internal links pointing to them
- [ ] Add contextual links within blog posts to service pages
- [ ] Create "Related Posts" sections on blog articles
- [ ] Add breadcrumb navigation
- [ ] Ensure homepage links to all major pages

**Time Estimate:** 2-3 hours

**Success Metric:** Strong internal link network established

---

### Day 28 (July 23) - Content Refresh + Update

**Priority:** 🟢 ONGOING

**Tasks:**
- [ ] Update original welcome blog post with fresh data
- [ ] Add new testimonials to location pages
- [ ] Refresh pricing/promotion info site-wide
- [ ] Update "last updated" dates on all content
- [ ] Add new before/after photos to gallery

**Time Estimate:** 2 hours

**Success Metric:** All content current and accurate

---

### Day 29 (July 24) - Monthly Reporting Prep

**Priority:** 🟢 ONGOING

**Tasks:**
- [ ] Compile all metrics into dashboard:
  - Organic traffic (GA4)
  - Keyword rankings (top 20)
  - GBP insights (views, clicks, calls)
  - Review count & average rating
  - Backlink count
  - Top landing pages
  - Conversion rate
- [ ] Compare to Day 1 baseline
- [ ] Calculate ROI (time invested vs bookings gained)
- [ ] Prepare Month 2 plan based on learnings

**Time Estimate:** 3 hours

**Success Metric:** Comprehensive monthly report ready

---

### Day 30 (July 25) - Month 1 Review + Month 2 Planning

**Priority:** 🟢 ONGOING

**Tasks:**
- [ ] **Full Month Review:**
  - What worked exceptionally well?
  - What underperformed expectations?
  - Which keywords are ranking?
  - Which content drives most traffic/conversions?
  - Review velocity vs goals
- [ ] **Month 2 Goals Setting:**
  - Increase review target to 25/month
  - Target 10+ new backlinks
  - Publish 8 new blog posts
  - Achieve top 3 rankings for 5 P0 keywords
  - Expand to 3 new location pages
- [ ] **Resource Allocation:**
  - Time budget per activity
  - Tools/software needs
  - Outsourcing opportunities (content writing, link building)
- [ ] **Report to Marketing Director:**
  - Submit monthly SEO report
  - Present key wins
  - Request support for Month 2 initiatives

**Time Estimate:** 4 hours

**Success Metric:** Month 1 complete, Month 2 plan approved

---

## Daily Habits (Throughout 30 Days)

### Morning Routine (15 min)
- [ ] Check GBP for new reviews/messages
- [ ] Respond to any reviews (within 24 hours)
- [ ] Monitor GA4 for traffic anomalies
- [ ] Check GSC for crawl errors

### Weekly Routine (2 hours/week)
- [ ] Publish 1 Google Post
- [ ] Add 5 new photos to GBP
- [ ] Send review requests to recent customers
- [ ] Engage in Tesla communities (Facebook groups, Reddit)
- [ ] Track keyword rankings

### Ongoing (30 min/day)
- [ ] Social media engagement (comment on Tesla accounts)
- [ ] HARO query monitoring/response
- [ ] Community building (answer questions, provide value)

---

## Success Metrics - 30 Day Targets

| Metric | Baseline | Day 30 Target |
|--------|----------|---------------|
| Organic Traffic | 0-50/mo | 500+/mo |
| Keyword Rankings (Top 10) | 0 | 10+ keywords |
| Google Reviews | 0-5 | 25+ reviews |
| GBP Profile Views | 0 | 1,000+/mo |
| Website Clicks from GBP | 0 | 100+/mo |
| Backlinks | 0 | 10+ quality links |
| Blog Posts Published | 1 | 6 posts |
| Location Pages | 0 | 5 pages |
| Citations | 0 | 15+ listings |
| GA4 Conversions | 0 | 20+ bookings |

---

## Tools & Resources Needed

**Free Tools:**
- Google Analytics 4
- Google Search Console
- Google Business Profile
- Bing Webmaster Tools
- Google Keyword Planner
- Google Rich Results Test
- Schema.org Validator
- HARO (Help A Reporter Out)
- TinyPNG (image compression)

**Recommended Paid Tools (Month 2+):**
- Ahrefs or SEMrush ($99-199/mo) - keyword tracking, competitor analysis
- BrightLocal ($29/mo) - local rank tracking, citation management
- Moz Local ($14/mo) - citation distribution
- Screaming Frog (£149/year) - technical SEO audits

---

## Risk Mitigation

**If GBP Verification Delays:**
- Continue building citations
- Focus on on-page SEO
- Accelerate content creation
- Pursue link building aggressively

**If Rankings Don't Improve by Day 30:**
- Audit content quality (E-E-A-T signals)
- Increase backlink velocity
- Expand location page content
- Add more internal linking
- Consider technical SEO deep-dive

**If Review Generation Stalls:**
- Increase incentive value ($25 vs $10)
- Simplify review process (direct link, QR code)
- Train technicians on in-person asks
- Add review request to email signature
- Follow up more aggressively (Day 1, 3, 7, 14)

---

**Prepared by:** SEO Specialist, Tesla Cool Pro Marketing Team  
**Start Date:** June 26, 2026  
**Review Cadence:** Weekly check-ins, Monthly comprehensive report

*Tesla Cool Pro - Clean Air. Mobile Service. Tesla Expertise.*
