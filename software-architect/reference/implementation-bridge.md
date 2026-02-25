# Implementation Bridge

After generating engineering documentation, offer the user these next steps.

## Option 1: Implementation Plan

Generate a phased development plan from the documentation:

1. Read the generated use cases (02) and requirements (07)
2. Break into development phases (MVP first, then iterations)
3. For each phase, list:
   - Features to implement (reference RF-XXX)
   - Files to create/modify
   - Dependencies between tasks
   - Estimated complexity (S/M/L)
4. Save as `docs/plans/YYYY-MM-DD-implementation-plan.md`
5. **REQUIRED SUB-SKILL:** Invoke superpowers:writing-plans for detailed task breakdown

## Option 2: Project Scaffold

Generate initial project structure:

1. Based on architecture (01) and tech stack, create directory structure
2. Create placeholder files with documented interfaces from API catalog (05)
3. Create database migration stubs from ER diagram (04)
4. Create configuration files from architecture decisions (13)

Example scaffold output:
```
project/
  src/
    models/          # From section 04
    routes/          # From section 05
    services/        # From section 02
    middleware/       # From section 11
  tests/
    unit/
    integration/
  docs/engineering/  # Generated documentation
  docker-compose.yml # From section 01
  .env.example       # From section 01
```

## Option 3: Test Contracts

Generate test stubs from documentation:

1. From API catalog (05): HTTP endpoint tests (request/response contracts)
2. From use cases (02): Integration test scenarios (happy path + error flows)
3. From state diagrams (06): State transition tests
4. From error map (11): Error handling tests

## Option 4: Full System (All of the Above)

Execute options 1 + 2 + 3 in sequence.

## Presenting Options to User

After documentation is complete, ask:

"Documentation complete. What's next?"
- Generate implementation plan (phases + tasks)
- Create project scaffold (directory structure + stubs)
- Generate test contracts (test files from docs)
- Full system (plan + scaffold + tests)
- Done for now
