# AGENTS.md

This repository is a layered knowledge base for emergent embodied AI, serving learning, research, and practice. Agents working here should organize knowledge by technical links in an embodied AI system, not as an undifferentiated link dump.

## Audience

The repository should support multiple reader levels:

- Newcomers who need a clear map of robotics, embodied AI, robot learning, VLA, simulation, control, hardware, and deployment.
- Intermediate readers who want to connect concepts, papers, systems, and implementation choices.
- Advanced readers who want frontier tracking, route analysis, case studies, and research judgment.

Write so that each level can get value:

- Start with the problem each topic solves.
- Prefer concrete examples over abstract claims.
- Explain acronyms before using them heavily.
- Separate facts, interpretations, and open questions.
- Avoid assuming the reader already knows robotics jargon.
- Include deeper tradeoffs, failure modes, and open research questions when useful.

## Repository Structure

Use the existing technical-link structure:

- `00-start-here/`: entry points, scope, principles, language policy, maintenance.
- `01-system-overview/`: full system loop, stack overview, capability ladder.
- `02-perception/`: vision, depth, point cloud, tactile, proprioception, multimodal understanding.
- `03-representation/`: state, scene, object, spatial, action, and world-model representations.
- `04-data/`: robot data sources, teleoperation, datasets, human videos, data quality.
- `05-policy-learning/`: behavior cloning, imitation learning, RL, offline RL, diffusion policy, VLA.
- `06-planning-and-control/`: task planning, motion planning, skills, low-level control, recovery.
- `07-simulation-and-evaluation/`: simulation, Sim2Real, benchmarks, real robot evaluation.
- `08-hardware-and-deployment/`: robot platforms, sensors, safety, latency, monitoring, operations.
- `09-frontier-tracking/`: papers, repository watchlists, open source, datasets, companies, source maps.
- `10-case-studies/`: representative systems, products, platforms, and research projects.
- `11-glossary/`: terms, acronyms, and concept distinctions.
- `12-roadmaps/`: learning roadmap, research agenda, route map, timeline, inflection points.
- `99-templates-and-notes/`: reusable note templates and working notes.

When adding content, first decide which technical link it belongs to. Put stable explanations in the relevant technical directory. Put dynamic materials in `09-frontier-tracking/`. Put deep dives on representative systems in `10-case-studies/`.

## Content Style

Use Markdown. Keep pages readable and scannable.

Preferred section pattern for topic pages:

```md
# Topic

## It Solves What

## Plain Explanation

## Common Methods

## Why It Matters In Embodied AI

## Typical Failure Modes

## Advanced Notes

## Representative Papers Or Projects

## Open Questions
```

For source-tracking pages, use tables with explicit fields:

- title or name
- type
- source URL
- technical link
- why it matters
- evidence strength
- status
- last checked

## Language Support

The repository supports Chinese and English, with Chinese as the primary maintenance language.

Rules:

- Keep `README.md` as the primary Chinese entry and `README.en.md` as the English entry.
- Use adjacent English files for important translations, such as `topic.en.md`.
- Do not create a full mirrored English directory unless the content is stable enough to maintain.
- In Chinese pages, introduce important terms as `中文术语（English Term, Acronym）`.
- Preserve canonical English names for papers, models, datasets, benchmarks, and projects.
- Update `11-glossary/README.md` when adding important bilingual terminology.
- Prefer clear explanation over literal translation.
- If an English page is incomplete, mark it with `Status: draft` or `Status: partial translation`.

See `00-start-here/language-policy.md` for the detailed policy.

## Source Handling

The user wants this repository to be filled from external materials such as papers, official pages, code repositories, articles, discussions, and project pages.

Rules:

- Treat community discussion, long-form articles, blog posts, and search results as leads, not final evidence.
- Prefer primary sources for factual claims: paper, official project page, code repository, dataset page, benchmark page, company or lab announcement.
- Record the source type and URL in `09-frontier-tracking/inbox.md` or the relevant tracking page.
- If a claim may change over time, add `last checked`.
- For high-impact claims, include a short caveat or evidence-strength note.
- Do not copy long passages from external sources. Summarize in original wording and link the source.

## Reader Orientation

Every major topic should help readers answer:

- What problem does this solve?
- What are the inputs and outputs?
- Where does it sit in the embodied AI system loop?
- What are the simplest examples?
- What can go wrong?
- What are the important tradeoffs or research disagreements?
- Which papers, repos, or systems should I look at next?

## Updating Existing Pages

Before creating a new page, check whether an existing page already covers the topic.

When updating:

- Preserve useful existing structure.
- Prefer adding a concise subsection over making a page sprawling.
- Move stable knowledge from `09-frontier-tracking/` into the relevant technical directory when it matures.
- Keep old index pages only if they help navigation.
- Update `README.md` files when adding important new pages.
- Update `11-glossary/README.md` when adding important terms or acronyms.

## Case Studies

Use `10-case-studies/templates/case-study.md` for systems such as OpenVLA, RT-X, Octo, LeRobot, pi0, RDT, diffusion policy systems, humanoid platforms, benchmark environments, or notable products.

A case study should answer:

- What is it?
- Which technical links does it touch?
- What is new or important?
- What evidence supports it?
- What are its limitations?
- What should readers learn from it at different depths?

## Paper Notes

Use `99-templates-and-notes/templates/paper-note.md`.

Paper notes should not just summarize the paper. They should explain:

- Which technical link the paper belongs to.
- What problem it solves.
- What prior assumption it changes.
- Whether the evidence is simulation, benchmark, real robot, code, dataset, or demo.
- What a reader should remember after reading.

## File And Naming Conventions

- Use lowercase kebab-case file names.
- Use ASCII filenames.
- Prefer concise pages over very long pages.
- Use relative Markdown links for repository-local pages.
- Keep external links as normal Markdown links.
- Do not add generated binaries unless explicitly requested.

## Quality Checklist

Before finishing a substantial update:

- Check Markdown links resolve.
- Make sure the new content has a clear plain-language explanation plus useful depth where appropriate.
- Make sure dynamic claims have source URLs or are clearly marked as open questions.
- Make sure new pages are reachable from a relevant `README.md`.
- Avoid turning the repository into a raw awesome list.

## Current Maintenance Direction

Near-term priorities:

1. Fill each technical directory with clear explanations, advanced notes, tradeoffs, and open questions.
2. Build source maps from papers, official project pages, code repositories, articles, discussions, search results, and related external materials.
3. Create case studies for OpenVLA, Open X-Embodiment / RT-X, Octo, LeRobot, pi0, and representative simulation or benchmark projects.
4. Expand `11-glossary/README.md` with concise bilingual definitions and concept distinctions.
5. Keep `12-roadmaps/learning-roadmap.md` aligned with the technical-link structure.
