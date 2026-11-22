# Moon CDP – Client Data Protection & Employee Lifecycle Management

### Employee Onboarding, Compliance & Resource Lifecycle | Microsoft Power Platform

Moon CDP is a centralized employee and contractor lifecycle management solution built with Microsoft Power Apps. It brings resource onboarding, roll-on and roll-off tracking, yearly training follow-ups, client data protection acknowledgements and resource record management into one structured application experience.

The application is designed to help Moon maintain consistent lifecycle records, improve visibility into resource status and support timely compliance-related follow-ups.

---

## App Gallery

The screenshots below are taken from the supplied application documentation. Add the corresponding image files to `Screenshots/` and update the paths if you rename them.

 <img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/abf3539a-80a3-41fa-93a7-bbd45a644924" />
 <img width="975" height="543" alt="image" src="https://github.com/user-attachments/assets/e1d28480-5e15-43cb-b598-ce1d378d056e" />
 <img width="975" height="550" alt="image" src="https://github.com/user-attachments/assets/ec7825e6-68cd-4b21-98be-3e2903150141" />
 <img width="975" height="555" alt="image" src="https://github.com/user-attachments/assets/7448ca3b-b58b-4a84-8c52-8fb97c24231c" />
<img width="975" height="554" alt="image" src="https://github.com/user-attachments/assets/f3b013bd-66fd-46b6-94ec-a54f705a2297" />
<img width="975" height="550" alt="image" src="https://github.com/user-attachments/assets/ca6d35e2-8a76-4838-81bf-dbac60f941e6" />
<img width="975" height="553" alt="image" src="https://github.com/user-attachments/assets/c704dd7c-382e-4eac-8119-174e9e685c27" />
<img width="975" height="547" alt="image" src="https://github.com/user-attachments/assets/c304cb18-a6e7-4a30-810b-acbecb80273d" />
<img width="975" height="553" alt="image" src="https://github.com/user-attachments/assets/625764f2-8082-4670-9d00-0a61b3a3afac" />
 
---

## 01. Project Overview

| Item | Details |
|---|---|
| Application name | Moon CDP – Client Data Protection & Employee Lifecycle Management |
| Application type | Microsoft Power Apps Canvas App |
| Business domain | Employee lifecycle management, client data protection, compliance and resource operations |
| Primary purpose | Centralize employee/contractor onboarding, lifecycle tracking, compliance acknowledgements, yearly training and roll-off requests |
| Intended users | PMO/resource management users, onboarding coordinators, employees and contractors completing required acknowledgements |
| Interface | Desktop/tablet, landscape |
| Canvas dimensions | 1366 × 768 |
| Project status | Application package supplied for portfolio documentation; production deployment status is not established by the supplied files |

### What the application does

Moon CDP provides a common workspace to:

- Register a new employee or contractor resource.
- Capture enterprise ID, employee details and lifecycle dates.
- Search existing resources by enterprise ID or onboarding date.
- Review a resource's onboarding and roll-off information.
- Update lifecycle details and track roll-on/roll-off status.
- Initiate yearly training and compliance follow-ups.
- Present client data protection and security rules for acknowledgement.
- Capture roll-off requests, status information, audit history and attachments.
- Trigger workflow actions through a connected Power Automate flow.

---

## 02. Business Problem & Objective

### Business problem

Employee and contractor lifecycle processes involve multiple checkpoints: resource registration, onboarding dates, client policy acknowledgement, training follow-ups, active status monitoring and eventual roll-off. When these activities are managed across disconnected trackers, forms and email conversations, it can become difficult to maintain a consistent resource record, identify pending actions and follow up at the right time.

Client data protection requirements add another layer: resources need to review the applicable rules and explicitly acknowledge that they have read and accepted them.

### Previous/manual process

The supplied application files do not document a formal before-state process or measured baseline. The operational challenges the application is designed to address include:

- Resource information and lifecycle dates needing a common record.
- Manual searching and checking of employee/contractor status.
- Tracking onboarding, yearly training and roll-off milestones.
- Collecting and retaining acknowledgement of client data protection rules.
- Coordinating follow-ups and reminders for lifecycle events.
- Maintaining visibility of status changes and supporting audit information.

### Application objectives

1. Provide a centralized record for employee and contractor lifecycle information.
2. Standardize new resource onboarding data capture.
3. Allow users to find existing resources using enterprise ID or onboarding date.
4. Track roll-on, roll-off, active status and related lifecycle dates.
5. Present policy and security requirements through a guided acknowledgement experience.
6. Capture acceptance before users proceed through the relevant acknowledgement journey.
7. Support yearly training and lifecycle follow-up actions.
8. Maintain request details, audit history and supporting attachments.
9. Use workflow automation to support downstream notifications or follow-up processes.

---

## 03. Key Features & Functionality

### 3.1 Home dashboard

- Central landing screen with a short application introduction.
- Separate entry points to onboard a new resource and manage an existing resource.
- Shared header and user identity area.
- Navigation to the main resource lifecycle journeys.

### 3.2 New resource onboarding

- Employee/contractor enterprise ID capture.
- Roll-on date and due date fields.
- PMO submission metadata, including modified-by name and email.
- Form-based submission with mandatory-field validation.
- Success and failure feedback following submission.

### 3.3 Manage existing resources

- Search by Enterprise ID.
- Alternate search mode by onboarding date.
- Search, reset and back navigation actions.
- Search results area for matching resource records.
- Resource detail view with lifecycle information.
- Actions to initiate relevant follow-ups, including yearly training and roll-off.

### 3.4 Lifecycle and status management

The resource record includes lifecycle-related fields such as:

- Enterprise ID, employee name and email.
- External/alternate email.
- Roll-on date and roll-off completion date.
- Next roll-on date.
- Roll-on and roll-off indicators.
- Accepted/acknowledged status.
- Active status and next-year reminder status.
- Due date and reminder information.
- Modified-by details and item history.

The exact business meaning and permitted transitions for each status should be confirmed with the process owner before deployment.

### 3.5 Client data protection acknowledgement

- Guided, multi-page acknowledgement experience.
- Separate content covering data protection and security/accountability expectations.
- Progress indicators across the acknowledgement pages.
- Read/accept checkbox before enabling the final acceptance action.
- Record lookup using an ID passed to the app through a URL parameter.
- Submission of acknowledgement through a form.

The supplied screenshots show policy content and acceptance steps. They do not establish the exact legal wording or the complete downstream audit process; those should be validated against the approved policy and production configuration.

### 3.6 Project roll-off acknowledgement

- Dedicated roll-off acknowledgement screen.
- Policy content presented in a structured, guided layout.
- Acceptance control and submit action.
- Resource record retrieved using the supplied record ID.
- Submission feedback after the acknowledgement form is saved.

### 3.7 Raise new request

The request form is organized into sections:

**Employee basic information**
- Enterprise ID
- Employee name
- Employee email
- Employee external email

**Roll-on lifecycle details**
- Roll-on date
- Roll-on completion date
- Next roll-on date
- Is roll-on indicator
- Acceptance status
- Next-year reminder active status

**Roll-off details**
- Is roll-off indicator

**Status and activity control**
- Active status
- Blank date/status field
- Test-date-only field

**Audit details**
- Item history
- Attachments

The form includes reset and submit actions.

### 3.8 User roles and permissions

The app package and screenshots establish a PMO-oriented management experience and an employee/contractor acknowledgement journey. A complete role-permission matrix is not available in the supplied files.

| User group | Visible/expected application interaction |
|---|---|
| PMO / resource management user | Register resources, search records and manage lifecycle information |
| Employee / contractor | Review and acknowledge the applicable policy content |
| Administrator / app owner | Maintain the connected data sources, app access and workflow configuration |

> The table describes the functional user groups implied by the app journeys. It does not claim that row-level security or a specific role-based authorization model has been verified.

### 3.9 Forms, validation and notifications

- Power Apps forms are used for resource and acknowledgement submissions.
- Required-field checks are present on the onboarding submission path.
- Search actions warn users when the required search input is missing.
- `Notify()` provides success, warning and error messages.
- Form failure handling displays a submission error message on the new request screen.
- The connected flow is invoked after relevant record submissions.

---

## 04. Screenshots & User Interface

The supplied Word document contains five pages of screenshots. The following mapping identifies the visible experiences and their source pages.

| Screen / experience | What it demonstrates | Source document |
|---|---|---|
| Home / ELM dashboard | Welcome panel and entry points for onboarding and resource management | Page 1 |
| New onboarding | Employee basic information, roll-on lifecycle details and PMO submission metadata | Page 1 |
| Manage user – empty search | Enterprise ID search, search instructions, reset and search actions | Page 2 |
| Manage user – search modes | Enterprise ID and onboarding-date search tabs | Page 2 |
| Manage user – matching record | Resource result with employee details and lifecycle action buttons | Page 3 |
| Client data protection rules | Guided policy content and progress indicator | Page 3 |
| Security and accountability | Security-related acknowledgement and acceptance checkbox | Page 4 |
| Project roll-off | Project roll-off acknowledgement content and acceptance | Page 4 |
| Raise new request – lifecycle | Employee details, roll-on and roll-off fields | Page 5 |
| Raise new request – status and audit | Due date, reminder, active status, item history and attachments | Page 5 |

### UI design observations

- Purple is used as the primary action/accent colour.
- White content surfaces and light neutral backgrounds keep forms readable.
- Reusable header components provide consistent branding and page titles.
- Forms are grouped into clearly labelled sections.
- Search and result areas are separated to make resource lookup straightforward.
- Guided acknowledgement screens use progress indicators and explicit acceptance controls.
- Primary actions use filled buttons, while secondary navigation uses outlined buttons.

### Suggested repository screenshot structure

```text
Screenshots/
├── home-and-onboarding.png
├── manage-user-search.png
├── resource-details.png
├── cdp-acknowledgement.png
├── security-acknowledgement.png
├── rolloff-acknowledgement.png
└── raise-new-request.png
```

The image paths in the App Gallery are placeholders until the screenshots are exported from the supplied Word document and added to the repository.

---

## 05. Technical Architecture

### Technology stack

| Layer | Technology / component | Evidence |
|---|---|---|
| Presentation | Microsoft Power Apps Canvas App | Confirmed in `.msapp` package |
| Application logic | Power Fx | Confirmed in screen source |
| Data layer | SharePoint Online lists | SharePoint connector and connected list metadata are present |
| Workflow integration | Power Automate | Connected flow `dev_CDPFlows` is referenced by the app |
| Email integration | Office 365 Outlook connector | Connection reference is present in the app package |
| Reusable UI | Canvas components | Multiple component definitions are included |
| File handling | Power Apps attachments control | Attachment controls are present on request forms |

### High-level architecture

```text
                  ┌──────────────────────────────┐
                  │           Moon CDP           │
                  │    Power Apps Canvas App     │
                  └──────────────┬───────────────┘
                                 │
             ┌───────────────────┼────────────────────┐
             │                   │                    │
             ▼                   ▼                    ▼
      Home & onboarding    Resource management   Acknowledgement
      New resource form    Search & edit          Roll-on / roll-off
             │                   │                    │
             └───────────────────┼────────────────────┘
                                 │
                                 ▼
                  ┌──────────────────────────────┐
                  │       SharePoint Online      │
                  │                              │
                  │ Resource lifecycle records   │
                  │ Staffing checklist records   │
                  └──────────────┬───────────────┘
                                 │
                                 ▼
                  ┌──────────────────────────────┐
                  │       Power Automate         │
                  │         dev_CDPFlows         │
                  │                              │
                  │ Lifecycle follow-up trigger  │
                  └──────────────┬───────────────┘
                                 │
                                 ▼
                  ┌──────────────────────────────┐
                  │     Microsoft 365 services   │
                  │  Office 365 Outlook connector│
                  └──────────────────────────────┘
```

> This is a logical architecture reconstructed from the Canvas App package. The full cloud flow definition and its downstream actions were not supplied, so the diagram should not be treated as a verified infrastructure or deployment diagram.

### Data sources identified in the app package

| Data source | Type | Apparent purpose |
|---|---|---|
| Main CDP resource list | SharePoint Online | Employee/contractor lifecycle and CDP dashboard records |
| Staffing checklist | SharePoint Online | Supporting staffing checklist information |
| `dev_CDPFlows` | Power Automate-connected flow | Lifecycle-related workflow trigger |
| Office 365 Outlook | Microsoft 365 connector | Connected email service |

The main SharePoint record schema includes fields for enterprise ID, employee details, lifecycle dates, roll-on/roll-off indicators, acceptance status, active status, reminder status, modified-by information, item history and attachments.

### Power Automate integration

The app invokes `dev_CDPFlows` with five text inputs. The flow metadata describes these inputs as:

1. Enterprise ID
2. Staffing status
3. Item ID
4. Supervisor
5. Enterprise email

The app source invokes the flow after relevant form submissions, including yearly training and roll-off update paths. The complete flow definition was not included in the uploaded package; its exact trigger actions, email templates, conditions and failure branches should be reviewed separately.

### Connectors and Microsoft services

- SharePoint Online – connected list data.
- Power Automate – workflow invocation through the connected flow.
- Office 365 Outlook – connector reference in the app's connection metadata.

No confirmed Power BI integration is established by the supplied app package.

---

## 06. Technical Implementation

### 6.1 App initialization and navigation

The app initializes shared colour variables in `App.OnStart` and uses the `stage` URL parameter to determine the initial screen.

```powerfx
Set(varPrimaryColour, RGBA(117, 0, 192, 1));
Set(varSecondaryColour, RGBA(237, 223, 247, 0.3));
Set(varTertiaryColour, RGBA(245, 245, 245, 1));
```

The start-screen routing is implemented using `Switch()`:

```powerfx
Switch(
    Param("stage"),
    "rollon", AgreementScreen,
    "rolloff", RolloffAgreementScreen,
    HomeScreen
)
```

This allows the app to open the relevant acknowledgement journey based on the supplied stage parameter.

### 6.2 Search state and resource lookup

The management screen initializes the search mode and clears the previously selected record/stage when the screen becomes visible.

```powerfx
Set(varSearchTab, "Enterprise");
Set(varStage, Blank());
Set(varSelectedUser, Blank());
```

The screen supports two search modes:

- Enterprise ID
- Onboarding date

Search input is stored in variables such as `varSearchUser` and `varSearchDate`. The app checks that the user has entered a search value before proceeding and uses `Notify()` to display a warning when the input is missing.

### 6.3 Forms and record submission

The app uses Power Apps Edit Forms and `SubmitForm()` for record submission.

Representative patterns from the source include:

```powerfx
SubmitForm(OnboardingForm1);
```

```powerfx
Notify(
    "Record submitted successfully",
    NotificationType.Success
);
```

```powerfx
Notify(
    "Submission failed. Please try again.",
    NotificationType.Error
);
```

The onboarding form's success handler captures the newly submitted SharePoint item ID and invokes the connected workflow.

### 6.4 Power Automate invocation

The source calls the connected flow using the enterprise ID, staffing status, item ID, supervisor and enterprise email values.

```powerfx
dev_CDPFlows.Run(
    DataCardValue28_2.Text,
    "YearlyTraining",
    vargalUser.ID,
    DataCardValue36.Text,
    DataCardValue25_2.Text
);
```

A separate roll-off path invokes the same flow with the `"Rolloff"` status. These examples are taken from the app source; control names are retained to show the implementation pattern.

### 6.5 Collections and variables

The inspected screen source uses global variables for UI state, search criteria, selected records and acknowledgement progress.

| Variable | Purpose inferred from usage |
|---|---|
| `varPrimaryColour` | Primary purple theme colour |
| `varSecondaryColour` | Secondary light accent colour |
| `varTertiaryColour` | Neutral background colour |
| `varSearchTab` | Selected resource search mode |
| `varSearchUser` | Enterprise ID search input |
| `varSearchDate` | Onboarding date search input |
| `varStage` | Selected lifecycle action/stage |
| `varSelectedUser` | Selected resource record |
| `vargalUser` | Resource record selected from the results gallery |
| `varShowPopup` | Popup visibility state |
| `varPage` | Current acknowledgement page |
| `varPage1Read` – `varPage4Read` | Acknowledgement page progress/read state |
| `varItemID` | Submitted record ID |

The supplied screen source does not establish a significant named collection-based data architecture; the primary record operations are form- and SharePoint-driven.

### 6.6 Component usage

The `.msapp` package contains multiple reusable header component definitions, including variants for branding, title display and header animation. The active screens reference reusable header components to keep the page header consistent.

The package also contains reusable layout containers, galleries, forms and standard Power Apps controls.

### 6.7 Delegation considerations

The SharePoint connector metadata identifies server-side filtering and sorting capabilities for supported fields. The app package also declares a default connected data source row limit of 2,000.

For production-scale use, validate:

- Whether the Enterprise ID and date search formulas remain delegable for the exact SharePoint columns used.
- Whether any searched or displayed columns are marked non-filterable by the connector metadata.
- Whether result galleries retrieve the expected records beyond the configured data row limit.
- Whether SharePoint list indexing is appropriate for the expected record volume.
- Whether repeated lookups or client-side filtering can be reduced.

The configured row limit does not, by itself, prove that every query retrieves all matching records.

### 6.8 Error handling and performance

The source demonstrates user feedback through `Notify()`, form success/failure handlers and required-input checks. The new request form includes a failure notification.

Before production deployment, validate connector failures, flow failures, duplicate submissions, incomplete records, attachment errors and permission-related failures. The complete flow definition was not supplied, so end-to-end retry and exception handling cannot be confirmed.

---

## 07. My Contribution

This section is written as a portfolio-ready contribution summary based on the application artefacts supplied. Adjust it if any part of the work was completed by another team member.

### Application design and development

- Designed and developed a multi-screen Power Apps Canvas application for employee and contractor lifecycle management.
- Structured the home screen to provide clear entry points for onboarding and existing resource management.
- Built the onboarding form and organized employee information, lifecycle dates and PMO submission details into logical sections.
- Developed resource search experiences using Enterprise ID and onboarding date.
- Implemented resource result presentation and lifecycle action entry points.
- Built guided client data protection and security acknowledgement screens with progress tracking and acceptance controls.
- Developed the roll-off acknowledgement journey.
- Created a structured new request form covering employee details, lifecycle status, audit history and attachments.
- Integrated SharePoint data sources and the connected Power Automate workflow.
- Used reusable header components and consistent colour styling to maintain a unified interface.

### Technical challenges and implementation decisions

| Challenge | Implementation approach |
|---|---|
| Multiple resource lookup methods | Separate search modes for Enterprise ID and onboarding date |
| Different lifecycle journeys | URL stage parameter and `Switch()`-based initial screen routing |
| Tracking the selected resource | Variables such as `varSelectedUser`, `vargalUser` and `varStage` |
| Guided policy acknowledgement | Page state and read/accept variables to manage progression |
| Consistent page layout | Reusable Canvas header components and shared styling variables |
| Workflow hand-off after record updates | Connected Power Automate flow invocation with resource and status details |
| Clear user feedback | `Notify()` messages and form success/failure handlers |

---

## 08. Project Files & Resources

### Repository structure

```text
Moon-CDP/
│
├── README.md
│
├── App/
│   └── APCDP.msapp
│
├── Screenshots/
│   ├── home-and-onboarding.png
│   ├── manage-user-search.png
│   ├── resource-details.png
│   ├── cdp-acknowledgement.png
│   ├── security-acknowledgement.png
│   ├── rolloff-acknowledgement.png
│   └── raise-new-request.png
│
└── Documentation/
    ├── application-overview.md
    └── architecture.md
```

### Included resources

| Resource | Description |
|---|---|
| `APCDP.msapp` | Original Power Apps Canvas App package supplied for this project |
| `APCDP.docx` | Application screenshot and reference document supplied for analysis |
| `README.md` | Project overview, features, architecture and implementation notes |
| `Screenshots/` | Recommended location for exported application screenshots |
| `Documentation/` | Optional location for supporting technical notes and architecture diagrams |

### Importing the Power App

1. Sign in to the Microsoft Power Apps maker portal.
2. Select the target environment.
3. Use the app import/open option for the `.msapp` Canvas App package.
4. Reconnect the required SharePoint and Office 365 connections.
5. Reconfigure the Power Automate flow connection and verify the target flow.
6. Confirm the SharePoint lists, columns, permissions and attachment settings.
7. Test onboarding, resource search, acknowledgement and roll-off journeys.
8. Publish only after validating the connections and end-to-end behaviour.

> The `.msapp` file contains connection references, not the external SharePoint lists or the complete cloud flow definition. A successful import therefore requires the target environment's data sources, connections and workflow to be configured.

---

## Power Apps Concepts Demonstrated

| Concept | Implementation in Moon CDP |
|---|---|
| Canvas App architecture | Multi-screen desktop/tablet Canvas App |
| Power Fx state management | `Set()` variables for search, selected records, stage and page state |
| Screen navigation | `Navigate()` and `Switch()`-based start-screen routing |
| URL parameters | `Param("stage")` and `Param("id")` for stage and record context |
| SharePoint integration | Connected resource and checklist data sources |
| Form processing | `SubmitForm()` with success and failure handlers |
| Search experience | Enterprise ID and date-based search modes |
| Conditional logic | `If()` and `Switch()` for validation and lifecycle routing |
| User feedback | `Notify()` for success, warning and error messages |
| Reusable components | Canvas header components |
| Workflow integration | Power Automate flow invocation through `.Run()` |
| File attachments | Attachments controls on request forms |

---

## Important Notes Before Publishing

- The screenshots and app package contain environment-specific configuration. Review all assets and metadata before making the repository public.
- The original connection metadata includes legacy tenant and internal resource identifiers. These are intentionally not reproduced in this README.
- Replace the placeholder screenshot paths with sanitized screenshots.
- Do not publish employee names, email addresses, enterprise IDs, internal policy content, tenant URLs, connection IDs or real resource records.
- Reconnect SharePoint and Power Automate dependencies in a development environment before testing the imported app.
- The supplied files do not establish production deployment status, a complete role-permission matrix or the full downstream Power Automate implementation.

---

## Author

**Power Platform Developer**

Project: **Moon CDP – Client Data Protection & Employee Lifecycle Management**

Technologies: Microsoft Power Apps | Power Fx | SharePoint Online | Power Automate | Office 365 Outlook

---

*This repository is intended to showcase Power Platform application design, lifecycle process automation, form development, data integration and workflow implementation.*
