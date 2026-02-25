# Prospective Flow — Planning New Projects

## When This Applies

No source code exists. The user has an idea, concept, or specification and wants to plan before coding.

## Phase 1: Understand the Idea

Ask questions ONE AT A TIME. Prefer multiple choice. Cover:

1. **What does it do?** — Core functionality in 1-2 sentences
2. **Who uses it?** — Target users/actors
3. **Tech preferences?** — Language, framework, database, hosting
4. **Integrations?** — External APIs, services, payment gateways
5. **Scale expectations?** — Users, data volume, performance needs
6. **Constraints?** — Budget, timeline, team size, existing infrastructure

If the user provides a detailed spec, skip to Phase 2 and generate directly.

## Phase 2: Propose Architecture

Based on answers, propose 2-3 architectural approaches:

- Present trade-offs (complexity, scalability, cost, time-to-market)
- Lead with your recommendation
- Get user approval before proceeding

## Phase 3: Generate Documentation

Follow the sections selected by the user. For each section:

1. Read the template from sections-catalog.md
2. Generate content based on the gathered context
3. Mark everything as `[DESIGNED]` (not inferred from code)
4. Save to output directory

**Generation order (respecting dependencies):**

```
Batch 1 (parallel): 01, 02, 03, 04, 06, 12, 13
Batch 2 (needs 02): 05, 07, 09, 10, 11
Batch 3 (needs 02+07): 08
```

## Phase 4: Validate with User

Present each generated section for review. Iterate until approved.

## Common Patterns by Project Type

**Web App (fullstack):** All 13 sections relevant. Emphasize 01, 02, 04, 05, 09.
**API/Backend:** Focus on 01, 02, 04, 05, 06, 07, 09, 11.
**CLI Tool:** Focus on 01, 02, 06, 07, 13. Skip 04, 05.
**Mobile App:** All sections. Emphasize 01, 02, 06, 09, 10.
**Data Pipeline:** Focus on 01, 04, 06, 07, 10, 11, 12.
**Chatbot/AI:** Focus on 01, 02, 06, 07, 09, 11, 13.
