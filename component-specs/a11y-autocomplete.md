
# Accessibility Component Specifications

## Component 12: Search Input Field with Autocomplete (with Low-Vision Proximity Considerations)

### Gherkin Story

```gherkin
Feature: Search Input Field with Autocomplete

  Scenario: A keyboard-only user searches for jobs using an autocomplete input
    Given I am a keyboard-only user
    When I focus on the search input field for jobs
    Then I should be able to type a job title or keyword
    And I should be able to use the Down and Up arrow keys to navigate through autocomplete suggestions
    And I should be able to select a suggestion using the Enter or Space key

  Scenario: A screen reader user searches for jobs using an autocomplete input
    Given I am a screen reader user
    When I focus on the search input field for jobs
    Then the screen reader should announce that autocomplete suggestions are available as I type
    And I should be able to navigate through the suggestions using the arrow keys
    And the screen reader should announce each suggestion as I navigate

  Scenario: A user with cognitive impairments uses the search autocomplete feature
    Given I am a user with cognitive impairments
    When I type into the search input field
    Then the autocomplete suggestions should offer simple, clear options to guide me
    And I should be able to easily select a suggestion using the arrow keys and Enter or Space key

  Scenario: A low-vision user searches for jobs using autocomplete input
    Given I am a low-vision user using screen magnification
    When I type in the search input field
    Then the autocomplete suggestions should appear close to the input field to maintain proximity and visibility
    And the focused suggestion should be clearly highlighted with high contrast
```

### Expected Interaction Design and Keystrokes

- **Keyboard Navigation:**
  - Use the `Tab` key to focus on the search input field.
  - Type to trigger the autocomplete suggestions.
  - Use the `Down` and `Up` arrow keys to navigate through suggestions.
  - Use the `Enter` or `Space` key to select a suggestion and trigger the search.

- **Screen Reader Behavior:**
  - As the user types, the screen reader should announce when autocomplete suggestions become available.
  - Each suggestion should be announced as the user navigates through the list using the arrow keys.
  - Upon selecting a suggestion, the screen reader should confirm the selection.

- **Low-Vision User Behavior:**
  - Autocomplete suggestions must appear close to the input field to maintain spatial proximity when the screen is magnified.
  - The focused suggestion should be clearly highlighted and visually distinct, ensuring it stands out during magnification.

### Component Anatomy

- **Elements:**
  - A text input field (`<input>` with `type="search"` or `text`).
  - An autocomplete dropdown list (`<ul>` or `<div>`) that appears when suggestions are available.
  - Each suggestion as an individual list item (`<li>` or `<div>`) within the autocomplete dropdown.

### Properties

- **Size:**
  - **Width:** The search input should be wide enough to display meaningful input (e.g., `300px` minimum width).
  - **Height (Target Size):** Ensure the input field is at least `44px` in height to meet touch accessibility guidelines.

- **ARIA Attributes:**
  - `aria-autocomplete="list"` to indicate that the input provides suggestions as the user types.
  - `aria-expanded="true"` or `aria-expanded="false"` depending on whether suggestions are visible.
  - `aria-owns` or `aria-controls` to link the input to the dropdown list of suggestions.
  - `aria-activedescendant` to indicate the currently focused suggestion in the list.

### States

- **Visual States:**
  - **Default:** The search input is empty, with no suggestions visible.
  - **Typing:** As the user types, the autocomplete suggestions become visible.
  - **Suggestion Focus:** When a suggestion is focused, it is highlighted visually (e.g., background color change).
  - **Selected:** Once a suggestion is selected, the input field is populated with that suggestion.

- **ARIA States:**
  - `aria-expanded="true"` when suggestions are visible, and `aria-expanded="false"` when they are hidden.
  - `aria-activedescendant` to keep track of the currently focused suggestion.

### Design Tokens

- **Typography:**
  - **Font Family:** `Arial, sans-serif`.
  - **Font Size:** `16px` for both input text and suggestions.
  - **Line Height:** `24px` for readability.

- **Colors:**
  - **Input Text Color:** `#000000` (Black).
  - **Suggestion Text Color:** `#333333` (Dark Gray).
  - **Suggestion Background Color (Focused):** `#E1E1E1` (Light Gray).
  
- **Spacing:**
  - **Padding:** Ensure sufficient padding inside the input field and around suggestions for easy selection.
  - **Margin:** Provide `8px` of space between the input field and the autocomplete dropdown, ensuring that suggestions are positioned close enough for magnification without loss of context.

### Benefits for Users with Disabilities

- **Keyboard Navigation:** Users relying on the keyboard can type and use arrow keys to navigate suggestions without needing to use a mouse.
- **Screen Reader Compatibility:** Autocomplete functionality is announced to users, making the process of searching more efficient.
- **Cognitive Accessibility:** Clear, relevant suggestions help users with cognitive impairments find what they’re looking for without getting overwhelmed by too many choices.
- **Low Vision:** Ensuring proximity between the input field and suggestions benefits users who rely on screen magnifiers, preventing them from losing spatial context while zooming in.

### Applicable WCAG Criteria

- **1.3.1 Info and Relationships:** Ensure that the input and its suggestions are programmatically linked.
- **1.4.3 Contrast (Minimum):** Ensure sufficient contrast between the suggestion text and background.
- **1.4.4 Resize Text:** Ensure that text remains readable when resized up to 200%.
- **1.4.10 Reflow:** Ensure that suggestions appear close to the input field and remain legible and in context when magnified.
- **2.1.1 Keyboard:** The search input and autocomplete suggestions must be fully operable via keyboard, including navigation and selection.
- **2.4.3 Focus Order:** Ensure that focus moves logically between the input and suggestions.
- **4.1.2 Name, Role, Value:** Ensure that screen readers announce the input's autocomplete functionality and each suggestion as the user navigates.

### Alignment with WCAG Tokens

- **Focus Indicator Token:** Ensure clear visual focus indication on both the input field and the focused suggestion.
- **Color Contrast Tokens:** Ensure that suggestions and text meet the 4.5:1 contrast ratio.
- **Text Size Token:** Use a minimum font size of `16px` for both the input and suggestions to ensure readability.

### Assistive Technologies Considerations

- **Screen Readers:** Announce the autocomplete suggestions as users type, and confirm selections when a suggestion is chosen.
- **Keyboard Navigation:** Allow users to easily navigate through autocomplete suggestions using arrow keys, with clear focus management and feedback.
- **Low Vision (Magnified Screen):** Ensure that the suggestions are positioned close to the input field and maintain spatial context for users who rely on magnification.

### WCAG Success Criteria Checklist

**Product:**

- [ ] Ensure that the autocomplete functionality provides clear and relevant suggestions.
- [ ] Ensure that suggestions are well-labeled and easy to understand for users with cognitive impairments.
- [ ] Ensure that the proximity between the input field and autocomplete suggestions is maintained for low-vision users.

**Design:**

- [ ] Use high-contrast colors for the input and suggestions to make them easy to read.
- [ ] Ensure the input field is large enough for easy interaction, especially on touch devices.
- [ ] Provide a clear focus indicator for both the input field and suggestions.

**Development:**

- [ ] Implement `aria-autocomplete="list"` and ensure screen readers can announce suggestions properly.
- [ ] Ensure the input field is fully keyboard navigable, including selecting suggestions with arrow keys and Enter/Space.
- [ ] Ensure suggestions are announced correctly by screen readers and are programmatically associated with the input.
- [ ] Ensure that suggestions are positioned close to the input field and remain visible and contextually relevant when magnified.

**QA:**

- [ ] Test the autocomplete functionality with screen readers to ensure suggestions are announced as the user navigates.
- [ ] Ensure that users can navigate the suggestions using only the keyboard and select them with ease.
- [ ] Verify that suggestions are easy to understand and help users quickly find what they are searching for.
- [ ] Test with magnification to ensure that suggestions remain close to the input field and are contextually relevant.
