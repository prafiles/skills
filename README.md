# Skills

Reusable agent skills maintained in [prafiles/skills](https://github.com/prafiles/skills).

| Skill | Purpose |
| --- | --- |
| [django-primary-replica](django-primary-replica/SKILL.md) | Plan Django connections and primary/replica routing through PgBouncer. |
| [api-performance-plan](api-performance-plan/SKILL.md) | Diagnose slow table-view APIs and plan indexing and row-level caching. |
| [email-thread-summary](email-thread-summary/SKILL.md) | Summarize email threads and identify the user's action items. |
| [design-review](design-review/SKILL.md) | Review interfaces using Design for Developers, with evidence and prioritized fixes. |

Each directory is a self-contained skill with a `SKILL.md` entrypoint. Its YAML frontmatter defines the name and when the skill applies; the body provides the workflow.

## Local use

Clone the repository, or use the `skills/` checkout in the prafiles `repo` workspace:

```sh
git clone https://github.com/prafiles/skills.git
```

For Codex, copy or symlink the individual skill directories into `${CODEX_HOME:-$HOME/.codex}/skills`. For example, from the repository root:

```sh
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
for skill in django-primary-replica api-performance-plan email-thread-summary design-review; do
  ln -s "$PWD/$skill" "${CODEX_HOME:-$HOME/.codex}/skills/$skill"
done
```

The commands leave an existing destination untouched and report a conflict if a skill is already installed. Invoke a skill by name, such as `$api-performance-plan`, or let the agent select it when its description matches the task.
