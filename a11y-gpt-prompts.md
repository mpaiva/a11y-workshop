# Designing with words

- A step-by-step guide for Accessible Prototyping
- These guidelines will help build a content-first mindset to create accessible experiences.

**Poor Content Leads to Poor Accessibility**

With this premise in mind, we encourage using a language model like ChatGPT to assist you in creating content. 

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
```
For each Gherkin story, imagine each page using only descriptive bullet points to outline the interface layout using these native components. Begin each page with the Gherkin story using the give, when, then statements. Please remember to add skip links to important sections. Suggest relevant content for headings, paragraphs, and labels, and be thorough with lists, adding at least 5 items as content examples. Be aware of alert messages needs, etc. Avoid using tables. Think of this task as designing with words.
```

