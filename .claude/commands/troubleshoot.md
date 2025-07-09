**Purpose**: Professional debugging and issue resolution

---

@include shared/universal-constants.yml#Universal_Legend

## Command Execution
Execute: immediate. --plan→show plan first
Legend: Generated based on symbols used in command
Purpose: "[Action][Subject] in $ARGUMENTS"

Systematically debug and resolve issues in $ARGUMENTS using root cause analysis and evidence-based solutions.

@include shared/flag-inheritance.yml#Universal_Always

Examples:
- `/troubleshoot "app crashes on startup"` - Debug crash
- `/troubleshoot --performance "slow API"` - Performance issues
- `/troubleshoot --interactive "login fails"` - Guided debugging

## Command-Specific Flags
--performance: "Focus on performance bottlenecks"
--memory: "Memory leak detection and analysis"
--network: "Network-related debugging"
--interactive: "Step-by-step guided troubleshooting"
--trace: "Enable detailed execution tracing"
--bisect: "Git bisect to find breaking commit"

## Troubleshooting Approach

**1. Reproduce:** Isolate minimal reproduction | Document steps | Verify consistency | Capture full context

**2. Gather Evidence:** Error messages & stack traces | Logs & metrics | System state | Recent changes | Environment differences

**3. Form Hypotheses:** Most likely causes | Alternative explanations | Test predictions | Rule out possibilities

**4. Test & Verify:** Targeted experiments | Change one variable | Document results | Confirm root cause

**5. Fix & Prevent:** Implement solution | Add tests | Document fix | Prevent recurrence

## Common Issue Categories

**Performance:** Slow queries | Memory leaks | CPU bottlenecks | Network latency | Inefficient algorithms

**Crashes/Errors:** Null references | Type mismatches | Race conditions | Memory corruption | Stack overflow

**Integration:** API failures | Authentication issues | Version conflicts | Configuration problems | Network timeouts

**Data Issues:** Corruption | Inconsistency | Migration failures | Encoding problems | Concurrency conflicts

@include shared/quality-patterns.yml#Root_Cause_Analysis

## Quick Setup Checklist for AI-Context Tools

1. **Create Navigation Tools** - Identify architectural elements, create summarization commands
2. **Implement Logging Tools** - Set up combined log viewing, error filtering  
3. **Add Status Tools** - System overview, health checks, environment verification
4. **Document Usage** - Add project CLAUDE.md with tools section

## Project Integration Template

```markdown
# Project Name

## AI-Context Tools (Essential Navigation)

```bash
# Navigation - START HERE
just list-services    # Service/API discovery
just list-types       # Data structures
just list-endpoints   # Available interfaces

# Status & Logs - RAPID DIAGNOSIS
just status-all       # System overview
just logs-tail        # Recent activity (last 20 lines)
just logs-errors      # Error summary
```
```

This approach provides context-efficient development tools that prevent AI spelunking while maintaining professional standards across all projects.

## Deliverables

**Root Cause Report:** Issue description | Evidence collected | Analysis process | Root cause identified | Fix implemented

**Fix Documentation:** What was broken | Why it broke | How it was fixed | Prevention measures | Test cases added

**Knowledge Base:** Problem→Solution mapping | Troubleshooting guides | Common patterns | Prevention checklist

@include shared/universal-constants.yml#Standard_Messages_Templates