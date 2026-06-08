# Contribution [1]: [Issue Title]

**Contribution Number:** [1]  
**Student:** [Oluwatomisin Sapara-Williams]  
**Issue:** [https://github.com/release-plz/release-plz/issues/1876]  
**Status:** [Phase I]

---

## Why I Chose This Issue

[I chose this issue because this a UI implementation, I enjoy working on designs and logos help users quickly identify what they are looking for and in this case, this would be for company's social which can helps users get more information]


---

## Understanding the Issue

### Problem Description

[ The website footer’s Social section is missing the logos for the social links. The page currently shows BlueSky and LinkedIn as plain text links instead of branded icon links.

]

### Expected Behavior

[The Social links in the footer should display with their respective logos, so the footer visually matches the intended social branding.

]

### Current Behavior

[The footer renders only the link labels BlueSky and LinkedIn. No logos appear next to them.]

### Affected Components

[ The issue is in the website footer configuration in docusaurus.config.js, specifically the themeConfig.footer.links section for the Social column. The rendering is handled by Docusaurus’ default classic theme footer component, and there is no custom footer override under website/src/theme.]

---

## Reproduction Process

### Environment Setup

[The website dependencies were not installed initially, so docusaurus was not available. I fixed that by running npm install in the website package. I also had to start the dev server from the website directory explicitly, because running it from the repo root caused npm to look for a missing root-level package.json. Using npm --prefix website run start -- --host 127.0.0.1 --port 3000 worked.]

### Steps to Reproduce

1. [Start the website locally from the website package.]
2. [Open the homepage.]
3. [Scroll to the footer.]
4 [Observe that the Social section shows BlueSky and LinkedIn as text-only links.]


### Reproduction Evidence

- **Commit showing reproduction:** (https://github.com/tsw-codes/release-plz.git)]
- **Screenshots/logs:** [If applicable]
- **My findings:** [ the footer config at docusaurus.config.js:117 defines those social items only with label and href, so the default footer renderer has no logo data to display.
]

---

## Solution Approach

### Analysis

[The root cause is that the footer social links are declared as simple link items, not as HTML or icon-bearing items. Docusaurus’ footer rendering only shows the text label for those entries, so the logos never appear.]

### Proposed Solution

[Update the Social footer items to render branded markup instead of plain text links. The fix should use footer items that can include custom HTML, with the logo and label placed together, and add any necessary CSS for alignment and sizing]

### Implementation Plan

Using UMPIRE framework (adapted):

Understand: The footer Social section should show logos for BlueSky and LinkedIn, not plain text links.

Match: The codebase already uses custom styling for other visual elements in custom.css, and the footer is already configured centrally in docusaurus.config.js.

Plan:

Modify docusaurus.config.js so the Social footer items render logo markup instead of plain text labels.
Add or reuse social logo assets in the website static assets if needed.
Update custom.css for consistent icon sizing and spacing.
Verify the footer in a browser and confirm the site still builds.
Implement: I’m working on branch website-add-logos-to-release-plz-socials-1876.

Review: Check that the change stays within the website package, keeps accessible link text, and does not disturb unrelated footer items or the navbar.

---

## Testing Strategy

### Unit Tests

- [ ] Test case 1: [Description]
- [ ] Test case 2: [Description]
- [ ] Test case 3: [Description]

### Integration Tests

- [ ] Integration scenario 1
- [ ] Integration scenario 2

### Manual Testing

[What you tested manually and results]

---

## Implementation Notes

### Week [X] Progress

[What you built this week, challenges faced, decisions made]

### Week [Y] Progress

[Continue documenting as you work]

### Code Changes

- **Files modified:** [List]
- **Key commits:** [Links to important commits]
- **Approach decisions:** [Why you chose certain approaches]

---

## Pull Request

**PR Link:** [GitHub PR URL when submitted]

**PR Description:** [Draft or final PR description - much of the content above can be adapted]

**Maintainer Feedback:**
- [Date]: [Summary of feedback received]
- [Date]: [How you addressed it]

**Status:** [Awaiting review / Iterating / Approved / Merged]

---

## Learnings & Reflections

### Technical Skills Gained

[What you learned technically]

### Challenges Overcome

[What was hard and how you solved it]

### What I'd Do Differently Next Time

[Reflection on your process]

---

## Resources Used

- [Link to helpful documentation]
- [Tutorial or Stack Overflow post that helped]
- [GitHub issues or discussions that helped]
