# Skills

Reusable agent skills maintained in [prafiles/skills](https://github.com/prafiles/skills).

| Skill | Purpose |
| --- | --- |
| [django-primary-replica](django-primary-replica/SKILL.md) | Plan Django connections and primary/replica routing through PgBouncer. |
| [api-performance-plan](api-performance-plan/SKILL.md) | Diagnose slow table-view APIs and plan indexing and row-level caching. |
| [email-thread-summary](email-thread-summary/SKILL.md) | Summarize email threads and identify the user's action items. |
| [design-review](design-review/SKILL.md) | Lead with distinctive art direction, visibly greater beauty, and more expressive animation by default. Evolve the visual language within scope; reduced motion is opt-in. Grounded in Design for Developers and Animation at Work. |

Each directory is a self-contained skill with a `SKILL.md` entrypoint. Its YAML frontmatter defines the name and when the skill applies; the body provides the workflow.

The same skill directory works in both Claude and Codex. Both read `SKILL.md` and its `references/`; `agents/openai.yaml` holds Codex-only display settings, which Claude ignores. Keep the `SKILL.md` frontmatter to keys the Claude apps accept (`name`, `description`, `license`, `allowed-tools`, `metadata`, `compatibility`); an upload with any other key fails.

## Install as a plugin

[`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json) makes this repository a plugin marketplace that both Claude Code and Codex read. It currently lists `design-review`.

Claude Code, from a session:

```text
/plugin marketplace add prafiles/skills
/plugin install design-review@prafiles-skills
```

From your shell, the same steps are `claude plugin marketplace add prafiles/skills` and then `claude plugin install design-review@prafiles-skills`.

Codex:

```sh
codex plugin marketplace add prafiles/skills
codex plugin add design-review@prafiles-skills
```

Both agents select the skill when a task matches its description. Plugin skills are namespaced by plugin, so the skill is listed as `design-review:design-review`. In Claude Code you can run it directly with `/design-review:design-review`. To pick up new commits, refresh the marketplace with `claude plugin marketplace update prafiles-skills` or `codex plugin marketplace upgrade prafiles-skills`.

## Local use

Clone the repository, or use the `skills/` checkout in the prafiles `repo` workspace:

```sh
git clone https://github.com/prafiles/skills.git
```

Symlink the skill directories into Claude Code's `~/.claude/skills` and into `~/.agents/skills`, the user skills directory Codex reads. Edits in the clone then take effect without reinstalling, and the skills keep their short names, such as `/design-review` in Claude Code and `$design-review` in Codex. From the repository root:

```sh
for dir in "$HOME/.claude/skills" "$HOME/.agents/skills"; do
  mkdir -p "$dir"
  for skill in django-primary-replica api-performance-plan email-thread-summary design-review; do
    if [ -e "$dir/$skill" ] || [ -L "$dir/$skill" ]; then
      echo "skipped $dir/$skill: already exists"
    else
      ln -s "$PWD/$skill" "$dir/$skill"
    fi
  done
done
```

The loop leaves an existing destination untouched and reports it. Older Codex releases read `${CODEX_HOME:-$HOME/.codex}/skills` instead; current releases read both. Invoke a skill by name, such as `$api-performance-plan` in Codex or `/api-performance-plan` in Claude Code, or let the agent select it when its description matches the task.

For the Claude apps (claude.ai and Claude Desktop), zip a skill directory and upload it from the Skills section of Claude's settings:

```sh
zip -r design-review.zip design-review
```
