# WORK IN PROGRESS

# Building an Job Search app with Cursor AI

## Getting Started

- Install Cursor AI
- Install Github Desktop
- Install NodeJS
- 


## Step 1 - Prime the model

```

[User Persona]
INTRODUCTION:
I am creating a job search engine that is fully accessible to candidates like Jacob. 

NOTE:
- Do NOT react to this request just yet.
- I will give you specific tasks in the next prompt.
- Just reply with an acknowledgement "Jobs for Jacob!" 

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

## Step 2 - Give clear instructions

```
Initiate Git a repository
Build an accessibility-first app using NextJS.
Then deploy the app to Replit

Follow the [User Persona] (already given), [Journey Map] and [Key Considerations] sections to have an understand of the expected outcome.

[Journey Map]

Stage 1: Job Searching

Navigating to the Job Search Website
Description: Jacob opens his laptop and uses JAWS to navigate to the website's homepage. He uses keyboard shortcuts to access the search bar and activate it via his screen reader.

Searching for Jobs
Description: Jacob enters relevant search terms (e.g., "Paralegal jobs" or "Legal assistant") into the search field and refines results by location, salary, and employment type using screen reader-friendly filters.

Sorting and Filtering Job Listings
Description: Jacob leverages the site’s accessible filtering and sorting options to narrow down job listings. He uses the arrow keys to navigate and choose the most relevant positions.

---

Stage 2: Reviewing Job Descriptions

Navigating Through Job Listings
Description: Jacob uses his keyboard and Braille display to scroll through the list of jobs. The screen reader reads aloud key information like job titles, companies, and posting dates.

Opening a Job Description
Description: Jacob selects a job posting of interest by activating the link. The page opens, and his screen reader begins reading the job description aloud.

Evaluating the Job Description
Description: Jacob carefully listens to the job details, focusing on qualifications, salary, location, and the application process. He takes notes using an audio recorder if needed.

---

Stage 3: Applying for a Job

Accessing the Application Form
Description: After deciding to apply, Jacob navigates to the "Apply Now" button using keyboard commands and screen reader feedback. He clicks it to open the application form.

Filling Out the Application
Description: Jacob uses his screen reader to tab through each field in the form, ensuring that all form controls (e.g., text boxes, checkboxes) are accessible and labeled correctly. He inputs his information accurately using his keyboard.

Submitting the Application
Description: Once Jacob completes the form, he reviews his input using the screen reader. Satisfied with the entries, he submits the application by activating the submit button.

Receiving Confirmation
Description: Upon successful submission, Jacob's screen reader informs him of a confirmation message, confirming his application has been received, and any further instructions are read aloud.

---

End of Journey: Jacob Confidently Pursues His Next Opportunity

[Key Considerations]

1. Assume all users have a disability, including blindness, motor, deafness, cognitive and neurodiversity.
2. Begin each page with the Gherkin story using the give, when, and then statements.
3. Please remember to add skip links to important sections.
4. Suggest relevant content for headings, paragraphs, and labels.
5. Please include a complementary paragraph after each heading 1 and heading 2 describing plain-language instructions for the user.
6. Be thorough with lists, adding at least five items as content examples.
7. Consider alert messages needing to provide successful and unsuccessful patterns.
8. Avoid using tables.

```


