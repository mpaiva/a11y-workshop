
# Accessibility Component Specifications

## Component 6: Fieldset and Legend

### Gherkin Story

```gherkin
Feature: Fieldset and Legend

  Scenario: A screen reader user completes a grouped form
    Given I am using a screen reader
    When I focus on a fieldset in the job application form
    Then the screen reader should announce the legend of the group
    And the individual form elements should be announced with their respective labels

  Scenario: A user with cognitive disabilities completes a grouped form
    Given I am a user with cognitive disabilities
    When I see the form
    Then I should understand the form's structure due to the clear grouping of related inputs under a legend
    And the instructions provided should be easy to understand and follow
```

### Expected Interaction Design and Keystrokes

- **Keyboard Navigation:**
  - Use the `Tab` key to move between different form fields within the fieldset.
  - Use `Shift + Tab` to move backward through the form.
  - Press `Enter` or `Space` to activate buttons or checkboxes within the fieldset.

- **Screen Reader Behavior:**
  - The screen reader announces the **legend** (heading of the group) as the user enters the fieldset.
  - It will read the label of each input field as the user navigates through the form.

### Component Anatomy

- **Elements:**
  - `<fieldset>` to group related form inputs.
  - `<legend>` to provide context and description for the input fields within the group.
  - Input fields such as:
    - Text input fields.
    - Radio buttons.
    - Checkboxes.
    - Select dropdowns.

### Properties

- **Size:**
  - **Width:** 100% width for the entire group of fields.
  - **Fieldset Height:** Variable based on the number of form fields.
  - **Spacing:** 16px between each field in the group, and additional 16px between multiple fieldsets.

- **Fieldset and Legend Labels:**
  - The legend must clearly describe the purpose of the grouped fields.
  - The fieldset contains individual form fields, each associated with a `<label>` element.

### States

- **Visual States:**
  - **Default:** The legend is visible, and each field within the fieldset has its label.
  - **Focus:** Focused fields are highlighted with a border or background color change to indicate active input.
  - **Error State:** Error messages appear below individual fields when validation fails (e.g., red borders, red text).

- **ARIA States:**
  - **Legend:** Announced as the title of the grouped fields when entering the fieldset.
  - **Field Labels:** Each label is announced as the user navigates through the individual fields.

### Design Tokens

- **Typography:**
  - **Font Family:** `Arial, sans-serif`.
  - **Font Size (Legend):** `18px` for legends to distinguish them as section headers.
  - **Font Size (Labels):** `16px`.
  - **Line Height:** `24px`.

- **Colors:**
  - **Text Color (Legend):** `#000000` (Black).
  - **Error Message Color:** `#D32F2F` (Red).

- **Spacing:**
  - **Margin:** `16px` between fieldsets.
  - **Padding:** `8px` inside the fieldset for form elements.

- **Focus Indicator:**
  - **Outline Width:** `2px`.
  - **Outline Style:** `solid`.
  - **Outline Color:** `#0078D4` (Blue) for focus.

### Applicable WCAG Criteria

- **1.3.1 Info and Relationships:** The fieldset and legend provide semantic grouping for form inputs, ensuring that assistive technologies can properly interpret the structure.
- **1.3.5 Identify Input Purpose:** The fieldset must clearly describe the purpose of the grouped form controls.
- **2.4.6 Headings and Labels:** The legend serves as a heading for the grouped form controls.
- **2.4.7 Focus Visible:** Clearly indicate when a user has focused on an individual form input.

### Alignment with WCAG Tokens

- **Text Size Token:** Use `18px` for legends and `16px` for labels to ensure clear hierarchy.
- **Color Contrast Tokens:** Ensure the text and background meet the 4.5:1 contrast ratio for readability.
- **Focus Indicator Token:** Use a 2px solid outline for focus on active form fields.

### WCAG Success Criteria Checklist

**Product:**

- [ ] Ensure fieldsets are used in forms where related form inputs are grouped together logically.
- [ ] Each fieldset must have a clearly defined legend explaining its purpose.

**Design:**

- [ ] Design clear, readable legends and labels for each form group.
- [ ] Ensure spacing between fields and groups of fields maintains visual clarity.
- [ ] Use high-contrast colors for error messages and focus states.

**Development:**

- [ ] Ensure correct HTML markup for fieldsets and legends is implemented.
- [ ] Associate fieldsets with a relevant `<legend>` for screen reader users.
- [ ] Implement ARIA roles and states (if necessary) to enhance accessibility.

**QA:**

- [ ] Verify that screen readers correctly announce the legend and associated form fields.
- [ ] Ensure each field within the fieldset is keyboard accessible.
- [ ] Check that visual focus indicators are present and visible for low-vision users.
- [ ] Validate that users with cognitive disabilities can understand the form structure through clear grouping and labeling.
