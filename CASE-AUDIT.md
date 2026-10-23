# GitHub Profile README case audit

## Scope

The source is the case index in [abhisheknaiidu/awesome-github-profile-readme](https://github.com/abhisheknaiidu/awesome-github-profile-readme) at commit `a2f2de46099a6d503d9240d8f90b4f504755b27f`. Its `Categories` section contains 193 category entries across 16 categories and 191 unique profile cases. The index itself is CC0-1.0, while every linked profile repository remains an independent work whose license must be checked before copying content.

## Indexed categories

| Category | Indexed cases | Direct-reuse implications |
| --- | ---: | --- |
| GitHub Actions 🤖 | 31 | Requires workflow and permission review; unsuitable for the zero-dependency draft. |
| Game Mode 🚀 | 8 | Usually needs generated assets or interactive logic; unsuitable for a factual minimum. |
| Code Mode 👨🏽‍💻 | 8 | Mostly presentational, but often embeds code-shaped personal claims. |
| Dynamic Realtime 💫 | 16 | Depends on APIs, Actions, or generated images; intentionally excluded. |
| A Little Bit of Everything 😃 | 20 | Combines many fields and services; would require unverified personal details. |
| Descriptive 🗒 | 10 | Text-first, but depends on biography, skills, or experience that are not public here. |
| Simple but Innovative Ones 🤗 | 25 | Visually simple but may still use custom layout, assets, or external services. |
| Typing.. Mode 🎰 | 6 | Usually depends on animated SVG services; intentionally excluded. |
| Anime 👾 | 4 | Relies on visual assets; outside the zero-fiction minimum. |
| Minimalistic ✨ | 19 | Best source category for a static identity-and-link structure. |
| GIFS 👻 | 20 | Relies on animated assets; intentionally excluded. |
| Just Images 🎭 | 6 | Relies primarily on image assets; intentionally excluded. |
| Badges 🎫 | 11 | Relies on third-party badge endpoints and often encodes unverified skills. |
| Fancy Fonts 🖋 | 1 | Uses presentation assets or special typography; unnecessary here. |
| Icons 🎯 | 6 | Adds icon assets and often social links not present on the account. |
| Retro 😎 | 2 | Strong custom presentation rather than a neutral factual profile. |

## Audited candidates

| Case | Source category | Current dependency profile | Audit conclusion |
| --- | --- | --- | --- |
| [Bilivro](https://github.com/bilivro/bilivro) | Minimalistic ✨ | Plain Markdown, one external website link, no images, badges, Actions, or dynamic API. No repository license detected. | Retained as an audit candidate only, showing that basic static Markdown is feasible. It was not adopted as a template, and no wording was copied. |
| [Alex Martin](https://github.com/AlexMartinFR/AlexMartinFR) | Minimalistic ✨ | Plain Markdown and text links, no dynamic images or Actions; includes extensive personal narrative and an ASCII-style table. No repository license detected. | Technically reusable as a text-only pattern, but it needs biography and interests that are not verified for this account. |
| [Caneco](https://github.com/caneco/caneco) | Minimalistic ✨ | Plain headings, lists, and text links with no dynamic image service; repository reports an MIT license. | Legally clearer than most linked cases, but its role, tools, communities, and projects would all require personal facts that are unavailable. |
| [Gift Egwuenu](https://github.com/lauragift21/lauragift21) | Minimalistic ✨ | Markdown/HTML text and direct social links, no dynamic image service or Action. No repository license detected. | Its centered identity-and-links structure is reusable in principle, but the account has no verified social/contact fields to populate. |
| [ChungZH](https://github.com/ChungZH/ChungZH) | Minimalistic ✨ | The indexed link now resolves to `Zirnc/Zirnc`; the README contains a third-party dynamic Telegram badge. No repository license detected. | Rejected because the index target has drifted and the badge adds an unnecessary external dependency. |

## Audit conclusion

The Bilivro case is a restrained audit candidate because it demonstrates that a profile can use basic static Markdown without dynamic dependencies. It is evidence of technical feasibility only. The local `README.md` was independently written and does not adopt, combine, replace, or stand in for any indexed case; its visible content is limited to `Amor.`, `iStarrySummer`, and the user-authorized blog deployment URL `https://iStarrySummer.github.io/`. It introduces no badges, statistics, skills, employment, location, biography, contact method, image, animation, or automation.

## Verified facts and boundary

The public GitHub API returned login `iStarrySummer`, numeric user ID `223387801`, display name `Amor.`, and empty/null values for bio, blog, location, and company, with zero public repositories at verification time. The private repository named elsewhere in the task was not opened, inspected, summarized, or used. The blog URL is separately authorized by the user and is not an API-derived account field. The required publication order is to complete and verify `https://iStarrySummer.github.io/` first, then create the Profile repository `iStarrySummer/iStarrySummer`.
