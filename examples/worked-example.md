# Worked examples

Two passes through the framework: one physical subject, one decision. Both end in a synthesis.

---

## Example 1 — "What is espresso?"

### Formal — what it is

**Components**

- *Essential* — a bed of finely ground coffee, water forced through it under pressure, a basket and
  portafilter to hold the bed against that pressure
- *Common* — crema, a nine-bar pump, a pre-infusion phase, a tamped puck
- *Rare* — a lever group for manual pressure profiling, a naked bottomless portafilter
- *Background* — the grinder, the water supply and its mineral content, ambient humidity

**Arrangement**

- *Order* — grind, dose, distribute, tamp, pre-infuse, extract, cut the shot
- *Position* — the puck sits between the dispersion screen above and the basket holes below; the
  compacted bed is the only resistance in the path
- *Geometry* — a shallow cylinder, roughly 58 mm across and 20–25 mm deep, wide relative to its
  height so flow is even across the face
- *Dimensions* — 18 g dry dose, 36 g in the cup, 25–30 s

### Material — what it is made of

Roasted coffee ground to roughly 200–400 µm, and water. An 18 g dose meets about 36 g of water at
92–96 °C, driven at 8–10 bar. Between 18 % and 22 % of the dry mass dissolves; the cup ends up at
8–12 % dissolved solids, an order of magnitude denser than drip coffee.

### Efficient — what brings it about

**Enables** — pressure forces water through a bed too fine to drip through, so contact is short and
extraction is fast. Heat raises solubility. A uniform, well-tamped bed keeps the flow front flat, so
every part of the puck gives up roughly the same fraction of its mass.

**Prevents** — channelling: any weak point in the bed takes the flow, over-extracting its own path
and leaving the rest untouched. Grinding too coarse drops resistance and the shot runs thin and
sour; too fine and it chokes and turns bitter. Stale grounds outgas CO₂ that disrupts the flow
front.

### Final — what it is for

**Benefits** — concentration, in a form that works alone or as the base of milk drinks. Thirty
seconds per serving makes it viable behind a counter. The short contact window makes the variables
tight enough to control deliberately.

**Drawbacks** — that same tightness is intolerance: a few hundred microns of grind error is a
visibly worse shot. It needs an expensive grinder, a pressure source, and a trained hand, and it
cannot be made ahead.

### Synthesis

Espresso is not strong coffee — it is a different extraction regime. Pressure buys a short contact
time, the short contact time demands a fine grind, and the fine grind is what makes the bed so
sensitive to its own uniformity. Every difficulty in the craft traces back to one decision: forcing
the water rather than letting it fall. What you buy with that decision is speed and concentration;
what you pay is tolerance.

---

## Example 2 — "Should we add a caching layer?"

### Formal

*Essential* — a key-value store, a read path that consults it first, an invalidation rule.
*Common* — a TTL, metrics on hit rate. *Rare* — write-through or write-behind paths.
*Background* — the existing database and its query patterns.

*Order* — read cache, miss, read database, populate, return. *Position* — between application and
database, on the read path only. *Dimensions* — sized to the working set, not the dataset.

### Material

Memory, and engineering time. A cache holding the hot 5 % of a 200 GB dataset needs roughly 10 GB
of RAM; the invalidation logic is the ongoing cost, not the instance.

### Efficient

**Enables** — a skewed access distribution. If a small key set serves most reads, hit rates are
high without much memory.

**Prevents** — a flat distribution gives you an expensive miss path and nothing else. Writes that
must be read back immediately force synchronous invalidation and erase much of the gain.

### Final

**Benefits** — lower read latency, database load headroom, a cheaper scaling path than a larger
primary.

**Drawbacks** — a second source of truth, and stale-read bugs that reproduce only under load.
Cold-start thundering herds. One more thing to operate.

### Synthesis

The answer is set by the material and efficient causes, not by the final one: the benefits are real
but conditional on access skew. Measure the distribution first. If the hot set is small and
tolerates seconds of staleness, add the cache; if reads are flat or must be strictly fresh, the
drawbacks arrive and the benefits do not.
