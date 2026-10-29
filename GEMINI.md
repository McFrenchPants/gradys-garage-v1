# Agent Instructions & Workflow Rules

## 1. Automated Testing & Verification
- Prior to finalizing any changes, always test and confirm the modifications:
  - **Static Web Files (HTML, CSS, JS):** Validate markup syntax, ensure all internal asset and image paths exist and resolve properly, check responsive layout integrity, and ensure zero broken links.
  - **Documentation & Configuration:** Verify Markdown formatting, links, and operational guides.
  - **Code & Builds:** Run any available linting, syntax validation, or build commands before concluding.

## 2. Automated Git Commit & Push
- Every task that modifies files in the repository must automatically be committed and pushed to the remote repository upon verification:
  1. Verify working directory status (`git status`).
  2. Stage the relevant modified/added files (`git add ...`).
  3. Create a clear, conventional commit message (`git commit -m "..."`).
  4. Push directly to the remote repository (`git push origin <current-branch>`).
  5. Confirm push success and report the commit hash and status to the user.
