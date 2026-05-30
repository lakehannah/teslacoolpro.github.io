# Tesla Cool Pro - Website Deployment Checklist
## Get Your Site Live in 15 Minutes

---

## STEP 1: Upload Photos (5 minutes)

**Create the images folder:**
```
tesla-cool-pro-website/
├── index.html          ← Already built
└── images/             ← Create this folder
    ├── before-1.jpg    ← Your before photo #1
    ├── after-1.jpg     ← Your after photo #1
    ├── before-2.jpg    ← Your before photo #2
    ├── after-2.jpg     ← Your after photo #2
    ├── before-3.jpg    ← Your before photo #3
    └── after-3.jpg     ← Your after photo #3
```

**If your photos have different names, update the HTML:**
- Open `index.html`
- Find the photo references (lines with `before-1.jpg`, `after-1.jpg`, etc.)
- Change to match your actual filenames

---

## STEP 2: Deploy Website (10 minutes)

**Option A: Netlify (Recommended - FREE)**

1. Go to **netlify.com**
2. Sign up (free, use Google/GitHub account)
3. Drag and drop the `tesla-cool-pro-website` folder
4. Get instant URL: `https://teslacoolpro.netlify.app`
5. Done!

**Option B: GitHub Pages (FREE)**

1. Go to **github.com**
2. Create new repository: `tesla-cool-pro`
3. Upload all files
4. Go to Settings → Pages
5. Select "Deploy from main branch"
6. URL: `https://yourusername.github.io/tesla-cool-pro`

**Option C: Buy Domain + Host ($12/year)**

1. Buy domain at **Namecheap** or **GoDaddy**
   - Suggested: `teslacoolpro.com`
   - Cost: ~$12/year
2. Upload files via FTP or use website builder
3. Connect domain to hosting

---

## STEP 3: Connect Domain (Optional - 5 minutes)

**If you bought a custom domain:**

1. In Netlify: Domain Settings → Add Custom Domain
2. Enter: `teslacoolpro.com`
3. Update DNS records (Netlify gives you instructions)
4. Wait 5-30 minutes for propagation
5. Test: `https://teslacoolpro.com`

---

## STEP 4: Test Everything (5 minutes)

**Checklist:**
- [ ] Website loads on phone
- [ ] Phone number links work (click to call)
- [ ] Pricing shows correctly
- [ ] Photos display properly
- [ ] Text "COOL" to 435.695.6996 works
- [ ] All buttons scroll to correct sections
- [ ] Looks good on mobile and desktop

---

## STEP 5: Google Business (10 minutes)

**Add website to Google Business Profile:**
1. Go to **business.google.com**
2. Search for "Tesla Cool Pro"
3. Click "Add website"
4. Enter: `https://teslacoolpro.com`
5. Save

---

## STEP 6: Share It (Ongoing)

**Where to post your new website:**
- Instagram bio link
- Facebook page
- TikTok bio
- Twitter/X bio
- Email signature
- Business cards
- Flyers
- Text to customers

---

## FILES READY TO DEPLOY

**Location:** `/Users/hannahlake/.openclaw/workspace/tesla-cool-pro-website/`

**What's included:**
- `index.html` - Complete website (already updated with phone and service area)
- `gallery-styles.css` - Gallery styling
- `images/` - Folder for your before/after photos

---

## QUICK START COMMANDS

**If using command line:**

```bash
# Navigate to website folder
cd tesla-cool-pro-website

# Add your photos to images folder
cp ~/Desktop/your-photos/* images/

# Deploy with Netlify CLI (if installed)
npm install -g netlify-cli
netlify deploy --prod --dir=.

# Or upload to GitHub Pages
git init
git add .
git commit -m "Initial website launch"
git remote add origin https://github.com/yourusername/tesla-cool-pro.git
git push -u origin main
```

---

## TROUBLESHOOTING

**Photos not showing?**
- Check file names match exactly (case-sensitive)
- Make sure photos are in `images/` folder
- Check file extensions (.jpg, .jpeg, .png)

**Phone number not clickable?**
- Should be: `<a href="tel:4356956996">435.695.6996</a>`
- Already set up in the HTML

**Website looks weird on mobile?**
- Already responsive, but test on actual phone
- Use Chrome DevTools (F12 → Toggle device toolbar)

**Want to change colors?**
- Find `#00d4ff` in the CSS (that's the blue)
- Replace with your brand color
- Find `#1a1a2e` (that's the dark background)

---

## NEXT STEPS AFTER DEPLOYMENT

1. **Submit to Google** - `https://search.google.com/search-console`
2. **Add analytics** - Google Analytics or Plausible
3. **Set up forms** - Contact form with Formspree or Netlify Forms
4. **SEO optimize** - Add meta tags, keywords
5. **Create blog** - Add blog section for SEO

---

**Ready to deploy? Follow steps 1-2 and you'll be live in 15 minutes.**
