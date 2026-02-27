# Personal Skills for Claude Code

This repository contains custom skills for Claude Code that can be installed via the skills marketplace.

## Quick Start

**First time setup?** Follow the [Setup Instructions](SETUP.md) to publish your repository to GitHub.

**Creating skills?** Check out the [Quick Start Guide](QUICKSTART.md) to get up and running in minutes!

## Installation

### Via Claude Code Marketplace

1. Open Claude Code
2. Run `/skills add https://github.com/kyoko-df/skills`
3. The skills will be automatically discovered and installed

### Manual Installation

```bash
# Clone to your Claude Code skills directory
cd ~/.claude/skills
git clone https://github.com/kyoko-df/skills personal-skills
```

## Available Skills

### Humanizer (去 AI 味)
- **Description**: 去除文档中的 AI 生成痕迹,支持中英文文档。识别并修复 24+ 种 AI 写作模式,包括成语堆砌、空洞排比、宣传语言、模糊归因等
- **Usage**: 当需要去除文档的 AI 味时自动触发,或明确请求"帮我去除这段文字的 AI 味"
- **Location**: `humanizer/`
- **Languages**: 中文 + English
- **Version**: 1.0.0

### Example Skill
- **Description**: A template skill to demonstrate the structure
- **Usage**: `/example` or when user mentions "example task"
- **Location**: `example-skill/`

## Creating New Skills

Each skill should:
1. Be in its own directory
2. Contain a `SKILL.md` file with metadata and instructions
3. Follow the [Claude Code skill format](https://docs.anthropic.com/claude/docs/skills)

### Skill Structure

```
skill-name/
├── SKILL.md          # Required: Skill definition
├── resources/        # Optional: Additional files
└── examples/         # Optional: Usage examples
```

## Contributing

Feel free to add your own skills to this repository! See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

**Quick steps**:
1. Create a new directory for your skill
2. Add a `SKILL.md` file following the format
3. Test the skill locally
4. Submit a pull request

## License

MIT License - See LICENSE file for details

## Documentation

- 🚀 [Quick Start Guide](QUICKSTART.md) - Get started in minutes
- ⚙️ [Setup Instructions](SETUP.md) - Publish to GitHub
- 📋 [Cheat Sheet](CHEATSHEET.md) - Quick reference for common tasks
- 🤝 [Contributing Guide](CONTRIBUTING.md) - How to add new skills
- 📝 [Example Skill](example-skill/) - Reference implementation
- 💡 [Best Practices](example-skill/resources/best-practices.md) - Tips for writing effective skills

## Resources

- [Claude Code Documentation](https://docs.anthropic.com/claude/docs/claude-code)
- [Skills Guide](https://docs.anthropic.com/claude/docs/skills)
- [Example Skills Repository](https://github.com/anthropics/claude-code-skills)
- [Markdown Guide](https://www.markdownguide.org/)
