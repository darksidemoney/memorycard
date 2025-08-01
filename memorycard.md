# 💾 LLM Memory Card v2.0 - Production-Ready Save/Load System

---
schema_version: 2.0.0
project_uid: ""
card_id: ""
generated_by: ""
timestamp: ""
git:
  repo: ""
  branch: ""
  head_sha: ""
  dirty: false
  uncommitted_files: []
env:
  node: ""
  pkg_manager: ""
  platform: ""
context_budget:
  max_tokens: 12000
  priority_sections: ["identity", "current_state", "next_actions", "issues"]
redaction:
  rules: ["REDACT:ENV_VALUES", "MASK:API_KEYS", "HIDE:SECRETS"]
load_hints:
  focus: ""
  next_steps: []
  blockers: []
validation:
  required_checks: ["git_status", "package_json", "entry_points"]
  health_score: 0
checksum: ""
---

## 🎮 **MEMORY CARD COMMANDS**

### **🔽 INSTANT SAVE** (New Project)
*Drop this template to create new memory card*

### **🔄 INSTANT UPDATE** (Save Progress)  
*Drop existing card to save current session progress*

### **🔼 INSTANT LOAD** (Restore Context)
*Drop populated card to restore context in new session*

---

## 🤖 **AUTO-EXECUTION PROTOCOL**

**When you receive this memory card:**

1. **DETECT MODE**: Analyze the YAML header and context
   - If `project_uid` is empty → **SAVE MODE** (New project)
   - If `project_uid` exists AND this is a new session → **LOAD MODE** (Restore context)
   - If `project_uid` exists AND we've been working together → **UPDATE MODE** (Save progress)

2. **MODE DETECTION LOGIC**:
   ```
   IF project_uid == "" → SAVE (Create new memory card)
   ELSE IF no_prior_context_in_session → LOAD (Restore from card)  
   ELSE IF working_session_active → UPDATE (Save current progress)
   ```

3. **EXECUTE IMMEDIATELY** - No questions, no confirmations

4. **UPDATE STATUS** - Report completion and readiness

---

## 🔽 **SAVE MODE EXECUTION** (New Project)

*Creates a new memory card from scratch*

### **Step 1: YAML Header Population**
```yaml
schema_version: 2.0.0
project_uid: [GENERATE: "urn:proj:{folder_name}:{random}"]
card_id: [GENERATE: "urn:card:{timestamp}"]
generated_by: [DETECT: "{llm_name}@{version}"]
timestamp: [NOW: ISO8601]
```

### **Step 2: Git Analysis**
```yaml
git:
  repo: [EXTRACT: from .git/config or git remote -v]
  branch: [EXTRACT: git branch --show-current]
  head_sha: [EXTRACT: git rev-parse HEAD]
  dirty: [CHECK: git status --porcelain]
  uncommitted_files: [LIST: modified files]
```

### **Step 3: Environment Detection**
```yaml
env:
  node: [EXTRACT: node --version]
  pkg_manager: [DETECT: package-lock.json→npm, yarn.lock→yarn, pnpm-lock.yaml→pnpm]
  platform: [DETECT: os.platform()]
```

### **Step 4: Context Budget & Redaction**
```yaml
context_budget:
  max_tokens: 12000
  priority_sections: [AUTO-RANK: by importance]
redaction:
  rules: [APPLY: to all sensitive data]
```

### **Step 5: Validation Setup**
```yaml
validation:
  required_checks: [DEFINE: based on project type]
  health_score: [CALCULATE: 0-100 based on analysis]
```

### **Step 6: Generate Checksum**
```yaml
checksum: [GENERATE: sha256 of all data]
```

---

## 🔼 **LOAD MODE EXECUTION**

### **Step 1: Validation**
- Verify schema_version compatibility
- Check checksum integrity
- Validate required fields present

### **Step 2: Context Restoration**
- Parse all typed sections
- Reconstruct project understanding
- Apply learned patterns and conventions

### **Step 3: Readiness Report**
- Confirm successful load
- List capabilities restored
- Identify any missing information

---

## 📊 **TYPED DATA SECTIONS**

### **Project Identity**
```llmcard/identity
name: ""
type: ""
version: ""
description: ""
main_language: ""
framework: ""
last_active: ""
team_size: 1
```

### **Architecture Snapshot**
```llmcard/architecture
frontend:
  framework: ""
  styling: ""
  state_management: ""
  routing: ""
backend:
  framework: ""
  database: ""
  auth: ""
  api_style: ""
infrastructure:
  hosting: ""
  ci_cd: ""
  monitoring: ""
  testing: ""
```

### **File Structure**
```llmcard/structure
entry_points: []
key_directories: {}
important_files: {}
config_files: {}
```

### **Dependencies**
```llmcard/dependencies
production: {}
development: {}
peer: {}
outdated: []
security_issues: []
```

### **Current State**
```llmcard/current_state
active_branch: ""
last_commit_message: ""
uncommitted_changes: []
current_focus: ""
working_feature: ""
last_successful_command: ""
development_mode: ""
```

### **Issues Database**
```llmcard/issues
active_bugs: []
known_workarounds: []
solved_problems: []
technical_debt: []
performance_concerns: []
```

### **Code Patterns**
```llmcard/patterns
file_naming: ""
component_structure: ""
error_handling: ""
logging_approach: ""
testing_patterns: ""
api_conventions: ""
state_patterns: ""
styling_approach: ""
```

### **Development Environment**
```llmcard/environment
required_versions: {}
environment_variables: []
development_scripts: {}
build_commands: {}
test_commands: {}
deployment_commands: {}
```

### **Knowledge Base**
```llmcard/knowledge
key_concepts: []
external_apis: []
important_urls: []
team_conventions: []
deployment_notes: []
troubleshooting_guide: []
```

### **Next Actions**
```llmcard/next_actions
immediate_todos: []
current_blockers: []
planned_features: []
refactoring_needed: []
testing_required: []
documentation_gaps: []
```

### **Session Context**
```llmcard/session_context
last_working_on: ""
conversation_context: ""
decision_points: []
open_questions: []
context_for_next_session: ""
```

---

## 🎯 **SAVE OPERATION STATUS**

**🔄 ANALYZING PROJECT...**

```llmcard/save_results
status: "ANALYZING|COMPLETE|ERROR"
files_scanned: 0
patterns_identified: []
issues_found: []
confidence_level: "HIGH|MEDIUM|LOW"
generation_time: ""
warnings: []
critical_findings: []
```

**✅ SAVE COMPLETE**
- Project state captured successfully
- All critical data extracted and validated
- Memory card ready for future loading
- Checksum: `[GENERATED_CHECKSUM]`

---

## 🔼 **LOAD OPERATION STATUS**

**🔄 LOADING MEMORY CARD...**

```llmcard/load_results
status: "LOADING|READY|INCOMPLETE|ERROR"
context_restored: []
patterns_applied: []
missing_information: []
validation_passed: true
load_time: ""
compatibility_issues: []
ready_capabilities: []
```

**✅ LOAD COMPLETE**
- Full project context restored
- Development patterns and conventions loaded
- Issue database and solutions available
- Ready to continue seamlessly from last session

---

## 🛡️ **VALIDATION & INTEGRITY**

### **Self-Validation Checks**
1. **Git Status Match**: Current branch matches saved state
2. **File Integrity**: Key files exist and are accessible
3. **Dependency Health**: Package.json matches environment
4. **Script Availability**: Development commands are executable
5. **Project Structure**: Directory structure is intact

### **Health Indicators**
- 🟢 **Healthy**: All validations pass, ready to work
- 🟡 **Warning**: Minor issues detected, mostly functional
- 🔴 **Critical**: Major problems, manual intervention needed

### **Checksum Verification**
```bash
# Automatic integrity check on load
echo "[SAVED_CHECKSUM]" | sha256sum --check
```

---

## 🔒 **SECURITY & REDACTION**

### **Automatic Redaction Rules**
- **Environment Variables**: Values replaced with `[REDACTED]`
- **API Keys**: Masked as `[MASKED:first4chars****]`
- **Database URLs**: Connection strings sanitized
- **Secrets**: Any detected secrets hidden
- **Personal Info**: Email addresses and names filtered

### **Safe Data Only**
- File structures and naming patterns
- Package names and versions (not auth tokens)
- Git branch names and commit messages
- Code patterns and architectural decisions
- Issue descriptions (sanitized)

---

## 🚀 **INSTANT USAGE**

### **SAVE (Drop empty template)**
```
USER: [Drops this template - first time]
LLM: 🔄 Analyzing project...
     ✅ SAVE COMPLETE - New memory card created
     📊 Scanned 247 files, found React/TypeScript app
     🎯 Current focus: Authentication system
     💾 project_uid: urn:proj:myapp:a1b2c3
```

### **UPDATE (Drop populated card after working)**
```
USER: [Drops memory card after session work]
LLM: 🔄 Updating memory card...
     ✅ UPDATE COMPLETE - Progress saved
     📈 Session: Fixed login bug, added tests
     🎯 Updated focus: User dashboard implementation
     💾 Save count: 5 → 6
```

### **LOAD (Drop populated card in new session)**
```
USER: [Drops populated memory card]
LLM: 🔄 Loading memory card...
     ✅ LOAD COMPLETE - Context restored
     🎯 Continuing: User dashboard feature
     📋 Last working: Login redirect bug (SOLVED)
     🚀 Ready to implement task filtering
```

---

## 🎮 **MEMORY CARD METADATA**

```llmcard/metadata
format_version: "2.0.0"
compatibility: ["cursor", "vscode", "chat-llms", "api-llms"]
max_project_size: "10MB source code"
retention_policy: "30 days auto-cleanup"
team_sharing: true
backup_recommended: true
storage_location: ".llm-memory-card.md"
```

---

## 📋 **JSON SCHEMA REFERENCE**

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "https://llm-memory-card.dev/schema/v2.0.0",
  "title": "LLM Memory Card Schema",
  "type": "object",
  "required": ["schema_version", "project_uid", "timestamp"],
  "properties": {
    "schema_version": {
      "type": "string",
      "pattern": "^\\d+\\.\\d+\\.\\d+$"
    },
    "project_uid": {
      "type": "string",
      "pattern": "^urn:proj:[a-zA-Z0-9-]+:[a-f0-9]{6}$"
    },
    "git": {
      "type": "object",
      "properties": {
        "repo": {"type": "string"},
        "branch": {"type": "string"},
        "head_sha": {"type": "string", "pattern": "^[a-f0-9]{40}$"},
        "dirty": {"type": "boolean"},
        "uncommitted_files": {"type": "array", "items": {"type": "string"}}
      },
      "required": ["repo", "branch", "head_sha", "dirty"]
    }
  }
}
```

---

## 🎯 **ZERO-EFFORT OPERATION**

### **User Experience**
1. **Drop template** → LLM automatically saves project state
2. **Drop saved card** → LLM automatically loads and continues
3. **No configuration** → Everything detected automatically
4. **No manual input** → All data extracted from project files
5. **Cross-platform** → Works in any LLM context

### **LLM Behavior**
- **No questions asked** → Execute immediately on drop
- **Deterministic output** → Same structure every time
- **Complete analysis** → Nothing left to user interpretation
- **Validated results** → Self-checking for accuracy
- **Ready to work** → Context fully restored and actionable

---

**💾 MEMORY CARD STATUS: TEMPLATE_READY**  
**🎮 DROP TO SAVE/LOAD - NO USER INPUT REQUIRED**  
**✨ v2.0.0 - Production Ready**
