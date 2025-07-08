# Website Exploration and Functional Testing

Perform comprehensive functional testing of the website at $ARGUMENTS (default: http://localhost:3000).

## Testing Protocol:

### 1. Navigation Discovery
- Navigate to the starting URL
- Take initial screenshot (desktop 1920x1080)
- Discover all navigation links, menu items, and primary CTAs
- Create a sitemap of discoverable pages

### 2. Page-by-Page Analysis
For each discovered page:
- Navigate to the page
- Take screenshot (desktop and mobile 375x667)
- Test ALL interactive elements:
  - Buttons (click and verify response)
  - Forms (attempt to fill and submit)
  - Links (verify they navigate correctly)
  - Dropdowns, modals, accordions
  - Search functionality
  - Any dynamic content
- Record console errors or JavaScript issues
- Note any loading errors, 404s, or broken functionality
- Test mobile responsiveness and touch interactions

### 3. User Flow Testing
Test critical user journeys:
- Registration/login flow
- Purchase/checkout process
- Contact forms
- Search functionality
- Any multi-step processes

### 4. Cross-Page Functionality
- Test navigation between pages
- Verify consistent header/footer functionality
- Test any global search or user account features

## Report Format:

Generate a comprehensive markdown report with the following structure:

```markdown
# Website Functional Analysis Report
**URL:** [Starting URL]
**Date:** [Current Date]
**Test Duration:** [Duration]

## Executive Summary
- Total pages tested: [number]
- Total interactive elements tested: [number]
- Issues found: [number]
- Critical issues: [number]

## Site Structure
[ASCII tree of discovered pages and navigation]

## Detailed Findings

### [Page Name/URL]
**Status:** ✅ Functional | ⚠️ Issues Found | ❌ Broken

**Interactive Elements:**
- Button: "Submit" → ✅ Works | ❌ Non-functional | ⚠️ Partial
- Form: Contact Form → ✅ Submits successfully | ❌ Fails to submit
- Link: "About Us" → ✅ Navigates correctly | ❌ 404 error

**Console Errors:**
- [List any JavaScript errors]

**Mobile Issues:**
- [Any mobile-specific problems]

**Screenshots:**
- Desktop: [screenshot file path]
- Mobile: [screenshot file path]

## Critical Issues Summary
1. **[Issue Title]**
   - **Location:** [Page/Element]
   - **Description:** [What's broken]
   - **Impact:** High/Medium/Low
   - **Recommended Action:** [What needs to be fixed]

## Recommendations
1. **Priority 1 (Critical):**
   - [List critical fixes needed]

2. **Priority 2 (Important):**
   - [List important improvements]

3. **Priority 3 (Minor):**
   - [List minor issues]

## Test Coverage
- ✅ All navigation links tested
- ✅ All forms tested
- ✅ All buttons tested
- ✅ Mobile responsiveness checked
- ✅ Console errors logged
- ✅ User flows validated

## Next Steps
[Specific actionable items for development team]
```

## Testing Guidelines:
- Test each element at least twice to confirm consistency
- Take screenshots before and after interactions when possible
- Don't attempt to fix code - only report functional behavior
- Focus on user experience and functionality, not code quality
- Include specific error messages and browser console output
- Note any performance issues (slow loading, timeouts)
- Test with both mouse interactions and keyboard navigation
- Verify accessibility basics (can elements be tabbed to, etc.)

## Important Notes:
- This is FUNCTIONAL TESTING ONLY - do not analyze or modify source code
- Focus on what works/doesn't work from a user perspective
- Report exact error messages and console output
- Include specific steps to reproduce any issues found
- Prioritize critical user journeys and core functionality