# Skill Best Practices

## Writing Effective Skills

### 1. Clear Metadata
- Use descriptive names that indicate the skill's purpose
- Keep descriptions concise (1-2 sentences)
- Add relevant tags for discoverability
- Include version numbers for tracking changes

### 2. Specific Triggers
- Define clear activation conditions
- Use unique keywords to avoid conflicts
- Consider slash commands for explicit invocation
- Document when the skill should NOT be used

### 3. Actionable Instructions
- Write step-by-step procedures
- Use imperative language ("Do X", not "You could do X")
- Include validation steps
- Specify expected outcomes
- Handle error cases

### 4. Comprehensive Examples
- Show realistic use cases
- Include both simple and complex scenarios
- Demonstrate edge cases
- Use actual code/commands when relevant

### 5. Resource Organization
- Keep related files in the `resources/` directory
- Use clear, descriptive filenames
- Document what each resource file contains
- Keep files focused and modular

## Common Patterns

### Code Generation Skills
```markdown
## Instructions
1. **Analyze requirements** from user input
2. **Check existing code** to maintain consistency
3. **Generate code** following project patterns
4. **Validate output** for correctness
5. **Explain changes** to the user
```

### Analysis Skills
```markdown
## Instructions
1. **Gather context** by reading relevant files
2. **Apply analysis framework** defined in resources
3. **Generate findings** with specific examples
4. **Prioritize issues** by severity
5. **Provide recommendations** with rationale
```

### Workflow Skills
```markdown
## Instructions
1. **Verify prerequisites** are met
2. **Execute steps** in defined order
3. **Check results** after each step
4. **Handle errors** gracefully
5. **Confirm completion** with user
```

## Testing Your Skills

### Local Testing
1. Install skill in `~/.claude/skills/`
2. Start Claude Code
3. Trigger the skill with test cases
4. Verify behavior matches expectations
5. Iterate based on results

### Quality Checklist
- [ ] Metadata is complete and accurate
- [ ] Triggers are specific and non-conflicting
- [ ] Instructions are clear and actionable
- [ ] Examples cover main use cases
- [ ] Resources are well-organized
- [ ] Documentation is up-to-date
- [ ] Skill works as expected in testing

## Common Pitfalls

### ❌ Avoid
- Vague or ambiguous instructions
- Overly broad trigger conditions
- Missing error handling
- Incomplete examples
- Outdated documentation
- Hardcoded paths or values
- Conflicting with built-in functionality

### ✅ Do
- Be specific and prescriptive
- Use targeted triggers
- Handle edge cases
- Provide realistic examples
- Keep documentation current
- Use relative paths or parameters
- Complement existing features

## Versioning

Use semantic versioning (MAJOR.MINOR.PATCH):
- **MAJOR**: Breaking changes
- **MINOR**: New features, backward compatible
- **PATCH**: Bug fixes

Document changes in Version History section.

## Distribution

### Public Skills
- Host on GitHub
- Use clear README
- Include LICENSE
- Provide installation instructions
- Accept community contributions

### Private Skills
- Keep in private repository
- Share installation link with team
- Document any dependencies
- Maintain consistent structure

## Resources

- [Claude Code Documentation](https://docs.anthropic.com/claude/docs/claude-code)
- [Skills Guide](https://docs.anthropic.com/claude/docs/skills)
- [Markdown Guide](https://www.markdownguide.org/)
