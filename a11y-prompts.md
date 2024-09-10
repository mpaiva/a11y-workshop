# Designing with words

This design with words activity will help you outline a user-friendly, accessible interface for Jacob’s job search journey. Each page structure provides clear navigation, content hierarchy, and well-labeled forms to ensure screen reader users can easily engage with every component.

## Goal

- A step-by-step guide for Accessible Prototyping
- These guidelines will help build a content-first mindset to create accessible experiences.

**Poor Content Leads to Poor Accessibility**

With this premise in mind, we encourage the use of a language model like ChatGPT to help you create content. 

## Chat GPT Prompts for the Activities
The following prompts were created as examples for the content-first activities at the workshop. 

### 1. Prime the AI with Jacob's persona.
```
INTRODUCTION:
I am creating a prototype for a fictitious job search engine to showcase the accessibility and user requirements for a candidate like Jacob. 

NOTE:
- Do NOT react to this request just yet.
- I will give you specific tasks in the next prompt.
- Just reply with an acknowledgement "Jobs for Jacobs!" 

USER PERSONA:
Here's the persona I'd like to use as a reference for making sure the solution is accessible:

Jacob, Blind in love with technology.
"The right technology lets me do anything."

Overview on Jacob
- Jacob is a paralegal in a large law firm. He reviews cases and writes summaries, cross-referencing them to the firm’s own cases and clients. He’s building expertise in his area of law and is hoping to go to law school in a year or so.
- As far as Jacob is concerned, it’s the technology that’s handicapped, not him. When everything is in place, he can work just as fast and just as effectively as anyone in his office.
- He’s a bit of a gadget geek, always trying out new tools, looking for a little edge and something new. The last few years have been a lot of fun with all the new apps, and VoiceOver on his Mac and phone lets him use most of them pretty well. He likes the challenge of learning new tools.
- His other challenge is running. He’s training for a 10K run, running with a club in his neighborhood and using an app to plan his routes and track his distance.
- He’s just started to use The iPhone app, Passbook, and uses it to get train tickets and other travel. The regional rail system has an app, so he can just pull up the barcode and scan it at the ticket office. No fumbling for the right printed card—total independence. Same phone as everyone. Same app as everyone, and it all just works.

Snapshot of Jacob
- 32 years old
- College graduate, legal training courses
- Shares an apartment with a friend
- Paralegal, reviews cases and writes case summaries
- Laptop, braille display, iPhone

The A’s
- Ability: Blind since birth with some light perception
- Aptitude: Skilled technology user
- Attitude: Digital native, early adopter, persists until he gets it

Assistive Technology
- Screen reader (JAWS on his laptop, VoiceOver on his phone)
- Audio recorder (to take notes)
- Braille display
```

## 2. Create User Journey Map

```
TASK: USER JOURNEY MAP
Create a high-level user journey map outlining the steps my user persona might take to [DESCRIBE END-USER’S GOAL - WHY ARE THEY USING YOUR PRODUCT?] using the following stages. Breakdown the stages in steps for this journey: 

- Stage 1: [DESCRIPTIVE STAGE NAME]
- Stage 2: [DESCRIPTIVE STAGE NAME]
- Stage 3: [DESCRIPTIVE STAGE NAME]

Please include HEADLINE and DESCRIPTION for each step of the journey.
```


### Example:
```
TASK: USER JOURNEY MAP
Create a high-level user journey map outlining the steps Jacob might take on the website to find his next job opportunity using the following stages. Breakdown the stages in steps for this journey: 
- Stage 1: Job Searching
- Stage 2: Reviewing Job Descriptions
- Stage 3: Applying for a Job
Include headline and description for each step of the journey.
```

## 3. Create Gherkin Stories

```
TASK: CREATE GHERKIN STORIES
Create a gherkin story for each step of the journey. Each Gherkin Story should be structured as follows:
- Each page must begin with a Gherkin story to outline the user’s interaction in plain language.
- Use the Given, When, Then (And) structure considering different assistive technologies and form factors.

```

## 4. Outline the semantic structure of each page

```
TASK: DESIGN WITH WORDS
Think of this task as designing with words, where you get to describe the interface to someone without drawing it.

For each Gherkin story, follow these eight steps:
1. Imagine each page using only descriptive bullet points to outline the interface layout using these native components.
2. Begin each page with the Gherkin story using the give, when, and then statements.
3. Please remember to add skip links to important sections.
4. Suggest relevant content for headings, paragraphs, and labels.
5. Please include a complementary paragraph after each heading 1 and heading 2 describing plain-language instructions for the user.
6. Be thorough with lists, adding at least five items as content examples.
7. Consider alert messages needing to provide successful and unsuccessful patterns.
8. Avoid using tables.

Expected Output:

1. Stage and Page Naming Stage:
Clearly define the stage of the journey (e.g., "Stage 1: Job Searching").

2. Page Name:
Provide a descriptive title for the page, reflecting the step of the journey (e.g., "Page 1: Accessing the Job Search Engine").

3. Gherkin Story Structure:
Each page must begin with a Gherkin story to outline the user’s interaction in plain language.
Use the Given, When, Then (And) structure considering different assistive technologies and form factors:

- Given: Describes the user and their initial context (e.g., "Given I am a blind user with a screen reader").
- When: Specifies the user’s action on the page (e.g., "When I navigate to the job search engine").
- Then: Describes the expected outcome or experience (e.g., "Then I should land on the homepage").
- And: If necessary, add additional expectations or outcomes (e.g., "And the page should be accessible with clear headings and navigation").

4. Interface Layout Sections
Break the page into clear interface sections using descriptive bullet points. Ensure that each section contains specific components with labels, headings, and content examples.

Example:

Interface Layout: Outlines the overall structure of the page.

[Skip Links]
Include skip links to essential sections for keyboard users and screen readers, like:
- Skip to Search Bar
- Skip to Main Content
- Skip to Footer

[Header]
Provide the website's main navigation and any action buttons.

[Navigation Menu]
Include a list of links (e.g., "Home," "Job Search," "Profile," "Help").

[Search Bar]

Label: "Search for Jobs"
Input field: Text input (e.g., for job titles like "Paralegal")
Button: "Search"

[Main Section]
Organize content with accessible headings and paragraphs. Example structure:

Heading 1 (h1): Provide a descriptive page title (e.g., "Welcome to the Accessible Job Search Engine").
Paragraph: Summarize the content or purpose of the page (e.g., "Use this platform to search for jobs that match your skills. We ensure full accessibility for screen reader users.").

[Lists] or [Filters]
Provide structured lists, dropdowns, or other UI elements. For each list or filter, offer examples.

Heading 2 (h2): "Popular Job Categories"

List of clickable categories:
- Legal
- Healthcare
- Engineering
- Marketing
- IT

[Form Sections] (if applicable)
When building forms, break them into logical sections with labels and input types. Ensure each input has an accessible label.

Example:

Heading 2 (h2): "Personal Information"
- Label: "First Name"
- Input field: Text input
- Label: "Last Name"
- Input field: Text input
- Label: "Email Address"
- Input field: Email input

[Footer]
Could you ensure each page has consistent footer elements for navigation and legal links?

Links to:
- "Privacy Policy,"
- "Accessibility Statement,"
- "Terms of Service"

[Alert Messages] (if applicable)
Include success or error messages based on user actions. Use ARIA live regions for screen reader announcements.

- Success Message (aria-live="assertive"): "Your application has been submitted successfully!"
- Error Message (aria-live="assertive"): "Please complete all required fields before submitting."

5. End each page with Accessibility notes and recommendations for testing this content with users with multiple disabilities, including those in the neurodiversity spectrum.
```



## 5. Components Inventory

```
TASK: EXTRACT COMPONENTS
Take each gherkin story for each step of the journey and create a list of components or user controls each step will require.

List the component name, description, WCAG considerations, and key interaction design recommendations for multiple disabilities, including - but not limited to - keyboard-only, screen reader, and neurodiversity.
This list includes additional visible and invisible patterns that help create an equitable experience for people with disabilities, such as landmark regions, paragraphs, unordered list groups, items, form groups, fieldsets, accordion controls, tab groups, and more.
Assume these components are coming from a design system like USWDS or Carbon.
```

## 6. Create Components Requirements

```
TASK: WRITE GHERKIN STORIES FOR EACH COMPONENT
Create a gherkin story for each component listed. Where appropriate, consider multiple disabilities, such as blindness, low vision, hearing, motor impairment, and cognitive disabilities.
```

## 7.Component Requirements

```
TASK: WRITE REQUIREMENTS FOR EACH COMPONENT
For each Gherkin story created for the components, I want you to display and create a markdown file of this output. Your important task is to put on your design system architect and years of digital accessibility and spec each component design aiming for the highest accessibility conformance level possible:
- display the current gherkin story
- list the expected interaction design and keystrokes and how/if tabs and arrow keys should used (this is something to pay attention, as different assistive technologies have different default preferences and customization)
- list the anatomy of each component,
- list all properties (Recommend width, height, target size, etc)
- list all states (visual and ARIA where appropriate)
- list all possible design tokens you can think of. As a starting point, you may consider the following: typography family color size line-height, color foreground background, spacing margin padding, focus width color style, border width color style, etc.
- list all WCAG criteria that are applicable to current component.
- Mention whether any tokens could be directly aligned with an absolute value based on WCAG Token set.
- Create a thorough, detailed checklist (with checkboxes) itemizing all possible WCAG success criteria for each team member to execute: product, design, development, and QA.

After each story, show the number of stories left to be created, pause, and ask me to press continue.
```








