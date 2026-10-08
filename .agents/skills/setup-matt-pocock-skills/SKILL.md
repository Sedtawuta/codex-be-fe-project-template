---
name: setup-matt-pocock-skills
description: Configure or change local work tracking and domain document pointers for this template.
disable-model-invocation: true
---

# Setup planning skills

This template already uses local Markdown. Read
`docs/agents/issue-tracker.md` and `docs/workflow.md`; report the current setup
and finish when it matches the user's request. Re-running setup is not required
for every project or feature.

If a change is requested:

1. Clarify only the missing choice of tracker or authoritative document location.
   Preserve root `GLOSSARY.md` as the terminology source and link shared rules.
2. Update `docs/agents/issue-tracker.md` with ticket location, dependencies, statuses,
   and which artifact is authoritative. Keep PRD and feature bodies single-sourced;
   external tickets may link to local contracts instead of duplicating them.
3. Update affected workflow pointers and planning skills. Add remote operations
   only when requested; changing a configuration alone does not authorize publishing
   issues, creating labels, or sending messages. Report changed paths and blockers.

Adapted from [setup-matt-pocock-skills](https://github.com/mattpocock/skills/blob/main/skills/engineering/setup-matt-pocock-skills/SKILL.md) for this template.
