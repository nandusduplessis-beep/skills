# JobOps on Mobile (Claude Code on the web)

The JobOps plugin (https://github.com/reggiechan74/JobOps) vendored into
this repo so it works in mobile Claude Code sessions, where the `/plugin`
system isn't available.

## What's here

- `.claude/skills/jobops-*/` — 37 JobOps skills (resume, assessment, OSINT,
  interview prep, crisis management, etc.). Invokable autonomously via the
  Skill tool when you ask Claude to do the matching task.
- `.claude/agents/` — 17 JobOps agents (resume drafting, OSINT, interview
  generation). Invokable via the Agent tool.
- `.claude/jobops/templates/` — bundled markdown + LaTeX templates.
- `.claude/jobops/styles/` — CSS for PDF/HTML output.

`${CLAUDE_PLUGIN_ROOT}` references in skill files have been rewritten to
`.claude/jobops`, so template paths resolve from the repo root.

## Usage from mobile

Open a Claude Code on the web session against this repo, then ask in
natural language — Claude will pick the right skill:

- "Set up the JobOps workspace here" → invokes `jobops-setup`
  (creates `.jobops/config.json`, `ResumeSourceFolder/`, `Job_Postings/`,
  `Applications/`, etc. in this repo root).
- "Build a resume for this posting" → `jobops-buildresume`
- "Assess this job for me" → `jobops-assessjob`
- "Run OSINT on Acme Corp" → `jobops-osint`
- "Show my application dashboard" → `jobops-dashboard`

For the full skill list: `ls .claude/skills`.

## Caveats

- The original `/jobops:setup` slash command does not exist here — there is
  no slash-command surface without the plugin system. Skills must be
  triggered by description.
- `jobops-setup` has `disable-model-invocation: true` upstream, meaning
  Claude won't auto-pick it. To run it, explicitly say "run the jobops-setup
  skill".
- This repo is `@remotion/skills` at its root; JobOps lives only under
  `.claude/` and doesn't touch the Remotion package.

## Updating

Re-vendor from upstream:

```
git clone --depth 1 https://github.com/reggiechan74/JobOps.git /tmp/jobops
rm -rf .claude/skills/jobops-* .claude/agents .claude/jobops
# then re-run the vendor script in this PR's history
```
