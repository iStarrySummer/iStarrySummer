# iStarrySummer GitHub Profile README Design

## Intent

Rebuild the visible GitHub profile README for `iStarrySummer` using the presentation language of the selected reference, `xiaoluoboding/xiaoluoboding`, while publishing only facts that are publicly verifiable or explicitly authorized by the user. The result should feel recognizably related to the selected case without copying Robert Shaw's biography, accounts, projects, skills, or prose.

## Goals

- Keep the reference's visual sequence: stylized Unicode identity heading, flat-square link badges, a Bookmark Style project card, and a Dracula-themed GitHub statistics card.
- Use only the verified identity `Amor.`, GitHub login `iStarrySummer`, the user-authorized blog URL `https://iStarrySummer.github.io/`, and the public repository `iStarrySummer/iStarrySummer.github.io`.
- Make every visible badge, card, and link resolve to the user's own public resource.
- Preserve a clear attribution and licensing record without implying that the unlicensed reference repository was copied or relicensed.
- Verify the final README through GitHub's real rendered profile page in a browser at desktop and narrow viewport widths.

## Non-goals and anti-goals

The implementation will not invent biography, employment, location, contact methods, social accounts, interests, technologies, or projects. It will not copy Robert Shaw's wording, name, Twitter, CodePen, CodeSandbox, personal site, four project cards, or 28 technology badges. It will not add GitHub Actions, generated local assets, JavaScript, dependencies, new animations, or any section that requires private data. It will not inspect or use any private repository. A result that looks fuller by inserting placeholders or unverified claims is considered a failure.

## Constraints

The profile repository is `https://github.com/iStarrySummer/iStarrySummer`, with local checkout at `/Users/a1/Documents/Codex/2026-10-23/github-1-fuwari-https-github-com/work/profile-readme`. Remote writes must use the local `gh` identity `iStarrySummer` and the existing HTTPS remote. The selected reference is fixed at commit `6ba5426db6a2680addff1e90691dbdbd33a21f31`; it has no detected license, so only general layout ideas and third-party service conventions may be followed. External image requests are limited to `img.shields.io`, `svg.bookmark.style`, and `github-readme-stats.vercel.app`, which were reachable during the source audit. The README must remain valid GitHub Flavored Markdown and must not require a build step.

## Approaches considered

### 1. Strict verified profile — selected

Keep the reference's visual vocabulary but reduce its content to verified material: a stylized `Hello, I'm Amor.` heading, GitHub and blog badges, one `Currently working on` card for `iStarrySummer/iStarrySummer.github.io`, and a Dracula-themed statistics card for `iStarrySummer`. Omit the personal-introduction and tech-stack blocks because the available public data does not support them. This preserves the strongest recognizable effects while keeping every claim true.

### 2. Complete skeleton with placeholders

Retain every reference section and show `Not public` or `To be added` where facts are unavailable. This would match the source's section count more closely, but it would make the public profile look unfinished and add content the user did not provide.

### 3. Wait for reproduction permission and more profile data

Do not publish until the reference author grants copying permission and the user supplies a biography, social links, and skill claims. This could eventually produce the closest content density, but it blocks a useful verified profile now and is unnecessary for reproducing the public visual pattern.

## Visible design

The first line will be a level-one heading rendered with the same class of italic mathematical Unicode characters as the reference and will read `Hello, I'm Amor.`. Immediately below it, two flat-square Shields.io badges will link to the user's GitHub profile and blog. The GitHub badge will use GitHub's dark styling; the website badge will use Shields.io's website-status endpoint and display `iStarrySummer.github.io` when available.

The next visible section will use the reference's stylized bold Unicode heading corresponding to `Currently working on`. It will contain one horizontal Bookmark Style card whose target and card source are both the public blog repository. A final stylized `Stats` section will embed GitHub Readme Stats with `username=iStarrySummer`, icons enabled, and the same `dracula` theme used by the reference. If a third-party image service is temporarily unavailable, the image's alt text and surrounding link must still identify the destination accurately.

No visible personal paragraph or `My Tech Stack` heading will be present. Omitting those sections is intentional: the profile should be content-dense only where the account supplies evidence, rather than filling the reference's space with assumptions.

## Repository documentation and licensing

`ATTRIBUTION.md` will identify the selected reference repository and pinned commit, state that no license was detected there, enumerate the presentation ideas followed, and state that no author-specific prose or assets were copied. `CASE-AUDIT.md` will be updated so its conclusion records `xiaoluoboding/xiaoluoboding` as the user-selected case and reflects the current public repository facts.

The root `LICENSE` currently contains the Awesome GitHub Profile README index's CC0 text, which could be misread as licensing this profile repository. It will be moved unchanged to `THIRD_PARTY_NOTICES/awesome-github-profile-readme-CC0-1.0.txt`. This preserves the original license text while making its third-party scope explicit; no new license will be assigned to the user's profile content.

## Validation and delivery

Before committing, automated checks will confirm that `README.md` contains only the approved identity, URLs, repository, and service endpoints; that it contains none of the reference author's identity, social accounts, projects, or technology claims; and that every embedded HTTPS resource responds successfully. After pushing, the real GitHub profile at `https://github.com/iStarrySummer` will be opened in a browser and checked for heading rendering, badge and card loading, link targets, statistics rendering, desktop layout, and narrow/mobile reflow. The delivered record will include the commit identifier, local directory, public URL, comparison result, and the intentional differences caused by the verified-data and licensing constraints.

## Builder discretion

The builder may choose URL-encoding details, descriptive alt text, and the exact line wrapping that GitHub Markdown produces, provided these choices do not change the visible content, introduce new claims, or alter the selected services and theme.
