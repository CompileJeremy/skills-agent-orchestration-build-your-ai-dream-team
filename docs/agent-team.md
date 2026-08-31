# Agent team

For Mona's Project Pulse dashboard, I am using a custom multi-agent workflow defined under `.github/agents/` and orchestrated through GitHub Copilot CLI in a Codespace.

## Custom agents

- Planner — target model: Claude Opus 4.7 (copilot). Responsibility: research the repo, identify constraints and edge cases, and produce an implementation plan with file ownership, dependencies, and validation steps. Definition: `.github/agents/planner.agent.md`.
- Coder — target model: GPT-5.5 (copilot). Responsibility: implement code changes, fix logic bugs, and create runnable app support such as launch config when the task requires it. Definition: `.github/agents/coder.agent.md`.
- Designer — target model: Gemini 3.1 Pro (copilot). Responsibility: shape the dashboard UX/UI, accessibility, layout, visual hierarchy, and responsive styling for Project Pulse. Definition: `.github/agents/designer.agent.md`.
- Orchestrator — target model: Claude Opus 4.7 (copilot). Responsibility: break the work into phases, delegate to the specialist agents, manage sequencing and file boundaries, and verify the integrated result before reporting back. Definition: `.github/agents/orchestrator.agent.md`.

## How the team works

The Orchestrator coordinates the Planner, Coder, and Designer so the work flows from research and planning into implementation and design refinement, while keeping file scope and dependencies controlled. This lets the work be split cleanly across specialist responsibilities without mixing design, code, and planning tasks in one step.
