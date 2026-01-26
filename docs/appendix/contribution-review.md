# Code Review Standards for Contributors

> Guidelines for reviewing and being reviewed when contributing to the Awesome Vibecoding Guide.

## Overview

Code review is essential for maintaining quality. This document outlines standards for both reviewing others' contributions and having your contributions reviewed.

## Review Checklist

### Pre-Review Verification

**Before starting review:**

- [ ] PR description is complete
- [ ] Changes align with project scope
- [ ] Tests are included (if applicable)
- [ ] Documentation updated (if applicable)
- [ ] No obvious build failures
- [ ] AI disclosure form completed (if applicable)

### Content Review

**For Documentation Changes:**

| Check | Description | Severity |
|-------|-------------|----------|
| Accuracy | Information is factually correct | Critical |
| Completeness | Topic fully covered | High |
| Actionability | Steps are implementable | High |
| Examples | Working code provided | High |
| Links | All references work | Medium |
| Style | Matches project voice | Medium |
| Formatting | Consistent throughout | Low |
| Grammar | No errors | Low |

### Code Review

**For Code Changes:**

| Check | Description | Severity |
|-------|-------------|----------|
| Functionality | Code works as intended | Critical |
| Security | No vulnerabilities | Critical |
| Testing | Tests pass, coverage adequate | High |
| Performance | Reasonable efficiency | High |
| Style | Matches project standards | Medium |
| Documentation | Code is documented | Medium |
| Dependencies | No unnecessary additions | Medium |
| Error Handling | Edge cases covered | High |

### Cross-Reference Verification

**For Content Linking:**

| Check | Description | Severity |
|-------|-------------|----------|
| Internal Links | Relative paths work | Critical |
| External Links | URLs are current and valid | High |
| Anchor Links | Section anchors exist | Medium |
| Cross-Docs | Related docs referenced | Medium |

### Link Testing

**Verify All Links:**

```bash
# Test all links in PR
npm run test:links --pr=123

# Test specific file
npm run test:links --file=docs/section.md

# Full link audit
npm run test:links --full
```

**Link Check Categories:**

| Link Type | Test Method | Timeout |
|-----------|-------------|---------|
| Internal | File existence | 5s |
| External | HTTP 200 | 10s |
| Anchor | Section exists | 5s |
| Image | File exists + loads | 10s |

### Content Accuracy Verification

**For Factual Claims:**

- [ ] Statistics from reliable sources
- [ ] Code examples tested
- [ ] Tools/technologies verified current
- [ ] No hallucinated content
- [ ] References traceable

**For Technical Accuracy:**

- [ ] API usage correct
- [ ] Best practices followed
- [ ] No deprecated methods
- [ ] Security patterns sound
- [ ] Performance implications considered

### Style Consistency Checks

**Writing Style:**

| Element | Check |
|---------|-------|
| Voice | Matches project tone |
| Terminology | Consistent throughout |
| Formatting | Follows template |
| Emoji usage | Appropriate placement |
| List style | Consistent bullet types |
| Code blocks | Proper language tags |

**Code Style:**

| Element | Check |
|---------|-------|
| Indentation | Consistent (2 spaces) |
| Variable names | Descriptive, consistent |
| Comments | Clear, not excessive |
| Line length | Under 100 characters |
| File naming | kebab-case |

## Review Process

### For Reviewers

**Step 1: Understand the Change**

1. Read the PR description
2. Review changed files
3. Check related issues/discussions
4. Understand the intent

**Step 2: Systematic Review**

1. Run pre-review checklist
2. Check each changed file
3. Test code if applicable
4. Verify links and references
5. Check style consistency

**Step 3: Provide Feedback**

**Constructive Feedback Format:**

```markdown
## Review Summary
[Overall assessment]

### Items to Address
1. **[Issue Description]**
   - Impact: [High/Medium/Low]
   - Suggestion: [How to fix]
   - File: [path/to/file]:[line]

### Items to Consider
1. **[Suggestion]**
   - Rationale: [Why this helps]

### Approved With
- [ ] No changes required
- [ ] Minor changes (see above)
- [ ] Major changes required
```

**Review Response Types:**

| Response | Meaning |
|----------|---------|
| Approve | Ready to merge |
| Approve with comments | Minor suggestions, merge okay |
| Request changes | Significant issues, must fix |
| Comment | General feedback, no action required |

**Feedback Guidelines:**

- Be specific about issues
- Explain the "why" behind suggestions
- Offer alternative solutions
- Acknowledge good work
- Keep tone constructive
- Focus on the content, not the person

### For Contributors

**Before Requesting Review:**

- [ ] Self-review completed
- [ ] All checks pass locally
- [ ] PR description complete
- [ ] Changes focused (no scope creep)
- [ ] Ready for constructive feedback

**Responding to Review:**

1. Acknowledge all feedback
2. Address each item systematically
3. Ask clarifying questions if needed
4. Push changes promptly
5. Re-request review when ready

**Sample Response:**

```markdown
## Response to Review

Thanks for the thorough review!

### Addressed Items
- [x] Fixed typo in [file]:line
- [x] Added error handling for edge case
- [x] Updated link to current URL
- [x] Added code comments

### Questions
- Regarding "Consider using X": I chose Y because [reason]. Does that work?

### Remaining Items
- [ ] Awaiting clarification on item 3
```

## Project-Type Specific Review

### Website Projects

**Additional Checks:**

| Check | Description |
|-------|-------------|
| Responsive design | Works on mobile |
| Performance | Lighthouse score adequate |
| Accessibility | Alt text, ARIA labels |
| SEO | Meta descriptions present |
| Browser support | Tested in major browsers |

### Automation Projects

**Additional Checks:**

| Check | Description |
|-------|-------------|
| Error handling | Failures handled gracefully |
| Idempotency | Running twice is safe |
| Logging | Adequate for debugging |
| Rate limits | Respects external limits |
| Credentials | No hardcoded secrets |

### Documentation Projects

**Additional Checks:**

| Check | Description |
|-------|-------------|
| Tone | Consistent with project |
| Examples | Tested and working |
| Completeness | Covers main use cases |
| Navigation | Clear structure |
| Links | All internal/external work |

## Quality Gates

### Pre-Ship Checklist

**Before merge, verify:**

- [ ] All review comments addressed
- [ ] Tests passing
- [ ] No linting errors
- [ ] Links verified
- [ ] Cross-references checked
- [ ] AI disclosure complete
- [ ] Contributor license signed
- [ ] CI/CD passes

### Merge Requirements

| Requirement | Who Verifies | Tool |
|-------------|--------------|------|
| CI passes | GitHub Actions | Automated |
| Review approved | Maintainer | GitHub |
| Tests pass | CI | Jest/Mocha |
| Links valid | CI | Link Checker |
| Style check | CI | ESLint/Prettier |

## Review Metrics

### Response Time Targets

| PR Size | First Review | Subsequent Reviews |
|---------|--------------|---------------------|
| Small (<100 lines) | 24 hours | 12 hours |
| Medium (100-500 lines) | 48 hours | 24 hours |
| Large (500+ lines) | 72 hours | 48 hours |

### Review Quality Metrics

| Metric | Target |
|--------|--------|
| Review thoroughness | All items checked |
| Constructive feedback | 100% actionable |
| Response time | Within SLA |
| Approval rate | >80% on first review |

## Common Review Issues

### Frequent Feedback Categories

| Category | Example | Frequency |
|----------|---------|-----------|
| Style | "Use consistent formatting" | High |
| Missing tests | "Add test for edge case" | Medium |
| Security | "Don't log credentials" | Low |
| Performance | "Use memoization here" | Medium |
| Documentation | "Add code comments" | Medium |

### Resolving Disagreements

**Step 1: Discuss in PR**
- Explain your reasoning
- Ask for clarification
- Seek common ground

**Step 2: Escalate if needed**
- Tag maintainer for opinion
- Reference similar decisions
- Accept final ruling

**Step 3: Move forward**
- Once decided, implement or accept
- Don't hold up progress

## Recognition

### Reviewer Credits

Contributors who review others' work earn:
- Recognition in monthly newsletter
- Priority in contributor tier advancement
- Badge for "Helpful Reviewer"

### Review Leaderboard

Top reviewers are highlighted:
- Monthly most reviews
- Quarterly most impactful reviews
- Annual "Best Reviewer" award

---

**Related Documents:**
- [Contributing Guide](contributing.md)
- [Contributor Levels](contribution-levels.md)
- [AI Contribution Guide](ai-contribution-guide.md)
- [Community Guidelines](community-guidelines.md)
