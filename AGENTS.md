# OpenCode Global Rules for This Project

## Project Overview

This is an OpenCode plugin project using the `@opencode-ai/plugin` dependency.

## Development Guidelines

### Code Style
- Use TypeScript for type safety
- Follow existing code patterns in the `.opencode/node_modules/@opencode-ai/plugin/dist/` directory for reference
- Maintain consistent code structure with the plugin examples

### File Organization
- Source files should follow the plugin's module structure
- Use the `.opencode/agents/` directory for custom agent definitions
- Use the `.opencode/config.json` for project-specific configurations

### Testing
- Before committing changes, ensure all functionality works correctly
- Test any new agents or tools before deployment

### Documentation
- Update AGENTS.md when adding new agents or changing project structure
- Document any new tools or custom commands in the project

## Agent Configuration

### Available Agents
- **build**: Primary agent for development work with all tools enabled
- **plan**: Primary agent for planning and analysis (restricted mode)
- **general**: Subagent for general research and multi-step tasks
- **explore**: Subagent for fast codebase exploration (read-only)

### Custom Agents
Place custom agent markdown files in `.opencode/agents/` directory following the naming convention `{agent-name}.md`

## Project-Specific Tools

### Plugin Development
When working with the plugin:
- Reference existing implementation in `.opencode/node_modules/@opencode-ai/plugin/dist/`
- The plugin exports tool functionality and Zod schema validation
- Follow the plugin's API structure when extending functionality

## Commands

### Testing
- Run `opencode models` to list available models
- Use `/connect` to configure provider connections
- Use `/init` to reinitialize the project (updates AGENTS.md)

### Development Workflow
1. Use `plan` agent (Tab key) to analyze and plan changes
2. Switch to `build` agent to implement the planned changes
3. Use `@general` or `@explore` subagents for specific tasks
4. Use `/undo` to revert changes if needed
5. Use `/redo` to restore undone changes

## Notes

- This project is not a git repository - use version control if needed
- The AGENTS.md file should be committed to version control when git is initialized
- OpenCode will automatically load and apply rules from this file