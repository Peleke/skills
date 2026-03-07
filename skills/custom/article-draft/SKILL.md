---
name: article-draft
description: "Draft technical articles with narrative structure, visual injection, and prose quality enforcement. Combines SPIN storytelling, engagement science, Bragi prose gate, and comedy-writer voice calibration for articles that are rigorous AND readable."
license: MIT
metadata:
  openclaw:
    emoji: "\u270D\uFE0F"
---

# Article Draft

Draft technical articles that tell a story, not a lecture. This skill enforces narrative structure (SPIN arc), prose quality (Bragi gate), engagement science (sensory hooks), and voice calibration (irreverent but substantive) at draft time so review passes catch less garbage.

## Step 0: Inputs

Before drafting, you need:

1. **Editorial map** — what the article covers, what it claims, what evidence supports each claim
2. **Visual inventory** — screenshots, charts, diagrams available for injection
3. **War stories** — specific anecdotes, incidents, real data (not hypotheticals)
4. **Voice target** — which register(s) to blend (see Voice Calibration below)

If any of these are missing, do an elicitation pass before drafting. Do not draft from an outline alone.

---

## Phase 1: SPIN Arc

Map the article to SPIN (Rackham). The solution does NOT appear until the Need-Payoff phase. The audience must feel pain BEFORE seeing the solution.

| Phase | Function | Reader's internal question |
|-------|----------|---------------------------|
| **Situation** | Establish shared reality | "Yeah, I know this" |
| **Problem** | Name the specific pain | "Oh god, yes, this sucks" |
| **Implication** | Show what the pain costs | "Wait, it's THAT bad?" |
| **Need-Payoff** | Present the solution + proof | "OK, show me" |

Rules:
- Solution does NOT appear before the Implication section. Period.
- Each phase transition is a natural question the reader is asking
- The Situation phase is max 2 paragraphs. Do not over-explain what people already know.
- The Problem phase uses a specific war story, not an abstract description

---

## Phase 2: Beat Map

Map every section to an emotional beat. Adjacent sections cannot have the same beat.

**Tension building (first half):**
- Intrigue ("huh, what's this about")
- Recognition ("oh I know exactly what this is")
- Discomfort ("oh no, I do this too")
- Empathy ("I feel seen")

**The Turn (midpoint):**
- Respect ("but there's a way")

**Conviction building (second half):**
- Clarity ("oh, I see how this works")
- Insight ("wait, THAT'S what's actually happening?")
- Relief ("this is solvable")
- Confidence ("I could do this / I believe this works")

**Closing:**
- Resolution (callback to the opening war story, now resolved)

---

## Phase 3: Visual Injection Protocol

Every article has three visual layers. Plan injection points during outlining, not after drafting.

### Layer 1: Data visuals (charts, screenshots)
- Place AFTER the claim they support, not before
- Caption must state what the reader should see, not just label the axes
- Max 2 data visuals per section. If you need more, the section is too long.

### Layer 2: Architecture diagrams (SVG)
- One hero diagram per article (the "big picture")
- Place at the SPIN transition (end of Situation or start of Need-Payoff)
- Pipeline/flow diagrams: left-to-right or top-to-bottom, never circular unless the loop IS the point
- Dark theme. Minimal color palette (2-3 colors max). No gradients unless they encode data.

### Layer 3: Interactive elements (d3.js, animations)
- Max 1-2 per article. These are expensive; use them where static fails.
- Best for: distributions updating in real time, graph traversals, parameter exploration
- Every interactive MUST have a static fallback (PNG) for non-JS contexts
- Place after the reader has built intuition, not as the introduction to a concept

### Injection checklist
For each visual, answer:
1. What claim does this support?
2. What should the reader notice first?
3. What's the caption? (Must be a complete sentence, not a label)
4. Does removing this visual weaken the argument? (If no, cut it.)

---

## Phase 4: Voice Calibration

### Three registers to blend

**Register A: Frustrated Engineer (Mickens)**
- Escalating specificity. Start general, narrow to a specific system, narrow to a specific log line, narrow to a specific token.
- Real terror underneath the laughs. The joke works because the problem is genuinely absurd.
- Hyperbolic analogy that clarifies, not obscures.
- USE FOR: war stories, failure descriptions, "the state of the industry" sections

**Register B: Self-Deprecating Narrator (Sedaris)**
- Be harder on yourself than anyone else in the story.
- Mundane details elevated to absurdity. The joke is in the precision, not the exaggeration.
- Weight at the end. Laugh for 2,000 words, then one sentence that hits.
- USE FOR: personal anecdotes, "how I got here" sections, the opening hook

**Register C: Respectful Tour Guide (Paul Ford)**
- Direct address that dignifies the reader. Never talk down.
- Sustained genuine curiosity about the subject matter.
- The humor is in the juxtaposition: rigorous science described by someone who finds parts of it absurd.
- USE FOR: technical explanations, architecture walkthroughs, "how it works" sections

### Voice rules
- Default ratio: 40% Register A, 30% Register B, 30% Register C
- LinkedIn-facing articles: bias toward A+B (war stories + self-deprecation)
- Technical deep dives: bias toward C+A (tour guide + frustrated specificity)
- NEVER use all three in the same paragraph. One register per paragraph, blend across sections.

---

## Phase 5: Bragi Prose Gate (applied at draft time)

These 20 rules are enforced DURING drafting, not on review. Internalize them.

### Hard bans (zero tolerance)
1. **No em dashes (—).** Use colons, semicolons, commas, parentheses, or separate sentences.
2. **No AI vocabulary blocklist words.** Additionally, align with, crucial, delve, emphasizing, enduring, enhance, fostering, garner, highlight (as verb), interplay, intricate/intricacies, key (as adjective), landscape (abstract), pivotal, showcase, tapestry (abstract), testament, underscore (as verb), valuable, vibrant.
3. **No performative honesty.** "Being honest:", "To be frank:", "The truth is:" — if you have to announce you're being honest, cut the announcement.
4. **No self-referential pivots.** "This is where things get interesting" — just make the point.
5. **No inflated significance framing.** "Marking a pivotal moment", "setting the stage for", "evolving landscape" — name the specific consequence or delete.

### Structural bans
6. **No hedging then inflating.** "Though limited, it contributes to the broader..." — if it's minor, say it's minor and move on.
7. **No punchy fragment marketing copy.** "One knowledge base, every agent surface." — technical articles aren't ad copy.
8. **No tricolon/pentad enumerations for rhythm.** "Fast, reliable, scalable, secure, and observable" — itemize what matters, not what sounds balanced.
9. **No rhythmic parallel construction closers.** "Decisions tied to outcomes, updated by evidence, grounded in practice" — end with a concrete claim.
10. **No challenges-and-future-prospects formula.** "Despite challenges, the future looks promising" — name the problems and skip the sandwich.

### Word-level bans
11. **No elegant variation.** If you mean the same thing, use the same word. Do not cycle through synonyms.
12. **No copula avoidance.** "Serves as", "stands as", "represents a" — just say "is."
13. **No dismissive 'with' framing.** "A demo with persistence" — don't reduce complex features to prepositional afterthoughts.
14. **No vague attribution.** "Experts argue", "Industry reports suggest" — name the source or cut the claim.
15. **No false ranges.** "From X to Y" only when there's an actual spectrum.

### Analysis bans
16. **No superficial participle analysis.** "...creating a lively community", "...further enhancing its significance" — if you stated a fact, stop. Don't append a gerund.
17. **No hedging with 'not' lists.** "Not X. Not Y. Not Z." — say what the thing IS.
18. **No colon-into-bold-statement.** "The question: **How do you...**" — formatting is not argumentation.
19. **No promotional puffery.** "Groundbreaking", "renowned", "boasts a", "showcasing" — cut every adjective that doesn't distinguish this subject from any other.
20. **No notability assertion sections.** Don't build a section whose purpose is arguing the subject deserves attention. Show the work.

---

## Phase 6: Engagement Hooks

From engagement science (Warnick et al., 2018): named characters create 2.5x more neural engagement than abstractions. Circular stories are 22% more memorable than linear ones.

### Required elements
- **Named protagonist by paragraph 3.** Not "developers" or "teams." A specific person (can be the author) with a specific problem.
- **Protagonist appears 3+ times by name.** Thread them through the article.
- **Circular close.** The ending callbacks to the opening. The war story that opened the piece resolves (or deepens) at the end.
- **Code before formula.** Show the output, THEN explain the math. Never introduce notation first.
- **One "holy shit" data point per section.** Not buried in a table. Called out in prose. ("56% of all mistakes were repeats.")

### Engagement budget per article
- 1 war story opening (required)
- 3-5 data callouts (bold or standalone line)
- 2-4 code blocks (real output, not pseudocode)
- 1 circular close (required)
- 0-2 footnotes for technical asides that would break flow (Roach technique)

---

## Phase 7: Draft Execution

With all the above internalized, draft in this order:

1. **Write the opening war story first.** This anchors everything. Get the specific anecdote, the specific failure, the specific feeling. Register B (Sedaris).
2. **Write the SPIN transitions.** The questions that move the reader from Situation → Problem → Implication → Need-Payoff.
3. **Fill each section.** One register per paragraph. Inject visuals at planned points.
4. **Write the circular close.** Callback to the opening. The same situation, now transformed by what the reader knows.
5. **Run Bragi gate.** Search the draft for every banned pattern. Fix them. This is non-negotiable.
6. **Caption every visual.** Complete sentence stating what the reader should see.
7. **Read aloud test.** Does any sentence make you cringe? Cut it. Does any paragraph feel like filler? Cut it. Does the piece work without any single section? If yes, that section is filler. Cut it.

---

## Anti-patterns (things this skill prevents)

- "Let me explain the architecture" opening (Register C without a war story setup = lecture)
- Visuals dumped at the end instead of injected at claim points
- Prose that passes spell check but reads like ChatGPT (Bragi gate catches this)
- Articles that explain what something IS but never show what it DOES (code-before-formula rule)
- Humor that tries too hard (the truth is funny enough; describe it precisely)
- Articles with no named protagonist (abstractions don't engage)

---

## Appendix: Quick Reference

### SPIN check
- [ ] Solution appears AFTER Implication section
- [ ] Each phase transition is a question the reader is asking
- [ ] War story in the Problem phase (not abstract)

### Beat check
- [ ] Adjacent sections have different beats
- [ ] Turn (midpoint) is identifiable
- [ ] Closing callbacks to opening

### Visual check
- [ ] Every visual supports a specific claim
- [ ] Every visual has a caption (complete sentence)
- [ ] Max 2 data visuals per section
- [ ] 1 hero SVG per article
- [ ] Interactive elements have static fallbacks

### Voice check
- [ ] One register per paragraph
- [ ] No all-three-registers paragraphs
- [ ] Default ratio appropriate for article type

### Bragi check
- [ ] Zero em dashes
- [ ] Zero blocklist words
- [ ] Zero performative honesty
- [ ] Zero self-referential pivots
- [ ] Zero puffery
