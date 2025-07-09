**Purpose**: Technical documentation and knowledge transfer

---

@include shared/universal-constants.yml#Universal_Legend

## Command Execution
Execute: immediate. --plan→show plan first
Legend: Generated based on symbols used in command
Purpose: "[Action][Subject] in $ARGUMENTS"

Provide comprehensive explanations of concepts, code, or systems specified in $ARGUMENTS.

@include shared/flag-inheritance.yml#Universal_Always

Examples:
- `/explain --depth beginner --style tutorial "React hooks"` - Explain React hooks for beginners
- `/explain --depth advanced --visual "B-tree indexes"` - Deep dive into database indexing
- `/explain --depth expert --think "quicksort optimization"` - Algorithm explanation w/ complexity

Explanation modes:

**--depth:** Explanation depth level
- beginner: Basic concepts, simple language | intermediate: Standard technical depth
- advanced: Deep technical details | expert: Cutting-edge & internals

**--style:** Explanation style
- tutorial: Step-by-step learning | reference: Quick lookup format
- conversational: Natural dialogue | academic: Formal & thorough

**--visual:** Include visual aids
- Diagrams & flowcharts | Code examples w/ annotations
- Architecture visualizations | Sequence diagrams for flows

@include shared/research-patterns.yml#Explanation_Methodology

## AI-Context Development Tools

**Core Principle**: Context conservation - prevent AI from reading hundreds of files

### Essential Navigation Tools
```bash
# Code Structure Discovery - START HERE
<task-runner> list-services     # Map all services/APIs
<task-runner> list-types        # Data structures/models
<task-runner> list-endpoints    # Available interfaces
<task-runner> list-functions    # Key functions/methods
<task-runner> db-schema         # Database structure

# Status & Logs - RAPID DIAGNOSIS
<task-runner> status-all        # Complete system overview
<task-runner> logs-tail         # Last 20 lines from all services
<task-runner> logs-errors       # Error logs only
<task-runner> health-summary    # Service health checks
<task-runner> env-check         # Environment verification
```

### Universal Tool Patterns

**Navigation Tools** - High-level maps without file exploration:
- `list-services`: API endpoints, routes, services
- `list-types`: Data structures, models, schemas
- `list-endpoints`: Available interfaces
- `list-functions`: Key functions/methods
- `db-schema`: Database structure

**Logging Tools** - Efficient access to recent activity:
- `logs-tail`: Combined recent logs (last 20 lines)
- `logs-errors`: Error logs only
- `logs-search TERM`: Search across logs
- `logs-service NAME`: Service-specific logs

**Status Tools** - System health without deep investigation:
- `status-all`: Complete system overview
- `health-summary`: Service health checks
- `env-check`: Environment verification

### Technology Stack Examples

#### Rust (Axum/Tonic/Async-GraphQL)
```bash
# Navigation
list-services: grep -r "async fn\|pub fn.*serve\|Router\|Service" src/
list-types: find src/ -name "*.rs" -exec grep "pub struct\|pub enum\|type.*=" {} \;
list-endpoints: grep -r "get\|post\|put\|delete\|route\|rpc" src/

# Status
status-all: cargo check && docker-compose ps
health-summary: curl localhost:3000/health
env-check: rustc --version && cargo --version
```

#### Bun/Solid.js
```bash
# Navigation
list-routes: grep -r "createRouter\|Route\|defineRoute" src/
list-components: find src/ -name "*.tsx" -o -name "*.jsx" | grep -E "(component|Component)"
list-endpoints: grep -r "Bun.serve\|app.get\|app.post" .

# Status
status-all: bun run dev --check
health-summary: curl localhost:3000/api/health
env-check: bun --version
```

#### Astro
```bash
# Navigation
list-pages: find src/pages/ -name "*.astro" -o -name "*.md"
list-components: find src/components/ -name "*.astro" -o -name "*.tsx"
list-endpoints: grep -r "export.*get\|export.*post" src/pages/api/

# Status
status-all: npm run build && npm run preview
health-summary: curl localhost:3000/api/health
env-check: astro --version
```

#### Go
```bash
# Navigation
list-handlers: grep -r "func.*Handler\|http\." .
list-structs: grep -r "type.*struct" .
list-endpoints: grep -r "HandleFunc\|Handle\|mux\." .

# Status
status-all: go build && docker ps
health-summary: curl localhost:8080/health
env-check: go version
```

#### Python
```bash
# Navigation
list-views: find . -name "*.py" -exec grep -l "@app.route\|def.*view" {} \;
list-models: find . -name "*.py" -exec grep -l "class.*Model\|Base" {} \;
list-endpoints: grep -r "@app.route\|path\|url" .

# Status
status-all: python -m pytest --collect-only
health-summary: curl localhost:8000/health
env-check: python --version && pip --version
```

#### Android (Jetpack Compose)
```bash
# Navigation
list-screens: find app/src/main/java/ -name "*.kt" -exec grep -l "@Composable\|Screen" {} \;
list-viewmodels: find app/src/main/java/ -name "*.kt" -exec grep -l "ViewModel" {} \;
list-activities: find app/src/main/java/ -name "*.kt" -exec grep -l "Activity" {} \;

# Status
status-all: ./gradlew assembleDebug
health-summary: adb logcat | grep -i "error\|exception" | head -10
env-check: java --version && ./gradlew --version
```

#### iOS (SwiftUI)
```bash
# Navigation
list-views: find . -name "*.swift" -exec grep -l "View\|@main" {} \;
list-models: find . -name "*.swift" -exec grep -l "struct.*:\|class.*:" {} \;
list-viewmodels: find . -name "*.swift" -exec grep -l "ObservableObject\|@Published" {} \;

# Status
status-all: xcodebuild -scheme [AppName] build
health-summary: xcrun simctl list devices | grep Booted
env-check: swift --version && xcodebuild -version
```

### Best Practices

#### Tool Design
- **Fast response** (< 2 seconds)
- **Concise output** (essential info only)
- **Consistent interface** (same patterns)
- **Graceful failures** (helpful errors)

#### Workflow Integration
- **Start with navigation** - Use list-services, list-types first
- **Quick status check** - Use status-all for overview
- **Efficient logs** - Use logs-tail and logs-errors for diagnosis
- **Document patterns** - Capture debugging workflows

@include shared/docs-patterns.yml#Standard_Notifications

@include shared/universal-constants.yml#Standard_Messages_Templates