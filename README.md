# Aristotle's Four Causes

A Claude skill that answers through Aristotle's four causes — formal, material, efficient, final —
and ends with a synthesis.

## The skill

```
Answer using Aristotle's four causes.
For a short fact, code, technical execution, small talk, or when it adds no value — answer normally.

1. Formal — the structure:
   - Components, ordered by: essential, common, rare, background
   - Order, position, geometry and dimensions
2. Material — what it is made of, including quantities and data (for an abstract subject: the resources and infrastructure)
3. Efficient — the factors that enable or prevent it
4. Final — the purpose, including advantages and disadvantages

* An irrelevant slot: leave it empty or briefly explain why.
* End with a synthesis that ties the causes into a single insight.
```

That is the whole of it. See [`SKILL.md`](SKILL.md).

## Background

The four causes are Aristotle's, from *Physics* II.3 — the [Stanford Encyclopedia
entry](https://plato.stanford.edu/entries/aristotle-causality/) sets them out.

The same division has already served as a computational schema. In 1991 James Pustejovsky's
[*The Generative Lexicon*](https://aclanthology.org/J91-4003.pdf) proposed representing a word's
meaning through four qualia roles — Formal, Constitutive, Agentive and Telic — following
Moravcsik's reading of Aristotle's *aitia*. Under other names, those are the four causes.

That is not evidence this skill works, and Pustejovsky was after something else: how a word
shifts sense with context. What it does show is that the division survives being made
machine-readable, and that it was reached for, in another field and for another purpose, by
someone who needed more than a flat definition.

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

Copyright (c) 2026 Michael Kenigsberg.
Licensed under [Creative Commons Attribution 4.0 International](LICENSE) (CC BY 4.0).

You may share and adapt this skill, including commercially, provided you give
appropriate credit, link to the license, and indicate if changes were made.

> Aristotle's Four Causes skill by Michael Kenigsberg, licensed under
> [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
