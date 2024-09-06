
# Accessibility Component Specifications

## Component 15: Job Application Form with Inline Validation

### Gherkin Story

```gherkin
Feature: Job Application Form with Inline Validation

  Scenario: A keyboard-only user completes and submits the job application form
    Given I am a keyboard-only user
    When I navigate through the job application form
    Then I should be able to complete all fields using the Tab key
    And I should receive inline validation feedback after each required field
    And I should be able to submit the form by pressing Enter on the "Submit" button

  Scenario: A screen reader user fills out the job application form
    Given I am a screen reader user
    When I navigate the job application form
    Then the screen reader should announce each form field label and any inline validation feedback
    And I should be able to correct errors with clear feedback on what needs to be changed

  Scenario: A low-vision user fills out the job application form
    Given I am a low-vision user using a screen magnifier
    When I navigate the job application form
    Then the form fields and validation messages should be large and have high contrast for easy readability
    And the inline validation messages should appear close to the form fields they refer to
```

### Expected Interaction Design and Keystrokes

- **Keyboard Navigation:**
  - Use the `Tab` key to move between form fields.
  - When required fields are left blank or incorrectly filled, inline validation messages should appear immediately after the field in question.
  - Use `Enter` to submit the form.

- **Screen Reader Behavior:**
  - Each form field should have an accessible label.
  - Inline validation messages should be programmatically associated with the field and announced by the screen reader when an error occurs.
  - The screen reader should also announce when the form is successfully submitted or if any errors remain.

- **Low-Vision User Behavior:**
  - The form fields should be large enough with sufficient contrast.
  - Inline validation messages should appear immediately next to or below the corresponding field to maintain proximity and clarity for users with magnification.

### Component Anatomy

- **Elements:**
  - Form container (`<form>`), including form fields (`<input>`, `<textarea>`, `<select>`).
  - Labels (`<label>`) for each field.
  - Inline validation message area (`<span>` or `<div>`) to display error or success messages.
  - Submit button (`<button type="submit">`).

### Properties

- **Size:**
  - **Width:** Form should be responsive and flexible, with fields taking up at least `80%` of the container width.
  - **Height (Target Size):** Ensure form fields and the submit button are at least `44px` in height.

- **ARIA Attributes:**
  - Use `aria-required="true"` for required fields.
  - Apply `aria-invalid="true"` for fields with validation errors.
  - Use `aria-live="polite"` for inline validation messages to announce them as they appear.
  - Associate validation messages with their corresponding fields using `aria-describedby`.

### States

- **Visual States:**
  - **Default:** The form is displayed with no validation messages visible.
  - **Inline Validation:** As the user completes the form, validation messages appear next to fields with errors.
  - **Success:** After submission, a success message appears, confirming that the form was successfully submitted.

- **ARIA States:**
  - `aria-invalid="true"` for fields with validation errors.
  - `aria-live="polite"` for validation messages to announce dynamically when they appear.

### Design Tokens

- **Typography:**
  - **Font Family:** `Arial, sans-serif`.
  - **Font Size:** `16px` for form fields and labels, `14px` for inline validation messages.
  - **Line Height:** `24px` for readability.

- **Colors:**
  - **Field Border Color (Error):** `#D32F2F` (Red) to indicate a validation error.
  - **Validation Text Color:** `#D32F2F` (Red) for inline error messages.
  - **Success Text Color:** `#388E3C` (Green) to confirm successful form submission.

- **Spacing:**
  - **Padding:** Ensure sufficient padding inside form fields and around labels for clarity.
  - **Margin:** Ensure `8px` margin between fields and inline validation messages for visual clarity.

### Benefits for Users with Disabilities

- **Keyboard Navigation:** Users relying on the keyboard can navigate through the form and submit it easily using the Tab and Enter keys, with real-time validation feedback.
- **Screen Reader Compatibility:** Inline validation is announced to screen reader users, ensuring they know what needs to be corrected and can submit the form confidently.
- **Low Vision (Magnified Screen):** Form fields and inline validation messages are large, with high contrast and proximity for easy navigation and readability when magnified.

### Applicable WCAG Criteria

- **1.3.1 Info and Relationships:** Ensure the relationship between form fields and validation messages is programmatically clear.
- **1.3.5 Identify Input Purpose:** Ensure form fields are correctly identified for users with assistive technologies.
- **1.4.3 Contrast (Minimum):** Ensure sufficient contrast between text and background for both form fields and validation messages.
- **1.4.4 Resize Text:** Ensure that form fields and validation messages remain legible when resized up to 200%.
- **2.1.1 Keyboard:** The form must be fully operable via keyboard, including field navigation and submission.
- **2.4.3 Focus Order:** Ensure logical focus movement between form fields and validation messages.
- **3.3.1 Error Identification:** Ensure that inline validation messages clearly identify errors and how to resolve them.
- **4.1.2 Name, Role, Value:** Ensure that screen readers announce the form fields and their associated validation messages correctly.

### Alignment with WCAG Tokens

- **Focus Indicator Token:** Ensure clear focus indication for form fields and the submit button.
- **Color Contrast Tokens:** Ensure validation messages meet the 4.5:1 contrast ratio against their background.
- **Text Size Token:** Use a minimum font size of `16px` for form fields and labels, and `14px` for validation messages.
- **Target Size Token:** Ensure each form field and the submit button have a target size of at least 44px in height.

### Assistive Technologies Considerations

- **Screen Readers:** Announce form fields, their labels, and any associated validation messages clearly. Validation errors should be announced in real-time as they appear.
- **Keyboard Navigation:** Allow users to navigate easily between form fields, receive real-time validation feedback, and submit the form using Enter.
- **Low Vision (Magnified Screen):** Ensure form fields and inline validation messages are large and legible, with high contrast and proximity for ease of use when magnified.

### WCAG Success Criteria Checklist

**Product:**

- [ ] Ensure the form provides real-time feedback for errors and successes.
- [ ] Ensure the inline validation messages are accessible and provide clear, actionable feedback.

**Design:**

- [ ] Use high-contrast colors for validation messages and form fields.
- [ ] Ensure the form layout is clear, with sufficient spacing between fields and validation messages.
- [ ] Provide large enough text and buttons for easy interaction on all devices.

**Development:**

- [ ] Implement `aria-invalid="true"` and associate validation messages with their respective fields using `aria-describedby`.
- [ ] Ensure the form is fully keyboard accessible, with inline validation messages that announce errors in real time.
- [ ] Ensure that real-time validation works properly and that the form submission provides clear feedback.

**QA:**

- [ ] Test the form with screen readers to ensure validation feedback is announced correctly.
- [ ] Verify that keyboard users can navigate the form and submit it with clear feedback.
- [ ] Ensure that the form fields and validation messages remain usable and legible when zoomed in.
- [ ] Ensure that the inline validation provides real-time feedback and correctly identifies the error field.
