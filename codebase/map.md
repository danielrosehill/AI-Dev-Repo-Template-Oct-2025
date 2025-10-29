# Directory Map For: Codebase

This is the base level for the repository code. All project code should be created within this directory structure.

**Important**: No code for the project should ever be created at the project base or above this level. This maintains a clear separation between code and project management/documentation files.

## Structure

- **tests/**: All testing-related code and resources
  - **unit/**: Unit tests for individual functions and modules
  - **integration/**: Integration tests for component interactions
  - **e2e/**: End-to-end tests for complete user workflows
  - **fixtures/**: Test fixtures and static test data
  - **mocks/**: Mock implementations for testing dependencies 