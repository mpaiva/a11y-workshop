
# Accessibility Component Specifications

## Component 9: Dropdown Select Box (for Job Search Filters)

### Gherkin Story

```gherkin
Feature: Dropdown Select Box for Job Search Filters

  Scenario: A keyboard-only user interacts with a dropdown select box
    Given I am a keyboard-only user
    When I focus on the dropdown filter for job categories
    Then I should be able to use the Tab key to focus on the dropdown
    And I should be able to use the Up and Down arrow keys to navigate through options
    And I should be able to use the Enter key to select an option

  Scenario: A screen reader user interacts with a dropdown select box
    Given I am a screen reader user
    When I focus on the dropdown filter for job categories
    Then the screen reader should announce the label and the selected option
    And I should be able to use the Up and Down arrow keys to navigate the list
    And the screen reader should announce each option as I navigate
    And I should be able to press Enter to select an option

  Scenario: A user with motor impairments interacts with a dropdown select box
    Given I have motor impairments and use an alternative input device (e.g., switch control)
    When I reach the dropdown filter for job categories
    Then I should be able to use my input device to focus on and navigate through the options
    And I should be able to select an option using the device
```

### Expected Interaction Design and Keystrokes

- **Keyboard Navigation:**
  - Use the `Tab` key to focus on the dropdown.
  - Use `Enter` or `Space` to open the dropdown.
  - Use `Up` and `Down` arrow keys to navigate through the list of options.
  - Use `Enter` to select an option and close the dropdown.
  
- **Screen Reader Behavior:**
  - The screen reader should announce the dropdown label (e.g., "Job Categories").
  - When navigating the options, the screen reader should announce each option.
  - The selected option should be announced after selection.

### Component Anatomy

- **Elements:**
  - `<select>` element for the dropdown.
  - `<option>` elements for each choice in the dropdown.
  - Optionally, use a `<label>` to describe the dropdown filter’s purpose.

### Properties

- **Size:**
  - **Width:** Adjustable to fit the content.
  - **Height (Target Size):** A minimum of 44px height for the select control to ensure it meets touch target accessibility requirements. 
    - **Note:** Many common design systems tend to use smaller target sizes for select controls (often around 32px), which can lead to accessibility issues for users with motor impairments or those using touch devices. It's critical to increase the target size to ensure accessibility.

- **ARIA Attributes:**
  - `aria-labelledby` to associate the dropdown with its label.
  - `aria-expanded="true"` or `aria-expanded="false"` to indicate the state of the dropdown.

### States

- **Visual States:**
  - **Default:** The dropdown shows the selected option.
  - **Focus:** A visible focus outline appears around the dropdown when focused.
  - **Open:** The dropdown list is expanded, and the options are displayed.

- **ARIA States:**
  - `aria-expanded="true"` when the dropdown is open.
  - `aria-expanded="false"` when the dropdown is closed.

### Design Tokens

- **Typography:**
  - **Font Family:** `Arial, sans-serif`.
  - **Font Size:** `16px` for dropdown options.
  - **Line Height:** `24px` for readability.

- **Colors:**
  - **Text Color (Selected Option):** `#000000` (Black).
  - **Dropdown Background Color:** `#FFFFFF` (White).
  - **Focus Outline Color:** `#0078D4` (Blue) for focus.
  
- **Spacing:**
  - **Padding:** `8px` for options inside the dropdown.
  - **Margin:** `16px` between dropdowns in the layout.

### Benefits for Users with Motor Impairments

- **Accessible Input Options:** Users with motor impairments can rely on alternative input devices (e.g., switch control) to navigate dropdowns.
- **Simplified Navigation:** The dropdown allows for focused navigation through a smaller set of options, reducing the need for large-scale scrolling or pointer movement.

### Applicable WCAG Criteria

- **1.3.1 Info and Relationships:** Ensure that the label is programmatically associated with the dropdown.
- **1.3.2 Meaningful Sequence:** Ensure that dropdown options follow a logical and meaningful order.
- **2.1.1 Keyboard:** Dropdowns must be fully operable via keyboard, including navigation and selection.
- **2.4.3 Focus Order:** Focus should follow a logical order when navigating to and within the dropdown.
- **2.4.7 Focus Visible:** The dropdown should have a clear focus state for keyboard and alternative input users.
- **4.1.2 Name, Role, Value:** Ensure that screen readers announce the label, role, and value of the dropdown and its options.

### Alignment with WCAG Tokens

- **Focus Indicator Token:** Use a 2px solid outline for the dropdown when it receives focus.
- **Color Contrast Tokens:** Ensure that dropdown text and background meet the 4.5:1 contrast ratio.
- **Text Size Token:** Use a minimum font size of `16px` to ensure readability.
- **Target Size Token:** Ensure that the dropdown's target size meets or exceeds the 44px height standard to accommodate touch and motor impairment users.

### Assistive Technologies Considerations

- **Screen Readers** will announce the label of the dropdown, the current selection, and each option as users navigate.
- **Alternative Input Devices** must allow navigation through and selection of options using various input methods.
- **Screen Magnifiers** should ensure that both the dropdown and its options are clearly visible when zoomed.

### WCAG Success Criteria Checklist

**Product:**

- [ ] Define dropdown filters with clear labels that describe their purpose.
- [ ] Ensure the dropdown is designed for users with various input needs.

**Design:**

- [ ] Provide sufficient spacing between dropdowns for readability.
- [ ] Ensure that the dropdown is keyboard and alternative device accessible.
- [ ] Use clear focus states for dropdowns and options.
- [ ] Ensure the dropdown's target size meets accessibility guidelines, particularly for touch and motor-impaired users.

**Development:**

- [ ] Implement proper HTML and ARIA attributes for the dropdown and options.
- [ ] Ensure keyboard navigation is functional for opening, navigating, and selecting options.
- [ ] Ensure screen readers announce the label, current option, and each option as the user navigates.

**QA:**

- [ ] Test dropdown functionality with screen readers, ensuring that all options are announced correctly.
- [ ] Verify that dropdowns are fully keyboard and alternative input accessible.
- [ ] Ensure dropdown focus and interaction states are visible and accessible.
- [ ] Verify that users with motor impairments can navigate and select options using alternative input devices.
