
# Accessibility Component Specifications

## Component 8: Accordion Controls (Supporting Users with Dyslexia)

### Gherkin Story

```gherkin
Feature: Accordion Controls

  Scenario: A screen reader user navigates an accordion
    Given I am a screen reader user
    When I encounter an accordion section
    Then the screen reader should announce the heading and state of each section (expanded or collapsed)
    And I should be able to expand and collapse sections using the Enter or Space key

  Scenario: A keyboard-only user navigates an accordion
    Given I am a keyboard-only user
    When I navigate to an accordion section
    Then I should be able to use the Tab key to focus on accordion headers
    And I should be able to expand or collapse sections using the Enter or Space key

  Scenario: A user with dyslexia views a page with an accordion
    Given I am a user with dyslexia
    When I navigate to a page that contains long blocks of text
    Then the text should be presented in collapsed accordion sections to avoid overwhelming me
    And I should be able to expand sections to view smaller, digestible chunks of information
```

### Expected Interaction Design and Keystrokes

- **Keyboard Navigation:**
  - Use the `Tab` key to navigate between accordion headers.
  - Use `Enter` or `Space` to expand or collapse the accordion sections.
  - Once expanded, users can tab through content inside the section.
  
- **Screen Reader Behavior:**
  - Screen readers announce the state of the accordion (expanded or collapsed) and the heading of each section.
  - The screen reader will also announce any interactive elements within the expanded section.

- **User with Dyslexia:**
  - Presenting content in a collapsed state by default helps prevent the overwhelming sensation of a “wall of text.”
  - Users can focus on one section at a time, reducing cognitive load and improving reading comprehension.

### Component Anatomy

- **Elements:**
  - Accordion `<button>` element used for the headers (collapsible).
  - `<div>` or `<section>` for the content inside each accordion panel.
  - Each accordion button has an `aria-expanded` attribute to indicate its state.

### Properties

- **Size:**
  - **Width:** Flexible to fill the container (e.g., 100% width).
  - **Content Height:** Adjusts dynamically based on the content in each section.
  
- **ARIA Labels:**
  - Each accordion button must have `aria-expanded="true"` or `aria-expanded="false"`.
  - Headers should have proper `aria-controls` to associate the button with its content.

### States

- **Visual States:**
  - **Default:** Accordion sections are collapsed by default to reduce cognitive load.
  - **Expanded:** When expanded, the section content becomes visible, and the button is visually styled to indicate the open state.
  - **Focus:** Accordion headers are styled with a focus outline to indicate keyboard focus.

- **ARIA States:**
  - `aria-expanded="true"` when the section is expanded.
  - `aria-expanded="false"` when the section is collapsed.

### Design Tokens

- **Typography:**
  - **Font Family:** `Arial, sans-serif`.
  - **Font Size:** `18px` for accordion headings.
  - **Line Height:** `24px` for readability.

- **Colors:**
  - **Header Text Color:** `#000000` (Black).
  - **Expanded Background Color:** `#F1F1F1` (Light Gray).
  
- **Spacing:**
  - **Margin:** `16px` between accordion sections.
  - **Padding:** `12px` inside each section for content.

- **Focus Indicator:**
  - **Outline Width:** `2px`.
  - **Outline Style:** `solid`.
  - **Outline Color:** `#0078D4` (Blue) to show focus.

### Benefits for Users with Dyslexia

- **Reduced Cognitive Load:** Collapsing content into sections prevents overwhelming the user with large blocks of text, which can create reading difficulties.
- **Focused Reading:** Users can open one section at a time, focusing on smaller chunks of content, which improves their ability to comprehend the material.
- **Enhanced Control:** Users can control the flow of information, expanding and collapsing sections as needed to process text at their own pace.

### Applicable WCAG Criteria

- **1.3.1 Info and Relationships:** Accordion sections should be programmatically associated with their content.
- **1.4.10 Reflow:** Content inside accordion sections should resize and reflow properly when zoomed or adjusted to prevent horizontal scrolling.
- **1.4.12 Text Spacing:** Text inside accordion content should be adjustable for spacing, line height, and word spacing, ensuring readability for dyslexic users.
- **2.1.1 Keyboard:** Accordion controls must be fully operable via keyboard, including expansion and collapsing.
- **2.4.3 Focus Order:** Focus must follow a logical order through the accordion headers and content.
- **2.4.7 Focus Visible:** Ensure a clear visual indication of focus on accordion headers.
- **4.1.2 Name, Role, Value:** Screen readers must announce the role (button), state (expanded or collapsed), and name (header) for each accordion section.

### Alignment with WCAG Tokens

- **Focus Indicator Token:** Use a 2px solid outline for accordion headers when they receive focus.
- **Color Contrast Tokens:** Ensure that the text and background colors for accordion headers and expanded content meet the 4.5:1 contrast ratio.

### Assistive Technologies Considerations

- **Screen Readers** will announce the name, state (expanded or collapsed), and role of each accordion section.
- **Keyboard Navigation** should allow users to easily navigate through accordion headers and toggle sections.
- **Users with Dyslexia** benefit from the accordion's ability to segment content into smaller, manageable pieces, reducing the sense of cognitive overload.
- **Screen Magnifiers** should ensure that focus states and content are clearly visible when zoomed.

### WCAG Success Criteria Checklist

**Product:**

- [ ] Ensure accordions are used to group large sections of content logically.
- [ ] Default accordion sections should be collapsed to reduce cognitive overload for users with dyslexia and others who benefit from smaller text blocks.

**Design:**

- [ ] Ensure focus states are visually clear for each accordion header.
- [ ] Ensure expanded content is easy to distinguish with sufficient spacing.

**Development:**

- [ ] Implement `aria-expanded` for all accordion buttons to indicate the state (expanded/collapsed).
- [ ] Ensure keyboard navigation works for expanding and collapsing sections.
- [ ] Implement focus management, ensuring that focus moves into the content after expansion.

**QA:**

- [ ] Test that accordions are fully keyboard accessible.
- [ ] Verify that screen readers announce the state and heading of each section.
- [ ] Ensure visual focus indicators are present and clear for low-vision users.
- [ ] Verify that content remains accessible when expanded and collapsed.
- [ ] Test the cognitive benefits of the accordion with users who have dyslexia, ensuring that collapsed content improves focus and reduces reading fatigue.
