# iStarrySummer GitHub Profile README Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Publish a verified-data-only `iStarrySummer` GitHub profile README that follows the selected `xiaoluoboding/xiaoluoboding` presentation pattern without copying its author-specific content.

**Architecture:** Keep the implementation as GitHub Flavored Markdown with remote image endpoints and no build system. Separate the visible profile in `README.md` from provenance and licensing records in `ATTRIBUTION.md`, `CASE-AUDIT.md`, and `THIRD_PARTY_NOTICES/`, then validate both source constraints and the rendered GitHub profile before delivery.

**Tech Stack:** GitHub Flavored Markdown, Shields.io, Bookmark Style, GitHub Readme Stats, Git, GitHub CLI, real browser rendering

**Spec:** `docs/superpowers/specs/2026-10-24-xiaoluoboding-profile-design.md`

## Global Constraints

- Publish only the verified identity `Amor.`, GitHub login `iStarrySummer`, user-authorized blog URL `https://iStarrySummer.github.io/`, and public repository `iStarrySummer/iStarrySummer.github.io`.
- Never inspect or use private repositories.
- Do not publish biography, employment, location, other social accounts, interests, technologies, or project claims that are not verified.
- Do not copy Robert Shaw's author-specific wording, identity, social accounts, project list, or technology badges.
- Use only `img.shields.io`, `svg.bookmark.style`, and `github-readme-stats.vercel.app` for remote images; add no packages, workflows, scripts, JavaScript, or generated assets.
- Preserve the Awesome GitHub Profile README CC0 license text as a third-party notice, not as the root license for this profile repository.
- Before any remote write, `gh api user --jq .login` must return exactly `iStarrySummer`, and the push remote must remain the existing HTTPS URL `https://github.com/iStarrySummer/iStarrySummer.git`.
- The final acceptance target is the real profile page `https://github.com/iStarrySummer`, not a locally generated screenshot.

## Review Focus

- A missing or slow remote image service must leave accurate alt text and clickable destinations instead of creating a misleading blank element; Task 2 source assertions and Task 3 browser checks cover this.
- Unicode mathematical characters must remain intact after Git commit, push, and GitHub rendering; Task 2 UTF-8 assertions and Task 3 rendered-heading checks cover this.
- The website badge must target the authorized blog URL even if the blog status endpoint reports an error; Task 2 link assertions and Task 3 click-target checks cover this.
- The profile must not inherit the Awesome index's CC0 license by accident; Task 1 root-license absence and third-party-notice identity checks cover this.
- A transient GitHub Readme Stats failure must not be mistaken for a source defect; Task 3 checks the endpoint separately and records external-service status without rewriting the design.

---

### Task 1: Correct provenance and third-party license scope

**Files:**

- Create: `docs/superpowers/specs/2026-10-24-xiaoluoboding-profile-design.md`
- Create: `docs/superpowers/plans/2026-10-24-xiaoluoboding-profile.md`
- Modify: `ATTRIBUTION.md`
- Modify: `CASE-AUDIT.md`
- Move: `LICENSE` → `THIRD_PARTY_NOTICES/awesome-github-profile-readme-CC0-1.0.txt`

**Interfaces:**

- Consumes: The pinned reference commit `6ba5426db6a2680addff1e90691dbdbd33a21f31`, the selected-design spec, the existing Awesome index audit, and current public GitHub metadata.
- Produces: A provenance record that Task 2 can cite and a repository layout that cannot imply CC0 licensing of the user's profile content.

- [ ] **Step 1: Run pre-change assertions and confirm the current documentation is stale**

  Run `test -f LICENSE && ! rg -q 'xiaoluoboding/xiaoluoboding' ATTRIBUTION.md`.

  Expected: exit status `0`, proving that the root CC0 file exists and the selected reference has not yet been documented.

- [ ] **Step 2: Move the unchanged CC0 license into third-party notices**

  Create `THIRD_PARTY_NOTICES/` and move the existing `LICENSE` verbatim to `THIRD_PARTY_NOTICES/awesome-github-profile-readme-CC0-1.0.txt`; do not create a replacement root license.

- [ ] **Step 3: Rewrite `ATTRIBUTION.md` around the selected case**

  Record the Awesome index commit, `xiaoluoboding/xiaoluoboding` commit `6ba5426db6a2680addff1e90691dbdbd33a21f31`, the absence of a detected license in that repository, the presentation conventions followed, the user-specific substitutions, and the explicit non-copying boundary.

- [ ] **Step 4: Update `CASE-AUDIT.md` with current facts and final selection**

  Retain the useful index-scope explanation, add the selected case as the final choice, replace the stale zero-public-repositories statement with the verified two-repository state, and identify only `iStarrySummer/iStarrySummer` and `iStarrySummer/iStarrySummer.github.io`.

- [ ] **Step 5: Verify provenance and licensing invariants**

  Run `test ! -e LICENSE && cmp THIRD_PARTY_NOTICES/awesome-github-profile-readme-CC0-1.0.txt <(git show 946e97207547961cd82876f1fc46b9bcdde0908f:LICENSE) && rg -q 'xiaoluoboding/xiaoluoboding' ATTRIBUTION.md && rg -q '6ba5426db6a2680addff1e90691dbdbd33a21f31' ATTRIBUTION.md && rg -q 'no license|No license|no detected license' ATTRIBUTION.md && rg -q 'iStarrySummer/iStarrySummer.github.io' CASE-AUDIT.md`.

  Expected: exit status `0`; the notice is byte-for-byte unchanged, and the required provenance facts are present.

- [ ] **Step 6: Review the diff and commit the documentation change**

  Run `git diff --check && git diff -- ATTRIBUTION.md CASE-AUDIT.md LICENSE THIRD_PARTY_NOTICES/awesome-github-profile-readme-CC0-1.0.txt`.

  Expected: no whitespace errors; the diff changes only provenance facts and license placement.

  Commit with `git add ATTRIBUTION.md CASE-AUDIT.md LICENSE THIRD_PARTY_NOTICES/awesome-github-profile-readme-CC0-1.0.txt docs/superpowers/specs/2026-10-24-xiaoluoboding-profile-design.md docs/superpowers/plans/2026-10-24-xiaoluoboding-profile.md && git commit -m "docs: record selected profile reference"`.

### Task 2: Implement the verified visual profile

**Files:**

- Modify: `README.md`

**Interfaces:**

- Consumes: The visible-design section of the spec and the provenance boundaries produced by Task 1.
- Produces: A standalone GitHub-renderable README with two badges, one project card, and one statistics card for Task 3 to validate live.

- [ ] **Step 1: Run a pre-change content check and confirm the selected visual structure is absent**

  Run `! rg -q 'svg\.bookmark\.style|github-readme-stats\.vercel\.app|𝙃𝙚𝙡𝙡𝙤' README.md`.

  Expected: exit status `0`, confirming that none of the required rendered components is present yet.

- [ ] **Step 2: Replace `README.md` with the selected verified-data structure**

  Add a stylized level-one `Hello, I'm Amor.` heading; a flat-square GitHub badge linked to `https://github.com/iStarrySummer`; a flat-square website-status badge linked to `https://iStarrySummer.github.io/`; a stylized `Currently working on` heading and one horizontal Bookmark Style card targeting `https://github.com/iStarrySummer/iStarrySummer.github.io`; and a stylized `Stats` heading with `https://github-readme-stats.vercel.app/api?username=iStarrySummer&show_icons=true&theme=dracula`.

  Give every image descriptive alt text. Do not add a biography paragraph, `My Tech Stack`, placeholders, or any other section.

- [ ] **Step 3: Assert the exact approved identifiers, endpoints, and Unicode content**

  Run `rg -q '^# 𝙃𝙚𝙡𝙡𝙤' README.md && rg -q 'https://github.com/iStarrySummer' README.md && rg -q 'https://iStarrySummer.github.io/' README.md && rg -q 'https://github.com/iStarrySummer/iStarrySummer.github.io' README.md && rg -q 'username=iStarrySummer&show_icons=true&theme=dracula' README.md`.

  Expected: exit status `0`.

- [ ] **Step 4: Assert that prohibited reference-specific content and unsupported sections are absent**

  Run `! rg -i 'Robert Shaw|robert_shaw|xiaoluoboding|CodePen|CodeSandbox|Vue\.js|Swift|Coffee|Agave|My Tech Stack|temporarily unavailable|to be added|待补充' README.md`.

  Expected: exit status `0`.

- [ ] **Step 5: Check the README surface area and Markdown links**

  Run `test "$(rg -o 'https://img\.shields\.io[^)]+' README.md | wc -l | tr -d ' ')" = 2 && test "$(rg -o 'https://svg\.bookmark\.style[^)]+' README.md | wc -l | tr -d ' ')" = 1 && test "$(rg -o 'https://github-readme-stats\.vercel\.app[^)]+' README.md | wc -l | tr -d ' ')" = 1 && test "$(rg -c '^## ' README.md)" = 2 && test "$(rg -c '\[!\[[^]]+\]\(' README.md)" = 3 && test "$(rg -c '^!\[[^]]+\]\(' README.md)" = 1`.

  Expected: exit status `0`, proving the README has exactly the selected two section headings, four remote image components, and non-empty alt text for every image.

- [ ] **Step 6: Review the diff and commit the visible profile**

  Run `git diff --check && git diff -- README.md`.

  Expected: no whitespace errors and no content outside the approved design.

  Commit with `git add README.md && git commit -m "feat: add verified GitHub profile cards"`.

### Task 3: Verify external services, render on GitHub, and publish

**Files:**

- Modify only if verification finds a source defect: `README.md`, `ATTRIBUTION.md`, or `CASE-AUDIT.md`
- Record user-facing results outside the repository: `/Users/a1/Documents/Codex/2026-10-23/github-1-fuwari-https-github-com/outputs/xiaoluoboding-profile-verification.md`

**Interfaces:**

- Consumes: Task 2's committed README, the repository's HTTPS remote, and the three approved third-party image services.
- Produces: A pushed GitHub profile, real-browser acceptance evidence, and a concise delivery record.

- [ ] **Step 1: Re-run all source and repository checks from a clean worktree**

  Run the Task 1 Step 5 and Task 2 Steps 3–5 commands, then run `git diff --check && test -z "$(git status --porcelain)"`.

  Expected: every command exits `0`, and the worktree is clean.

- [ ] **Step 2: Check the approved remote image endpoints independently**

  Extract the two Shields.io image URLs, the Bookmark Style URL, and the GitHub Readme Stats URL from `README.md`; request each with redirects enabled and record the final HTTP status and content type.

  Expected: each returns HTTP `200` and an image content type. If a service is transiently unavailable, retry once and record the outage without redesigning the README.

- [ ] **Step 3: Verify authenticated GitHub identity and push path immediately before writing**

  Run `test "$(gh api user --jq .login)" = iStarrySummer && test "$(git remote get-url --push github)" = https://github.com/iStarrySummer/iStarrySummer.git`.

  Expected: exit status `0`. Any mismatch stops the push; do not switch accounts or remotes.

- [ ] **Step 4: Push the reviewed commits**

  Run `git push github main`.

  Expected: the remote `main` branch advances to the local `HEAD` without rewriting history.

- [ ] **Step 5: Verify remote source identity**

  Run `test "$(gh api repos/iStarrySummer/iStarrySummer/commits/main --jq .sha)" = "$(git rev-parse HEAD)"` and fetch the public `README.md` through the GitHub API for comparison with the local file.

  Expected: the remote SHA equals local `HEAD`, and the decoded remote README is byte-for-byte identical to local `README.md`.

- [ ] **Step 6: Inspect the real GitHub-rendered profile at desktop width**

  Open `https://github.com/iStarrySummer` in a real browser. Confirm the stylized identity heading is readable; both badges render and link to the correct GitHub and blog destinations; the single Bookmark Style card renders and targets the blog repository; the Dracula statistics card renders for `iStarrySummer`; and no bio, unsupported social account, tech stack, or reference-author content appears.

  Expected: all visible elements match the approved design and every clickable target is correct.

- [ ] **Step 7: Inspect the same live profile at a narrow/mobile viewport**

  Resize the real browser to a narrow mobile viewport and confirm badges wrap without clipping, the project and statistics cards scale or scroll according to GitHub's native README renderer, text stays readable, and no component overlaps another.

  Expected: GitHub's native responsive layout presents all components without loss of information.

- [ ] **Step 8: Write the verification record**

  Create `/Users/a1/Documents/Codex/2026-10-23/github-1-fuwari-https-github-com/outputs/xiaoluoboding-profile-verification.md` containing the local directory, remote repository and profile URLs, source and final commit SHAs, source-reference commit, exact intentional differences from the reference, endpoint results, desktop/mobile browser results, and every necessary source/documentation change with its reason.

- [ ] **Step 9: Perform final whole-change review**

  Compare `git diff 946e97207547961cd82876f1fc46b9bcdde0908f..HEAD`, the design spec, the implementation plan, and the live GitHub profile. Confirm that every design goal is met, no non-goal slipped in, and all reported evidence matches the current remote state.

  Expected: no unresolved discrepancy remains; otherwise fix the smallest source defect, commit it, push again after rechecking identity, and repeat Steps 5–9.
