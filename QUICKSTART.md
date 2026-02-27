# Quick Start Guide

Get your skills repository up and running in minutes.

## Prerequisites

- Claude Code installed
- Git configured
- GitHub account (for publishing)

## Setup Your Repository

### 1. Update README.md

Replace `YOUR_USERNAME` in `README.md` with your actual GitHub username:

```bash
sed -i '' 's/YOUR_USERNAME/your-actual-username/g' README.md
```

### 2. Update LICENSE

Edit `LICENSE` file and replace `[Your Name]` with your name.

### 3. Create Your First Skill

```bash
# Copy the example skill as a template
cp -r skills/example-skill my-first-skill

# Edit the SKILL.md file
# Update metadata, triggers, and instructions
```

### 4. Test Locally

```bash
# Link to Claude Code skills directory
ln -s $(pwd)/my-first-skill ~/.claude/skills/my-first-skill

# Start Claude Code
claude

# Test your skill
/my-first-skill
```

### 5. Commit and Push

```bash
git add .
git commit -m "feat: add my-first-skill"
git push origin main
```

## Publishing to Marketplace

### Option 1: Public Repository

1. **Push to GitHub**:
   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/skills.git
   git push -u origin main
   ```

2. **Users can install via**:
   ```bash
   /skills add https://github.com/YOUR_USERNAME/skills
   ```

### Option 2: Private Repository

1. **Push to private GitHub repo**
2. **Share installation link with team**:
   ```bash
   /skills add https://github.com/YOUR_USERNAME/skills
   ```
   (Users need repo access)

## Creating a New Skill

### Quick Template

```bash
# Create skill directory
mkdir my-new-skill
cd my-new-skill

# Copy template
cp ../skills/example-skill/resources/template.md SKILL.md

# Edit SKILL.md with your content
# - Update metadata (name, description, tags)
# - Define triggers (when to activate)
# - Write step-by-step instructions
# - Add usage examples

# Create resources directory if needed
mkdir resources

# Test locally
ln -s $(pwd) ~/.claude/skills/my-new-skill
```

### Skill Checklist

- [ ] Unique directory name (kebab-case)
- [ ] `SKILL.md` with all sections
- [ ] Clear trigger conditions
- [ ] Step-by-step instructions
- [ ] At least 2 examples
- [ ] Tested locally
- [ ] README.md updated

## Common Skill Patterns

### Code Generation Skill

```markdown
## Triggers
Use this skill when user requests "generate [type] code"

## Instructions
1. **Analyze requirements** from user input
2. **Read existing code** to match style
3. **Generate code** following patterns
4. **Validate** for correctness
5. **Explain** changes made
```

### Analysis Skill

```markdown
## Triggers
Use this skill when user requests "analyze [target]"

## Instructions
1. **Gather context** by reading files
2. **Apply framework** from resources
3. **Generate findings** with examples
4. **Prioritize** by severity
5. **Recommend** solutions
```

### Workflow Skill

```markdown
## Triggers
Use this skill when user requests "/workflow-name"

## Instructions
1. **Verify prerequisites** are met
2. **Execute steps** in order
3. **Check results** after each step
4. **Handle errors** gracefully
5. **Confirm completion**
```

## Troubleshooting

### Skill Not Activating

1. Check trigger conditions in `SKILL.md`
2. Verify skill is linked in `~/.claude/skills/`
3. Restart Claude Code
4. Try explicit slash command: `/skill-name`

### Skill Conflicts

1. Use more specific triggers
2. Add unique slash command
3. Check for naming conflicts
4. Review trigger keywords

### Skill Not Found

```bash
# Check if skill is linked
ls -la ~/.claude/skills/

# Re-link if needed
ln -s /path/to/your/skills/my-skill ~/.claude/skills/my-skill

# Verify SKILL.md exists
ls my-skill/SKILL.md
```

## Best Practices

### DO ✅
- Use descriptive, unique names
- Write clear, actionable instructions
- Test thoroughly before publishing
- Include multiple examples
- Document limitations
- Version your skills
- Keep instructions focused

### DON'T ❌
- Use vague or generic names
- Write ambiguous instructions
- Skip testing
- Forget examples
- Hide important details
- Hardcode paths or values
- Make instructions too complex

## Next Steps

1. **Read** `CONTRIBUTING.md` for detailed guidelines
2. **Review** `skills/example-skill/resources/best-practices.md`
3. **Create** your first custom skill
4. **Test** locally with Claude Code
5. **Share** with the community

## Resources

- [Claude Code Documentation](https://docs.anthropic.com/claude/docs/claude-code)
- [Skills Guide](https://docs.anthropic.com/claude/docs/skills)
- [Markdown Guide](https://www.markdownguide.org/)
- [Semantic Versioning](https://semver.org/)

## Getting Help

- Check existing skills for examples
- Open an issue in this repository
- Review Claude Code documentation
- Join Claude Code community discussions

---

**Ready to create your first skill?** Start with the example skill and customize it for your needs!
