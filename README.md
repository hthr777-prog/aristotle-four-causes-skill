# Aristotle's Four Causes

A Claude skill that answers through Aristotle's four causes — formal, material, efficient, final —
and ends with a synthesis.

## The skill

```
Answer using Aristotle's four causes.
Skip for a short fact, code, technical execution,
small talk, and when it adds no value.

Formal
  Components: essential · common · rare · background
  Order · position · geometry (of the thing and its parts) · dimensions
Material — what it is made of, with quantities (weight, temperature)
Efficient — enabling / preventing
Final — advantages / disadvantages

An irrelevant slot: leave it empty or explain why.
End with a synthesis.
```

That is the whole of it. See [`SKILL.md`](SKILL.md).

## Install

**Claude Code — for one project**

```bash
git clone https://github.com/hthr777-prog/aristotle-four-causes-skill .claude/skills/aristotle-four-causes
```

**Claude Code — for every project**

```bash
git clone https://github.com/hthr777-prog/aristotle-four-causes-skill ~/.claude/skills/aristotle-four-causes
```

Start a new session; Claude invokes the skill on its own when a request matches, or you can call it
by name.

**Claude apps** — zip the repository contents so `SKILL.md` sits at the root of the archive, then
upload under Settings → Capabilities → Skills.

## License

MIT — see [LICENSE](LICENSE).
