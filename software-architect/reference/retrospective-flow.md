# Retrospective Flow — Documenting Existing Projects

## When This Applies

Source code exists. The project needs documentation generated from code analysis.

## Phase 1: Automated Analysis

Explore the codebase systematically:

### 1. Project Structure
```bash
# Understand project layout
ls -la
find . -name "*.md" -maxdepth 2
cat README.md 2>/dev/null
cat package.json 2>/dev/null || cat requirements.txt 2>/dev/null || cat Gemfile 2>/dev/null
```

### 2. Architecture Detection
- Look for: docker-compose.yml, Dockerfile, kubernetes/, terraform/
- Identify: monolith vs microservices vs serverless
- Find: config files, environment variables, ports

### 3. Data Models
- ORM models: models/, entities/, schemas/
- Migrations: migrations/, alembic/, prisma/
- Database configs: database.yml, knexfile, ormconfig

### 4. Routes/Endpoints
- Route files: routes/, controllers/, views/
- API definitions: swagger.json, openapi.yaml
- Middleware: middleware/, auth/

### 5. Business Logic
- Services: services/, usecases/, domain/
- State machines: check for status/state fields in models
- Validations: validators/, schemas/

### 6. Error Handling
- Error handlers: middleware/error, exceptions/
- Try/catch patterns: search for catch blocks
- Error codes/messages: constants/, errors/

### 7. External Integrations
- HTTP clients: search for axios, fetch, requests, http
- API keys: .env, .env.example, config/
- Third-party SDKs: check dependencies

## Phase 2: Ask for Gaps

After analysis, ask the user about what CANNOT be inferred:
- Business rules not encoded in code
- Non-functional requirements (SLAs, performance targets)
- Future plans or roadmap
- Stakeholders and their concerns

## Phase 3: Generate Documentation

For each section:
1. Read template from sections-catalog.md
2. Generate content primarily from code analysis
3. Mark `[INFERRED]` for deductions, `[PENDING]` for unknowns
4. Save to output directory

## Phase 4: Gap Report

After generating all sections, produce a summary of:
- What was fully documented from code
- What was inferred (needs human validation)
- What could not be determined (needs input)
- Suggested improvements for the codebase itself
