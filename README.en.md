# Emergent Embodied AI

Language: [中文](README.md) | English

A knowledge base for learning, research, and practice in embodied AI, organized by the technical links of an embodied AI system from input to real-world deployment.

This repository is not meant to be a raw link collection. It helps readers build a clear map: what components an embodied AI system needs, what problem each component solves, which methods are common, and where frontier papers, system case studies, and open projects fit in the system.

## Learning Path

Recommended reading order:

1. [00-start-here](00-start-here/README.md): what embodied AI is and how to use this repository.
2. [01-system-overview](01-system-overview/README.md): the full system loop.
3. [02-perception](02-perception/README.md): how robots perceive the environment.
4. [03-representation](03-representation/README.md): how to represent space, objects, states, and actions.
5. [04-data](04-data/README.md): where robot learning data comes from and why it is expensive.
6. [05-policy-learning](05-policy-learning/README.md): how robot policies are learned from data and interaction.
7. [06-planning-and-control](06-planning-and-control/README.md): how goals become executable actions.
8. [07-simulation-and-evaluation](07-simulation-and-evaluation/README.md): simulation, benchmarks, and real robot evaluation.
9. [08-hardware-and-deployment](08-hardware-and-deployment/README.md): hardware, safety, deployment, and operations.
10. [09-frontier-tracking](09-frontier-tracking/README.md): papers, projects, articles, discussions, frontier indexes, and weekly reviews.
11. [10-case-studies](10-case-studies/README.md): representative systems and project breakdowns.
12. [11-glossary](11-glossary/README.md): terms, acronyms, and concept distinctions.
13. [12-roadmaps](12-roadmaps/README.md): learning, research, and technical roadmaps.
14. [99-templates-and-notes](99-templates-and-notes/README.md): templates for paper notes, topic briefs, and question cards.

## Why Organize By Technical Links

Embodied AI spans models, data, control, simulation, hardware, and deployment. Organizing by technical links helps newcomers build a map, while also supporting deeper research and route analysis:

```text
task goal
→ perceive the environment
→ represent the world and actions
→ collect and organize data
→ learn policies
→ plan and control
→ simulate and evaluate
→ deploy on hardware
→ track frontiers and review cases
```

When reading a paper or project, first identify which technical link it mainly improves, then ask what bottleneck it addresses.

## How To Use

1. If you are new to the field, start with [00-start-here/overview-map.md](00-start-here/overview-map.md).
2. Skim each directory README along the learning path.
3. Check [11-glossary](11-glossary/README.md) when you meet unfamiliar terms.
4. Use [09-frontier-tracking](09-frontier-tracking/README.md) for frontier updates.
5. Use [10-case-studies](10-case-studies/README.md) to understand complete systems.
