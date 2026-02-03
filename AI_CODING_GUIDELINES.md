# AI Coding Guidelines for Komorebi

This document outlines the coding standards, workflows, and principles for AI agents and developers working on the Komorebi project.

## 1. Technology Stack

*   **Language**: Dart (Latest Stable)
*   **Framework**: Flutter (Frontend) & Serverpod (Backend)
*   **Architecture**: Client-Server model using Serverpod.
    *   `komorebi_server`: Backend logic, endpoints, and database management.
    *   `komorebi_client`: Generated client library (DO NOT EDIT MANUALLY).
    *   `komorebi_flutter`: Flutter frontend application.

## 2. Clean Code Principles

*   **SOLID**: Adhere to SOLID principles for object-oriented design.
*   **DRY (Don't Repeat Yourself)**: Extract common logic into reusable functions or widgets.
*   **KISS (Keep It Simple, Stupid)**: Avoid over-engineering. Write code that is easy to read and maintain.
*   **Naming Conventions**:
    *   Classes: `PascalCase`
    *   Variables/Functions: `camelCase`
    *   Files: `snake_case`
    *   Constants: `SCREAMING_SNAKE_CASE`

## 3. Testing Strategy

All features and bug fixes must include appropriate tests.

*   **Unit Tests**:
    *   Required for all business logic in `komorebi_server` and `komorebi_flutter`.
    *   Mock dependencies to ensure isolation.
*   **Widget Tests**:
    *   Required for all new Flutter widgets and screens.
    *   Verify UI rendering and user interactions.
*   **Execution**:
    *   Run tests *before* finishing any iteration to ensure no regressions.
    *   Command: `dart test` (Backend/Logic) or `flutter test` (Frontend).

## 4. Workflow & Iteration

1.  **Plan**: Analyze the requirement and identify necessary changes in `server` and `flutter` directories.
2.  **Code**: Implement the changes following Clean Code principles.
3.  **Review**: Self-review code against these guidelines.
4.  **Test**: Run existing tests and add new ones to verify the changes.
5.  **Commit**: Create a commit *for each iteration* or logical unit of work. Do not bundle unrelated changes.

## 5. File Structure & Boundaries

*   **Backend (`komorebi_server`)**:
    *   Endpoints go in `lib/src/endpoints/`.
    *   Models go in `lib/src/models/`.
    *   Run `serverpod generate` after modifying models or endpoints.
*   **Frontend (`komorebi_flutter`)**:
    *   UI code in `lib/ui/`.
    *   State management logic separated from UI widgets.

## 6. Pre-Finish Checklist

Before declaring a task complete:
- [ ] Code follows Clean Code principles?
- [ ] `serverpod generate` run (if backend changed)?
- [ ] Unit tests passed?
- [ ] Widget tests passed?
- [ ] Code committed?
