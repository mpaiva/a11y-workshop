
# Job Search Accessibility Prototype - User Journey

---

## Stage 1: Job Searching

### Page 1: Accessing the Job Search Engine

#### Gherkin Story Structure:
- **Given**: I am a blind user with a screen reader.
- **When**: I navigate to the job search engine.
- **Then**: I should land on the homepage.
- **And**: The page should include skip links for easy navigation, and headings should be clearly defined for screen readers to announce.

#### Interface Layout:
1. **[Skip Links]**
   - Skip to Search Bar
   - Skip to Job Listings
   - Skip to Footer

2. **[Header]**
   - **Navigation Menu**:
     - Home
     - Job Search
     - Profile
     - Help
   - **Search Bar**:
     - **Label**: "Search for Jobs"
     - **Input field**: Text input for keywords (e.g., "Paralegal")
     - **Button**: "Search"
   - **Plain-Language Instructions**: Use the search bar to find job listings based on your skills and location. Enter a keyword like "Paralegal" and press "Search."

3. **[Main Section]**
   - **Heading 1 (h1)**: "Welcome to the Accessible Job Search Engine"
   - **Paragraph**: Use this platform to search for jobs that match your skills. We ensure that all users, including those using screen readers, can navigate the site with ease.

4. **[Filters Section]**
   - **Heading 2 (h2)**: "Popular Job Categories"
   - **Paragraph**: Filter by job category to refine your search. Choose the category that fits your expertise to explore matching opportunities.
   - **List of clickable categories**:
     - Legal
     - Healthcare
     - Engineering
     - Marketing
     - IT

5. **[Footer]**
   - Links to:
     - Privacy Policy
     - Accessibility Statement
     - Terms of Service

#### Alert Messages:
- **Success Message**: "Your job search results are ready. Scroll down to view them."
- **Error Message**: "Please enter a valid job title or keyword to start your search."

#### Accessibility Notes:
- Ensure that all skip links are accessible via keyboard and that they announce themselves properly to screen readers.
- Test the search bar for compatibility with assistive technologies, ensuring users can enter text and submit the form with ease.
- Ensure the filters and categories are accessible for screen reader users and easily navigable with the keyboard.

---

### Page 2: Viewing Search Results

#### Gherkin Story Structure:
- **Given**: I have completed a search for jobs using my screen reader.
- **When**: I navigate through the job listings.
- **Then**: The job titles, companies, and posting dates should be announced by the screen reader.
- **And**: I should be able to select a job listing to view its full description.

#### Interface Layout:
1. **[Skip Links]**
   - Skip to Job Listings
   - Skip to Footer

2. **[Header]**
   - **Navigation Menu**:
     - Home
     - Job Search
     - Profile
     - Help
   - **Search Bar**:
     - **Label**: "Search for Jobs"
     - **Input field**: Text input (pre-filled with the previous search)
     - **Button**: "Search"

3. **[Main Section]**
   - **Heading 1 (h1)**: "Search Results"
   - **Paragraph**: Here are the jobs that match your search. Use your screen reader or keyboard to navigate through the listings.
   - **List of job listings** (each item is focusable and announced by a screen reader):
     - Paralegal at XYZ Law Firm, posted 2 days ago.
     - Legal Assistant at ABC Legal Services, posted 5 days ago.
     - Senior Paralegal at DEF Law Group, posted 1 week ago.
     - Junior Paralegal at GHI Legal Partners, posted 3 days ago.
     - Legal Researcher at JKL Associates, posted 2 weeks ago.

4. **[Footer]**
   - Links to:
     - Privacy Policy
     - Accessibility Statement
     - Terms of Service

#### Alert Messages:
- **Success Message**: "You have successfully applied the filters. Use your keyboard to navigate through the updated job listings."
- **Error Message**: "No jobs found matching your search criteria. Try adjusting your filters."

#### Accessibility Notes:
- Ensure that job listings are keyboard navigable and each job's title, company, and posting date are properly labeled for screen readers.
- Test the interaction between filters and results to ensure that updates are announced correctly to screen readers.

---


## Stage 2: Reviewing Job Descriptions

### Page 3: Viewing Job Descriptions

#### Gherkin Story Structure:
- **Given**: I have selected a job listing to view.
- **When**: I load the job description page.
- **Then**: The page should announce the job title and key details like salary, qualifications, and location.
- **And**: I should be able to review all sections of the job description with my screen reader.

#### Interface Layout:
1. **[Skip Links]**
   - Skip to Job Details
   - Skip to Qualifications
   - Skip to Footer

2. **[Main Section]**
   - **Heading 1 (h1)**: "Paralegal at XYZ Law Firm"
   - **Paragraph**: Review the details of this job, including salary, qualifications, and location. Ensure you meet the requirements before applying.

   - **Heading 2 (h2)**: "Job Details"
   - **Paragraph**: This section contains an overview of the job, the salary range, and the expected work schedule.
   - **List of job details**:
     - Location: Orlando, FL
     - Salary: $50,000 - $60,000 per year
     - Full-time position
     - Remote work available
     - Benefits: Health, Dental, 401k

   - **Heading 2 (h2)**: "Job Qualifications"
   - **Paragraph**: Ensure you meet the qualifications for this position. You can navigate through this section to review the necessary skills and experience.
   - **List of qualifications**:
     - Bachelor’s degree in Legal Studies or related field
     - 3+ years of paralegal experience
     - Familiarity with legal research databases
     - Excellent written and verbal communication skills
     - Ability to work independently and manage multiple tasks

#### Footer:
- Links to:
  - Privacy Policy
  - Accessibility Statement
  - Terms of Service

#### Alert Messages:
- **Success Message**: "You are now viewing the full job description. Use your screen reader or keyboard to navigate the details."
- **Error Message**: "An error occurred while loading the job description. Please try again."

#### Accessibility Notes:
- Ensure headings are logically structured for easy screen reader navigation.
- Test each section to ensure it is properly labeled and content is accessible to keyboard and screen reader users.

---

## Stage 3: Applying for a Job

### Page 4: Applying for a Job

#### Gherkin Story Structure:
- **Given**: I have reviewed the job description and decided to apply.
- **When**: I fill out the application form.
- **Then**: Each form field should be labeled and navigable via keyboard.
- **And**: The screen reader should announce required fields and validation errors, if any.

#### Interface Layout:
1. **[Skip Links]**
   - Skip to Application Form
   - Skip to Footer

2. **[Main Section]**
   - **Heading 1 (h1)**: "Job Application for Paralegal at XYZ Law Firm"
   - **Paragraph**: Please fill out the following form to apply for the job. Ensure that all required fields are filled before submitting the application.

   - **Heading 2 (h2)**: "Personal Information"
   - **Form Fields**:
     - **Label**: "First Name"
     - **Input field**: Text input
     - **Label**: "Last Name"
     - **Input field**: Text input
     - **Label**: "Email Address"
     - **Input field**: Email input

   - **Heading 2 (h2)**: "Professional Experience"
   - **Form Fields**:
     - **Label**: "Years of Paralegal Experience"
     - **Input field**: Text input
     - **Label**: "Current Employer"
     - **Input field**: Text input

3. **[Submit Button]**
   - Button text: "Submit Application"

4. **[Footer]**
   - Links to:
     - Privacy Policy
     - Accessibility Statement
     - Terms of Service

#### Alert Messages:
- **Success Message**: "Your application has been submitted successfully!"
- **Error Message**: "Please complete all required fields before submitting."

#### Accessibility Notes:
- Test form validation and ensure errors are announced clearly with `aria-live` regions.
- Ensure all form fields have corresponding labels, and that required fields are indicated for screen reader users.

---

### Page 5: Confirmation and Follow-Up

#### Gherkin Story Structure:
- **Given**: I have submitted my job application.
- **When**: I receive confirmation.
- **Then**: The screen reader should announce the success message and any next steps.

#### Interface Layout:
1. **[Main Section]**
   - **Heading 1 (h1)**: "Application Submitted"
   - **Paragraph**: Thank you for applying to XYZ Law Firm. Your application has been received, and our team will review it shortly. You will receive an email confirmation with further instructions.

---

#### Footer:
- Links to:
  - Privacy Policy
  - Accessibility Statement
  - Terms of Service

#### Alert Messages:
- **Success Message**: "Your application has been submitted successfully!"
- **Error Message**: "An error occurred while submitting your application. Please try again."

---

#### Accessibility Notes:
- Ensure the success message is announced immediately after submission via a screen reader.
- Test for proper focus management, ensuring the user is taken to the confirmation page after submission.

