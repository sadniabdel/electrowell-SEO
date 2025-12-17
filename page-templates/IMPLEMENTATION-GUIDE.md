# Page Templates Implementation Guide

This guide explains how to add the created page templates to your BigCommerce store.

## Overview

The following page templates have been created in `/page-templates/` directory:

### Legal Pages (Critical - Dead footer links)
1. **privacy-policy.html** - GDPR/CCPA/Australian Privacy Act compliant
2. **terms-and-conditions.html** - Complete T&C with Australian Consumer Law
3. **shipping-policy.html** - Worldwide shipping information
4. **return-refund-policy.html** - 30-day return policy with RMA process

### Content Pages (SEO & Engagement)
5. **about-us.html** - Brand story focused on PLCs/VFDs/automation
6. **faq.html** - Comprehensive FAQ for industrial automation products

### Industry Solution Pages (SEO-targeted landing pages)
7. **manufacturing-solutions.html** - Manufacturing automation applications
8. **process-control-solutions.html** - Process industries (oil, gas, chemical, water)
9. **building-automation-solutions.html** - HVAC, BMS, energy management

---

## How to Add Pages to BigCommerce

### Step 1: Access Web Pages Section

1. Log in to your **BigCommerce Admin Panel**
2. Navigate to **Storefront** → **Web Pages**
3. Click the **Create a Web Page** button

### Step 2: Create Each Web Page

For each HTML file in `/page-templates/`, follow these steps:

#### 2.1 - Basic Information

- **Page Name:** Enter the page title (e.g., "Privacy Policy", "About Us", etc.)
- **Page URL:** Set a clean URL path:
  - privacy-policy.html → `/privacy-policy/`
  - about-us.html → `/about-us/`
  - manufacturing-solutions.html → `/manufacturing-solutions/`
  - etc.

#### 2.2 - Page Content

1. Open the corresponding `.html` file from `/page-templates/`
2. **Copy the ENTIRE contents** of the file
3. In BigCommerce, switch the editor to **HTML mode** (click the `<>` icon)
4. **Paste the HTML content** into the editor

#### 2.3 - SEO Settings (Expand "Advanced Settings")

Configure SEO for each page:

**Privacy Policy:**
- **Page Title:** Privacy Policy | ElectroWell
- **Meta Description:** Learn how ElectroWell collects, uses, and protects your personal information. GDPR and CCPA compliant privacy policy for industrial automation products.
- **Meta Keywords:** privacy policy, data protection, GDPR, CCPA

**Terms & Conditions:**
- **Page Title:** Terms and Conditions | ElectroWell
- **Meta Description:** Terms of service, product warranties, liability limitations, and Australian Consumer Law compliance for ElectroWell industrial automation equipment.
- **Meta Keywords:** terms and conditions, warranties, industrial automation

**Shipping Policy:**
- **Page Title:** Shipping Policy - Worldwide Delivery | ElectroWell
- **Meta Description:** Worldwide shipping for PLCs, VFDs, and industrial automation products. Delivery times for Australia, New Zealand, and international destinations.
- **Meta Keywords:** shipping policy, international delivery, industrial automation shipping

**Return & Refund Policy:**
- **Page Title:** Return & Refund Policy | ElectroWell
- **Meta Description:** 30-day return policy for industrial automation products. RMA process, warranty claims, and Australian Consumer Law compliance information.
- **Meta Keywords:** return policy, refund policy, warranty, RMA

**About Us:**
- **Page Title:** About Us - Industrial Automation Experts | ElectroWell
- **Meta Description:** ElectroWell supplies PLCs, VFDs, drives, and industrial automation products from Omron, Danfoss, Allen-Bradley, Siemens, and Schneider Electric worldwide.
- **Meta Keywords:** industrial automation, PLC supplier, VFD supplier, about us

**FAQ:**
- **Page Title:** FAQ - Industrial Automation Support | ElectroWell
- **Meta Description:** Frequently asked questions about PLCs, VFDs, drives, ordering, shipping, technical support, and industrial automation product compatibility.
- **Meta Keywords:** industrial automation FAQ, PLC questions, VFD support

**Manufacturing Solutions:**
- **Page Title:** Manufacturing Automation Solutions | PLCs & VFDs | ElectroWell
- **Meta Description:** Advanced PLCs, VFDs, and automation systems for manufacturing: assembly lines, conveyors, packaging, material handling. Industry 4.0 ready solutions.
- **Meta Keywords:** manufacturing automation, assembly line control, PLC manufacturing, VFD conveyor

**Process Control Solutions:**
- **Page Title:** Process Control & Automation | PLCs for Oil, Gas, Chemical | ElectroWell
- **Meta Description:** Process automation PLCs, VFDs, and SCADA systems for chemical processing, oil & gas, water treatment, and power generation. SIL-rated safety systems.
- **Meta Keywords:** process control, process automation, DCS, SCADA, chemical processing

**Building Automation Solutions:**
- **Page Title:** Building Automation & HVAC Controls | BMS Solutions | ElectroWell
- **Meta Description:** Smart building automation, HVAC controls, energy management, and BMS integration. VFDs for pumps, fans, chillers. BACnet compatible systems.
- **Meta Keywords:** building automation, BMS, HVAC control, energy management

#### 2.4 - Additional Settings

- **Sort Order:** Set the order pages appear in sitemaps (lower numbers appear first)
  - Legal pages: 10-13
  - Content pages: 20-21
  - Industry pages: 30-32

- **Visible in Menu:**
  - Legal pages: **No** (these go in footer)
  - About Us: **Yes** (add to main navigation if desired)
  - FAQ: **Yes** (add to main navigation)
  - Industry pages: **Yes** (add to main navigation or dropdown)

- **Status:** **Published**

#### 2.5 - Save

Click **Save** to publish the page.

---

## Step 3: Update Footer Links

After creating the legal pages, update your footer to link to them:

1. Navigate to **Storefront** → **Footer Scripts** (or edit `templates/components/common/footer.html` if using Stencil CLI)

2. Find the footer links section (around lines 82-91 in footer.html)

3. **Current footer has dead links pointing to "#"**. Update them to:

```html
<div class="footer-info-col">
    <h3>Customer Service</h3>
    <ul>
        <li><a href="/privacy-policy/">Privacy Policy</a></li>
        <li><a href="/terms-and-conditions/">Terms & Conditions</a></li>
        <li><a href="/shipping-policy/">Shipping Policy</a></li>
        <li><a href="/return-refund-policy/">Returns & Refunds</a></li>
        <li><a href="/faq/">FAQ</a></li>
        <li><a href="/about-us/">About Us</a></li>
        <li><a href="/contact-us/">Contact Us</a></li>
    </ul>
</div>
```

4. If you want to add industry solution pages to navigation:

```html
<div class="footer-info-col">
    <h3>Solutions</h3>
    <ul>
        <li><a href="/manufacturing-solutions/">Manufacturing Automation</a></li>
        <li><a href="/process-control-solutions/">Process Control</a></li>
        <li><a href="/building-automation-solutions/">Building Automation</a></li>
    </ul>
</div>
```

---

## Step 4: Add Pages to Main Navigation (Optional)

To add industry solution pages to your main navigation:

1. Go to **Storefront** → **Menus**
2. Edit your main navigation menu
3. Add new menu items:
   - **Manufacturing Solutions** → `/manufacturing-solutions/`
   - **Process Control** → `/process-control-solutions/`
   - **Building Automation** → `/building-automation-solutions/`

Consider organizing them under a "Solutions" dropdown menu.

---

## Step 5: Verify & Test

After adding all pages:

1. **Test all footer links** - Click each link to ensure pages load correctly
2. **Check mobile responsiveness** - View pages on mobile devices
3. **Verify internal links** - Ensure links to `/contact-us/`, `/faq/`, etc. work
4. **Review SEO** - Use tools like Google Search Console to verify metadata
5. **Test forms** - If you added contact forms, test submissions

---

## Customization Notes

### Placeholder Text to Update

Before publishing, search for and replace these placeholders in the HTML files:

- **[Your Phone Number]** - Add your actual phone number (appears in multiple pages)
- **support@electrowell.com** - Confirm this email is correct and monitored
- **Product Category Links** - Update links like `/plcs/`, `/vfds/` to match your actual category URLs

Example locations:
- FAQ page: Line 207 (phone number)
- About Us page: Line 94 (phone number)
- Manufacturing Solutions: Line 402 (phone number)
- Process Control: Line 337 (phone number)
- Building Automation: Line 405 (phone number)

### Add Brand/Product Category Links

The industry solution pages reference product categories that should link to your actual BigCommerce categories:

- `/plcs/` → Your PLC category URL
- `/vfds/` → Your VFD category URL
- `/hmis/` → Your HMI category URL
- `/servo-motors/` → Servo motor category
- Etc.

**To find your category URLs:**
1. Go to **Products** → **Product Categories**
2. View each category on the storefront
3. Copy the URL and update the links in the HTML files

---

## Priority Implementation Order

Based on urgency and SEO impact:

### Priority 1 (CRITICAL - Fix Dead Footer Links)
1. Privacy Policy
2. Terms & Conditions
3. Shipping Policy
4. Return & Refund Policy

**Why:** Your footer currently has dead links pointing to "#" which hurts SEO and user trust.

### Priority 2 (High SEO Value)
5. FAQ
6. About Us

**Why:** Google favors sites with comprehensive FAQ and About pages. These build trust signals.

### Priority 3 (SEO & Lead Generation)
7. Manufacturing Solutions
8. Process Control Solutions
9. Building Automation Solutions

**Why:** Target high-value keywords and attract qualified leads searching for industry-specific solutions.

---

## SEO Benefits of These Pages

### Legal Pages
- **Trust Signals:** Google ranks sites higher when they have complete legal policies
- **Conversion Rate:** Customers more likely to buy when privacy/return policies are clear
- **GDPR/CCPA:** Legal compliance reduces risk of fines

### About Us
- **E-A-T Score:** Demonstrates expertise, authoritativeness, trustworthiness
- **Brand Story:** Helps with brand searches (people searching "ElectroWell")

### FAQ
- **Featured Snippets:** Well-structured FAQs often appear in Google's featured snippet boxes
- **Long-tail Keywords:** Captures "how to", "what is", "can I" type searches
- **Reduces Support:** Answers common questions before customers need to contact you

### Industry Solution Pages
- **Keyword Targeting:** Each page targets specific high-value keywords:
  - Manufacturing automation, assembly line control, packaging automation
  - Process control, SCADA, DCS, chemical processing automation
  - Building automation, BMS, HVAC control, energy management
- **Conversion Optimization:** Tailored content for specific industries increases relevance
- **Internal Linking:** Provides strategic link hubs to product category pages

---

## Monitoring & Optimization

After implementation, monitor these metrics:

### Google Search Console
- Track impressions/clicks for new pages
- Monitor which keywords drive traffic
- Check for crawl errors or indexing issues

### Google Analytics
- Page views and time on page
- Bounce rate (should be <50% for engaging content)
- Conversion rate (contact form submissions, product clicks)

### Ongoing Optimization
- Update FAQ quarterly with new common questions
- Add case studies to industry solution pages
- Update product links as new categories are added
- Keep legal pages current with regulatory changes

---

## Support

If you encounter issues:

1. **BigCommerce Support:** Help documentation at support.bigcommerce.com
2. **Stencil CLI:** If editing theme files directly, see Stencil documentation
3. **HTML Validation:** Use validator.w3.org to check for HTML errors

---

## Summary Checklist

- [ ] Create all 9 web pages in BigCommerce admin
- [ ] Configure SEO metadata for each page
- [ ] Replace placeholder phone numbers and emails
- [ ] Update footer links to point to new legal pages
- [ ] Verify product category links are correct
- [ ] Test all internal links (contact forms, category pages, etc.)
- [ ] Check mobile responsiveness
- [ ] Submit sitemap to Google Search Console
- [ ] Monitor page performance in analytics

---

**Implementation Time Estimate:** 2-3 hours for all pages (including testing and verification)

**Immediate Impact:**
- Fixes 4 dead footer links (SEO issue)
- Adds legal compliance (reduces business risk)
- Improves Google E-A-T score (SEO ranking factor)
- Enables organic traffic from industry-specific keywords

**Questions?** Contact the development team or BigCommerce support for assistance.
