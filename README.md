# Four Causes

A Claude skill that answers through Aristotle's four causes — **formal**, **material**,
**efficient**, **final** — and closes with a synthesis.

The aim is not philosophy. It is coverage. Most explanations describe structure and stop, or list
benefits and stop. Running all four causes forces the parts of an answer that are easiest to skip:
what something is actually made of, in what quantity, what mechanism drives it, and what it costs.

## The framework

| Cause | Question | What the answer contains |
|---|---|---|
| **Formal** | What is it? | Components — essential · common · rare · background.<br>Arrangement — order · position · geometry · dimensions |
| **Material** | What is it made of? | The substance, with quantities (mass, temperature, duration, count) |
| **Efficient** | What brings it about? | What **enables** it · what **prevents** it |
| **Final** | What is it for? | **Benefits** · **drawbacks** |

Two rules hold the frame together:

- **An empty slot stays empty**, or gets a one-line reason. Slots are never padded to fill the
  form — a blank slot is information, an invented one is noise.
- **Every pass ends in a synthesis.** Taking a thing apart is half the work; the close puts it back
  together and says what follows.

## When it triggers

Definitions and explanations · comparisons · causal and feasibility questions ("why did X happen",
"is X worth it", "should we do X") · planning and analysis · structuring or editing a body of text ·
building a thing or a representation of one — a document, a deck, a landing page, a brief.

It applies whether or not you mention the method.

## When it stays out of the way

Short factual questions · routine code · simple technical execution · small talk · anything where
the frame would add length without adding understanding.

Skipping is a designed behaviour, not an oversight. Four headings over a one-line answer is a worse
answer.

## Install

**Claude Code — for one project**

```bash
git clone https://github.com/hthr777-prog/aristotle-four-causes-skill .claude/skills/four-causes
```

**Claude Code — for every project**

```bash
git clone https://github.com/hthr777-prog/aristotle-four-causes-skill ~/.claude/skills/four-causes
```

Start a new session and the skill is available; Claude invokes it on its own when a request matches
the triggers above, or you can call it by name.

**Claude apps** — zip the repository contents so that `SKILL.md` sits at the root of the archive,
then upload it under Settings → Capabilities → Skills.

## Use

Just ask. The skill engages on its own:

```
What is the difference between a mutex and a semaphore?
Why did our deploy times triple after the monorepo migration?
Is it worth moving this service off Postgres?
Draft the landing page for the new plan.
```

To force it, name it: *"answer through the four causes."*

See [`examples/worked-example.md`](examples/worked-example.md) for two full passes — one physical
subject, one engineering decision.

## Repository layout

```
SKILL.md                     the skill — frontmatter, triggers, and the method
examples/worked-example.md   two worked passes through the framework
LICENSE                      MIT
```

## License

MIT — see [LICENSE](LICENSE).
