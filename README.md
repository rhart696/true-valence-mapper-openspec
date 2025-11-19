# True Valence Relationship Mapper (OpenSpec Edition)

**Short name:** True Valence Mapper
**Edition type:** Methodology/Tooling Integration
**Status:** 🚧 In Development

## Edition Focus

This edition integrates [OpenSpec](https://github.com/Fission-AI/OpenSpec) for AI-assisted specification generation and spec-driven development.

## About OpenSpec

**OpenSpec** is Fission AI's framework for specification-driven development with AI coding assistants, enabling automated spec generation and validation.

### Key Features
- **AI-Assisted Spec Generation**: Automatically generate specifications from requirements
- **Multi-Agent Support**: Works with Gemini, Claude Code, RooCode, and other AI assistants
- **CLI Integration**: Powerful command-line tools for spec management
- **Validation & Testing**: Built-in spec validation and testing frameworks

**Current Version**: v0.15.0 (Released 2025-11-14)

## Installation

### Prerequisites
- Node.js 18+ or Python 3.11+
- Git
- An AI coding assistant (Claude Code, Gemini, GitHub Copilot, etc.)

### Install OpenSpec

**Via npm (Node.js):**
```bash
npm install -g openspec@0.15.0
```

**Via pip (Python):**
```bash
pip install openspec==0.15.0
```

**From source:**
```bash
git clone https://github.com/Fission-AI/OpenSpec.git
cd OpenSpec
npm install
npm link  # or: pip install -e .
```

### Verify Installation

```bash
openspec --version
# Should output: 0.15.0

openspec help
```

## Integration with True Valence Mapper

This edition explores how OpenSpec's AI-assisted specification framework can enhance relationship mapping:

1. **Auto-Generate Specs**: Generate relationship mapping specifications from natural language requirements
2. **Validation Framework**: Validate relationship data against auto-generated specs
3. **AI Collaboration**: Enable multiple AI agents to work from the same specification
4. **Documentation**: Automatically generate and maintain relationship mapping documentation
5. **Testing**: Create test suites from specifications

## Quick Start

### 1. Initialize OpenSpec Project

```bash
# Create a new OpenSpec project
openspec init true-valence-specs

# Navigate to project
cd true-valence-specs
```

### 2. Generate Specification from Requirements

```bash
# Create requirements file
cat > requirements.txt << 'EOF'
The system should track relationships between people and organizations.
People can have multiple roles in different organizations.
Relationships should have start dates and optional end dates.
The system should validate that start dates come before end dates.
EOF

# Generate specification
openspec generate --input requirements.txt --output specs/relationships.yml
```

### 3. Validate Specification

```bash
# Check specification validity
openspec validate specs/relationships.yml

# Run tests against specification
openspec test specs/relationships.yml
```

### 4. Use with AI Agents

```bash
# Generate prompts for AI agents
openspec prompt specs/relationships.yml --agent claude

# Generate implementation code
openspec implement specs/relationships.yml --language typescript
```

## Project Structure

```
openspec-project/
├── specs/                  # Generated specifications
│   ├── relationships.yml   # Relationship specifications
│   ├── mappings.yml       # Mapping workflow specs
│   └── validations.yml    # Validation rules
├── tests/                 # Auto-generated tests
│   ├── relationship.test.js
│   └── validation.test.js
├── docs/                  # Auto-generated documentation
│   └── api-reference.md
└── openspec.config.yml    # OpenSpec configuration
```

## Usage Examples

### Generate Relationship Spec

```bash
# From natural language
openspec generate \
  --prompt "Create a spec for person-to-organization employment relationships with roles, dates, and departments" \
  --output specs/employment.yml

# From existing code
openspec reverse-engineer \
  --input src/models/relationship.ts \
  --output specs/relationship.yml
```

### Multi-Agent Collaboration

```bash
# Generate agent-specific prompts
openspec prompt specs/employment.yml --agent claude > prompts/claude.md
openspec prompt specs/employment.yml --agent gemini > prompts/gemini.md

# Different agents can now work from the same spec
```

### Validation & Testing

```bash
# Validate specification
openspec validate specs/employment.yml

# Generate test suite
openspec test generate specs/employment.yml --output tests/

# Run tests
openspec test run specs/employment.yml
```

### Documentation Generation

```bash
# Generate markdown documentation
openspec docs generate specs/ --format markdown --output docs/

# Generate interactive API docs
openspec docs generate specs/ --format html --output public/docs/
```

## OpenSpec Configuration

Create `openspec.config.yml`:

```yaml
version: "0.15.0"

project:
  name: "True Valence Mapper"
  description: "Relationship mapping system"

agents:
  - name: claude
    provider: anthropic
    model: claude-sonnet-4-5
  - name: gemini
    provider: google
    model: gemini-2.0

specs:
  directory: specs/
  format: yaml
  validation: strict

testing:
  framework: jest
  coverage: 80%

documentation:
  auto_generate: true
  format: markdown
  output: docs/
```

## CLI Commands

```bash
# Initialize project
openspec init [project-name]

# Generate specification
openspec generate --input <file> --output <file>

# Validate specification
openspec validate <spec-file>

# Generate tests
openspec test generate <spec-file>

# Run tests
openspec test run <spec-file>

# Generate documentation
openspec docs generate <spec-dir>

# Generate agent prompts
openspec prompt <spec-file> --agent <agent-name>

# Reverse-engineer from code
openspec reverse-engineer --input <code-file>

# Watch mode (auto-regenerate on changes)
openspec watch specs/
```

## Integration Features

### RooCode Support (v0.15.0)
OpenSpec v0.15.0 added native support for RooCode:

```bash
openspec prompt specs/relationships.yml --agent roocode
```

### Gemini CLI Integration (v0.15.0)
Enhanced Gemini integration:

```bash
openspec generate --agent gemini --interactive
```

## Resources

- [OpenSpec GitHub Repository](https://github.com/Fission-AI/OpenSpec)
- [OpenSpec Documentation](https://github.com/Fission-AI/OpenSpec#readme)
- [Latest Release (v0.15.0)](https://github.com/Fission-AI/OpenSpec/releases/tag/v0.15.0)
- [Fission AI](https://fission.ai)

## License

This edition follows the license of the True Valence Mapper project.

OpenSpec is separately licensed - see the [OpenSpec repository](https://github.com/Fission-AI/OpenSpec) for details.

---

**Parent Repository**: [true-valence-mapper](https://github.com/rhart696/true-valence-mapper)
**Edition Status**: Tool/Dependency Integration
**Installed Version**: v0.15.0
**Last Updated**: 2025-11-18
