# Skills Repository Cheat Sheet

Quick reference for common tasks and commands.

## Initial Setup

```bash
# 1. Update repository information
sed -i '' 's/YOUR_USERNAME/your-github-username/g' README.md
sed -i '' 's/\[Your Name\]/Your Actual Name/g' LICENSE
git add README.md LICENSE
git commit -m "chore: update repository information"

# 2. Create GitHub repository and push
gh repo create skills --public --source=. --remote=origin
git push -u origin main

# 3. Install in Claude Code
/skills add https://github.com/your-github-username/skills
```

## Creating a New Skill

```bash
# Create skill directory
mkdir my-skill-name && cd my-skill-name

# Copy template
cp ../example-skill/resources/template.md SKILL.md

# Edit SKILL.md (update all sections)
# - Metadata: name, version, description, tags
# - Triggers: when to activate
# - Instructions: step-by-step actions
# - Examples: usage scenarios

# Create resources if needed
mkdir resources

# Test locally
ln -s $(pwd) ~/.claude/skills/my-skill-name

# Commit and push
cd ..
git add my-skill-name/
git commit -m "feat: add my-skill-name skill"
git push origin main
```

## Skill Template Quick Fill

```markdown
# [Skill Name]

## Metadata
- **Name**: My Skill Name
- **Version**: 1.0.0
- **Author**: Your Name
- **Description**: Brief description of what this skill does
- **Tags**: tag1, tag2, tag3

## Triggers
Use this skill when:
- User explicitly requests `/my-skill`
- User mentions "specific keywords"

## Instructions
1. **First step**: Do something
2. **Second step**: Do something else
3. **Final step**: Complete the task

## Examples
### Example 1
\```
User: Do something
Claude: [Response]
\```

## Notes
- Important considerations
- Limitations
```

## Common Commands

### Git Operations
```bash
# Check status
git status

# Stage all changes
git add .

# Commit with message
git commit -m "type: description"

# Push to GitHub
git push origin main

# View commit history
git log --oneline

# Undo last commit (keep changes)
git reset --soft HEAD~1
```

### Claude Code Operations
```bash
# Install skills from repository
/skills add https://github.com/username/skills

# Update installed skills
/skills update

# List installed skills
ls ~/.claude/skills/

# Test a skill
/skill-name

# Check skill file
cat ~/.claude/skills/skills/skill-name/SKILL.md
```

### Testing Skills Locally
```bash
# Link skill to Claude Code
ln -s /path/to/skills/my-skill ~/.claude/skills/my-skill

# Remove link
rm ~/.claude/skills/my-skill

# Check if linked
ls -la ~/.claude/skills/ | grep my-skill

# Test in Claude Code
claude
# Then: /my-skill
```

### Troubleshooting
```bash
# Skill not found - re-install
cd ~/.claude/skills
rm -rf skills
/skills add https://github.com/username/skills

# Skill not activating - check file
cat ~/.claude/skills/skills/skill-name/SKILL.md

# Update not working - manual pull
cd ~/.claude/skills/skills
git pull origin main

# Permission issues - fix ownership
sudo chown -R $USER:$USER ~/.claude/skills/
```

## Commit Message Format

```
type: description

Types:
- feat: New skill or feature
- fix: Bug fix
- docs: Documentation only
- chore: Maintenance (no code change)
- refactor: Code change (no functionality change)
- test: Adding tests
- ci: CI/CD changes

Examples:
feat: add code-reviewer skill
fix: correct trigger conditions in example-skill
docs: update installation instructions
chore: update dependencies
```

## File Structure Reference

```
skill-name/
├── SKILL.md              # Required
├── resources/            # Optional
│   ├── templates/
│   ├── examples/
│   └── guides/
└── README.md             # Optional
```

## Required SKILL.md Sections

```markdown
## Metadata          # Name, Version, Author, Description, Tags
## Triggers          # When to activate this skill
## Instructions      # Step-by-step what to do
## Examples          # Usage scenarios
## Notes             # Optional: considerations, limitations
## Version History   # Optional: version changes
```

## Common Patterns

### Code Generation Skill
```markdown
## Instructions
1. **Analyze** requirements from user
2. **Read** existing code for context
3. **Generate** code following patterns
4. **Validate** correctness
5. **Explain** changes
```

### Analysis Skill
```markdown
## Instructions
1. **Gather** context by reading files
2. **Apply** analysis framework
3. **Generate** findings with examples
4. **Prioritize** by severity
5. **Recommend** solutions
```

### Workflow Skill
```markdown
## Instructions
1. **Verify** prerequisites
2. **Execute** steps in order
3. **Check** results after each step
4. **Handle** errors gracefully
5. **Confirm** completion
```

## Quick Links

- 📖 [README](README.md) - Main documentation
- 🚀 [QUICKSTART](QUICKSTART.md) - Getting started guide
- ⚙️ [SETUP](SETUP.md) - GitHub setup instructions
- 🤝 [CONTRIBUTING](CONTRIBUTING.md) - Contribution guidelines
- 📝 [Example Skill](example-skill/SKILL.md) - Reference implementation
- 💡 [Best Practices](example-skill/resources/best-practices.md) - Tips and patterns

## Keyboard Shortcuts (Claude Code)

```
/skill-name          Explicitly invoke a skill
Ctrl+C              Cancel current operation
Ctrl+D              Exit Claude Code
↑/↓                 Navigate command history
Tab                 Auto-complete (if available)
```

## Useful Scripts

### Update All Skills
```bash
#!/bin/bash
for dir in ~/.claude/skills/*/; do
  if [ -d "$dir/.git" ]; then
    echo "Updating $(basename $dir)..."
    (cd "$dir" && git pull origin main)
  fi
done
```

### Validate Skill Structure
```bash
#!/bin/bash
skill_file="$1/SKILL.md"
if [ ! -f "$skill_file" ]; then
  echo "❌ SKILL.md not found"
  exit 1
fi

grep -q "## Metadata" "$skill_file" && echo "✅ Metadata" || echo "❌ Metadata"
grep -q "## Triggers" "$skill_file" && echo "✅ Triggers" || echo "❌ Triggers"
grep -q "## Instructions" "$skill_file" && echo "✅ Instructions" || echo "❌ Instructions"
```

## Environment Variables

```bash
# Claude Code skills directory
~/.claude/skills/

# Installed skills location
~/.claude/skills/skills/

# Individual skill
~/.claude/skills/skills/skill-name/
```

## Version Numbers (Semantic Versioning)

```
MAJOR.MINOR.PATCH

1.0.0 - Initial release
1.1.0 - New features (backward compatible)
1.0.1 - Bug fixes
2.0.0 - Breaking changes

Examples:
1.0.0 → 1.0.1  Bug fix
1.0.1 → 1.1.0  New feature
1.1.0 → 2.0.0  Breaking change
```

## Resources

- [Claude Code Docs](https://docs.anthropic.com/claude/docs/claude-code)
- [Skills Guide](https://docs.anthropic.com/claude/docs/skills)
- [Markdown Guide](https://www.markdownguide.org/)
- [Semantic Versioning](https://semver.org/)
- [GitHub CLI](https://cli.github.com/)

---

**Print this cheat sheet** for quick reference while creating skills!
