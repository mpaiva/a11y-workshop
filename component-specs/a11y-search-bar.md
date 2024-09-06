
# Accessibility Component Specifications

## Component 3: Search Bar

### Gherkin Story

```gherkin
Feature: Search Bar

  Scenario: A screen reader user uses the search bar
    Given I am a screen reader user
    When I focus on the search bar
    Then the screen reader should announce "Search for jobs, input"
    And I should be able to type a job title and submit using the enter key
  
  Scenario: A user with cognitive disability uses the search bar
    Given I am a user with cognitive disabilities
    When I use the search bar
    Then there should be a placeholder with an example, like "e.g., Paralegal"
    And instructions should be provided in plain language
```

### Expected Interaction Design and Keystrokes

- **Keyboard Navigation:**
  - Use the `Tab` key to focus on the search bar.
  - After focusing, type the job title or keyword.
  - Press `Enter` to submit the search query.

- **Screen Reader Behavior:**
  - Search bar should be announced as "Search for jobs, input."
  - When focused, placeholder text such as "e.g., Paralegal" should be announced by the screen reader.

### Component Anatomy

- **Elements:**
  - `<input>` element of type `text` with a descriptive label.
  - Submit button for triggering the search.
  - Placeholder text to provide examples of typical search queries.

### Properties

- **Size:**
  - **Width:** 100% or constrained within the layout.
  - **Height:** At least 44px for touch accessibility.
  - **Target Size:** Minimum 44x44px to meet touch guidelines (WCAG 2.5.5).

- **Placeholder Text:**
  - Clear and concise example, e.g., "e.g., Paralegal."

### States

- **Visual States:**
  - **Default:** Input with placeholder text.
  - **Focus:** Highlighted border and background color to indicate active input.
  - **Error State:** Red border and error message below the input if the search query is invalid.

- **ARIA States:**
  - `aria-label="Search for jobs"` for users of assistive technology.
  - `aria-invalid="true"` in case of errors.

### Design Tokens

- **Typography:**
  - **Font Family:** `Arial, sans-serif`.
  - **Font Size:** `16px`.
  - **Line Height:** `24px`.

- **Colors:**
  - **Text Color (Foreground):** `#000000` (Black).
  - **Placeholder Text Color:** `#757575` (Gray).
  - **Background Color:** `#FFFFFF` (White).
  
- **Spacing:**
  - **Padding:** `8px 16px`.
  - **Margin:** `16px` (top and bottom).

- **Focus Indicator:**
  - **Outline Width:** `2px`.
  - **Outline Style:** `solid`.
  - **Outline Color:** `#0078D4` (Blue) for accessibility.

### Applicable WCAG Criteria

- **1.3.1 Info and Relationships:** The input field must have a clear label.
- **2.1.1 Keyboard:** Search functionality should be operable via keyboard.
- **3.3.2 Labels or Instructions:** Placeholder text or label should describe the purpose of the input field.
- **1.4.3 Contrast (Minimum):** Text and background must meet contrast requirements (4.5:1 for normal text).

### Alignment with WCAG Tokens

- **Text Size Token:** Use `16px` as the minimum font size for readability.
- **Color Contrast Tokens:** Ensure placeholder and foreground text meet the 4.5:1 contrast ratio.
- **Focus Indicator Token:** Use a clear and consistent focus outline to guide users with keyboard navigation.

### WCAG Success Criteria Checklist

**Product:**

- [ ] Define the search functionality, ensuring it is accessible for users with disabilities.
- [ ] Ensure placeholder text provides useful guidance.

**Design:**

- [ ] Provide clear, simple instructions for search input.
- [ ] Design a focus state that is visually distinctive.
- [ ] Ensure the search bar meets size and spacing requirements for touch target accessibility.

**Development:**

- [ ] Implement proper `aria-label` and `aria-invalid` attributes.
- [ ] Ensure the search bar is keyboard focusable.
- [ ] Use clear error messages and validation.

**QA:**

- [ ] Verify the search bar can be operated via keyboard and screen reader.
- [ ] Ensure placeholder text is announced by screen readers.
- [ ] Check that the focus state is clearly visible and meets accessibility requirements.
