# Vaccine Assistant

A JavaFX desktop application for managing personal vaccination records and dose schedules. The project brings account access, vaccine information, and dose-progress tracking into a form-based interface backed by local XML persistence.

## Core workflow

Create or sign into an account, open the dashboard, inspect vaccine records, and record vaccination progress. The domain model associates vaccines with disease names, dose counts, age-related fields, intervals between doses, dates, and current dose status.

## Architecture

```text
JavaFX views and controllers
            |
     Account / Vaccine models
            |
       ListOfAccounts
            |
   XMLDecoder / XMLEncoder
            |
       Database.xml
```

## Project map

| Component | Responsibility |
| --- | --- |
| `src/mainPackage/MainClass.java` | JavaFX application entry point |
| `SignIn`, `SignUp`, `Password` | Account-access forms and interactions |
| `Dashboard` | Main account view |
| `Vaccine` | Vaccine attributes, timing, and dose-progress state |
| `VaccineController` | Vaccine-form interactions and record updates |
| `MainDatabase`, `ListOfAccounts` | Database access and account collection |
| `Database.xml` | JavaBean-encoded local data |

FXML layouts, CSS, and image resources accompany the controllers in `src/`.

## Run

Import the repository as a Java project with a JDK and JavaFX controls/FXML configured. Mark `src/` as the source root, include its resources on the runtime classpath, and launch `mainPackage.MainClass` from the repository root. The application resolves its local database from `Database.xml`.

Use the account screens to reach the dashboard and vaccine forms. Record updates are serialized through Java's XML encoding facilities, connecting the UI state to persistent account and vaccine objects.

## Technical contributions

The implementation demonstrates a stateful desktop workflow, separation of data models from FXML views, dose-sequence representation, and XML-backed persistence using standard JavaBean encoding APIs.
