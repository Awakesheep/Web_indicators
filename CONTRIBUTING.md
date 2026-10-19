# Workflow

Every change follows the same path, so the history explains itself.

1. **Issue first.** Open an issue with the *Bug / incident* template: actual vs expected, reproduction, impact, evidence.
   Problems found while working get their own issue too (never a silent fix).
2. **Diagnose before fixing.** Reproduce it, then add a comment to the issue: **Root cause** (with the evidence) and the
   **planned fix**.
3. **Branch:** `fix/<issue>-<slug>` (features: `feat/<issue>-<slug>`). Never commit fixes straight to `main`.
4. **Commits:** [Conventional Commits](https://www.conventionalcommits.org): `fix(component): short summary (#N)`.
   Small, one purpose each. Run the linters CI runs (see the CI workflow) before pushing.
5. **Pull request** using the template: Problem · Root cause · Fix · Verification · Risk/rollback · Follow-ups, with `Fixes #N`.
6. **CI must be green.** A red run is an incident: issue + fix before merging.
7. **Squash-merge** (one commit per fix on `main`; the PR title is the commit message). Deploy and verify live.
8. **Close with a resolution comment** (posted by the PR merge or by hand): what was deployed, live verification result,
   and links to follow-up issues. Changes outside git (VM scripts, database repairs) are recorded in this comment with the
   backup file names.
