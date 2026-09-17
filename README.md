# do-it

This repository provides a senior front-end developer profile for GitHub Copilot:

- Agent: `.github/agents/app-dev-front-end.agent.md`
- Core agent creator: `.github/agents/core-agent-creator.agent.md`
- HTML skill: `.github/skills/html/SKILL.md`
- CSS skill: `.github/skills/css/SKILL.md`
- JavaScript skill: `.github/skills/javascript/SKILL.md`
- TypeScript skill: `.github/skills/typescript/SKILL.md`
- Vue skill: `.github/skills/vue/SKILL.md`
- Vite skill: `.github/skills/vite/SKILL.md`

For new demo applications, the agent defaults to Vue 3, TypeScript, and Vite.
Specialized instructions are discovered and applied from the skills according
to the task.

The core agent creator interviews users to scope focused custom agents, separates
distinct personas when needed, checks repository-local skills before proposing
new ones, and writes approved definitions only after presenting a file plan.