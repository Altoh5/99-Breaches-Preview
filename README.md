# 99-Breaches-Preview

Static GitHub Pages microsite summarising selected chapters from *99 Privacy Breaches to Beware Of*.

## Purpose

This site is designed as a lead magnet for privacy and data protection audiences, especially:
- new Data Protection Officers (DPOs)
- operational compliance teams
- business users who need practical, scenario-based data protection examples

The page packages selected chapters into a more accessible training-style experience with:
- short chapter summaries
- DPO-focused takeaways
- actionable checklists
- embedded short-form video explainers where available

## Audience Positioning

The content is intentionally practical rather than legalistic. It is meant to help a new or non-specialist DPO quickly understand:
- what the breach scenario looks like in real life
- why it matters operationally
- what immediate controls or habits should be implemented

## Site Structure

The site is a single static `index.html` file with all content embedded client-side.

Main content model:
- `aboutBookData`: about section, book summary, testimonials
- `bookData`: section and chapter data used to render navigation and content cards
- each chapter contains:
  - `num`
  - `title`
  - `context`
  - `learnings`
  - `checklists`
  - optional `videoTitle`
  - optional `videoUrl`
  - optional `infographic`

UI behavior:
- left sidebar navigation by topic area
- searchable chapter content
- expandable chapter cards
- lead capture CTA blocks in both the overview and chapter flows

## Video Mapping

Video placeholders were reviewed against the Straits Interactive / DPEX Network YouTube playlist below on March 14, 2026:
- Playlist: `https://www.youtube.com/watch?v=i_rP-44Kqgw&list=PLeFbwfnrYD4rIRJyKTgyQ-EPIVK6kPrn7`

Updated exact matches:
- Chapter 1: `Data protection - don’t forget that it is also physical`
- Chapter 8: `Are your sales and service counters compliant with the data protection law?`
- Chapter 41: `Identity Verification | The Right Way`
- Chapter 62: `Beware - don't ever lose or misplace your USB drive or other portable storage device`
- Chapter 73: `A-tearing we will go`
- Chapter 80: `CCTV footage – To Show or Not To Show… and To Warn?`
- Chapter 86: `Think Twice before disclosing employees' personal data`
- Chapter 95: `Ransomware - Pay up or else...`

Updated inferred matches:
- Chapter 38 uses `Hitting the “send” button and regretting it` because the scenario centers on emailing the wrong spreadsheet / attachment.
- Chapter 49 uses `Lock it or lose it` as the closest fit to clean desk and workspace locking behavior.

Deliberate adjustment:
- Chapter 40 no longer embeds a video because the playlist contained a clear match for the "right way" variant, not the "wrong way" variant.

Embeds now use `youtube-nocookie.com` rather than Google Drive preview URLs.

## GitHub Pages

Deployment settings:
- Branch: `main`
- Folder: `/ (root)`
- `.nojekyll` is included

Expected site URL:
- `https://altoh5.github.io/99-Breaches-Preview/`

## Analytics Setup

### LinkedIn Insight Tag (pending — assign to marketing manager)

The page does not yet have a LinkedIn Insight Tag. This enables visitor tracking for LinkedIn ad audiences and retargeting.

**Steps to set up:**
1. Log in to [LinkedIn Campaign Manager](https://www.linkedin.com/campaignmanager/) → account **SI Campaign Manager (508758293)**
2. In the left sidebar, go to **Measurement → Conversion tracking**
3. Click **Insight Tag** → **Create Insight Tag** (if not yet created)
4. Choose **"I will install the tag myself"**
5. Copy the numeric **Partner ID** (e.g. `1234567`)
6. In `app.html`, add inside the `<head>` tag:
   ```html
   <!-- LinkedIn Insight Tag -->
   <script type="text/javascript">
   _linkedin_partner_id = "XXXXXXX"; // replace with your Partner ID
   window._linkedin_data_partner_ids = window._linkedin_data_partner_ids || [];
   window._linkedin_data_partner_ids.push(_linkedin_partner_id);
   </script>
   <script type="text/javascript">
   (function(l) {
   if (!l){window.lintrk = function(a,b){window.lintrk.q.push([a,b])};
   window.lintrk.q=[]}
   var s = document.getElementsByTagName("script")[0];
   var b = document.createElement("script");
   b.type = "text/javascript";b.async = true;
   b.src = "https://snap.licdn.com/li.lms-analytics/insight.min.js";
   s.parentNode.insertBefore(b, s);})(window.lintrk);
   </script>
   <noscript>
   <img height="1" width="1" style="display:none;" alt="" src="https://px.ads.linkedin.com/collect/?pid=XXXXXXX&fmt=gif" />
   </noscript>
   ```
7. Replace both `XXXXXXX` with your actual Partner ID
8. Commit and push — tag goes live in ~24 hours

### GA4 / Meta Pixel

Not yet added. Add tracking IDs to `.env` or directly in `app.html` as needed.

## Editing Notes

If you update or expand the site:
- keep new chapter entries inside `bookData`
- prefer exact playlist-title matches before adding a video to a chapter
- if a match is only approximate, label it as a related video rather than a chapter video
- keep the site static so it continues to work cleanly on GitHub Pages
