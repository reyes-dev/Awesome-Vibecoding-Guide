# Contributor AI Disclosure Requirements

> Guidelines for documenting and disclosing AI assistance in contributions to the Awesome Vibecoding Guide.

## Purpose

This document establishes requirements for disclosing AI assistance in contributions to ensure transparency, maintain quality standards, and comply with licensing requirements.

## When Disclosure Is Required

### Mandatory Disclosure

You **must** disclose AI assistance when:

| Scenario | Disclosure Required |
|----------|---------------------|
| AI generated code examples | Yes |
| AI wrote documentation sections | Yes |
| AI refined or edited your writing | Yes |
| AI helped with formatting | Yes |
| AI generated images or diagrams | Yes |
| AI reviewed or suggested changes | Yes |

### Examples of Required Disclosure

```
✅ "I used Claude to help draft this section on prompt engineering"
✅ "ChatGPT assisted with code examples in the automation chapter"
✅ "This documentation was written with AI assistance and reviewed by humans"
```

### When Disclosure Is Optional

Disclosure is optional when:
- AI used only for spell-checking or grammar
- AI used for translation with human review
- AI used for research/reference lookup
- Minimal AI suggestions (single words/phrases)

## Documentation Requirements

### AI Tool Disclosure Format

Include the following in your contribution:

```markdown
---
ai_disclosure: true
ai_tools:
  - tool_name: Claude
    provider: Anthropic
    version: Claude 3.5 Sonnet
  - tool_name: ChatGPT
    provider: OpenAI
    version: GPT-4
ai_assistance_type:
  - Code generation
  - Documentation writing
  - Editing/review
human_review: true
reviewer_names:
  - Reviewer 1
  - Reviewer 2
---
```

### Simplified Disclosure Format

For smaller contributions, use:

```markdown
<!-- AI Disclosure: Claude (Anthropic) assisted with code examples. Human reviewed. -->
```

### Required Information

At minimum, disclose:

1. **Tool(s) Used**: Name and provider
2. **Version/Model**: e.g., "GPT-4", "Claude 3.5 Sonnet"
3. **Assistance Type**: What the AI helped with
4. **Human Review**: Confirmation of review

## Human Review Requirements

### Why Human Review Is Required

AI-generated content requires human review because:
- AI may generate incorrect or outdated information
- Code may contain security vulnerabilities
- Writing may not match project voice
- Hallucinations must be caught and corrected

### Review Checklist

Human reviewers must verify:

| Check | Description |
|-------|-------------|
| Accuracy | Information is correct and current |
| Completeness | Content covers the topic adequately |
| Security | Code has no obvious vulnerabilities |
| Style | Matches project conventions |
| Links | All references work and are current |
| Examples | Code examples are functional |
| Bias | No harmful or biased content |

### Review Documentation

Reviewers should document:

```markdown
## Human Review Certification

- [x] Content accuracy verified
- [x] Code examples tested
- [x] Security reviewed
- [x] Style consistency confirmed
- [x] Links verified

**Reviewer:** [Name]
**Date:** [Date]
**Tools Used:** Claude, manual testing
```

## Attribution of AI-Assisted Work

### Proper Attribution

When AI assists with contributions:

1. **Credit the AI Contribution**: Be transparent about AI role
2. **Maintain License Compliance**: Ensure AI-generated content uses appropriate licenses
3. **Document Changes**: Track what AI changed vs. human input

### Attribution Examples

| Contribution Type | Attribution Format |
|-------------------|-------------------|
| Full AI draft | "AI-generated draft with human review" |
| AI-assisted writing | "Written with AI assistance" |
| AI code help | "Code with AI suggestions" |
| AI review | "Reviewed with AI assistance" |

### License Implications

If AI generates substantial content:
- The content inherits this project's MIT license
- You must include the AI disclosure
- Third parties must be informed of AI involvement

## Quality Standards for AI-Assisted Content

### Content Requirements

All AI-assisted content must meet:

| Requirement | Standard |
|-------------|----------|
| Accuracy | Factual correctness verified |
| Completeness | Covers topic adequately |
| Actionability | Contains implementation guidance |
| Examples | Working code with tests |
| References | Links to sources verified |

### Style Requirements

AI-assisted content must:
- Match project voice and tone
- Follow formatting conventions
- Use consistent terminology
- Include appropriate emojis
- Match section structures

### Code Requirements

AI-generated code must:
- Be tested before submission
- Include appropriate comments
- Follow language best practices
- Include error handling
- Have no hardcoded secrets

## Verification Checklist

### Before Submitting

Contributors must verify:

- [ ] AI disclosure completed accurately
- [ ] All AI tools and versions documented
- [ ] Human review completed and certified
- [ ] Content meets quality standards
- [ ] Code examples are tested
- [ ] Links and references verified
- [ ] No prohibited content included
- [ ] License requirements met

### For Reviewers

Reviewers must verify:

- [ ] Disclosure form is complete
- [ ] Human review certification present
- [ ] Quality standards met
- [ ] No obvious AI hallucinations
- [ ] Code is functional
- [ ] Content is original (not copied)
- [ ] Style consistency maintained

## Consequences of Non-Disclosure

### Failure to Disclose

If AI assistance is not disclosed:

| Violation | Consequence |
|-----------|-------------|
| First offense | Request to add disclosure |
| Second offense | Contribution returned for correction |
| Repeated offenses | Review of contribution privileges |
| Intentional concealment | Contribution rejected |

### Disputed Disclosures

If you believe disclosure was incorrectly required:
1. Open a discussion in GitHub Issues
2. Provide evidence of minimal AI use
3. Maintainers will review and decide

## Special Cases

### Bulk AI Contributions

For contributions that are substantially AI-generated:
- Full disclosure required
- Enhanced review process
- May require restructuring for quality

### AI Translation

When using AI for translation:
- Disclosure required
- Native speaker review recommended
- Cultural adaptation verification

### AI Code Assistance

For code with AI help:
- Testing required before submission
- Security review mandatory
- Performance considerations noted

## Tools and Automation

### AI Disclosure Tool

This project provides tools to help with disclosure:

```bash
# Check if disclosure is needed
python scripts/check_ai_disclosure.py --file docs/new-section.md

# Generate disclosure template
python scripts/generate_disclosure.py --tools "Claude,ChatGPT"
```

### Automated Checks

Pull requests are checked for:
- Missing AI disclosures
- Incomplete disclosure information
- Expired review certifications

## Questions and Support

### Getting Help

For questions about disclosure requirements:
- Review this document
- Check the [FAQ](#frequently-asked-questions)
- Open a GitHub Discussion
- Contact maintainers

### Reporting Violations

Report suspected non-compliance:
1. Open a private issue
2. Include evidence of non-disclosure
3. Maintainers will investigate

## Frequently Asked Questions

### "What if I used AI but it only fixed typos?"

Minor edits like spell-checking don't require disclosure. Use judgment based on the "Assistance Type" matrix above.

### "Can I refuse to disclose AI use?"

No. Non-disclosure is a violation of contribution terms and may result in contribution rejection.

### "Does AI disclosure affect my contribution credit?"

No. Contributors are credited regardless of AI assistance, as long as disclosure and quality standards are met.

### "Can I use AI for review only?"

Yes. AI-assisted review requires disclosure and the reviewer must be named in the disclosure.

## Related Documents

- [Contribution Guidelines](../appendix/contributing.md)
- [AI-Generated Content Disclaimer](ai-generated-content.md)
- [Repository License](repository-license.md)
- [Quality Standards](quality-standards.md)

---

**Document Version:** 1.0.0
**Last Updated:** January 2025
