# AI-Assisted Contribution Guidelines

> Guidelines for using AI tools to contribute effectively and ethically to the Awesome Vibecoding Guide.

## Overview

AI tools can significantly accelerate contributions, but require careful handling to maintain quality, transparency, and ethical standards. This guide explains how to use AI responsibly when contributing to this project.

## AI Tools for Contributions

### Recommended AI Tools

| Tool | Best For | Cost | Learning Curve |
|------|----------|------|----------------|
| Claude | Code, documentation, prompts | Free/Paid | Low |
| ChatGPT | General writing, code | Free/Paid | Low |
| GitHub Copilot | Code completion | Paid | Low |
| Claude Code | Complex implementations | Paid | Medium |

### When to Use AI

**Good Use Cases:**

| Task | AI Assistance Level |
|------|---------------------|
| Drafting documentation sections | High |
| Code examples and snippets | High |
| Grammar and style improvements | Medium |
| Brainstorming approaches | High |
| Generating placeholder content | High |

**Use with Caution:**

| Task | AI Assistance Level |
|------|---------------------|
| Technical explanations | Verify accuracy |
| Security-sensitive code | Expert review required |
| Legal content | Expert review required |
| Statistical claims | Verify sources |

**Don't Use AI For:**

| Task | Reason |
|------|--------|
| Attesting to factual accuracy | AI can hallucinate |
| Making commitments | Must come from human judgment |
| Emotional/political content | Requires human perspective |
| Unauthorized copying | Always respect IP |

## Required Human Review Process

### Why Human Review Is Mandatory

AI-generated content must be reviewed because:

**Common AI Issues:**

| Issue | Example | Risk Level |
|-------|---------|------------|
| Hallucinations | Fake API documentation | High |
| Outdated info | Deprecated methods as current | Medium |
| Incomplete context | Missing edge cases | Medium |
| Subtle errors | Almost-right code | High |
| Style mismatches | Doesn't match project tone | Low |

### Review Checklist

For all AI-assisted contributions:

**Accuracy Verification:**

- [ ] Facts cross-referenced with sources
- [ ] Code tested in actual environment
- [ ] Links verified working
- [ ] Numbers and statistics confirmed
- [ ] Terminology matches project standards

**Quality Verification:**

- [ ] Writing matches project voice
- [ ] Examples are functional
- [ ] Edge cases considered
- [ ] Error handling included
- [ ] No obvious security issues

**AI-Specific Checks:**

- [ ] No hallucinated content
- [ ] No fake citations or URLs
- [ ] No copyrighted material
- [ ] No proprietary code
- [ ] Bias not present

### Review Documentation

Document your review process:

```markdown
## AI Usage Disclosure

- AI Tools Used: Claude 3.5 Sonnet
- Assistance Type: Drafting, code generation
- Human Review: Complete

### Review Verification

- [x] Code tested and working
- [x] Links verified
- [x] Style checked
- [x] Security reviewed
- [x] Accuracy verified

**Reviewer:** [Your Name]
**Date:** [Date]
```

## Documentation of AI Assistance

### Required Disclosure Format

Include at the top of files with AI assistance:

```markdown
---
ai_disclosure: true
ai_tools:
  - tool: Claude
    version: 3.5 Sonnet
    provider: Anthropic
ai_assistance:
  - content_drafting
  - code_examples
  - formatting
human_review: true
reviewers:
  - name: [Name]
    role: Technical Review
  - name: [Name]
    role: Style Review
---
```

### Simplified Format

For smaller contributions:

```markdown
<!-- AI Disclosure: Claude assisted with initial draft. Human reviewed and verified. -->
```

### What to Document

| Item | Required | Format |
|------|----------|--------|
| AI tools used | Yes | Tool name + version |
| Assistance type | Yes | Categories from list |
| Human review | Yes | Boolean + reviewer names |
| Testing performed | Yes | Checklist items |
| Verification sources | If applicable | Links to sources |

## Quality Standards for AI-Assisted Content

### Content Requirements

| Requirement | Standard | Verification |
|-------------|----------|--------------|
| Accuracy | 100% factual | Source cross-reference |
| Completeness | Covers topic | Outline comparison |
| Actionability | Implementation-ready | Code test |
| Examples | Working code | Execute in environment |
| References | Current links | Click test |

### Code Requirements

| Requirement | Standard | Verification |
|-------------|----------|--------------|
| Functionality | Passes tests | Run test suite |
| Security | No vulnerabilities | Security scan |
| Performance | Reasonable speed | Benchmark if applicable |
| Style | Matches project | Linter check |
| Comments | Clear explanations | Human review |

### Writing Requirements

| Requirement | Standard | Verification |
|-------------|----------|--------------|
| Voice | Matches project style | Editor review |
| Structure | Follows templates | Template check |
| Formatting | Consistent | Automated check |
| Length | Appropriate for topic | Comparison to similar |

## AI Prompt Best Practices

### Effective Prompting

**DO:**

- [ ] Be specific about requirements
- [ ] Specify the target audience
- [ ] Request working code with tests
- [ ] Ask for edge case handling
- [ ] Request verification steps
- [ ] Ask for alternatives compared

**DON'T:**

- [ ] Accept first output without review
- [ ] Use prompts without context
- [ ] Skip testing AI code
- [ ] Ignore style mismatches
- [ ] Use AI for critical decisions without backup

### Prompt Templates

**Documentation Prompt:**

```
Write a [type] section about [topic] for the Awesome Vibecoding Guide.
- Audience: [beginner/intermediate/advanced]
- Tone: [practical/confident/cost-conscious]
- Include: [list requirements]
- Length: [approximate word count]
- Follow existing style: [reference file]
```

**Code Prompt:**

```
Write [function/component] in [language/framework] that:
- Purpose: [description]
- Inputs: [parameters]
- Outputs: [return value]
- Error handling: [approach]
- Include: [test cases]
- Reference: [similar existing code]
```

**Review Prompt:**

```
Review this [code/content] for:
- Accuracy: [what to check]
- Completeness: [what to verify]
- Security: [concerns to address]
- Style: [standards to match]
- Best practices: [patterns to follow]
```

## Verification Checklist

### Before Submission

**For AI-Assisted Content:**

- [ ] AI disclosure form completed
- [ ] All AI tools documented
- [ ] Human review certified
- [ ] Code tested and working
- [ ] Links verified
- [ ] Cross-references checked
- [ ] Style consistency verified
- [ ] No prohibited content
- [ ] License requirements met

**For Reviewers:**

- [ ] Disclosure form complete
- [ ] Review checklist items checked
- [ ] Quality standards met
- [ ] No AI hallucinations detected
- [ ] Code is functional
- [ ] Content is original
- [ ] Style matches

### Automated Checks

This project uses automated AI disclosure checks:

```bash
# Check for required disclosures
npm run ai:check --file=docs/new-section.md

# Verify disclosure completeness
npm run ai:verify --file=docs/new-section.md
```

Pull requests missing required disclosures will be rejected.

## Special Cases

### Bulk AI Contributions

For contributions that are substantially AI-generated:

1. **Full disclosure required** at top of PR
2. **Enhanced review process** with expert reviewer
3. **May require restructuring** for quality
4. **Higher scrutiny** on accuracy

### AI Translation

When using AI for translation:

1. **Disclosure required** - mention AI translation
2. **Native speaker review** recommended
3. **Cultural adaptation** verification needed
4. **Legal terms** need expert review

### AI Code Assistance

For code with AI help:

1. **Testing mandatory** before submission
2. **Security review** required
3. **Performance considerations** documented
4. **Edge cases** identified and handled

## Consequences

### Non-Disclosure Consequences

| Violation | Consequence |
|-----------|-------------|
| First offense | Request to add disclosure |
| Second offense | PR returned for correction |
| Repeated offenses | Review of contribution privileges |
| Intentional concealment | PR rejected, possible ban |

### Quality Failures

| Issue | Consequence |
|-------|-------------|
| Inaccurate content | PR blocked until corrected |
| Non-functional code | PR blocked until fixed |
| Security issues | PR blocked, security review |
| Style violations | PR blocked until fixed |

## Questions and Support

### Getting Help

For questions about AI contribution guidelines:

1. Review this document
2. Check the FAQ below
3. Open a GitHub Discussion
4. Ask in Discord

### Common Questions

**Q: What if AI fixed my typos - do I need to disclose?**

A: No. Minor grammar/spell corrections don't require disclosure. Disclose when AI contributed substantively.

**Q: Can I use AI to review my own contribution?**

A: Yes, but you must disclose AI review assistance and have a human verify the review.

**Q: Does AI disclosure affect my contribution credit?**

A: No. All contributors are credited regardless of AI assistance.

**Q: What if I disagree with a reviewer's AI concern?**

A: Discuss in the PR. Provide evidence for your position. Maintainers make final decisions.

---

**Related Documents:**
- [Contributing Guide](contributing.md)
- [Contributor Levels](contribution-levels.md)
- [Code Review Standards](contribution-review.md)
- [AI-Generated Content Disclaimer](../legal/ai-generated-content.md)
