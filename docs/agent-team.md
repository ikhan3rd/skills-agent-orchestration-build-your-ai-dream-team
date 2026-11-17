# Agent team

I will use GitHub Copilot CLI in a Codespace to orchestrate the agents building Mona's Project Pulse dashboard.

| Agent | Target model | Responsibility | Definition |
|---|---|---|---|
| Orchestrator | Claude Opus 5.5 (copilot) | Coordinates the specialists, assigns clear file scopes and phases, manages dependencies, and verifies the integrated result. | `.github/agents/orchestrator.agent.md` |
| Planner | Claude Opus 5.5 (copilot) | Researches the repository and requirements, then creates an implementation plan with steps, file assignments, dependencies, risks, and validation expectations. | `.github/agents/planner.agent.md` |
| Designer | Gemini 3.7 Flash (copilot) | Shapes the dashboard's user experience, accessibility, responsive layout, visual hierarchy, and polished Project Pulse styling. | `.github/agents/designer.agent.md` |
| Coder | GPT-5.5 (copilot) | Implements assigned application code and support configuration, following project patterns and validating the changes. | `.github/agents/coder.agent.md` |

The Orchestrator delegates planning to the Planner, then coordinates Designer and Coder work with explicit scopes so independent tasks can run in parallel and dependent work stays sequential.
