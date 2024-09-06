
# Accessibility Component Specifications

## Component 5: Form Groups (e.g., Search and Application Forms)

### Gherkin Story

```gherkin
Feature: Form Groups

  Scenario: A keyboard-only user fills out a job application form
    Given I am a keyboard-only user
    When I navigate through the application form
    Then I should be able to tab through all input fields in a logical order
    And I should be able to submit the form using the keyboard

  Scenario: A screen reader user fills out a form
    Given I am a screen reader user
    When I focus on a form field
    Then the screen reader should announce the label for each field
    And any required fields should be announced as required

  Scenario: A low-vision user navigates a form
    Given I am a user with low vision
    When I zoom into the form
    Then all form elements should remain clear and legible
    And form fields should maintain enough space to avoid crowding or overlap
    And I should be able to easily see the focus state on the active form field
```

### Expected Interaction Design and Keystrokes

- **Keyboard Navigation:**
  - Use `Tab` to navigate between form fields.
  - Use arrow keys to navigate through **radio buttons** and **checkboxes**.
  - For **select boxes** (dropdowns):
    - Press `Space` or `Enter` to open the dropdown.
    - Use `Up` and `Down` arrow keys to move between options.
    - Press `Enter` to select an option.
  - Use `Shift + Tab` to move backward through the form.
  
- **Screen Reader Behavior:**
  - Screen reader should announce each form field’s label when focused.
  - Required fields are announced as “required” (e.g., "First Name, required").
  - For **select boxes**, screen readers will announce the current selection and allow navigation through the list of options using the arrow keys.
  - Error messages should be associated with the form fields and announced by the screen reader after an unsuccessful submission.

- **Low-Vision User Needs:**
  - Text should be zoomable without breaking the layout.
  - Form fields and labels should remain clear and distinct when zoomed.
  - High contrast between text and background is essential to improve readability.
  - A clearly visible focus state must be present on active form fields.

### Component Anatomy

- **Elements:**
  - `<fieldset>` to group related form inputs.
  - `<legend>` to provide context for each form group.
  - Form elements include:
    - Text input fields.
    - Radio buttons, checkboxes (navigable using arrow keys).
    - Select boxes (navigable using arrow keys), buttons.

### Properties

- **Size:**
  - **Width:** 100% for text input fields and dropdowns.
  - **Height:** Minimum of 44px height for touch target accessibility.
  - **Field Group Spacing:** 16px between groups of fields (e.g., name, email, etc.).

- **Field Labels:**
  - Each input field has an associated `<label>` to describe its purpose.
  - Use `aria-describedby` or `aria-invalid` for error messaging.

- **Focus State:**
  - Ensure the focus indicator is highly visible (use bold or vibrant color outlines).

### States

- **Visual States:**
  - **Default:** Form fields display default values or placeholders.
  - **Focus:** Highlight the focused field with a border or background color change.
  - **Error State:** Red border and error message below the input if the input is invalid.
  - **Zoomed View (Low Vision):** Ensure that text and input fields scale proportionately when zoomed, without layout breakage.

- **ARIA States:**
  - `aria-invalid="true"` for fields with errors.
  - `aria-required="true"` for required fields.

### Design Tokens

- **Typography:**
  - **Font Family:** `Arial, sans-serif`.
  - **Font Size:** `16px` (with scalability for low vision users).
  - **Line Height:** `24px`.

- **Colors:**
  - **Text Color (Foreground):** `#000000` (Black).
  - **Placeholder Text Color:** `#757575` (Gray).
  - **Error Message Color:** `#D32F2F` (Red).
  
- **Spacing:**
  - **Padding:** `8px` inside input fields.
  - **Margin:** `16px` between field groups.

- **Focus Indicator:**
  - **Outline Width:** `2px`.
  - **Outline Style:** `solid`.
  - **Outline Color:** `#0078D4` (Blue) for focus.

### Applicable WCAG Criteria

- **1.3.1 Info and Relationships:** Ensure form fields and labels are programmatically associated.
- **2.1.1 Keyboard:** All form fields and submit buttons must be keyboard accessible.
- **3.3.1 Error Identification:** Error messages must be associated with their respective fields.
- **3.3.2 Labels or Instructions:** Labels must clearly describe the purpose of each form field.
- **1.4.3 Contrast (Minimum):** Text and background must meet contrast requirements (4.5:1 for normal text).
- **1.4.4 Resize Text:** Text must remain readable and functional when resized by up to 200%.

### Alignment with WCAG Tokens

- **Text Size Token:** Use `16px` as the minimum for all form labels and inputs, ensuring scalability.
- **Color Contrast Tokens:** Ensure all text and error messages meet the 4.5:1 contrast ratio.
- **Focus Indicator Token:** Use a 2px solid outline to indicate focus on form fields.

### WCAG Success Criteria Checklist

**Product:**

- [ ] Define the form structure, ensuring clear and descriptive labels for each field.
- [ ] Ensure all fields are programmatically linked to their labels for assistive technologies.

**Design:**

- [ ] Design clear, simple labels for each field.
- [ ] Ensure form fields have appropriate spacing for accessibility and readability.
- [ ] Design error messages and validation that is visually clear and accessible.
- [ ] Ensure the layout is flexible for zoom and magnification without breaking content.

**Development:**

- [ ] Implement proper ARIA attributes (e.g., `aria-required`, `aria-invalid`) for form fields.
- [ ] Ensure forms are keyboard accessible.
- [ ] Ensure error messages are correctly associated with form fields using `aria-describedby`.
- [ ] Ensure the form layout and text scale properly for users with low vision.

**QA:**

- [ ] Test the form for keyboard navigation.
- [ ] Verify that each form field’s label is announced by screen readers.
- [ ] Ensure error messages are correctly read by screen readers.
- [ ] Check that the form is accessible to users with cognitive and low-vision disabilities, with clear instructions and responsive scaling.
