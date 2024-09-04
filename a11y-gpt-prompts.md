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
Create a high-level user journey map outlining the steps Jacob might take on the website to find his next job opportunity using the following stages. Breakdown the stages in steps for this journey: 
- Stage 1: Job Searching
- Stage 2: Reviewing Job Descriptions
- Stage 3: Applying for a Job
Include headline and description for each step of the journey.
```

## 3. Create Gherkin Stories

```
Create a gherkin story for each step of the journey.
```

## 4. Component Inventory

### 4.1 Extract components from gherkin stories
```
Take each gherkin story and create a list of components or user controls each step will require.
```

### 4.2 Create a single inventory of web components
```
Create a single list of native HTML components we will use. For each component, add a title, description, role, and accessible name along with accessibility notes.
```

## 5. Outline the semantic structure of each page

### 5.1 Short prompt

```
Think of this task as designing with words.
For each Gherkin story, imagine each page using only descriptive bullet points to outline the interface layout using these native components.
Begin each page with the Gherkin story using the give, when, and then statements.
Please remember to add skip links to important sections.
Suggest relevant content for headings, paragraphs, and labels.
After each heading 1 and heading 2, please provide a complementary paragraph describing plain language instructions to the user.
Be thorough with lists, adding at least five items as content examples.
Consider alert messages needing to provide successful and unsuccessful patterns.
Avoid using tables. 
```

### 5.2 Long prompt for better consistency across LLMs

```
Think of this task as designing with words.
For each Gherkin story, imagine each page using only descriptive bullet points to outline the interface layout using these native components.
Begin each page with the Gherkin story using the give, when, and then statements.
Please remember to add skip links to important sections.
Suggest relevant content for headings, paragraphs, and labels.
After each heading 1 and heading 2, please provide a complementary paragraph describing plain language instructions to the user.
Be thorough with lists, adding at least five items as content examples.
Consider alert messages needing to provide successful and unsuccessful patterns.
Avoid using tables.

Stage and Page Naming Stage:
Clearly define the stage of the journey (e.g., "Stage 1: Job Searching").

Page Name:
Provide a descriptive title for the page, reflecting the step of the journey (e.g., "Page 1: Accessing the Job Search Engine").

Gherkin Story Structure Each page must begin with a Gherkin story to outline the user’s interaction in plain language.
Use the Given, When, Then structure:

- Given: Describes the user and their initial context (e.g., "Given I am a blind user with a screen reader").
- When: Specifies the user’s action on the page (e.g., "When I navigate to the job search engine").
- Then: Describes the expected outcome or experience (e.g., "Then I should land on the homepage").
- And: If necessary, add additional expectations or outcomes (e.g., "And the page should be accessible with clear headings and navigation").

3. Interface Layout Sections
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

4. [Form Sections] (if applicable)
When building forms, break them into logical sections with labels and input types. Ensure each input has an accessible label.

Example:

Heading 2 (h2): "Personal Information"
- Label: "First Name"
- Input field: Text input
- Label: "Last Name"
- Input field: Text input
- Label: "Email Address"
- Input field: Email input

5. [Footer]
Ensure that each page has consistent footer elements for navigation and legal links.

- Links to "Privacy Policy," "Accessibility Statement," and "Terms of Service"

6. [Alert Messages] (if applicable)
Include success or error messages based on user actions. Use ARIA live regions for screen reader announcements.

- Success Message (aria-live="assertive"): "Your application has been submitted successfully!"
- Error Message (aria-live="assertive"): "Please complete all required fields before submitting."
```

