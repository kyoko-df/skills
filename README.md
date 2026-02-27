# Personal Skills for Claude Code

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Skills](https://img.shields.io/badge/skills-2-blue.svg)](./skills)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Compatible-brightgreen.svg)](https://docs.anthropic.com/claude/docs/claude-code)

This repository contains custom skills for Claude Code that can be installed via the skills marketplace.

## ⚡ Quick Install

```bash
/skills add https://github.com/kyoko-df/skills
```

This will automatically install all skills in this repository to your Claude Code environment.

## Installation Methods

### Method 1: Via Marketplace (Recommended)

In Claude Code, simply run:

```bash
/skills add https://github.com/kyoko-df/skills
```

This will:
- ✅ Automatically clone the repository
- ✅ Discover all skills in the `skills/` directory
- ✅ Make them immediately available for use
- ✅ Enable automatic updates with `/skills update`

### Method 2: Manual Installation

```bash
# Clone to your Claude Code skills directory
cd ~/.claude/skills
git clone https://github.com/kyoko-df/skills kyoko-df-skills

# Verify installation
ls -la kyoko-df-skills/skills/
```

### Method 3: Local Development

```bash
# For developing new skills
git clone https://github.com/kyoko-df/skills
cd skills
ln -s $(pwd)/skills/your-skill ~/.claude/skills/your-skill
```

## Available Skills

### Humanizer (去 AI 味)
- **Description**: 去除文档中的 AI 生成痕迹,支持中英文文档。识别并修复 24+ 种 AI 写作模式,包括成语堆砌、空洞排比、宣传语言、模糊归因等
- **Usage**: 当需要去除文档的 AI 味时自动触发,或明确请求"帮我去除这段文字的 AI 味"
- **Location**: `skills/humanizer/`
- **Languages**: 中文 + English
- **Version**: 1.0.0

### Example Skill
- **Description**: A template skill to demonstrate the structure
- **Usage**: `/example` or when user mentions "example task"
- **Location**: `skills/example-skill/`

## Creating New Skills

Each skill should:
1. Be in its own directory
2. Contain a `SKILL.md` file with metadata and instructions
3. Follow the [Claude Code skill format](https://docs.anthropic.com/claude/docs/skills)

### Repository Structure

```
skills/
├── skills/
│   ├── humanizer/           # Remove AI writing patterns
│   │   ├── SKILL.md
│   │   ├── README.md
│   │   └── resources/
│   └── example-skill/       # Template skill
│       ├── SKILL.md
│       └── resources/
├── README.md
└── CONTRIBUTING.md
```

### Individual Skill Structure

```
skills/skill-name/
├── SKILL.md          # Required: Skill definition
├── README.md         # Optional: Skill documentation
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

- 🤝 [Contributing Guide](CONTRIBUTING.md) - How to add new skills
- 📝 [Example Skill](skills/example-skill/) - Reference implementation
- 💡 [Best Practices](skills/example-skill/resources/best-practices.md) - Tips for writing effective skills

## Resources

- [Claude Code Documentation](https://docs.anthropic.com/claude/docs/claude-code)
- [Skills Guide](https://docs.anthropic.com/claude/docs/skills)
- [Example Skills Repository](https://github.com/anthropics/claude-code-skills)
- [Markdown Guide](https://www.markdownguide.org/)
