
# Gherkin Stories for Each Step of Jacob's Job Search Journey

## Stage 1: Job Searching

### Scenario 1: Navigating to the Job Search Website
```gherkin
Feature: Navigate to the job search website

  Scenario: Jacob opens the job search website using his screen reader
    Given Jacob is on his laptop with JAWS running
    When he types the URL for the job search website
    Then the screen reader should announce the homepage title
    And Jacob should be able to navigate the page using keyboard commands
```

### Scenario 2: Searching for Jobs
```gherkin
Feature: Search for jobs

  Scenario: Jacob searches for paralegal jobs
    Given Jacob is on the homepage of the job search website
    When he enters "Paralegal" in the search bar and submits the query
    Then the screen reader should announce the number of search results
    And Jacob should be able to filter jobs by location, salary, and employment type
```

### Scenario 3: Sorting and Filtering Job Listings
```gherkin
Feature: Sort and filter job listings

  Scenario: Jacob filters and sorts job listings
    Given Jacob has search results for paralegal jobs
    When he selects filters such as location and salary
    Then the screen reader should announce the updated results
    And the results should be sorted according to his preferences
```

---

## Stage 2: Reviewing Job Descriptions

### Scenario 1: Navigating Through Job Listings
```gherkin
Feature: Navigate through job listings

  Scenario: Jacob navigates through the job listings using his screen reader
    Given Jacob has a list of job results
    When he navigates using arrow keys or tab
    Then the screen reader should announce each job title, company, and posting date
    And Jacob should be able to choose a job listing to review
```

### Scenario 2: Opening a Job Description
```gherkin
Feature: Open a job description

  Scenario: Jacob opens a specific job description
    Given Jacob is reviewing job listings
    When he selects a job listing and presses "Enter"
    Then the screen reader should announce the job description page title
    And the screen reader should begin reading the job description aloud
```

### Scenario 3: Evaluating the Job Description
```gherkin
Feature: Evaluate the job description

  Scenario: Jacob listens to the job description details
    Given Jacob is on a job description page
    When the screen reader reads out the qualifications, salary, and location
    Then Jacob should be able to take notes using his audio recorder
    And he should be able to decide whether to apply or not
```

---

## Stage 3: Applying for a Job

### Scenario 1: Accessing the Application Form
```gherkin
Feature: Access the application form

  Scenario: Jacob opens the job application form
    Given Jacob has decided to apply for a job
    When he navigates to the "Apply Now" button
    Then the screen reader should announce the button text
    And Jacob should be able to activate the button using the keyboard
    And the screen reader should announce the opening of the application form
```

### Scenario 2: Filling Out the Application
```gherkin
Feature: Fill out the job application form

  Scenario: Jacob fills out the job application form
    Given Jacob is on the application form page
    When he navigates through the form fields using the keyboard
    Then the screen reader should announce the label for each field
    And Jacob should be able to fill in his details using the keyboard
    And he should be able to review the information before submission
```

### Scenario 3: Submitting the Application
```gherkin
Feature: Submit the job application

  Scenario: Jacob submits the completed job application
    Given Jacob has filled out the job application form
    When he activates the "Submit" button
    Then the screen reader should announce that the application has been submitted
    And Jacob should hear a confirmation message of successful submission
```

### Scenario 4: Receiving Confirmation
```gherkin
Feature: Receive application confirmation

  Scenario: Jacob receives a confirmation of his job application submission
    Given Jacob has submitted his job application
    When the confirmation page appears
    Then the screen reader should read the confirmation message
    And Jacob should receive any further instructions for follow-up actions
```
