# ECC for Gemini CLI

This file provides guidance to Gemini CLI when working with code in projects that have ECC installed.

## Overview

Everything Claude Code (ECC) is a production-ready AI coding plugin providing 28 agents, 127 skills, and 60 commands for software development workflows.

## Core Workflows

### Test-Driven Development
1. Write tests first (RED)
2. Run tests — they should fail
3. Write minimal implementation (GREEN)
4. Run tests — they should pass
5. Refactor (IMPROVE)
6. Verify 80%+ coverage

### Code Review
- Check for security vulnerabilities (OWASP Top 10)
- Verify error handling at system boundaries
- Ensure immutable data patterns
- Validate input at API boundaries

### Architecture
- Many small files over few large files (200-400 lines, 800 max)
- Organize by feature/domain, not by type
- Repository pattern for data access
- API response format: `{ success, data?, error?, meta? }`

## Coding Standards

- Prefer immutability — create new objects, never mutate
- Functions under 50 lines
- No deep nesting (4 levels max)
- Validate user input with schema validation (Zod, Joi, etc.)
- No hardcoded secrets — use environment variables
- Handle errors comprehensively with user-friendly messages

## Security Checklist

Before any commit:
- No hardcoded secrets
- All user inputs validated
- SQL injection prevention (parameterized queries)
- XSS prevention
- CSRF protection
- Authentication/authorization verified

## Commit Format

```
<type>: <description>
```

Types: feat, fix, refactor, docs, test, chore, perf, ci

## Available Skills

Skills are located in the `skills/` directory. Each contains a `SKILL.md` with detailed instructions.

Key skills: tdd-workflow, security-review, coding-standards, backend-patterns, frontend-patterns, lead-intelligence, autonomous-agent-harness, deep-research, exa-search, x-api
