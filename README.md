# Skills

Reusable agent skills maintained in [prafiles/skills](https://github.com/prafiles/skills).

| Skill | Purpose |
| --- | --- |
| [django-primary-replica](django-primary-replica/SKILL.md) | Plan Django connections and primary/replica routing through PgBouncer. |
| [api-performance-plan](api-performance-plan/SKILL.md) | Diagnose slow table-view APIs and plan indexing and row-level caching. |
| [email-thread-summary](email-thread-summary/SKILL.md) | Summarize email threads and identify the user's action items. |
| [design-review](design-review/SKILL.md) | Lead with distinctive art direction, visibly greater beauty, and more expressive animation by default. Evolve the visual language within scope; reduced motion is opt-in. Grounded in Design for Developers and Animation at Work. |

Each directory is a self-contained skill with a `SKILL.md` entrypoint. Its YAML frontmatter defines the name and when the skill applies; the body provides the workflow.

The skills work in both Codex and Claude. Frontmatter uses only `name` and `description`, which every agent reads. Keep it that way: claude.ai rejects an upload whose frontmatter has keys outside the [Agent Skills](https://agentskills.io) spec, such as Claude Code's `argument-hint`. Put agent-specific settings in separate files, as `agents/openai.yaml` does for Codex; Claude ignores that file and needs no equivalent.

## Local use

Clone the repository, or use the `skills/` checkout in the prafiles `repo` workspace:

```sh
git clone https://github.com/prafiles/skills.git
```

Copy or symlink the individual skill directories into your agent's skills directory. Symlinks let a `git pull` update every installed skill.

| Agent | Skills directory |
| --- | --- |
| Codex | `${CODEX_HOME:-$HOME/.codex}/skills` |
| Claude Code, all projects | `$HOME/.claude/skills` |
| Claude Code, one project | `.claude/skills` in that project |

For example, from the repository root, set `dest` to a directory from the table:

```sh
dest="$HOME/.claude/skills"
mkdir -p "$dest"
for skill in django-primary-replica api-performance-plan email-thread-summary design-review; do
  if [ -e "$dest/$skill" ] || [ -L "$dest/$skill" ]; then
    echo "conflict: $dest/$skill already exists" >&2
  else
    ln -s "$PWD/$skill" "$dest/$skill"
  fi
done
```

The commands leave an existing destination untouched and report a conflict if a skill is already installed. Invoke a skill by name, such as `$api-performance-plan` in Codex or `/api-performance-plan` in Claude Code, or let the agent select it when its description matches the task.

Cowork and Claude Code cloud sessions don't read `~/.claude/skills`. To use a skill there, upload its directory to your claude.ai account from the skills settings.
