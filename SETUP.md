# Setup Instructions

Follow these steps to publish your skills repository and make it available in Claude Code.

## Step 1: Update Repository Information

### 1.1 Update README.md

Replace `YOUR_USERNAME` with your GitHub username:

```bash
# macOS
sed -i '' 's/YOUR_USERNAME/your-github-username/g' README.md

# Linux
sed -i 's/YOUR_USERNAME/your-github-username/g' README.md
```

Or manually edit `README.md` and replace all instances of `YOUR_USERNAME`.

### 1.2 Update LICENSE

Edit `LICENSE` file and replace `[Your Name]` with your actual name:

```bash
# macOS
sed -i '' 's/\[Your Name\]/Your Actual Name/g' LICENSE

# Linux
sed -i 's/\[Your Name\]/Your Actual Name/g' LICENSE
```

### 1.3 Commit Changes

```bash
git add README.md LICENSE
git commit -m "chore: update repository information"
```

## Step 2: Create GitHub Repository

### Option A: Using GitHub CLI

```bash
# Create public repository
gh repo create skills --public --source=. --remote=origin

# Push to GitHub
git push -u origin main
```

### Option B: Using GitHub Web Interface

1. Go to https://github.com/new
2. Repository name: `skills`
3. Description: "Custom skills for Claude Code"
4. Choose Public or Private
5. **Don't initialize** with README (we already have one)
6. Click "Create repository"

7. Add remote and push:
```bash
git remote add origin https://github.com/YOUR_USERNAME/skills.git
git push -u origin main
```

## Step 3: Verify Repository

Visit your repository on GitHub:
```
https://github.com/YOUR_USERNAME/skills
```

Check that:
- [ ] README.md displays correctly
- [ ] example-skill/ directory is visible
- [ ] All documentation files are present
- [ ] GitHub Actions workflow is enabled (if public)

## Step 4: Install in Claude Code

### For Yourself

```bash
# In Claude Code, run:
/skills add https://github.com/YOUR_USERNAME/skills
```

This will:
1. Clone the repository to `~/.claude/skills/`
2. Discover all SKILL.md files
3. Make skills available for use

### For Others

Share the installation command:
```bash
/skills add https://github.com/YOUR_USERNAME/skills
```

**For private repositories**: Users need GitHub access to your repo.

## Step 5: Test Your Skills

### 5.1 Verify Installation

```bash
# List installed skills
ls ~/.claude/skills/

# Check if your skills are linked
ls -la ~/.claude/skills/ | grep skills
```

### 5.2 Test Example Skill

In Claude Code:
```
User: /example
```

Or:
```
User: Show me an example task
```

Claude should activate the example skill.

## Step 6: Create Your First Custom Skill

### 6.1 Create New Skill

```bash
# In your skills repository
mkdir my-custom-skill
cd my-custom-skill

# Copy template
cp ../example-skill/resources/template.md SKILL.md

# Edit SKILL.md
# - Update metadata (name, version, description)
# - Define triggers
# - Write instructions
# - Add examples
```

### 6.2 Test Locally

```bash
# Link skill to Claude Code
ln -s $(pwd) ~/.claude/skills/my-custom-skill

# Start Claude Code and test
claude
```

Try your skill:
```
User: /my-custom-skill
```

### 6.3 Commit and Push

```bash
git add my-custom-skill/
git commit -m "feat: add my-custom-skill"
git push origin main
```

### 6.4 Update in Claude Code

```bash
# In Claude Code, update skills
/skills update
```

Or manually:
```bash
cd ~/.claude/skills/skills
git pull origin main
```

## Troubleshooting

### Skill Not Found

**Problem**: Claude Code doesn't recognize your skill

**Solutions**:
1. Check SKILL.md exists in skill directory
2. Verify skill is linked in `~/.claude/skills/`
3. Restart Claude Code
4. Try explicit command: `/skill-name`

```bash
# Verify structure
ls -R ~/.claude/skills/skills/

# Re-link if needed
cd ~/.claude/skills
rm -rf skills
/skills add https://github.com/YOUR_USERNAME/skills
```

### Skill Not Activating

**Problem**: Skill exists but doesn't trigger

**Solutions**:
1. Check trigger conditions in SKILL.md
2. Use more specific triggers
3. Try slash command instead of natural language
4. Check for conflicts with other skills

```bash
# Test with explicit command
/skill-name

# Check skill file
cat ~/.claude/skills/skills/skill-name/SKILL.md
```

### Git Push Fails

**Problem**: Authentication error when pushing

**Solutions**:

For HTTPS:
```bash
# Use personal access token
git remote set-url origin https://YOUR_TOKEN@github.com/YOUR_USERNAME/skills.git
```

For SSH:
```bash
# Switch to SSH
git remote set-url origin git@github.com:YOUR_USERNAME/skills.git
```

### Changes Not Reflected

**Problem**: Updated skill but Claude Code shows old version

**Solutions**:
```bash
# Update skills in Claude Code
/skills update

# Or manually pull
cd ~/.claude/skills/skills
git pull origin main

# Restart Claude Code
```

## Advanced Setup

### Multiple Skill Repositories

You can install multiple skill repositories:

```bash
/skills add https://github.com/user1/skills
/skills add https://github.com/user2/awesome-skills
/skills add https://github.com/company/team-skills
```

Each repository is cloned to a separate directory in `~/.claude/skills/`.

### Custom Installation Path

```bash
# Clone to specific location
cd ~/.claude/skills
git clone https://github.com/YOUR_USERNAME/skills my-custom-name

# Skills will be available as:
/my-custom-name/skill-name
```

### Private Repository Access

For private repositories:

1. **Personal Access Token** (HTTPS):
   ```bash
   git clone https://TOKEN@github.com/YOUR_USERNAME/skills.git
   ```

2. **SSH Key** (recommended):
   ```bash
   git clone git@github.com:YOUR_USERNAME/skills.git
   ```

3. **GitHub CLI**:
   ```bash
   gh repo clone YOUR_USERNAME/skills
   ```

### Auto-Update Skills

Create a script to update all skills:

```bash
#!/bin/bash
# ~/.claude/scripts/update-skills.sh

echo "Updating Claude Code skills..."

for dir in ~/.claude/skills/*/; do
  if [ -d "$dir/.git" ]; then
    echo "Updating $(basename $dir)..."
    cd "$dir"
    git pull origin main
  fi
done

echo "All skills updated!"
```

Make it executable:
```bash
chmod +x ~/.claude/scripts/update-skills.sh
```

Run periodically:
```bash
~/.claude/scripts/update-skills.sh
```

## Next Steps

1. ✅ Repository created and pushed to GitHub
2. ✅ Skills installed in Claude Code
3. ✅ Example skill tested
4. 📝 Create your first custom skill
5. 📝 Share with team or community
6. 📝 Contribute to documentation

## Resources

- [Quick Start Guide](QUICKSTART.md)
- [Contributing Guide](CONTRIBUTING.md)
- [Example Skill](example-skill/)
- [Claude Code Documentation](https://docs.anthropic.com/claude/docs/claude-code)

## Getting Help

- **Issues**: Open an issue in this repository
- **Discussions**: Use GitHub Discussions
- **Documentation**: Check Claude Code docs
- **Community**: Join Claude Code community forums

---

**Ready to share your skills?** Push to GitHub and start using them in Claude Code!
