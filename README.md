# ServiceNow SDK

The ServiceNow IDE and ServiceNow SDK support developing applications in source code with ServiceNow Fluent, creating JavaScript modules, and using third-party libraries. ServiceNow Fluent is a TypeScript-based domain-specific programming language for creating application metadata in code.

# AI Skills

This repository contains agent skills for creating, editing, and deploying ServiceNow Fluent applications. These skills teach AI coding assistants how to use the [`@servicenow/sdk`](https://www.npmjs.com/package/@servicenow/sdk) CLI to look up platform conventions, metadata types, and project structure before making changes.

> [!IMPORTANT]
> These skills rely on features available only in version `4.6.0` or newer of the SDK.

## Skills

| Skill | Description |
|---|---|
| **now-sdk** | Covers CLI discovery, SDK documentation, and live instance queries. Automatically triggered when working in a Fluent app or when ServiceNow/Fluent topics are mentioned. Uses `npx @servicenow/sdk --help` and `explain quickstart` to orient the agent, then provides guidance for the `explain` and `query` subcommands. |

## Setup by Tool

### Claude Code

1. Start a Claude Code session.
2. Install the `servicenow-sdk` plugin from the `claude-plugins-official` marketplace:
   ```
   /plugin install servicenow-sdk@claude-plugins-official
   /reload-plugins
   ```

### Codex

1. Start a Codex session.
2. Run the following command to directly install the skill:
   ```
   $skill-installer https://github.com/ServiceNow/sdk/tree/master/skills/now-sdk
   ```
3. Restart Codex to load the skill.

### Cursor

1. Open Cursor Settings (Cmd+Shift+J).
2. Navigate to **Plugins**.
3. Paste in the link to the repo: `https://github.com/ServiceNow/sdk.git`
4. Select `Add to Cursor` for the `servicenow-sdk` plugin.

Alternatively, loading the skills into Claude Code will also allow Cursor to use them.

### GitHub Copilot

1. Update GitHub CLI to version `2.90.0` or later, then install the skill directly from this repo:
   ```
   gh skill install ServiceNow/sdk now-sdk
   ```
   By default this installs the skill as a project skill in `.github/skills/now-sdk`. Add `--scope user` to install it as a personal skill (`~/.copilot/skills/now-sdk`) shared across all your projects instead.
2. In an open Copilot CLI session, run `/skills reload`, or start a new session to load the skill.
3. Confirm it loaded with `/skills info now-sdk`.

Alternatively, without GitHub CLI, manually copy the [`skills/now-sdk`](skills/now-sdk) directory into `.github/skills/now-sdk` (project) or `~/.copilot/skills/now-sdk` (personal), then run `/skills reload`.

### Grok

1. Start a Grok session.
2. Add the marketplace and install the plugin:
   ```
   grok plugin marketplace add servicenow/sdk
   grok plugin install servicenow-sdk --trust
   ```
3. Restart Grok or run `/plugins` and reload plugins to load the skill.

Alternatively, install the plugin directly without adding the marketplace:
```
grok plugin install servicenow/sdk#providers/grok/plugin --trust
```

### Kiro

The [`providers/kiro/`](providers/kiro/) directory contains a Power with steering files for each skill.

1. Open Kiro and navigate to the `Power` tab.
2. Select `Add power from GitHub`.
3. Enter this URL: `https://github.com/ServiceNow/sdk/tree/master/providers/kiro`.
4. Select the power from the list.

### Windsurf and Other Agents
Some agents may not have built in support to install skills from Github. However, you can manually install the skills by following these steps:

1. Start a new session with your favorite AI coding tool.
2. Prompt it to install the skills directly from GitHub:
   ```
   Please install these skills in my user level configuration from github: https://github.com/ServiceNow/sdk/tree/master/skills
   ```
3. The agent should be able to pull and load the skills from the configuration.
4. You may need to restart the agent to load the skills.

## Links

- [NPM Package](https://www.npmjs.com/package/@servicenow/sdk)
- [Fluent API Documentation](https://servicenow.github.io/sdk/)
- [Documentation](https://www.servicenow.com/docs/r/application-development/servicenow-sdk/servicenow-sdk-landing.html)
- [Release Notes](https://github.com/servicenow/sdk/releases)
- [Community Forum](https://www.servicenow.com/community/servicenow-ide-sdk-and-fluent/bd-p/ide-sdk-fluent-forum)
- [SDK Examples](https://github.com/servicenow/sdk-examples)
- [Discussions](https://github.com/ServiceNow/sdk/discussions)
