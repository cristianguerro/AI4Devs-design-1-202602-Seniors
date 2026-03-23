---
description: "Generates a commit message following the Conventional Commits standard based on the current changes."
---

# Conventional Commit Message Generator

Please review the current staged or unstaged Git changes and generate a commit message that adheres strictly to the [Conventional Commits](https://www.conventionalcommits.org/) specification.

## Guidelines:

1.  **Format:** `<type>[optional scope]: <description>`
2.  **Types:**
    - `feat`: A new feature
    - `fix`: A bug fix
    - `docs`: Documentation only changes
    - `style`: Changes that do not affect the meaning of the code (whitespace, formatting, etc)
    - `refactor`: A code change that neither fixes a bug nor adds a feature
    - `perf`: A code change that improves performance
    - `test`: Adding missing tests or correcting existing tests
    - `chore`: Changes to the build process or auxiliary tools and libraries
    - `ci`: Changes to CI configuration files and scripts
3.  **Scope:** Optional, but should provide context on what part of the codebase the commit modifies (e.g., `api`, `ui`, `auth`).
4.  **Description:**
    - Use the imperative, present tense: "change" not "changed" nor "changes".
    - Don't capitalize the first letter.
    - No dot (.) at the end.
5.  **Body (Optional):** Provide detailed explanations of _what_ and _why_ rather than _how_, if the description is not sufficient. Wrap at 72 characters.
6.  **Footer (Optional):** Reference any issue tracker IDs (e.g., `Fixes #123`) or list `BREAKING CHANGE: <description>`.

Generate the commit message only. Do not include introductory text or explanations outside of the commit message itself.
