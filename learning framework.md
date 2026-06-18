# The Three-Layer Learning Framework

A domain-agnostic method for genuinely understanding technical concepts — not memorizing them.

Most technical knowledge is taught and stored as isolated facts: definitions, tool commands, step lists. This framework treats every concept the way it actually exists in a real system — as a **node with prerequisite states and downstream consequences**. The goal is to build understanding that *composes*: knowledge you can recombine to reason through novel situations, instead of procedures you can only replay.

The same three layers apply whether you're learning a networking protocol, a programming pattern, a hardware circuit, or an exploitation technique. The vocabulary changes; the structure doesn't.

---

## The core idea

Three layers, asked in order:

| Layer | Question it answers | What it gives you |
|-------|--------------------|-------------------|
| **Layer 1 — Mechanism** | What is *actually happening* underneath? | First-principles ground truth |
| **Layer 2 — Conditions** | What must be true *before* this applies, and what does failure tell me? | Situation → technique recognition |
| **Layer 3 — Connectivity** | What does this unlock, what does it close off, where does it sit? | Position on the larger problem graph |

The reason this generalizes is that most technical concepts aren't standalone — they have an underlying reality, a set of conditions under which they're active, and consequences that ripple outward. The model forces you to think in **states and transitions** rather than steps, which is the mental move that makes knowledge transferable across domains.

> **The test for whether you've truly learned a concept:** can you answer Layer 2 cold, without prompting? That's usually where real understanding either exists or doesn't.

---

## Step 0 — Domain research pass

Before any of the layers, you need enough of a mental model to derive from. Domain research, in *any* field, is answering five questions:

1. What is this thing?
2. How does it work at the mechanism level?
3. What are its components, and how do they relate to each other?
4. What is its normal, intended behavior?
5. Where does it live within the larger system it belongs to?

That's it. Once you can answer all five, you have enough to move into Layer 2 derivation without looking anything else up.

> Field-specific domain questions (e.g. for offensive security: authentication, defaults, exposure, versions) are just a more granular version of these five, tuned to what matters in that domain. The underlying structure is identical.

---

## Layer 1 — Mechanism

**Goal:** explain what is *literally occurring* underneath, stripped of jargon and abstraction. Not what it's called. Not what tool you use. What actually happens at the system level.

**The test:** can you explain it to someone with no context and have them understand the real process? If you're leaning on terminology to carry the explanation, the first-principles understanding isn't fully there yet.

**What to do:** after your domain research, close your notes and write out the mechanism in plain language from scratch. Wherever you get stuck or go vague is exactly where your understanding has a hole.

---

## Layer 2 — Conditions (fluency)

This is the layer that separates real understanding from procedural memory. It runs in two steps, then gets reinforced with reps.

### Step 1 — Map conditions explicitly

When you learn a concept, don't just take notes on what it is. Force yourself to complete this template, in concrete specifics rather than abstractions:

- **Technique** — what is it? Explain the mechanism in your own words. (Your Layer 1 work covers this — primarily information intake.)
- **Prerequisites** — what must I already *have* or already *be* for this to apply? Reason backwards from the concept to its assumed starting state.
- **Environment conditions** — what must be true about the *thing I'm interacting with* for this to apply? Shift perspective from yourself to the external system and ask what it needs to expose or have present.
- **Failure signals** — if this doesn't work, what are the possible reasons, and what would each one tell me? (Requires the other three mapped first, since you're reasoning about what partial or full absence of conditions looks like.)

Write specifics. Not *"need valid credentials"* but *"need a domain user account with a valid TGT."*

The key insight: **only the first field is about reading more.** The other three are derived by *reasoning from what you already understand* — which is why they can't be shortcut by consuming more material.

### Step 2 — Build a retrieval prompt

Take the condition map and rewrite the **observable** parts (prerequisites + environment conditions) as a short situation description — something you'd actually see in the wild. No technique name, no hints.

That situation description becomes a self-test prompt. Step 1 builds the map; Step 2 converts it into a testable scenario that trains recognition in the right direction.

### Step 3 — Practice conditions → concept retrieval

This is flashcard inversion. Instead of *"what are the conditions for technique X?"* you practice from the other side: describe an environment state and ask what it *unlocks*.

Write out a list of environment snapshots — e.g. *"low-priv domain user, can see SPNs registered in the domain, no AV"* — and derive which techniques are available. No looking at notes until you've committed to an answer.

The more reps you put in, the more your brain pattern-matches situations to technique availability automatically. That's the entire goal of this layer.

### Step 4 — Lab exposure (deliberate)

Reps in a real environment, made deliberate by **narrating your condition checks** as you go. Before reaching for a technique, explicitly state the conditions you've confirmed that justify it. That narration is what converts lab time into internalized pattern recognition instead of muscle memory.

The through-line across every step is the **situation-first direction**: map it that way, test it that way, narrate it that way.

---

## Layer 3 — Connectivity

**Goal:** place the concept on the larger graph of the problem space. To say you understand Layer 3, you can answer three things:

1. **What does this open up** if it succeeds?
2. **What does it close off** or make harder if it fails or is unavailable?
3. **Where does it sit** relative to everything else — is it an early-stage move, a pivot, an escalation?

**The test:** can you place the concept on the larger graph without prompting? Not just *"this leads to X,"* but understanding its *position* — what comes before it, what branches off it, what depends on it.

**What to do:** after mapping Layer 2, explicitly ask those three questions and write the answers out. If you can't answer the second one — what closing it off means — that's usually the gap, because most people only think forward.

---

## The unifying pattern

Across all three layers, the method is the same:

> **Derive it. Write it out cold. Identify where you go vague. That's where the work is.**

"What do I need to do next" is a *linear* question applied to what is almost always a *non-linear* problem space. Thinking in mechanism → conditions → connectivity reframes learning around states and transitions — which is what makes technical knowledge actually composable rather than just recallable.
