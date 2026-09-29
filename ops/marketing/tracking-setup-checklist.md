# Tesla Cool Pro - Tracking & Conversion Setup Checklist

**Priority:** CRITICAL - Complete before launching any paid ads  
**Date:** June 25, 2026  
**Owner:** Paid Ads Specialist + Web Developer

---

## Phase 1: Meta (Facebook/Instagram) Pixel Setup

### Step 1: Create Meta Pixel
- [ ] Go to Meta Events Manager (business.facebook.com)
- [ ] Click "Connect Data Sources" → "Web" → "Meta Pixel"
- [ ] Name pixel: "Tesla Cool Pro - Main Pixel"
- [ ] Copy Pixel ID (will look like: 1234567890123456)

### Step 2: Install Pixel on Website
**Option A: Manual Installation (Recommended for full control)**
- [ ] Add base pixel code to `<head>` section of ALL pages:
  ```html
  <!-- Meta Pixel Code -->
  <script>
  !function(f,b,e,v,n,t,s)
  {if(f.fbq)return;n=f.fbq=function(){n.callMethod?
  n.callMethod.apply(n,arguments):n.queue.push(arguments)};
  if(!f._fbq)f._fbq=n;n.push=n;n.loaded=!0;n.version='2.0';
  n.queue=[];t=b.createElement(e);t.async=!0;
  t.src=v;s=b.getElementsByTagName(e)[0];
  s.parentNode.insertBefore(t,s)}(window, document,'script',
  'https://connect.facebook.net/en_US/fbevents.js');
  fbq('init', 'YOUR_PIXEL_ID_HERE');
  fbq('track', 'PageView');
  </script>
  <noscript><img height="1" width="1" style="display:none"
  src="https://www.facebook.com/tr?id=YOUR_PIXEL_ID_HERE&ev=PageView&noscript=1"
  /></noscript>
  <!-- End Meta Pixel Code -->
  ```
- [ ] Replace `YOUR_PIXEL_ID_HERE` with actual Pixel ID
- [ ] Add to: index.html, payment.html, all landing pages

**Option B: Google Tag Manager (If using GTM)**
- [ ] Create new tag in GTM
- [ ] Tag type: "Facebook Pixel"
- [ ] Enter Pixel ID
- [ ] Trigger: All Pages
- [ ] Publish container

### Step 3: Set Up Conversion Events
**Add event tracking to specific pages/actions:**

**Payment Page View (Initiate Checkout):**
- [ ] Add to `payment.html` page, after base pixel code:
  ```html
  <script>
    fbq('track', 'InitiateCheckout', {
      value: 250.00,
      currency: 'USD',
      content_name: 'Standard Clean - $250'
    });
  </script>
  ```

**Purchase Completion:**
- [ ] Create confirmation/thank-you page after payment (confirmation.html)
- [ ] Add purchase event to confirmation page:
  ```html
  <script>
    fbq('track', 'Purchase', {
      value: 250.00, // or dynamic value from payment processor
      currency: 'USD',
      content_name: 'Standard Clean'
    });
  </script>
  ```

**Lead Form Submission (if using contact form):**
- [ ] Add to form submission success handler:
  ```html
  <script>
    fbq('track', 'Lead', {
      content_name: 'Free Inspection Request'
    });
  </script>
  ```

### Step 4: Set Up Conversions API (CAPI)
**Why:** iOS 14+ privacy changes reduce pixel accuracy; CAPI sends server-side events

**Option A: Use Payment Processor Integration (If applicable)**
- [ ] Check if payment processor (Stripe, Square, etc.) has Meta CAPI integration
- [ ] Enable integration in payment processor settings
- [ ] Map events: Payment Complete → Purchase

**Option B: Use Meta's Built-in CAPI (For WordPress/Wix/etc.)**
- [ ] If using CMS, check for native CAPI integration
- [ ] Follow platform-specific setup guide

**Option C: Custom Server-Side Implementation (Developer Required)**
- [ ] Set up server endpoint to receive conversion webhooks
- [ ] Forward events to Meta CAPI endpoint
- [ ] Include: event_name, event_time, user_data (hashed), custom_data

### Step 5: Configure Aggregated Event Measurement
**Required for iOS 14+ compliance:**
- [ ] Go to Events Manager → Settings → Aggregated Event Measurement
- [ ] Verify domain (if not already done):
  - Add DNS TXT record to domain registrar
  - Or upload HTML verification file to website root
- [ ] Prioritize conversion events (most important first):
  1. Purchase
  2. InitiateCheckout
  3. Lead
  4. ViewContent
  5. PageView

### Step 6: Create Custom Audiences
**In Meta Ads Manager → Audiences → Create Audience:**

**Website Visitors (Last 30 Days):**
- [ ] Name: "Website Visitors - Last 30 Days"
- [ ] Source: Website traffic
- [ ] Include: All visitors, last 30 days
- [ ] Use for: Retargeting campaigns

**Pricing Page Visitors (Last 7 Days):**
- [ ] Name: "Pricing Page Visitors - Last 7 Days"
- [ ] Source: Website traffic
- [ ] Include: URL contains "payment.html" OR "pricing", last 7 days
- [ ] Use for: Hot lead retargeting

**Video Viewers (50%+ Completion):**
- [ ] Name: "Video Viewers 50% - Last 30 Days"
- [ ] Source: Video engagement
- [ ] Include: People who viewed 50% or more of any video, last 30 days
- [ ] Use for: Warm audience retargeting

**Customer Email List:**
- [ ] Export customer emails from booking system (CSV format)
- [ ] Name: "Past Customers - Email List"
- [ ] Source: Customer list
- [ ] Upload CSV with email addresses
- [ ] Use for: Retention/referral campaigns

**Customer Phone List:**
- [ ] Export customer phone numbers from booking system
- [ ] Name: "Past Customers - Phone List"
- [ ] Source: Customer list
- [ ] Upload CSV with phone numbers
- [ ] Use for: Retention/referral campaigns (Meta matches phone numbers)

### Step 7: Create Lookalike Audiences
**Wait until pixel has 500+ conversions, then:**

**1% Lookalike of Customers:**
- [ ] Name: "Lookalike 1% - Customer List"
- [ ] Source: "Past Customers - Email List" or "Past Customers - Phone List"
- [ ] Location: United States (or Utah only if available)
- [ ] Audience size: 1% (most similar to source)
- [ ] Use for: Cold acquisition campaigns

**1% Lookalike of Purchasers:**
- [ ] Name: "Lookalike 1% - Pixel Purchasers"
- [ ] Source: Pixel data, Purchase event, last 180 days
- [ ] Location: United States
- [ ] Audience size: 1%
- [ ] Use for: Cold acquisition campaigns (once enough data)

### Step 8: Test Pixel Installation
**Use Meta Pixel Helper Chrome Extension:**
- [ ] Install Meta Pixel Helper extension
- [ ] Visit homepage → Should see PageView event fire
- [ ] Visit payment.html → Should see InitiateCheckout event fire
- [ ] Complete test purchase → Should see Purchase event fire on confirmation page
- [ ] Check for errors or warnings in extension
- [ ] Verify correct Pixel ID is firing on all pages

**Use Meta Events Manager Test Events Tool:**
- [ ] Go to Events Manager → Overview → Test Events
- [ ] Open website in new tab
- [ ] Browse pages, trigger events
- [ ] Confirm events appear in real-time in Test Events
- [ ] Check event parameters are correct (value, currency, etc.)

---

## Phase 2: Google Ads Conversion Tracking

### Step 1: Create Google Ads Conversion Actions
**In Google Ads → Tools & Settings → Conversions:**

**Conversion #1: Booking Completed (Primary)**
- [ ] Click "+ New conversion action"
- [ ] Source: Website
- [ ] Goal: Purchase (or Lead, depending on setup)
- [ ] Conversion name: "Booking Completed"
- [ ] Value: Use different values for each conversion (or dynamic)
- [ ] Count: One (for purchases)
- [ ] Click-through conversion window: 30 days
- [ ] View-through conversion window: 1 day
- [ ] Save and get tag code

**Conversion #2: Phone Call (Click-to-Call)**
- [ ] Source: Phone calls
- [ ] Type: Calls from ads
- [ ] Track calls from ads: Enable
- [ ] Call length threshold: 60 seconds (calls shorter than this don't count)
- [ ] Save

**Conversion #3: Text Message ("COOL" Keyword)**
- [ ] Source: Website
- [ ] Goal: Lead
- [ ] Conversion name: "Text Message Lead"
- [ ] Value: $50 (estimated value of text lead)
- [ ] Count: Every (count multiple texts from same user)
- [ ] Save and get tag code

**Conversion #4: Free Inspection Request (Form Submit)**
- [ ] Source: Website
- [ ] Goal: Lead
- [ ] Conversion name: "Free Inspection Request"
- [ ] Value: $0 (lead nurturing opportunity)
- [ ] Count: One
- [ ] Save and get tag code

### Step 2: Install Google Tag (gtag.js)
**Add to ALL pages, in `<head>` section:**
```html
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=AW-CONVERSION_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'AW-CONVERSION_ID');
</script>
```

**Replace `AW-CONVERSION_ID` with your actual Google Ads conversion ID**

### Step 3: Add Event Snippets to Specific Pages

**Payment Confirmation Page (Booking Completed):**
```html
<script>
  gtag('event', 'conversion', {
    'send_to': 'AW-CONVERSION_ID/CONVERSION_LABEL',
    'value': 250.00,
    'currency': 'USD',
    'transaction_id': '' // Add transaction ID if available
  });
</script>
```

**Text Message CTA Click (Text Message Lead):**
- [ ] Add onclick event to "Text COOL" button/link:
```html
<a href="sms:3853251912?body=COOL" onclick="gtag('event', 'conversion', {'send_to': 'AW-CONVERSION_ID/TEXT_LABEL'});">
  Text COOL
</a>
```

**Phone Call Click (Calls from Website):**
- [ ] Add onclick event to phone number links:
```html
<a href="tel:3853251912" onclick="gtag('event', 'conversion', {'send_to': 'AW-CONVERSION_ID/CALL_LABEL'});">
  (385) 325-1912
</a>
```

**Form Submission (Free Inspection Request):**
- [ ] Add to form submission success handler:
```html
<script>
  gtag('event', 'conversion', {
    'send_to': 'AW-CONVERSION_ID/FORM_LABEL'
  });
</script>
```

### Step 4: Enable Enhanced Conversions
**Improves tracking accuracy with iOS privacy changes:**
- [ ] Go to Google Ads → Tools & Settings → Conversions
- [ ] Click on "Booking Completed" conversion action
- [ ] Scroll to "Enhanced conversions"
- [ ] Click "Edit" → Select "Use Google Tag"
- [ ] Save

### Step 5: Link Google Analytics 4 (GA4) to Google Ads
**For richer attribution data:**
- [ ] Go to Google Ads → Tools & Settings → Linked accounts
- [ ] Find Google Analytics (GA4)
- [ ] Click "Link"
- [ ] Select GA4 property for Tesla Cool Pro
- [ ] Enable auto-tagging
- [ ] Import GA4 conversions if desired

### Step 6: Set Up Offline Conversion Tracking (Optional but Recommended)
**For phone bookings and text bookings that happen offline:**

**Step 6a: Enable Offline Conversions in Google Ads**
- [ ] Go to Google Ads → Tools & Settings → Conversions
- [ ] Click settings gear icon
- [ ] Under "Offline conversions", click "Set up offline conversions"
- [ ] Accept terms of service

**Step 6b: Capture GCLID (Google Click ID)**
- [ ] Add hidden field to booking form or store in cookie when user lands on site:
```javascript
// Capture GCLID from URL parameters
function getGCLID() {
  const urlParams = new URLSearchParams(window.location.search);
  return urlParams.get('gclid');
}
const gclid = getGCLID();
// Store in hidden form field or send to backend
```

**Step 6c: Upload Offline Conversions Weekly**
- [ ] Export phone/text bookings from CRM/booking system (CSV format)
- [ ] Include: GCLID, conversion name, conversion time, value
- [ ] Go to Google Ads → Tools & Settings → Conversions → Uploads
- [ ] Upload CSV file
- [ ] Schedule weekly uploads (automate if possible)

**CSV Format Example:**
```csv
Google Click ID,Conversion Name,Conversion Time,Conversion Value
ABC123GCLID,Booking Completed,2026-06-25 14:30:00,250.00
XYZ789GCLID,Booking Completed,2026-06-26 10:15:00,450.00
```

---

## Phase 3: Call & Text Tracking

### Option A: Dedicated Phone Numbers per Platform (Recommended)

**Sign up for call tracking service (CallRail, WhatConverts, etc.):**
- [ ] Purchase 3-4 local Utah phone numbers
- [ ] Assign numbers:
  - Number 1: Meta Ads ((385) XXX-XXXX)
  - Number 2: Google Ads ((385) XXX-XXXX)
  - Number 3: Organic/Direct ((385) XXX-XXXX)
  - Number 4: TikTok Ads ((385) XXX-XXXX)
- [ ] Set up call forwarding to main line: (385) 325-1912
- [ ] Configure call recording (enable for quality/training)
- [ ] Set up call transcription (optional but useful)
- [ ] Integrate with Meta/Google Ads for offline conversion import

**Update website with dynamic number insertion (DNI):**
- [ ] Add JavaScript snippet from call tracking provider
- [ ] Script swaps phone number based on traffic source
- [ ] Ensures accurate attribution without multiple numbers on page

### Option B: Single Number with Call Annotations (Budget Option)

**Use Google's native call reporting:**
- [ ] Enable call extensions in Google Ads
- [ ] Enable call reporting in campaign settings
- [ ] Review call data in Google Ads dashboard
- [ ] Manually tag calls as converted/not converted

**Limitation:** Doesn't work for Meta ads, less accurate attribution

---

## Phase 4: UTM Parameter Setup

### Create UTM Naming Convention

**Standard Format:**
```
?utm_source={platform}&utm_medium={medium}&utm_campaign={campaign_name}&utm_content={ad_variation}
```

**Examples:**

**Meta Ads:**
```
?utm_source=facebook&utm_medium=cpc&utm_campaign=summer-flash-sale&utm_content=ad-variation-1
?utm_source=instagram&utm_medium=cpc&utm_campaign=bogo-promo&utm_content=video-before-after
```

**Google Ads:**
```
?utm_source=google&utm_medium=cpc&utm_campaign=tesla-radiator-cleaning&utm_content=text-ad-savings
?utm_source=google&utm_medium=cpc&utm_campaign=tesla-ac-repair-utah&utm_content=responsive-search-ad-1
```

**TikTok Ads:**
```
?utm_source=tiktok&utm_medium=cpc&utm_campaign=ev-enthusiasts&utm_content=satisfying-clean-video
```

### Implement UTM Tracking

**In Ad Platforms:**
- [ ] Meta Ads: Add UTM parameters in URL Parameters field at ad level
- [ ] Google Ads: Use ValueTrack parameters for auto-tagging (gclid), add UTMs manually if needed
- [ ] TikTok Ads: Add UTM parameters in URL field

**In Google Analytics:**
- [ ] Go to GA4 → Reports → Acquisition → Traffic acquisition
- [ ] Filter by session source/medium to see UTM performance
- [ ] Create custom report for campaign performance

**Create UTM Tracking Spreadsheet:**
| Date | Platform | Campaign | Ad Variation | UTM URL | Status |
|------|----------|----------|--------------|---------|--------|
| | Facebook | summer-flash-sale | ad-variation-1 | | Active |
| | Instagram | bogo-promo | video-before-after | | Active |

---

## Phase 5: Google Analytics 4 (GA4) Setup

### Step 1: Create GA4 Property
- [ ] Go to analytics.google.com
- [ ] Click "Admin" → "Create Property"
- [ ] Property name: "Tesla Cool Pro"
- [ ] Set time zone: America/Denver (Utah)
- [ ] Set currency: USD
- [ ] Complete setup wizard

### Step 2: Install GA4 Tracking Code
**Add to ALL pages, in `<head>` section:**
```html
<!-- Google Analytics 4 -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

**Replace `G-XXXXXXXXXX` with your GA4 Measurement ID**

### Step 3: Configure Conversion Events in GA4
**Mark key events as conversions:**
- [ ] Go to GA4 → Admin → Events
- [ ] Find or create events:
  - `page_view` (automatic)
  - `view_item` (pricing page view)
  - `begin_checkout` (payment page view)
  - `purchase` (booking completion)
  - `generate_lead` (form submit, text message)
- [ ] Toggle "Mark as conversion" for key events

### Step 4: Create Audience Segments for Retargeting
**In GA4 → Admin → Audiences:**

**All Website Visitors:**
- [ ] Name: "All Visitors - Last 30 Days"
- [ ] Condition: Users with any event, last 30 days
- [ ] Link to Google Ads for retargeting

**Pricing Page Viewers:**
- [ ] Name: "Pricing Page Viewers - Last 7 Days"
- [ ] Condition: Users where page_location contains "payment.html" OR "pricing", last 7 days
- [ ] Link to Google Ads

**High-Intent Users:**
- [ ] Name: "High Intent - Last 14 Days"
- [ ] Condition: Users with begin_checkout OR generate_lead event, last 14 days
- [ ] Link to Google Ads

### Step 5: Set Up Funnel Exploration
**Visualize customer journey:**
- [ ] Go to GA4 → Explore → Funnel exploration
- [ ] Create funnel steps:
  1. Landing page view
  2. Pricing page view
  3. Payment page view
  4. Purchase completion
- [ ] Analyze drop-off points
- [ ] Optimize weak steps

---

## Phase 6: Testing & Verification

### Pre-Launch Checklist

**Meta Pixel:**
- [ ] Pixel Helper shows no errors on all pages
- [ ] Test Events tool shows real-time events
- [ ] Custom audiences are populating (wait 24-48 hours for data)
- [ ] Domain is verified in Business Manager
- [ ] Aggregated Event Measurement configured

**Google Ads:**
- [ ] Tag Assistant shows tags firing correctly
- [ ] Conversion actions show "Recording conversions" status
- [ ] Enhanced conversions enabled
- [ ] Google Analytics linked
- [ ] Offline conversion upload tested (if using)

**Call Tracking:**
- [ ] Test all phone numbers (ensure forwarding works)
- [ ] Verify call recording is active
- [ ] Check integration with ad platforms

**UTM Parameters:**
- [ ] Test UTM-tagged URLs in GA4 Real-Time report
- [ ] Verify source/medium/campaign data appears correctly
- [ ] Check that all ad platforms are passing UTMs

**GA4:**
- [ ] Real-Time report shows active users
- [ ] Conversion events firing correctly
- [ ] Audiences building (check audience sizes after 24-48 hours)
- [ ] Funnels configured and showing data

### Test Conversions End-to-End

**Complete a test booking:**
- [ ] Click on test Meta ad (use preview link)
- [ ] Browse website, visit pricing page
- [ ] Complete booking/payment
- [ ] Verify Meta Purchase event fired
- [ ] Verify Google Ads conversion fired
- [ ] Verify GA4 conversion recorded
- [ ] Check UTM data persisted through flow
- [ ] Confirm confirmation email sent (if applicable)

**Complete a test phone call:**
- [ ] Click on test Google Ad with call extension
- [ ] Call tracking number
- [ ] Verify call is logged in call tracking platform
- [ ] Manually mark as converted in platform

**Complete a test text message:**
- [ ] Click "Text COOL" button on website
- [ ] Send test text message
- [ ] Verify conversion event fired (if tracked)
- [ ] Confirm response workflow triggered

---

## Post-Launch Monitoring

### Week 1: Daily Checks
- [ ] Meta Events Manager: Confirm events firing, no errors
- [ ] Google Ads Conversions: Check conversion count matches bookings
- [ ] GA4 Real-Time: Monitor traffic sources, verify UTMs
- [ ] Call Tracking: Review call volume, recordings
- [ ] Discrepancy Check: Compare ad platform conversions vs. actual bookings (expect 20-30% discrepancy due to attribution differences)

### Week 2-4: Weekly Reviews
- [ ] ROAS Calculation: Revenue / Ad Spend (by platform)
- [ ] CPA Analysis: Cost Per Acquisition trends
- [ ] Attribution Comparison: Meta vs. Google vs. GA4 conversion counts
- [ ] Audience Performance: Which custom/lookalike audiences converting best
- [ ] Creative Performance: Which ad variations driving lowest CPA

### Monthly: Optimization Actions
- [ ] Upload offline conversions (phone/text bookings)
- [ ] Refresh custom audiences (update customer lists)
- [ ] Review and adjust conversion values if needed
- [ ] Audit tracking setup (ensure nothing broken after site updates)
- [ ] Document learnings in tracking spreadsheet

---

## Troubleshooting Common Issues

**Issue: Pixel not firing on certain pages**
- Solution: Check for ad blockers, verify code placement in `<head>`, clear browser cache

**Issue: Conversions not matching actual bookings**
- Solution: Expect 20-30% discrepancy; implement offline conversion uploads; check attribution windows

**Issue: iOS users not tracked accurately**
- Solution: Ensure Conversions API is set up; enable Enhanced Conversions; use modeled conversions

**Issue: UTMs not showing in GA4**
- Solution: Check URL formatting (no spaces, proper encoding); verify GA4 data stream configuration; wait 24 hours for processing

**Issue: Call tracking numbers not forwarding**
- Solution: Contact call tracking provider support; verify forwarding number is correct; test from different phones

---

## Tools & Resources

**Browser Extensions:**
- Meta Pixel Helper (Chrome)
- Google Tag Assistant (Chrome)
- UTM Builder (various)

**Platforms:**
- Meta Business Manager: business.facebook.com
- Google Ads: ads.google.com
- Google Analytics: analytics.google.com
- Call Tracking: callrail.com or whatconverts.com

**Documentation:**
- Meta Pixel Guide: developers.facebook.com/docs/meta-pixel
- Google Ads Conversion Tracking: support.google.com/google-ads
- GA4 Setup Guide: support.google.com/analytics

---

**Status:** Ready for implementation  
**Next Step:** Assign to web developer, schedule 2-3 hours for complete setup  
**Questions:** Contact Paid Ads Specialist before proceeding
