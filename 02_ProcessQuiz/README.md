# Moon Process Quiz

### Process Knowledge Assessment & Certification | Microsoft Power Platform

Moon Process Quiz is a Microsoft Power Apps Canvas application designed to assess users' understanding of defined business processes. It guides a participant through basic information capture, a structured question set, answer submission, automated scoring and a pass/fail result, with a certificate experience for successful completion.

## App Gallery

Explore the main experiences available in Moon Process Quiz.

| Experience | Description |
|---|---|
| Welcome screen | Introduces the quiz and provides the entry point to begin. |
| Participant details | Captures the participant's organizational details before the quiz. |
| Process quiz | Presents the active questions and answer choices with progress tracking. |
| Submission confirmation | Confirms the participant's intent before final submission. |
| Quiz result | Displays the calculated score and pass/fail outcome. |
| Certificate | Presents the completion certificate after the assessment. |

---

## 01. Project Overview

| Item | Details |
|---|---|
| **Application name** | Moon Process Quiz |
| **Application type** | Microsoft Power Apps Canvas App |
| **Business domain** | Process enablement, employee learning, process awareness and compliance training |
| **Primary purpose** | Assess users' understanding of business processes through a structured quiz and provide an immediate result and certificate experience. |
| **Intended users** | Employees / learners taking the assessment; questionnaire maintainers and Power Platform administrators supporting the solution. |
| **Interface** | Desktop / tablet-oriented Canvas App |
| **Project status** | Developed application; production deployment status is not established by the supplied files. |

### What the application does

Moon Process Quiz provides a guided assessment experience to:

- Welcome users and explain the purpose of the process quiz.
- Capture participant information before the assessment begins.
- Retrieve active questions from a SharePoint questionnaire list.
- Present question options and record selected answers.
- Track assessment progress and validate completion.
- Calculate the final score and determine the pass/fail outcome.
- Display the result and allow the participant to retake the quiz.
- Trigger a certificate-generation flow and present a certificate of completion.

---

## 02. Business Problem & Objective

### Business problem

Organizations need employees to understand and follow defined processes consistently. Without a structured assessment mechanism, it can be difficult to check process awareness in a repeatable way, ensure that participants answer the full question set, evaluate results consistently and provide evidence that a participant completed an assessment.

A central digital quiz experience helps standardize the assessment journey and makes the result immediately visible to the participant.

### Previous/manual process

The supplied application materials do not document a formal before-state process. The following describes the operational problem the application is designed to address, rather than claiming that a particular manual process was measured:

- Process knowledge needs to be checked in a consistent format.
- Participant details need to be associated with the assessment.
- Questions and answer choices need to be presented in a structured manner.
- Responses need to be checked and scored consistently.
- Participants need clear feedback on whether they met the passing requirement.
- Completion evidence may need to be generated without manually preparing an individual certificate.

### Application objectives

1. Provide a single, guided process-knowledge assessment experience.
2. Capture the participant's required details before starting the quiz.
3. Load active questions from a centrally maintained questionnaire source.
4. Prevent quiz submission until all displayed questions have been answered.
5. Calculate the assessment score using the stored correct-answer data.
6. Present a clear pass/fail outcome.
7. Support quiz retakes.
8. Integrate certificate generation with Power Automate.

---

## 03. Key Features & Functionality

### 3.1 Welcome and participant entry

- Welcome screen with an introduction to the purpose of the process quiz.
- Signed-in Microsoft 365 user context is used by the app.
- Existing participant details are looked up using the signed-in user's email.
- Participant information is captured through a dedicated Basic Details form.
- The user proceeds to the quiz after the required details are completed.

### 3.2 Participant details

The Basic Details experience captures the following fields, as shown in the supplied screenshots:

- Enterprise ID
- Stream
- Tower
- Team
- Supervisor

The participant form is connected to the SharePoint list `Process Quiz - User Details`.

### 3.3 Dynamic questionnaire

- Questions are retrieved from `Process Quiz - Questionnaire`.
- The app filters questionnaire records to active items using the `isActive` field.
- Active records are sorted by SharePoint item ID in ascending order.
- A sequential question number is added to the in-app question collection.
- Question content and answer options are displayed in the quiz gallery.

### 3.4 Answer capture and progress tracking

- Participants select an answer for each question.
- Selected responses are stored in the `colAnswers` collection.
- The progress label displays the number of answered questions against the total question count.
- The submission action is controlled by the answer-completion check.

### 3.5 Submission validation and confirmation

- Required participant fields must be completed before the quiz can be started.
- The quiz submission action is enabled only when the captured answer count matches the number of quiz gallery items and the participant form is valid.
- A confirmation dialog asks the participant to confirm before the quiz is submitted.

### 3.6 Scoring and result management

- Correct responses are counted by comparing the selected answer key with the correct-answer value.
- Incorrect responses are derived from the total question count minus the correct answer count.
- The final percentage is rounded to a whole number.
- The result screen displays the score and pass/fail status.
- Participants can retake the quiz.

**Passing-score verification note:** the supplied app formula uses a strict `> 90` comparison. The screenshot document shows an 89% result labelled PASS, while another screenshot shows a 13% result labelled FAIL. The 89% example and the formula do not agree. Confirm the intended business rule before publishing. If the intended rule is 90% or higher, the comparison should be `>= 90`.

### 3.7 Certificate generation

- The app invokes a connected Power Automate flow for certificate generation.
- The flow call passes the calculated percentage, result status, participant email and participant display name.
- The UI includes a Certificate of Completion view with the participant name, score, date and Moon branding, as shown in the supplied screenshot document.

### User roles and permissions

| User / responsibility | What is evidenced |
|---|---|
| **Quiz participant** | Enters participant details, answers the quiz, submits the assessment, views the result and accesses the certificate experience. |
| **Questionnaire maintainer** | Maintains the connected questionnaire data, including active status and question content. This is a data-maintenance responsibility; a separate in-app administrator experience is not evidenced. |
| **Power Platform / data administrator** | Maintains app sharing, SharePoint access, connector connections and the certificate flow in the target environment. |

The app uses `User()` to obtain the signed-in Microsoft 365 user's email, full name and image. A separate role-based permission matrix is not established by the supplied app package or screenshots.

### Search, filtering and reporting

- The questionnaire source is filtered to active records.
- The active question set is sorted by SharePoint item ID.
- A general user-facing search interface, reporting dashboard or analytics module is not evidenced in the supplied screens.

### Approval workflows and notifications

- No approval workflow is evidenced. The app implements an assessment and certificate journey rather than a manager approval process.
- The app uses Power Apps `Notify()` capability for user feedback in its interaction logic.
- Certificate generation is delegated to a connected Power Automate flow.
- A dedicated email notification sequence is not established by the supplied `.msapp` package alone.

---

## 04. Screenshots & User Interface

The supplied Word document (`PQ.docx`) contains five pages of screenshots. The screenshots show the main assessment journey and both successful and unsuccessful result states.

| Screen / experience | What it demonstrates | Source document |
|---|---|---|
| Welcome screen | Process Quiz landing page, welcome message and quiz entry panel | Page 1 |
| Certificate of Completion | Certificate layout with participant name, score, date and Moon FY26 label | Page 1 |
| Passed result | Home/result panel showing an 89% score and PASS status | Page 2 |
| Failed result | Home/result panel showing a 13% score and FAIL status | Page 2 |
| Participant details | Basic Details tab with Enterprise ID, Stream, Tower, Team and Supervisor | Page 3 |
| Quiz questions | Process Quiz tab, progress indicator and selectable answer options | Page 3 |
| Submission confirmation | Confirmation dialog displayed before submitting the quiz | Page 4 |
| Passed quiz result | Result page showing score, PASSED status and View Certificate action | Page 4 |
| Failed quiz result | Result page showing score, FAILED status and Retake Quiz action | Page 5 |

### Screenshot gallery

Export the relevant screenshots from `PQ.docx` as individual image files and place them in the repository. The following paths are suggested; update them to match the actual filenames you commit.

```text
Screenshots/
├── 01-Welcome/
│   ├── home-screen.png
│   └── certificate-of-completion.png
├── 02-Participant-Details/
│   └── participant-details.png
├── 03-Process-Quiz/
│   ├── quiz-questions.png
│   └── submit-confirmation.png
└── 04-Quiz-Results/
    ├── passed-result.png
    └── failed-result.png
```

### UI design observations

- Purple is used as the primary brand colour, with white content surfaces.
- The app uses a consistent header with the Process Quiz title and user profile initials.
- The assessment journey is separated into **Basic Details** and **Process Quiz** tabs.
- Question progress is shown above the question area.
- A confirmation dialog is used before final submission.
- Result states use distinct success and failure visual treatments.
- The certificate is presented as a separate completion view.

The screenshot document also contains an additional learning/session dashboard image on page 5 with different navigation and branding. It does not appear to be part of the Process Quiz screen journey documented in the `.msapp` package, so it should not be presented as a Process Quiz screen without further verification.

Before public release, review all screenshots for real participant names, email addresses, organization-specific branding, tenant URLs and confidential process content. Replace or blur these details as needed.

---

## 05. Technical Architecture

### Technology stack

| Layer | Technology / component | Evidence |
|---|---|---|
| Presentation | Microsoft Power Apps Canvas App | Confirmed in `.msapp` package |
| Application logic | Power Fx | Confirmed in screen and control formulas |
| Data layer | SharePoint Online lists | Data-source names and formulas are present in the app package |
| Workflow integration | Power Automate-connected flow | App invokes a named certificate flow |
| User identity | Microsoft 365 user context | `User()` is used in app formulas |
| Email connector | Office 365 Outlook | Connector reference is present in the app package; exact use in the certificate flow should be verified from the flow definition |

### High-level architecture

```text
                 ┌───────────────────────────────┐
                 │       Moon Process Quiz        │
                 │     Power Apps Canvas App     │
                 └───────────────┬───────────────┘
                                 │
                 ┌───────────────┼────────────────┐
                 │               │                │
                 ▼               ▼                ▼
          Participant       Quiz engine       Result and
          details form      and answers       certificate UI
                 │               │                │
                 └───────────────┼────────────────┘
                                 │
                                 ▼
                 ┌───────────────────────────────┐
                 │        SharePoint Online      │
                 ├───────────────────────────────┤
                 │ Process Quiz - User Details   │
                 │ Process Quiz - Questionnaire  │
                 └───────────────────────────────┘
                                 │
                                 ▼
                 ┌───────────────────────────────┐
                 │         Power Automate        │
                 │    Certificate generation     │
                 └───────────────────────────────┘
```

> This is a logical architecture reconstructed from the Canvas App package and supplied screenshots. It is not a verified infrastructure diagram. Confirm the actual SharePoint site, list schemas, flow actions, connection references and target environment before publishing a deployment architecture.

### Data sources identified in the app package

| Source identifier in `.msapp` | Apparent purpose based on usage |
|---|---|
| `Process Quiz - User Details` | Stores participant information and supports lookup of the signed-in participant. |
| `Process Quiz - Questionnaire` | Stores quiz questions, answer options, correct-answer data and active status. |

The exact SharePoint site URL, list GUIDs, column schema and permissions are environment-specific and should be validated in the target environment.

### Power Automate / connector references

The app source contains a call to:

- `Copyof-QuizCertificate`

The flow is invoked with the following values:

1. `varPercent` – calculated assessment percentage.
2. `varResult` – pass/fail result.
3. `User().Email` – signed-in participant email.
4. `User().FullName` – signed-in participant display name.

An Office 365 Outlook connector reference is present in the app package. The complete flow definition is not embedded as an editable cloud-flow export in the `.msapp`; therefore, the exact email actions, certificate file storage location, trigger configuration and error branches must be verified from the actual Power Automate flow.

---

## 06. Technical Implementation

### Power Fx implementation patterns

The source demonstrates the following implementation techniques:

| Pattern | Where it is used |
|---|---|
| `Set()` | Stores app-level variables such as theme colour, participant record, score and result. |
| `ClearCollect()` | Loads active questionnaire records and creates local working collections. |
| `Filter()` | Retrieves active questionnaire records. |
| `Sort()` | Orders the active question records by SharePoint item ID. |
| `LookUp()` | Retrieves the participant record associated with the signed-in user's email. |
| `ForAll()` and `Sequence()` | Iterates through the filtered questions and assigns sequential question numbers. |
| `Patch()` | Shapes question records with an additional question-number field in the local collection. |
| `CountRows()` | Tracks the number of captured answers and calculates score totals. |
| `Round()` | Rounds the percentage score to a whole number. |
| `If()` | Controls pass/fail evaluation and conditional UI behaviour. |
| `SubmitForm()` | Submits participant details through the Edit Form. |
| `Notify()` | Provides user-facing feedback. |
| `.Run()` | Invokes the certificate-generation Power Automate flow. |

### Collections and variables

Collections identified in the source include:

- `colTabs` – tab definitions for Basic Details and Process Quiz.
- `colQuestions` – active, sorted questionnaire records with sequential question numbers.
- `colAnswers` – selected answers captured during the quiz.
- `colRandomQuestions` – initialized in `App.OnStart` with up to five shuffled questionnaire records. The active quiz gallery is bound to `colQuestions`, not this collection.

Variables initialized or used include:

- `varPrimaryColour` – primary purple theme colour.
- `varSubmittedRecord` – participant record retrieved from SharePoint or submitted through the form.
- `varCurrentTab` – currently selected tab.
- `varBasicComplete` – controls progression from participant details to the quiz.
- `varNavBar` – controls tab navigation visibility.
- `varCorrect` – number of correct answers.
- `varIncorrect` – number of incorrect answers.
- `varPercent` – rounded percentage score.
- `varResult` – pass/fail status.
- `varSubmitQuizPopup` – controls the submission confirmation dialog.
- `varShowCertificate` – controls the certificate view.
- `varReviewAnswers` – controls the answer-review interface.
- `varResetRadio` – supports resetting radio-answer controls.

### Example: application initialization

The app initializes its primary colour and retrieves the participant record associated with the signed-in user's email.

```powerfx
Set(varPrimaryColour, RGBA(117, 0, 192, 1));

Set(
    varSubmittedRecord,
    LookUp(
        'Process Quiz - User Details',
        'Enterprise ID'.Email = User().Email
    )
);
```

This establishes the app's primary purple colour and uses the signed-in identity to look up the participant's existing details.

### Example: load active questions and assign question numbers

```powerfx
ClearCollect(
    colQuestions,
    With(
        {
            filteredData: Sort(
                Filter(
                    'Process Quiz - Questionnaire',
                    isActive.Value = "Yes"
                ),
                ID,
                SortOrder.Ascending
            )
        },
        ForAll(
            Sequence(CountRows(filteredData)),
            Patch(
                Last(FirstN(filteredData, Value)),
                { QuestionNumber: Value }
            )
        )
    )
);
```

This filters the questionnaire to active records, sorts them by SharePoint ID and adds a sequential `QuestionNumber` to the records used by the quiz gallery.

### Example: track quiz progress

```powerfx
"Progress: " & CountRows(colAnswers) &
" of " & CountRows(colQuestions) & " Questions"
```

The progress label compares the number of captured answers with the number of questions loaded into the quiz collection.

### Example: calculate the score

```powerfx
Set(
    varCorrect,
    CountRows(
        Filter(
            colAnswers,
            CorrectAns.Value = SelectedKey
        )
    )
);

Set(
    varIncorrect,
    CountRows(Gallery1_1.AllItems) - varCorrect
);

Set(
    varPercent,
    Round(
        (varCorrect / CountRows(Gallery1_1.AllItems)) * 100,
        0
    )
);
```

The formula counts matching correct answers, calculates the incorrect answer count and derives a rounded percentage score.

### Example: determine the result

```powerfx
If(
    varPercent > 90,
    Set(varResult, "PASSED"),
    Set(varResult, "FAILED")
);
```

**Important:** this is the comparison found in the supplied app formula. The screenshot document shows an 89% PASS example, which conflicts with a strict greater-than-90 rule. Confirm the expected rule and update either the formula or the displayed business guidance. For a 90%-or-higher passing rule, use `varPercent >= 90`.

### Example: invoke certificate generation

```powerfx
'Copyof-QuizCertificate'.Run(
    varPercent,
    varResult,
    User().Email,
    User().FullName
);
```

The app passes the participant's score, result, email and display name to the connected certificate-generation flow.

### Delegation and performance considerations

The app loads questionnaire records into a local collection and then shapes the data for display. For a production deployment, validate:

- Whether the SharePoint `Filter()` and `Sort()` query is delegable for the actual column types and formula.
- Whether `isActive` is a Choice column and whether the `.Value` comparison delegates as expected.
- Whether the questionnaire list may exceed the app's configured data row limit of 500.
- Whether client-side use of `ForAll()`, `Sequence()` and `FirstN()` is appropriate for the expected question volume.
- Whether question data needs to be refreshed when the quiz screen becomes visible.
- Whether the answer collection and gallery item count remain aligned after retakes or partial interactions.

The package's configured data row limit is 500. This setting does not by itself prove that all records are retrieved or that the query is delegation-safe.

### Error handling

The source includes form submission patterns and `Notify()` usage. The participant form's `OnSuccess` updates `varSubmittedRecord` using `BasicDetailsForm_1.LastSubmit`, and the participant data source is refreshed after submission.

For a production release, validate and document:

- Failed participant form submissions.
- Missing or invalid required details.
- Incomplete quiz responses.
- SharePoint connector failures.
- Failed or timed-out certificate flow calls.
- Whether the participant receives a clear message when certificate generation does not complete.

A complete Power Automate failure-handling design cannot be established from the `.msapp` package alone.

### Performance optimization

- Active questions are loaded into `colQuestions` when the quiz screen becomes visible.
- Collections support local answer tracking and progress calculations during the assessment.
- Reusable Canvas Components reduce repeated header construction.
- Galleries and containers structure the question and result experiences.
- For larger question banks, test loading time, SharePoint delegation and collection size using realistic data volumes.

---

## 07. Power Apps Concepts Demonstrated

This section gives recruiters a technical view of the Power Apps concepts implemented in Moon Process Quiz. The concepts below are based on the supplied Canvas App package and screenshot document. Where a capability is only a consideration rather than a verified implementation, it is identified accordingly.

### Technical concept map

| Power Apps concept | How it is used in Moon Process Quiz | Why it matters |
|---|---|---|
| Canvas App architecture | A multi-screen Canvas App provides the participant welcome, details, quiz, result and certificate experiences. | Structures the application around a clear end-to-end user journey. |
| Screen navigation and tab state | `varCurrentTab`, `varBasicComplete` and navigation visibility variables control the Basic Details and Process Quiz experience. | Guides users through the assessment in the intended order. |
| Microsoft 365 user context | `User()` provides the signed-in user's email, full name and image. | Associates the quiz journey with the current participant. |
| Power Fx state management | `Set()` stores participant, navigation, scoring, popup and certificate state. | Maintains application state across user interactions. |
| Collections and local data shaping | `ClearCollect()` creates `colQuestions`, `colAnswers` and other working collections. | Prepares question and answer data for galleries and calculations. |
| SharePoint data operations | Connected lists store participant information and questionnaire content. | Separates application UI and logic from persisted data. |
| Record lookup | `LookUp()` retrieves the signed-in participant's existing record. | Avoids treating each app visit as an unrelated participant entry. |
| Dynamic question numbering | `ForAll()`, `Sequence()` and `Patch()` shape the active question set. | Adds a sequential question number for presentation. |
| Galleries and data-driven UI | Galleries display the active question set and answer choices. | Supports a repeatable question interface driven by data. |
| Form validation | The participant Edit Form and required-field checks control progression. | Prevents the quiz from starting before required details are provided. |
| Conditional logic | `If()` controls validation, visibility and pass/fail evaluation. | Aligns the interface with the assessment rules. |
| Progress and score calculations | `CountRows()`, `Filter()` and `Round()` calculate progress and the result. | Converts participant responses into a measurable outcome. |
| Reusable components | Header component definitions are present in the app package. | Encourages a consistent interface and reduces duplicated UI definitions. |
| Dialog and popup handling | Variables control submission confirmation and certificate/result views. | Supports focused interactions without navigating away from the quiz journey. |
| Power Automate integration | A named flow is invoked to generate the certificate. | Extends the Canvas App with an automated downstream process. |
| User feedback | `Notify()` is used in the app logic. | Communicates validation and action feedback to participants. |

### Core Power Fx patterns

1. **Initialize participant context**

   The app retrieves the signed-in participant's existing record from the user details list.

   ```powerfx
   Set(
       varSubmittedRecord,
       LookUp(
           'Process Quiz - User Details',
           'Enterprise ID'.Email = User().Email
       )
   );
   ```

2. **Load and shape active questions**

   The app filters active questions, sorts them and adds a sequential question number for display in the quiz gallery.

   ```powerfx
   ClearCollect(
       colQuestions,
       With(
           {
               filteredData: Sort(
                   Filter(
                       'Process Quiz - Questionnaire',
                       isActive.Value = "Yes"
                   ),
                   ID,
                   SortOrder.Ascending
               )
           },
           ForAll(
               Sequence(CountRows(filteredData)),
               Patch(
                   Last(FirstN(filteredData, Value)),
                   { QuestionNumber: Value }
               )
           )
       )
   );
   ```

3. **Track responses and calculate the outcome**

   The app stores participant responses in `colAnswers`, counts correct answers and calculates the percentage score.

   ```powerfx
   Set(
       varCorrect,
       CountRows(
           Filter(
               colAnswers,
               CorrectAns.Value = SelectedKey
           )
       )
   );

   Set(
       varPercent,
       Round(
           (varCorrect / CountRows(Gallery1_1.AllItems)) * 100,
           0
       )
   );
   ```

4. **Trigger the certificate workflow**

   The result is passed to the connected certificate flow along with participant identity details.

   ```powerfx
   'Copyof-QuizCertificate'.Run(
       varPercent,
       varResult,
       User().Email,
       User().FullName
   );
   ```

These are representative formulas from the app source. The imported app package remains the authority for complete formulas, exact control names and control properties.

### Concepts recruiters should look for in the source

- App lifecycle: `App.OnStart` initialization and screen-level loading.
- Identity: signed-in user context through `User()`.
- Data retrieval: `LookUp`, `Filter` and `Sort`.
- Data shaping: `ClearCollect`, `ForAll`, `Sequence` and `Patch`.
- State management: `Set` variables for navigation, validation, score and result.
- Validation: required participant fields and complete-answer checks.
- Business logic: correct-answer comparison and pass/fail calculation.
- UI composition: galleries, forms, containers, dialogs and reusable components.
- Integration: Power Automate flow invocation for certificate generation.

### Delegation, security and performance considerations

These are important engineering considerations for the solution and should be validated in the target environment:

1. **Delegation:** Review the SharePoint question query for delegation warnings. Loading records into a collection does not remove delegation limits from the query that populates it.
2. **Question-bank size:** Confirm the expected number of active questions and whether the configured row limit is sufficient.
3. **Client-side processing:** `ForAll()`, `Sequence()` and `FirstN()` operate on the retrieved local data. Test with the largest expected question set.
4. **Answer integrity:** Confirm that each question has one valid answer record and that the selected key is compared against the intended correct-answer field.
5. **Passing rule:** Align the Power Fx threshold, quiz instructions and result examples.
6. **Identity and access:** The signed-in user lookup associates the participant record with an email address; SharePoint permissions must still enforce data access.
7. **Flow reliability:** Validate certificate flow failures and provide meaningful feedback if generation does not complete.
8. **Connection management:** Rebind SharePoint and flow connections when importing the app into another Power Platform environment.

---

## 08. My Contribution

This section is a draft summary based on the implementation present in the supplied `.msapp`. The app package can establish implementation patterns, but it cannot independently establish individual ownership of every feature. Retain only statements that accurately reflect your own work.

### Development contribution

- Designed and developed the Canvas App screens for the process quiz experience.
- Built the participant-details form and tab-based progression.
- Connected the app to SharePoint participant and questionnaire data.
- Implemented active-question retrieval, sorting and sequential question numbering.
- Developed answer capture and quiz progress tracking.
- Implemented submission validation and the confirmation dialog.
- Built the scoring calculation and pass/fail result experience.
- Developed the certificate and retake user experiences.
- Integrated the app with the certificate-generation Power Automate flow.
- Created reusable header components and applied a consistent purple-and-white UI theme.

### Technical challenges and design decisions

| Area | Implementation / design decision |
|---|---|
| Participant identification | Used the signed-in Microsoft 365 email to look up the participant's existing record. |
| Question management | Kept questionnaire content in SharePoint and loaded active records into a local collection. |
| Question ordering | Sorted active records by SharePoint ID and assigned sequential question numbers. |
| Assessment progression | Split participant details and quiz questions into separate tabs. |
| Submission control | Used answer count and form validity to control quiz submission. |
| Scoring | Compared selected answer keys with correct-answer values and calculated a percentage. |
| Result presentation | Separated pass/fail result states and provided a retake path. |
| Certificate automation | Passed score and participant information to a Power Automate flow. |
| Reusable UI | Used header components and a consistent visual system across the app. |

### Technical challenges to explain in an interview

- How active questionnaire records are loaded and transformed for the quiz gallery.
- How the app ensures that every question has been answered before submission.
- How selected answers are stored and matched with the correct-answer data.
- How the score is calculated and how the passing threshold is applied.
- How the app communicates with the certificate-generation flow.
- How SharePoint delegation and question-bank size are handled.

Only retain contribution statements that accurately reflect your own work.

---

## 09. Project Files & Resources

Suggested repository layout:

```text
Moon-Process-Quiz/
│
├── README.md
│
├── PowerApps/
│   └── Moon-Process-Quiz.msapp
│
├── Screenshots/
│   ├── 01-Welcome/
│   │   ├── home-screen.png
│   │   └── certificate-of-completion.png
│   │
│   ├── 02-Participant-Details/
│   │   └── participant-details.png
│   │
│   ├── 03-Process-Quiz/
│   │   ├── quiz-questions.png
│   │   └── submit-confirmation.png
│   │
│   └── 04-Quiz-Results/
│       ├── passed-result.png
│       └── failed-result.png
│
├── Architecture/
│   └── application-architecture.png
│
├── Documentation/
│   ├── process-quiz-screenshots.docx
│   ├── technical-documentation.md
│   └── data-dictionary.md
│
└── PowerAutomate/
    └── certificate-flow-documentation.md
```

### Project resources

| Resource | Description |
|---|---|
| `Moon-Process-Quiz.msapp` | Power Apps Canvas App source package. |
| `Screenshots/` | Individual screenshots of the app's key screens and result states. |
| `Architecture/application-architecture.png` | Optional exported architecture diagram. |
| `Documentation/process-quiz-screenshots.docx` | Original screenshot reference document supplied with the project. |
| `Documentation/technical-documentation.md` | Optional detailed implementation notes. |
| `Documentation/data-dictionary.md` | Optional SharePoint list and column reference. |
| `PowerAutomate/certificate-flow-documentation.md` | Notes on the certificate flow, its inputs and environment dependencies. |

### Publication checklist

- [ ] Replace organization-specific references with Moon in the app and documentation.
- [ ] Remove real participant names, email addresses and tenant-specific URLs.
- [ ] Replace production participant data with fictional sample data.
- [ ] Review screenshots for confidential information and branding.
- [ ] Verify that no connection secrets, access tokens or environment-specific configuration are exposed.
- [ ] Confirm that the `.msapp` can be imported into a clean demonstration environment.
- [ ] Document the required SharePoint lists, columns and choice values.
- [ ] Document or export the certificate-generation flow separately.
- [ ] Validate the intended passing threshold and align the formula with the quiz instructions.
- [ ] Confirm that all screenshots match the sanitized application.

---

## Scope & verification notes

This README was prepared using the supplied five-page screenshot document (`PQ.docx`) and the supplied Power Apps `.msapp` package.

**Verified from the application package:** Canvas App structure, screen and component definitions, SharePoint data-source identifiers, connector references, named certificate flow invocation and Power Fx implementation patterns.

**Visible in the screenshots:** welcome screen, participant details form, quiz questions, progress indicator, submission confirmation, passed and failed result states, and certificate presentation.

**Requires further validation:** exact SharePoint site and list schemas, deployed permissions, complete Power Automate flow definition, production deployment status, formal before-state process, and personally owned development tasks.

**Business-rule discrepancy to resolve:** the app formula uses `varPercent > 90`, while the screenshot document shows an 89% PASS example. The intended passing threshold must be confirmed before the portfolio describes it as a fixed business rule.

---

## About this project

Moon Process Quiz demonstrates how Microsoft Power Platform can be used to digitize a process-knowledge assessment, combining a Power Apps Canvas App, SharePoint-based questionnaire and participant data, Power Fx scoring logic and Power Automate certificate generation.
