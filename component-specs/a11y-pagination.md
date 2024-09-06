
# Accessibility Component Specifications

## Component 11: Pagination Controls

### Gherkin Story

```gherkin
Feature: Pagination Controls

  Scenario: A keyboard-only user navigates through job search results
    Given I am a keyboard-only user
    When I navigate through job search results using pagination controls
    Then I should be able to use the Tab key to move between pages
    And I should be able to use the Enter or Space key to select a page number or next/previous buttons

  Scenario: A screen reader user navigates through pagination
    Given I am a screen reader user
    When I encounter pagination controls
    Then the screen reader should announce the current page number and the available pages
    And I should be able to navigate between pages using the arrow keys and select a page using Enter or Space

  Scenario: A user with low vision navigates through paginated content
    Given I am a user with low vision using screen magnification
    When I navigate the pagination controls
    Then the current page number should be clearly highlighted and have sufficient contrast to make it distinguishable
    And I should be able to magnify the page numbers without losing context of the pagination controls
```

### Expected Interaction Design and Keystrokes

- **Keyboard Navigation:**
  - Use the `Tab` key to focus on pagination controls.
  - Use `Enter` or `Space` to select a specific page or move to the next/previous page.
  - Use arrow keys (`Left` and `Right`) to move between page numbers.

- **Screen Reader Behavior:**
  - The screen reader should announce the pagination structure, including the current page number, total pages, and any next/previous buttons.
  - As the user navigates, the screen reader should announce the page number that is currently focused.

- **Low-Vision User Behavior:**
  - Ensure that the current page is visually distinct, with high-contrast highlighting.
  - Allow magnification of the pagination area without losing visibility of page numbers or navigation controls.

### Component Anatomy

- **Elements:**
  - A series of page links (`<a>`, `<button>`, or `<li>`) for each page in the pagination.
  - A visual indicator (highlight or underline) for the current page.
  - Next/Previous buttons for navigation between pages.

### Properties

- **Size:**
  - **Width:** Flexible, based on the number of pages.
  - **Height (Target Size):** Ensure each control is at least `44px` in height to meet touch accessibility guidelines.

- **ARIA Attributes:**
  - `aria-current="page"` for the currently active page.
  - `aria-label` for each control (e.g., "Page 1", "Next Page").

### States

- **Visual States:**
  - **Default:** Pagination numbers and next/previous buttons are displayed.
  - **Active (Current Page):** The current page number is visually highlighted, typically using bold text, a different background color, or an underline.
  - **Focus:** Focus is visually indicated by an outline around the selected pagination control.

- **ARIA States:**
  - `aria-current="page"` for the current page.
  - `aria-label` to describe the purpose of each page link (e.g., "Go to page 3").

### Design Tokens

- **Typography:**
  - **Font Family:** `Arial, sans-serif`.
  - **Font Size:** `16px` for page numbers.
  - **Line Height:** `24px` for readability.

- **Colors:**
  - **Current Page Text Color:** `#FFFFFF` (White).
  - **Current Page Background Color:** `#0078D4` (Blue).
  - **Other Pages Text Color:** `#000000` (Black).
  
- **Spacing:**
  - **Margin:** `8px` between pagination numbers to avoid crowding.
  - **Padding:** Ensure sufficient padding for touch accessibility (minimum `8px` around each pagination control).

- **Focus Indicator:**
  - **Outline Width:** `2px`.
  - **Outline Style:** `solid`.
  - **Outline Color:** `#0078D4` (Blue) for a clear focus state.

### Benefits for Users with Disabilities

- **Keyboard Navigation:** Users relying on keyboard navigation can easily navigate between pages using the arrow keys, Tab, and Enter/Space to move through results without using a mouse.
- **Screen Reader Compatibility:** Pagination controls are announced clearly by screen readers, with details about the current page and the total number of pages.
- **Low Vision (Magnification):** Current page numbers are highly visible and easily identifiable through sufficient contrast and visual cues, which remain intact when zoomed.

### Applicable WCAG Criteria

- **1.3.1 Info and Relationships:** Pagination controls should be programmatically linked to their associated pages.
- **1.4.3 Contrast (Minimum):** Ensure sufficient contrast between the current page and other page numbers or controls.
- **1.4.4 Resize Text:** Ensure that pagination controls remain readable when text is resized up to 200%.
- **2.1.1 Keyboard:** Pagination controls must be fully operable via keyboard, including selecting page numbers and moving between pages.
- **2.4.3 Focus Order:** Focus should move logically through pagination controls in a clear, sequential order.
- **2.4.4 Link Purpose (In Context):** Ensure each page link is clear and descriptive, especially when read by screen readers (e.g., "Go to Page 3").
- **4.1.2 Name, Role, Value:** Screen readers must announce the current page and any pagination actions (next/previous) properly.

### Alignment with WCAG Tokens

- **Focus Indicator Token:** Use a 2px solid outline to highlight the focus state on pagination controls.
- **Color Contrast Tokens:** Ensure the current page's text and background meet the 4.5:1 contrast ratio for accessibility.
- **Text Size Token:** Use a minimum font size of `16px` to ensure readability.
- **Target Size Token:** Ensure the pagination control target size meets or exceeds the 44px height for touch accessibility.

### Assistive Technologies Considerations

- **Screen Readers:** Announce the current page, the total number of pages, and available next/previous navigation options.
- **Keyboard Navigation:** Ensure that users can move through pagination controls using Tab and arrow keys, and select pages using Enter or Space.
- **Low Vision (Magnified Screen):** Ensure the pagination layout remains clear and legible when magnified, with high-contrast highlighting for the current page.

### WCAG Success Criteria Checklist

**Product:**

- [ ] Ensure that pagination controls are easy to navigate, clear, and well-labeled for users with disabilities.
- [ ] Provide sufficient visual contrast and focus indicators for users navigating through pages.

**Design:**

- [ ] Use high-contrast colors for the current page to make it visually distinct.
- [ ] Ensure that pagination controls are large enough to be operated via touch or with limited mobility.
- [ ] Provide sufficient space between pagination numbers to avoid crowding.

**Development:**

- [ ] Implement `aria-current="page"` for the current page in the pagination controls.
- [ ] Ensure that pagination controls are fully keyboard accessible and work with screen readers.
- [ ] Ensure that text remains readable and pagination layout remains usable when zoomed up to 200%.

**QA:**

- [ ] Test that pagination controls are fully accessible via screen readers.
- [ ] Verify that pagination controls are keyboard accessible and follow logical focus order.
- [ ] Ensure that low-vision users can clearly identify the current page and navigate through pagination without losing context.
