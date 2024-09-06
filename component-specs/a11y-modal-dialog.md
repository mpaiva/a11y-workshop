
# Accessibility Component Specifications

## Component 13: Modal Dialog for Job Application Submission Confirmation (with Unsaved Changes Interaction)

### Gherkin Story

```gherkin
Feature: Modal Dialog for Job Application Submission Confirmation

  Scenario: A keyboard-only user confirms job application submission
    Given I am a keyboard-only user
    When I submit a job application
    Then a modal dialog should appear confirming the successful submission
    And I should be able to navigate to the "Close" button using the Tab key
    And I should be able to close the modal by pressing Enter, Space, or the Escape key

  Scenario: A screen reader user submits a job application
    Given I am a screen reader user
    When I submit a job application
    Then a modal dialog should appear confirming the successful submission
    And the screen reader should announce the confirmation message and the "Close" button
    And I should be able to close the modal using keyboard controls, including Escape

  Scenario: A low-vision user interacts with the modal dialog
    Given I am a low-vision user using a screen magnifier
    When the modal dialog appears
    Then the modal content should be centered and close to the center of the viewport for easy visibility
    And the "Close" button should be high contrast and visually distinct

  Scenario: A user exits the modal with unsaved information
    Given I have entered information into a form within the modal
    When I press the Escape key or attempt to close the modal
    Then I should receive a confirmation dialog informing me that unsaved changes will be lost
    And I should be able to choose either "Save" or "Discard" before closing the modal
```

### Expected Interaction Design and Keystrokes

- **Keyboard Navigation:**
  - When the modal dialog appears, focus should automatically move to the dialog.
  - Use the `Tab` key to navigate between the "Close" button and any other interactive elements within the modal.
  - Press `Enter`, `Space`, or `Escape` to close the modal.
  - The modal should trap focus until it is closed, either by clicking "Close" or pressing Escape.
  - If the user presses Escape with unsaved information, a confirmation dialog should appear asking whether to save or discard the changes.

- **Screen Reader Behavior:**
  - Upon opening, the screen reader should announce the dialog’s title, message, and "Close" button.
  - Focus should remain within the modal until it is dismissed, preventing interaction with background elements.
  - The screen reader should also announce the unsaved changes confirmation dialog when it appears.

- **Low-Vision User Behavior:**
  - The modal dialog should appear in the center of the screen and maintain close proximity to the main content for users with magnification.
  - Ensure high contrast between the modal content and its background, with a clear visual indicator for interactive elements like the "Close" button.

- **Unsaved Changes Confirmation:**
  - If the user has entered data into the modal and attempts to close it, the confirmation dialog should clearly state that unsaved changes will be lost, giving the option to either save or discard before exiting.

### Component Anatomy

- **Elements:**
  - A modal dialog container (`<div>` or `<section>`) that appears over the page content.
  - A heading for the modal title (`<h2>` or `<h3>`).
  - A confirmation message (`<p>` or `<div>`) to notify users of successful submission.
  - A "Close" button to dismiss the modal.
  - A confirmation dialog (`<div>`) with options "Save" and "Discard" when the user exits with unsaved information.

### Properties

- **Size:**
  - **Width:** The modal should take up about 50-70% of the viewport width, allowing enough space for the message while remaining focused.
  - **Height:** Adjust the height based on the content, but it should not exceed 75% of the viewport height to avoid overflow.

- **ARIA Attributes:**
  - `role="dialog"` to indicate that the container is a modal dialog.
  - `aria-labelledby` for the modal's title.
  - `aria-describedby` to associate the modal content (confirmation message) with the dialog.
  - `aria-modal="true"` to trap focus within the modal until dismissed.
  - If unsaved changes exist, apply `aria-describedby` to the confirmation dialog to describe the warning message.

### States

- **Visual States:**
  - **Default (Closed):** The modal is hidden, and the page content is accessible.
  - **Open:** The modal appears over the page content, and the background is visually dimmed to emphasize the modal.
  - **Unsaved Changes Dialog:** If the user attempts to close the modal with unsaved changes, a confirmation dialog appears asking whether to save or discard the changes.
  - **Focus (Modal Active):** Focus is trapped inside the modal until dismissed, and interactive elements within the modal are visually highlighted (e.g., the "Close" button).

- **ARIA States:**
  - `aria-hidden="true"` when the modal is closed.
  - `aria-hidden="false"` when the modal is visible and interactive.
  - For the unsaved changes confirmation dialog, apply `role="alertdialog"` and ensure screen readers announce it.

### Design Tokens

- **Typography:**
  - **Font Family:** `Arial, sans-serif`.
  - **Font Size:** `18px` for the modal text and button labels.
  - **Line Height:** `28px` for readability.

- **Colors:**
  - **Modal Background Color:** `#FFFFFF` (White) to provide a clear background.
  - **Modal Text Color:** `#000000` (Black) for high contrast.
  - **Close Button Text Color:** `#FFFFFF` (White).
  - **Close Button Background Color:** `#0078D4` (Blue).
  
- **Spacing:**
  - **Padding:** Add at least `16px` padding inside the modal to give space between the content and the modal edges.
  - **Margin:** Ensure `8px` margin between the confirmation message and the button for clarity.

### Benefits for Users with Disabilities

- **Keyboard Navigation:** Users relying on the keyboard can navigate the modal dialog easily, with focus being trapped inside the modal until it is closed. The Escape key provides an additional way to close the modal.
- **Screen Reader Compatibility:** The modal is announced to screen reader users, who can navigate the content and dismiss it using keyboard controls. The unsaved changes confirmation is also announced when it appears.
- **Low Vision (Magnification):** The modal content is positioned close to the center of the screen, ensuring that users with magnification do not lose context or have to scroll excessively to locate it.
- **Unsaved Changes Warning:** Ensures that users are warned before they accidentally discard any unsaved data, which is particularly helpful for users with cognitive impairments or those who accidentally press the Escape key.

### Applicable WCAG Criteria

- **1.3.1 Info and Relationships:** The modal dialog and its content should be programmatically associated for screen reader users.
- **1.4.3 Contrast (Minimum):** Ensure sufficient contrast between the modal content and the background, especially for low-vision users.
- **1.4.10 Reflow:** Ensure the modal dialog is positioned centrally and does not overflow the viewport when magnified.
- **2.1.1 Keyboard:** The modal dialog must be fully navigable via keyboard, and focus should remain inside the modal until dismissed. The Escape key should work as an alternative way to exit the modal.
- **2.4.3 Focus Order:** Ensure that focus moves logically through the modal’s interactive elements, starting with the content and ending with the "Close" button.
- **2.4.7 Focus Visible:** Interactive elements inside the modal (e.g., the "Close" button) should have a clear focus indicator.
- **3.2.2 On Input:** If unsaved changes exist, provide a warning and allow users to confirm their action before closing the modal.
- **4.1.2 Name, Role, Value:** Screen readers must announce the modal, its content, and any interactive elements (e.g., the "Close" button). The unsaved changes dialog should also be properly announced when invoked.

### Alignment with WCAG Tokens

- **Focus Indicator Token:** Ensure a clear focus outline is visible around the "Close" button and other interactive elements.
- **Color Contrast Tokens:** Ensure the modal’s text and background meet the 4.5:1 contrast ratio.
- **Text Size Token:** Use a minimum font size of `18px` to ensure readability for users with low vision.
- **Target Size Token:** Ensure the "Close" button is large enough (at least 44px in height) to be easily clickable or tappable.

### Assistive Technologies Considerations

- **Screen Readers:** Announce the modal when it appears, including its title and content. Ensure focus is trapped inside the modal. When unsaved changes are detected, announce the confirmation dialog to allow users to confirm their choice.
- **Keyboard Navigation:** Focus should move to the modal when it appears, allowing users to navigate within it and dismiss it using keyboard controls (Enter, Space, or Escape).
- **Low Vision (Magnified Screen):** Ensure the modal content is centered in the viewport and remains visible even when magnified, with sufficient contrast and proximity to the main content.
- **Unsaved Changes:** Provide a clear confirmation dialog for users attempting to close the modal with unsaved changes, ensuring they do not lose important data.
