# Developer Guide
Thank you for contributing to the development of java-linda source code!

Whether it's a small fix or a significant feature improvement, we greatly appreciate your contributions.

On GitHub, you can:

- Track issues
- Contribute code
- Suggest improvements
- Request new features
- Collaborate on maintaining documentation

If you plan to contribute to java-linda development, please follow the process below.



## Contribution Process Overview

1. **Fork the Repository**
    Fork the [java-linda repository](https://github.com/lindaprotocol/java-linda) to your personal account.
2. **Modify Code**
    Create a new branch based on the standard and start development.
3. **Submit Changes**
    Commit your changes with clear commit messages.
4. **Create a Pull Request (PR)**
    Push your changes to your forked repository and submit a PR to the official repository.
5. **Code Review and Merge**
    Maintainers will review your PR based on the [Code Review Guidelines](#code-review-guidelines) and merge it into the main branch if it meets the requirements.

## Submission Rules

- **Minor Fixes**
    You can directly submit a PR, but ensure it includes a complete description.
- **Complex Changes**
    Please first submit an Issue in the [LIP repository](https://github.com/lindaprotocol/tips), detailing the motivation and implementation plan.
Refer to the [LIP Specification](tips.md).
- **Early PR Submission**
    We encourage developers to submit PRs early, even if the feature is not yet complete. This allows other developers to know that the related LIP Issue has entered the *In Progress* state.
- **Development Branch**
    All development should be based on the `develop` branch, followed by a PR submission.

## Branch Management
The `java-linda` repository includes the following main branch types:

- **`develop` Branch**
    - Used for daily development
    - Only allows merging from forked branches and `release-*` branches
    - When preparing a new release, a `release-*` branch is created from this branch
- **`master` Branch**
    - Used only for releases
    - Only merges from `release-*` and `hotfix-*` branches
- **`release-*` Branch**
    - Created from `develop` for version finalization and regression testing
    - Merged into `master` branch after regression testing
    - Permanently retained as a release snapshot
    - Bug fixes are merged directly into this branch and synchronized back to `develop`
- **`feature-*` Branch**
    - Created from `develop` for new feature development
    - Merged back into `develop` after feature completion
    - Can be maintained long-term
- **`hotfix-*` Branch**
    - Created from `master` for urgent bug fixes
    - Merged back into both `master` and `develop` after fixes are complete

## Code Submission Process
### 1. Fork and Clone the Repository
```
git clone https://github.com/yourname/java-linda.git
cd java-linda
git remote add upstream https://github.com/lindaprotocol/java-linda.git
```
> `upstream` refers to the official repository. The name can be customized, but `upstream` is the conventional choice
### 2. Sync Upstream Code
```
git fetch upstream
git checkout develop
git merge upstream/develop --no-ff
```
> `--no-ff` avoids fast-forward merges to ensure a clear commit history.
### 3. Create a Development Branch
```
git checkout -b feature/branch_name develop
```
### 4. Commit Changes
```
git add .
git commit -m "commit message"
```
### 5. Push the Branch
```
git push origin feature/branch_name
```
### 6. Create a Pull Request
From your own repository, submit a Pull Request (PR) to `lindaprotocol/java-linda`.
   ![image](https://raw.githubusercontent.com/lindaprotocol/documentation-zh/master/images/javalinda_pr.png)
It’s recommended to select the options in the red box, setting `develop` branch of the `lindaprotocol/java-linda` as the base branch and your forked repository’s branch as the compare branch.

## Code Review Guidelines
The only way to merge code into **java-linda** is through **a Pull Request (PR)**.
All PRs must be reviewed before merging.

### Review Process
- Reviewers must understand the motivation and changes of the PR.
- For PRs lacking descriptions or with excessive changes, reviewers may request additional clarification.
- Reviewers check code style, feature completeness, and test coverage.
- Reviewers should remain polite, respectful, and follow up promptly.

### Feature Validation
- **Bug Fix PRs**
    - Reviewers should attempt to reproduce the issue and verify the fix.
    - It’s recommended that submitters provide unit tests that fail before the fix and pass after.
- **New Feature PRs**
    - Reviewers should test the new feature and provide feedback.
    - All new code must include unit tests.

### Code Specification Requirements

- Use code formatting tools to check code.
- Self-test before submission.
- Pass standardized tests.

CI Tools:

- Sonar: Static code analysis
- Travis CI: Continuous integration checks

Once all checks pass, maintainers will review and merge into `develop`.

> **Coding Standards**
>- Follow the [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)
>- All PRs must be based on the `develop` branch

## Branch Naming Conventions

1. `master` and `develop` are fixed names.
2. Version development branches are named by version number and version name (e.g., `GreatVoyage-v4.8.0(Kant)`).
3. `hotfix/*`: For urgent fixes ( e.g., `hotfix/typo`).
4. `feature/*`: For new feature development (e.g., `feature/new-resource-model`).

## Pull Request Specifications

1. One PR should address a single issue.
2. Avoid excessively large changes.
3. Title: Briefly describe the PR’s purpose.
4. Description: Provide detailed information for reviewers.
5. Specify areas where feedback is needed.

## Commit Message Specifications
Recommended format:

```
<type>(<scope>): <subject>

<body>

<footer>
```
### Commit Types

- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Formatting changes (no functional changes)
- `refactor`: Code refactoring
- `test`: Test code changes
- `chore`: Other (e.g., task assignments)

### Subject Specifications

1. Maximum 50 characters.
2. Start with a verb in the first-person present tense (e.g., `change`, not `changed`).
3. Start with a lowercase letter.
4. No period at the end.
5. Avoid meaningless commits.

Example:
```
feat(block): optimize the block-producing logic

1. increase the priority for acquiring synchronization lock
2. add interruption exception handling in block-producing thread

Closes #1234
```

## Handling Special Cases

- **Submitter Not Following Up**
    - Contact after a few days; if no response, the PR may be closed or continued by others.
- **Submitter Refactoring While Fixing Bugs**
    - Small-scale refactoring is acceptable.
    - Large-scale changes should be split into separate PRs or at least separate commits.
- **Submitter Rejects Feedback**
    - Reviewers may close the PR.

## Conduct
Please maintain respect and constructiveness to foster a positive community atmosphere.
