# Contributing to Personal Skills

Thank you for your interest in contributing! This guide will help you add new skills to this repository.

## Quick Start

1. **Fork and clone** this repository
2. **Create a new branch** for your skill
3. **Add your skill** in a new directory
4. **Test locally** to ensure it works
5. **Submit a pull request**

## Adding a New Skill

### 1. Create Skill Directory

```bash
mkdir my-new-skill
cd my-new-skill
```

### 2. Create SKILL.md

Use the template from `example-skill/resources/template.md`:

```bash
cp example-skill/resources/template.md my-new-skill/SKILL.md
```

### 3. Fill in Skill Details

Edit `SKILL.md` with your skill's:
- **Metadata**: Name, version, description, tags
- **Triggers**: When should this skill activate?
- **Instructions**: Step-by-step what Claude should do
- **Examples**: Show realistic usage scenarios
- **Resources**: List any additional files
- **Notes**: Important considerations or limitations

### 4. Add Resources (Optional)

If your skill needs additional files:

```bash
mkdir my-new-skill/resources
# Add your resource files
```

### 5. Test Locally

Install your skill locally to test:

```bash
# Link to Claude Code skills directory
ln -s $(pwd)/my-new-skill ~/.claude/skills/my-new-skill

# Start Claude Code and test your skill
claude
```

Test scenarios:
- Trigger the skill with slash command
- Try natural language triggers
- Verify all instructions work correctly
- Check edge cases and error handling

### 6. Update Repository README

Add your skill to the "Available Skills" section in `README.md`:

```markdown
### My New Skill
- **Description**: Brief description of what it does
- **Usage**: `/my-skill` or when user mentions "trigger phrase"
- **Location**: `my-new-skill/`
```

## Skill Requirements

### Must Have
- ✅ Unique skill directory name
- ✅ `SKILL.md` file with all required sections
- ✅ Clear and specific triggers
- ✅ Actionable step-by-step instructions
- ✅ At least 2 usage examples
- ✅ Version number (use 1.0.0 for new skills)

### Should Have
- ✅ Resources directory if needed
- ✅ Comprehensive error handling
- ✅ Notes on limitations or caveats
- ✅ Tags for discoverability

### Nice to Have
- ✅ Multiple examples covering different scenarios
- ✅ Best practices documentation
- ✅ Visual diagrams or screenshots
- ✅ Version history

## Code Quality

### Skill Instructions
- Use clear, imperative language
- Break complex tasks into steps
- Include validation checkpoints
- Handle common error cases
- Specify expected outcomes

### Documentation
- Write for clarity, not brevity
- Use proper markdown formatting
- Include code blocks with syntax highlighting
- Link to external resources when helpful

### File Organization
```
my-skill/
├── SKILL.md              # Required: Main skill definition
├── resources/            # Optional: Supporting files
│   ├── templates/        # Code or doc templates
│   ├── examples/         # Extended examples
│   └── guides/           # Additional documentation
└── README.md             # Optional: Skill-specific readme
```

## Testing Checklist

Before submitting:
- [ ] Skill activates on correct triggers
- [ ] All instructions execute successfully
- [ ] Examples are accurate and work as shown
- [ ] No conflicts with existing skills
- [ ] Resources are properly referenced
- [ ] Documentation is clear and complete
- [ ] Tested with Claude Code locally

## Pull Request Process

1. **Create a descriptive PR title**
   ```
   Add [skill-name] skill for [purpose]
   ```

2. **Describe your skill** in the PR description:
   - What problem does it solve?
   - How does it work?
   - Any special requirements or dependencies?

3. **Reference issues** if applicable:
   ```
   Closes #123
   Related to #456
   ```

4. **Wait for review**
   - Address any feedback
   - Make requested changes
   - Update documentation if needed

## Skill Naming Conventions

- Use **kebab-case** for directory names: `my-new-skill`
- Use **descriptive names** that indicate purpose: `code-reviewer`, `api-generator`
- Avoid generic names: `helper`, `utility`, `tool`
- Keep names concise: prefer `db-optimizer` over `database-query-optimizer-tool`

## Versioning

Use [Semantic Versioning](https://semver.org/):
- **1.0.0**: Initial release
- **1.1.0**: New features (backward compatible)
- **1.0.1**: Bug fixes
- **2.0.0**: Breaking changes

Update version in:
- `SKILL.md` metadata
- Version History section

## Getting Help

- Check `example-skill/` for reference implementation
- Read `example-skill/resources/best-practices.md`
- Open an issue for questions
- Review existing skills for patterns

## License

By contributing, you agree that your contributions will be licensed under the MIT License.
