# PR Comments Triage

An [agent skill](https://agentskills.io/home) that critically evaluates PR review comments against your actual code, instead of blindly accepting them.

## What it does

When you receive PR review comments, this skill investigates each one against the real code on your branch to determine if it's valid. It:

- Reads the actual code the comment refers to
- Reasons about whether the concern is factually accurate
- Distinguishes real issues from stylistic preferences or misunderstandings
- Explains its verdict with references to the specific code
- Offers to implement valid fixes

## Installation

### As a skill

```bash
npx skills add https://github.com/diegopetrucci/pr-comments-triage --skill pr-comments-triage
```

### As a Claude Code plugin

```shell
/plugin marketplace add diegopetrucci/ai-agents-skills
/plugin install pr-comments-triage@diegopetrucci-claude-plugins
```

### As a Codex plugin

```shell
codex plugin marketplace add diegopetrucci/ai-agents-skills
```

Restart Codex, then install `pr-comments-triage` from the "Diego Petrucci Agent Skills" marketplace in the plugin directory.

## Usage

Trigger the skill while on a feature branch:

- **Claude Code:** `/pr-comments-triage` or say "triage PR comments"

Then paste PR review comments one at a time. The skill will investigate each and give you a verdict before moving to the next.

## More Skills Like This

Found this skill useful? Browse all my hand-crafted ones in the [AI Agents skills](https://github.com/diegopetrucci/ai-agents-skills) repo.

## License

MIT
