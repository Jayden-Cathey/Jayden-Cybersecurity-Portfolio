You are assisting with a small, public static portfolio website.

Project context:	
-	Purpose: present a student's skills and projects to internship reviewers.
- Existing system: an HTML/CSS/JavaScript portfolio template.
-	Allowed changes: content, styling, and small front-end corrections only.
-	Do not add: a backend, login system, analytics tracker, or external data collection.
 
Acceptance criteria:	 
1. The landing page displays my name, role, and introduction	 
2. Portfolio content is verified against content-notes.md	 
3. Skills section lists cybersecurity-related concerns	 
4. Contact information is easily found at the beginning of the page	 
5. No personal information beyond my name, professional role, and public contact method appears on the site

Constraints:	
-	Do not invent education, work history, awards, links, or technical skills.	
-	Preserve required license and attribution.
-	Keep the site usable on mobile screens.
-	Maintain readable contrast, keyboard navigation, meaningful link text, and useful image alternative text.
-	Do not expose private information.	 

First provide:	
1.	A file- by - file implementation plan.
2.	2.	Any Assumptions or risks.
3.	A proposed test checklist.
4.	Any questions that must be answered before implementation.


# Implementation Plan: Student Portfolio Website

Before diving in, I want to flag one important item: **I don't have access to your actual project files** (the HTML/CSS/JS template or `content-notes.md`). I'll structure this plan generically based on typical portfolio site architecture, but you'll need to share the actual files/content for me to give file-specific edits rather than a template.

---

## 1. File-by-File Implementation Plan

| File | Likely Changes |
|---|---|
| `index.html` | - Add/verify name, role, intro in hero section near top of `<body>`.<br>- Move contact info (email or public profile link) to appear immediately after name/role (per criterion 4).<br>- Add/update Skills section with cybersecurity-related items pulled *only* from `content-notes.md`.<br>- Add `alt` text to all `<img>` tags.<br>- Ensure semantic HTML (`<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`) for accessibility.<br>- Verify all links have meaningful text (no "click here"). |
| `content-notes.md` | - Use as source of truth; cross-check every claim on the site against it. Do **not** add anything not present here. |
| `styles.css` | - Verify color contrast meets WCAG AA (4.5:1 for normal text).<br>- Add/check responsive breakpoints for mobile (flexbox/grid stacking, font scaling).<br>- Ensure focus states are visible (`:focus-visible` outlines) for keyboard nav. |
| `script.js` (if present) | - Review for any analytics, tracking, or data collection code — remove if found.<br>- Confirm no form submission handlers pointing to a backend/API.<br>- Keep only UI behaviors (nav toggle, smooth scroll, etc.). |
| `LICENSE` / attribution comments | - Preserve exactly as-is if template requires attribution. Do not remove or alter license headers. |
| Contact method (e.g., `mailto:` link or public LinkedIn/GitHub) | - Confirm it's a method you're comfortable making public (no phone number/address unless explicitly approved). |

---

## 2. Assumptions & Risks

**Assumptions:**
- The template already has a hero/landing section I can reposition rather than rebuild from scratch.
- `content-notes.md` contains your verified skills, projects, and bio text — I will treat it as the single source of truth.
- "Public contact method" means email or a professional profile link (LinkedIn/GitHub), not a phone number.
- The site has no existing backend/form submission (per constraints) — if one exists, it needs removal, which is a larger change than "small front-end correction."

**Risks:**
- If the template includes analytics snippets (e.g., Google Analytics) or a hidden form action, removing them may break unrelated styling/JS if not cleanly separated.
- If `content-notes.md` doesn't explicitly list cybersecurity skills, I cannot invent them — this could leave criterion 3 unmet without your input.
- Reordering the DOM to put contact info "at the beginning" could conflict with existing CSS layout (e.g., if hero image/name block is styled with specific flex ordering).
- If the template's existing skills list includes generic ones (e.g., "Python," "React"), I need explicit confirmation before removing/adding entries, since I must not invent *or silently delete* verified skills.

---

## 3. Proposed Test Checklist

**Content Accuracy**
- [ ] Every skill/project statement on the page matches an entry in `content-notes.md`
- [ ] No education, job history, award, or link appears that isn't in `content-notes.md`
- [ ] No personal info beyond name, role, and one public contact method is visible anywhere (including HTML comments/metadata)

**Structure & Criteria**
- [ ] Name, role, and intro visible without scrolling on desktop and mobile
- [ ] Contact info appears within the first visible screen / early in DOM order
- [ ] Skills section includes explicit cybersecurity-related items (as sourced from notes)

**Accessibility**
- [ ] Color contrast checked with a tool (e.g., WebAIM contrast checker) — passes AA
- [ ] All images have descriptive `alt` text (or `alt=""` if purely decorative)
- [ ] Tab order is logical; all interactive elements reachable via keyboard
- [ ] Visible focus indicator on links/buttons
- [ ] Link text is descriptive out of context (no "here"/"this link")

**Responsive**
- [ ] Layout usable at 320px width (small phones) without horizontal scroll
- [ ] Touch targets (buttons/links) are reasonably sized (~44px)

**Security/Privacy**
- [ ] No analytics/tracking scripts present
- [ ] No form that submits to an external service or backend
- [ ] No hidden metadata (e.g., in `<meta>` tags, JS comments) with private info

**Technical**
- [ ] Site loads with no console errors
- [ ] HTML validates (no unclosed tags, broken structure)
- [ ] License/attribution comments unchanged

---

## 4. Questions Before Implementation

1. **Can you share the actual files** — `index.html`, `styles.css`, `script.js`, and `content-notes.md`? I need real content to verify against, not placeholders.
2. **What is your approved public contact method** — email address, LinkedIn, GitHub, or a contact form (note: a form implies backend, which is disallowed unless it's a `mailto:` link or third-party static form service you already approved)?
3. **What cybersecurity-related skills/concerns are actually listed in `content-notes.md`**? I won't add any not already documented.
4. Does the current template have **any existing backend calls, analytics scripts, or tracking pixels** I should identify and remove?
5. Is there a **required license/attribution notice** from the original template author that must remain visible (e.g., in footer or code comments)? If so, please paste its exact current text so I preserve it verbatim.
6. Any specific **name/role/intro wording** you've already drafted, or should I pull that directly from `content-notes.md` as well?

---

Once you provide the actual files and answers above, I can give you concrete, line-level edits rather than a generic plan.
