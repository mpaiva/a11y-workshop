
# Accessibility Component Specifications

## Component 7: Paragraphs (Instructions and Descriptions)

### Gherkin Story

```gherkin
Feature: Instructions and Descriptions

  Scenario: A user with cognitive disabilities reads instructions
    Given I am a user with cognitive disabilities
    When I view instructions on the page
    Then the instructions should be in plain language and easy to understand
    And they should avoid technical jargon
  
  Scenario: A screen reader user reads a description
    Given I am using a screen reader
    When I encounter a paragraph of instructions
    Then the text should be properly announced and clear to understand
    And all links and references should be announced with meaningful descriptions
```

### Expected Interaction Design and Keystrokes

- **Keyboard Navigation:**
  - Use the `Tab` key to navigate to interactive elements (such as links or buttons) within or after paragraphs of text.
  - `Shift + Tab` allows navigation backward through focusable content.
  
- **Screen Reader Behavior:**
  - Screen readers will read the paragraph's text, including links, as users move through the content.
  - Instructions should use clear and simple language that is announced properly by the screen reader.

### Component Anatomy

- **Elements:**
  - `<p>` for paragraphs to provide instructions, explanations, or descriptions.
  - Optional inline elements like `<a>` (anchor) for links, `<strong>` or `<em>` for emphasis.

### Properties

- **Size:**
  - **Width:** Full-width, constrained by the layout (e.g., 100% inside containers).
  - **Text Length:** Limited to concise paragraphs (recommend no more than 3-5 sentences per paragraph for readability).

- **Readability:**
  - Ensure simple, plain language is used for cognitive accessibility.
  - Use headings (e.g., `<h2>`) to break up long sections of text.
  - Limit line length to **80 characters** (40 for CJK languages) to prevent users from losing their place while reading.

### States

- **Visual States:**
  - **Default:** Text is displayed as plain paragraphs.
  - **Focus (For Links):** Links within the paragraph are highlighted on focus.
  
- **ARIA States:**
  - No specific ARIA states required for plain paragraphs, though proper labeling of links and interactive elements within paragraphs should be used.

### Design Tokens

- **Typography:**
  - **Font Family:** `Arial, sans-serif`.
  - **Font Size:** `16px` for body text.
  - **Line Height:** `24px` to enhance readability and allow for clear spacing between lines.

- **Colors:**
  - **Text Color:** `#000000` (Black).
  - **Link Color:** `#0078D4` (Blue) for links to distinguish them from body text.
  - Ensure links provide sufficient color contrast against the paragraph background.

- **Spacing:**
  - **Margin:** `16px` bottom margin between paragraphs.
  - **Padding:** None for paragraphs (padding should apply to containers, not the text itself).

### Applicable WCAG Criteria

- **1.4.3 Contrast (Minimum):** Text and background colors must meet the 4.5:1 contrast ratio.
- **1.4.4 Resize Text:** Text must remain readable when resized up to 200%.
- **1.4.8 Visual Presentation:** Line height (spacing) should be at least 1.5x font size, and paragraph spacing should be at least 1.5x the line height for readability.
- **1.4.12 Text Spacing:** Ensure that the text spacing can be adjusted (e.g., line height, letter spacing, and word spacing) without loss of content or functionality. This supports users who need additional spacing to comprehend content.
- **2.4.4 Link Purpose (In Context):** Links within paragraphs should have clear and descriptive anchor text to convey the destination.
- **3.1.5 Reading Level:** Instructions and descriptions must be written in clear, plain language to ensure cognitive accessibility.
- **1.4.10 Reflow:** Ensure that text content can be resized and displayed without requiring horizontal scrolling, allowing for improved readability.

### Alignment with WCAG Tokens

- **Text Size Token:** Use `16px` for body text, ensuring readability.
- **Color Contrast Tokens:** Ensure paragraph text and links meet or exceed the required contrast ratio for accessibility.
- **Line Height Token:** Use a line height of at least 1.5x the font size to ensure readability for all users.

### Assistive Technologies Considerations

- **Screen Magnifiers** allow users to adjust text size, font, and color. Content must reflow to fit the screen without requiring horizontal scrolling, particularly when magnified.
- **Screen Readers** should announce all paragraph content and ensure that links have clear, meaningful descriptions.
- **Text-to-Speech Software** should convert the entire paragraph content into speech, preserving comprehension.
- **Speech Recognition Software** should allow users to navigate links and paragraphs using voice commands.
- **Alternative Keyboards** must allow navigation through paragraph content with easy keyboard shortcuts.

### WCAG Success Criteria Checklist

**Product:**

- [ ] Ensure all instructions and descriptions are written in plain language, avoiding technical jargon.
- [ ] Provide clear instructions for form actions, navigation, or content understanding.

**Design:**

- [ ] Use sufficient line height and spacing between paragraphs for readability.
- [ ] Ensure color contrast between text and background meets accessibility guidelines.
- [ ] Ensure the content reflows when zoomed or resized without requiring horizontal scrolling.

**Development:**

- [ ] Implement paragraphs using proper HTML semantic elements like `<p>`.
- [ ] Ensure any inline links or interactive elements within paragraphs are keyboard accessible and correctly labeled for screen readers.
- [ ] Ensure that text adjusts to accommodate user settings for line spacing, letter spacing, and word spacing without affecting functionality or layout.

**QA:**

- [ ] Verify that all paragraph text is readable by users with low vision and cognitive disabilities.
- [ ] Test paragraphs for readability when text is resized up to 200%.
- [ ] Ensure links within paragraphs are clearly labeled and navigable using a keyboard.
- [ ] Verify compliance with text spacing adjustments to meet 1.4.12 and 1.4.8 requirements.
