
# Accessibility Component Specifications

## Component 4: Unordered List Groups (Job Listings)

### Gherkin Story

```gherkin
Feature: Job Listings

  Scenario: A screen reader user navigates through job listings
    Given I am using a screen reader
    When I focus on the list of job postings
    Then the screen reader should announce each job title, company, and posting date
    And I should be able to navigate each item using arrow keys

  Scenario: A low-vision user navigates through job listings
    Given I have low vision
    When I scroll through the job listings
    Then I should be able to zoom in without losing content clarity or layout
```

### Expected Interaction Design and Keystrokes

- **Keyboard Navigation:**
  - Use `Tab` to move between job listings.
  - Use arrow keys to move between list items for navigation.

- **Screen Reader Behavior:**
  - Screen readers announce each job listing item in sequence, including job title, company, and date.
  - Job titles should be focusable, with `aria-label` attributes providing extra detail.

### Component Anatomy

- **Elements:**
  - An unordered list `<ul>` containing `<li>` elements for each job listing.
  - Each list item contains:
    - Job title (focusable).
    - Company name.
    - Posting date.

### Properties

- **Size:**
  - **Width:** Flexible to fit the container.
  - **Height:** Variable based on content.
  - **Spacing:** 16px margin between list items.

- **Focusable Items:**
  - Job title should be focusable, and `aria-labelledby` can be used to describe the item with extra context.

### States

- **Visual States:**
  - **Default:** Each list item displays job title, company, and date.
  - **Focus:** Highlight focusable job titles with a color change or underline for accessibility.
  - **Hover:** Optional state where the job title changes color.

- **ARIA States:**
  - `aria-label="Job title: Paralegal, Company: XYZ Law Firm, Posted: 2 days ago"` on focusable items to improve screen reader experience.

### Design Tokens

- **Typography:**
  - **Font Family:** `Arial, sans-serif`.
  - **Font Size:** `16px`.
  - **Line Height:** `24px`.

- **Colors:**
  - **Text Color (Foreground):** `#000000` (Black).
  - **Hover Color (Job Title):** `#0078D4` (Blue).
  
- **Spacing:**
  - **Margin:** `16px 0` between job listings.
  - **Padding:** `8px` inside each list item.

- **Focus Indicator:**
  - **Outline Width:** `2px`.
  - **Outline Style:** `solid`.
  - **Outline Color:** `#0078D4` (Blue).

### Applicable WCAG Criteria

- **1.3.1 Info and Relationships:** Ensure that the job listing structure is conveyed programmatically (e.g., job title, company, date).
- **2.1.1 Keyboard:** List items and job titles should be fully operable via keyboard.
- **2.4.3 Focus Order:** Navigation through job listings should follow a logical order.
- **2.4.7 Focus Visible:** Focusable items (e.g., job titles) must have a clear focus indicator.
- **1.4.4 Resize Text:** Text must be zoomable without loss of content or functionality.

### Alignment with WCAG Tokens

- **Text Size Token:** Use `16px` as the minimum for job title and company names.
- **Color Contrast Tokens:** Ensure text and background colors meet the 4.5:1 contrast ratio.
- **Focus Indicator Token:** Clear focus states on job titles with a 2px solid outline.

### WCAG Success Criteria Checklist

**Product:**

- [ ] Define the structure of job listings, ensuring all relevant details are conveyed to assistive technologies.
- [ ] Ensure job titles are focusable and navigable via keyboard.

**Design:**

- [ ] Provide consistent spacing between job listings.
- [ ] Use clear, readable typography for job titles and details.
- [ ] Design focus and hover states that are easily distinguishable.

**Development:**

- [ ] Implement proper ARIA labeling for job listing details.
- [ ] Ensure focus states are correctly applied to job titles.
- [ ] Implement keyboard and screen reader navigation through list items.

**QA:**

- [ ] Verify the job listings are fully operable via keyboard.
- [ ] Test that each job listing is announced correctly by screen readers.
- [ ] Check focus and hover states for accessibility.
- [ ] Ensure text is readable and scales correctly for low-vision users.
