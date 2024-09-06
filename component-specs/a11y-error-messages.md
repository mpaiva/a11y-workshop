
# Accessibility Component Specifications

## Component 10: Error Messages and Validation Feedback

### Gherkin Story

```gherkin
Feature: Error Messages and Validation Feedback

  Scenario: A keyboard-only user encounters an invalid form submission
    Given I am a keyboard-only user
    When I submit a job application form with errors
    Then the error messages should be displayed next to the invalid fields
    And I should be able to tab directly to each error to correct it

  Scenario: A screen reader user encounters an invalid form submission
    Given I am a screen reader user
    When I submit a job application form with missing or incorrect information
    Then the screen reader should announce that there are errors in the form
    And the error message associated with each field should be announced

  Scenario: A user with cognitive disabilities encounters an error
    Given I am a user with cognitive disabilities
    When I submit a form with errors
    Then the error messages should be simple and easy to understand
    And the instructions for fixing the errors should be clear and concise

  Scenario: A low-vision user encounters an invalid form submission
    Given I am a user with low vision using a screen magnifier
    When I submit a form with errors
    Then the error messages should be positioned near the invalid fields to ensure visibility while magnified
    And error text should be large and high-contrast for readability

  Scenario: A user with mobility impairments encounters status or alert messages
    Given I have a mobility impairment such as cerebral palsy
    When a status message or error alert appears
    Then I should be given sufficient time to read the message and dismiss it
```

### Expected Interaction Design and Keystrokes

- **Keyboard Navigation:**
  - Use the `Tab` key to navigate through fields, with the focus moving directly to the field with errors.
  - Use `Enter` or `Space` to activate any buttons or links associated with fixing the errors.

- **Screen Reader Behavior:**
  - When an invalid submission occurs, the screen reader should announce the presence of errors.
  - Error messages should be associated with specific fields and announced by the screen reader when focused.

- **Low-Vision User Behavior:**
  - Ensure error messages are placed near their respective fields to maintain proximity when the screen is magnified.
  - Use large, high-contrast text for error messages to ensure legibility under magnification.

- **Mobility Impairments (Cerebral Palsy):**
  - Provide ample time for users to read and dismiss error or alert messages.
  - Allow users to manually dismiss status or alert messages rather than having them disappear automatically.

### Component Anatomy

- **Elements:**
  - Error messages (`<span>` or `<div>`) associated with form fields.
  - Use `aria-describedby` to associate the error messages with the input fields that need correction.
  - Use `aria-invalid="true"` for form fields with errors.
  - Optional status or alert message areas that allow manual dismissal, such as a close button.

### Properties

- **Size:**
  - **Text Size:** Use at least `16px` for error message text to ensure readability.
  - **Spacing:** Add sufficient spacing around error messages to avoid crowding, with at least `8px` between the error message and the form field.

- **ARIA Attributes:**
  - `aria-describedby` to associate the error message with the form field.
  - `aria-invalid="true"` for invalid fields.
  - Optionally, use `aria-live="assertive"` to announce errors dynamically.

### States

- **Visual States:**
  - **Default:** No error messages are visible unless an error occurs.
  - **Error State:** Error messages appear in red or high-contrast colors next to or below invalid fields.
  - **Focus:** Error messages are visually emphasized when a user tabs to a field with an error.

- **ARIA States:**
  - `aria-invalid="true"` for fields with errors.
  - `aria-describedby` for error messages associated with the invalid field.
  - Use `aria-live="polite"` or `aria-live="assertive"` for dynamic error announcements.

### Design Tokens

- **Typography:**
  - **Font Family:** `Arial, sans-serif`.
  - **Font Size:** `16px` for error messages.
  - **Line Height:** `24px` for readability.

- **Colors:**
  - **Error Text Color:** `#D32F2F` (Red) to distinguish error messages.
  - **Background Color:** White or light background to ensure readability of error messages.
  
- **Spacing:**
  - **Margin:** `8px` between the error message and the associated input field.
  - **Padding:** None inside the error message itself.

### Benefits for Users with Disabilities

- **Screen Reader Compatibility:** Error messages are announced to users when navigating through invalid fields, ensuring that users with vision impairments can correct mistakes efficiently.
- **Cognitive Accessibility:** Clear, simple error messages help users with cognitive disabilities understand the problem and take corrective action.
- **Keyboard Navigation:** Users who rely on the keyboard can easily tab to invalid fields and receive immediate feedback on how to correct the issue.
- **Low-Vision Proximity:** Ensuring error messages are placed near their associated fields benefits users who are zoomed in, preventing them from losing track of which field has an error.
- **Mobility Impairments:** Users with conditions such as cerebral palsy may need more time to read and interact with error messages. Giving them control over when to dismiss alert messages ensures they aren't rushed or frustrated.

### Applicable WCAG Criteria

- **1.3.1 Info and Relationships:** Error messages should be programmatically associated with their respective form fields.
- **1.4.3 Contrast (Minimum):** Ensure sufficient contrast between error text and background.
- **1.4.4 Resize Text:** Ensure error text remains legible when resized up to 200%.
- **1.4.10 Reflow:** Ensure that error messages maintain proximity to their related fields even when zoomed in.
- **2.2.1 Timing Adjustable:** Ensure users have enough time to read and dismiss messages, especially those with mobility impairments.
- **2.2.3 No Timing:** Ensure that content requiring user interaction is not time-limited, so users with blindness, low vision, cognitive disabilities, or motor impairments can interact without being rushed. The only exception is real-time events.
- **3.3.1 Error Identification:** Users must be informed when an input error is detected and which fields require correction.
- **3.3.2 Labels or Instructions:** Ensure clear labels and instructions to help users fix the errors.
- **3.3.3 Error Suggestion:** Where possible, provide suggestions for correcting the errors.
- **4.1.2 Name, Role, Value:** Screen readers must announce the error messages and their association with the respective fields.

### Alignment with WCAG Tokens

- **Text Size Token:** Use a minimum font size of `16px` for error messages to ensure readability.
- **Color Contrast Tokens:** Ensure error text meets the 4.5:1 contrast ratio against its background for accessibility.
- **Spacing Tokens:** Ensure appropriate spacing between error messages and input fields to avoid overcrowding and enhance readability.

### Assistive Technologies Considerations

- **Screen Readers:** Announce error messages as users navigate through invalid fields.
- **Keyboard Navigation:** Ensure users can tab directly to fields with errors and view associated error messages.
- **Low Vision (Magnified Screen):** Position error messages near invalid fields to keep them visible during magnification.
- **Mobility Impairments (Cerebral Palsy):** Allow sufficient time for users to read and dismiss error or status messages. Avoid automatic timeouts, allowing users to control interaction time.

### WCAG Success Criteria Checklist

**Product:**

- [ ] Ensure error messages are clear and concise, providing actionable guidance to users.
- [ ] Define error messages that avoid technical language and are easy to understand for all users.

**Design:**

- [ ] Use high-contrast colors for error messages to make them easily visible.
- [ ] Ensure that error messages are positioned close to the form fields they relate to.
- [ ] Provide users with sufficient time to interact with and dismiss status or error messages.

**Development:**

- [ ] Implement `aria-invalid="true"` and `aria-describedby` for error messages and fields.
- [ ] Ensure error messages are announced by screen readers when users focus on invalid fields.
- [ ] Use `aria-live="assertive"` where necessary to announce errors dynamically.
- [ ] Ensure that no time limits are enforced for interacting with status or alert messages, especially for users with motor or cognitive impairments.

**QA:**

- [ ] Test form validation for screen reader compatibility to ensure errors are properly announced.
- [ ] Ensure error messages are visually clear, and users can tab directly to fields with errors.
- [ ] Verify that error messages provide clear guidance for users with cognitive disabilities.
- [ ] Ensure that low-vision users can view error messages near the invalid fields when zoomed.
- [ ] Verify that users with mobility impairments have ample time to read and dismiss alert messages without time constraints.
