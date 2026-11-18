# Accessibility Conformance Starter

Use this small site for Module 5 practice if you do not want to use your capstone yet.

## Files

- `index.html`: sample page with intentional accessibility issues.
- `styles.css`: starter styles with some focus, contrast, reflow, and motion issues to audit.

## Practice goal

Audit and remediate:

- landmarks and heading structure
- link and button names
- keyboard access and visible focus
- zoom/reflow behavior
- contrast
- form labels and required states
- table caption/headers
- image alternatives
- motion preference

Document each issue, fix, and retest result.

## Manual Accessibility Audit
Kiara McRae | GIT 414

### Scope and Method
I audited the supplied Community Tech Day practice page using
Chrome Lighthouse, keyboard navigation, HTML/CSS inspection,
and a narrow responsive viewport.

### Issues, Fixes, and Retests

1. Missing form labels
- Evidence: Lighthouse flagged inputs without associated labels.
- Impact: Assistive technology may not identify the requested information.
- Priority: High.
- Fix: Added labels associated with the Name and Email inputs.
- Retest: Labels focus the correct inputs. Lighthouse no longer flags them.

2. Unnamed submit button
- Evidence: The button was blank and Lighthouse flagged its missing name.
- Impact: Users could not identify the button's purpose.
- Priority: High.
- Fix: Added "Submit practice form" as visible button text.
- Retest: The button is labeled and the automated finding is resolved.

3. Invisible keyboard focus
- Evidence: During Tab navigation, I could not see the focused element.  The CSS removed outlines.
- Impact: Keyboard users could lose their position.
- Priority: High.
- Fix: Added a visible focus outline with a contrasting white edge.
- Retest: Focus is visible while moving through links and form controls.

4. Clipped narrow layout
- Evidence: The narrow view clipped content because of fixed widths.
- Impact: Small-screen and zoom users could struggle to reach content.
- Priority: High.
- Fix: Added a flexible main container, wrapping navigation, responsive card columns, and flexible hero spacing.
- Retest: The narrow layout fits without the earlier clipping.

5. Low-contrast card links
- Evidence: Lighthouse reported insufficient contrast.
- Impact: Links could be difficult to read.
- Priority: High.
- Fix: Replaced the gray card-link color with dark maroon.
- Retest: Lighthouse no longer reports the contrast issue.

6. Skipped heading level
- Evidence: Lighthouse flagged the jump from h1 to h3.
- Impact: Heading navigation could communicate an incorrect hierarchy.
- Priority: Medium.
- Fix: Changed the hero subtitle to a styled paragraph.
- Retest: Lighthouse no longer flags heading order.

7. Unhelpful links
- Evidence: Three "More" links used href="#" and provided no useful destination.
- Impact: Users could not predict or reach relevant information.
- Priority: Medium.
- Fix: Added descriptive links to the schedule or registration section.
- Retest: Links reach their intended sections.

8. Table relationships
- Evidence: The header row used td elements and had no caption.
- Impact: Table relationships were not explicitly identified.
- Priority: Medium.
- Fix: Added a caption and th elements with scope="col".
- Retest: HTML inspection confirms the caption and column headers.

9. Repeated decorative illustrations
- Evidence: The same generic graphic had inconsistent alternatives,
 including "poster."
- Impact: Unnecessary announcements could distract from session information.
- Priority: Low.
- Fix: Used empty alt text for all three decorative illustrations.
- Retest: HTML inspection confirms consistent empty alternatives.

10. Continuous motion
- Evidence: One card used an infinite pulse animation.
- Impact: Nonessential movement could distract or discomfort users.
- Priority: Medium.
- Fix: Disabled the animation.
- Retest: The card remains still.

### Additional Form Correction
The Name field was marked required visually but lacked required
validation. Email required validation lacked a visible required marker.
I made both fields visibly and programmatically required.

Instructions identify this as a practice form with no saved registration.
Empty-field validation worked during retesting.

### Automated and Manual Findings
Lighthouse caught missing form labels and the unnamed button.
Manual testing revealed the invisible keyboard focus and clipped layout,
which were not listed in the automated findings.

### Results
Lighthouse Accessibility:
- Before: 72.
- After: 100.

The final audit was run November 17, 2026, using Lighthouse 13.5.0
with emulated mobile and Slow 4G conditions.

I also retested keyboard navigation, revised links, narrow layout,
form labels, required validation, and motion.

### Evidence and Limitations
Before and after screenshots are stored in evidence/.

Testing was completed locally in Chrome. A score of 100 only describes
the automated checks and does not establish full accessibility conformance.
Screen-reader testing and cross-browser testing were not completed.


### AI Disclosure
For this week's assignment, I used ChatGPT to help organize audit findings. I applied the changes, performed the browser checks, and collected the evidence myself. Retest results reflect my
observations and the Lighthouse report.