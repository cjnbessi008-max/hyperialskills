---
name: consumer-state-transition
description: Analyze consumers, leads, parents, students, or buyers as dynamic decision states rather than static segments. Use when the user asks why people convert, hesitate, churn, ignore, respond, buy, fail to buy, or move through a funnel; when interpreting CRM, consultation, landing-page, ad, behavioral, sales, retention, or interview data; when choosing what evidence/message/action should move a person to the next decision state; or when modeling objections, trust, urgency, switching cost, price sensitivity, proof requirements, state transitions, or next-best actions. Do not trigger for generic copywriting or product ideation unless consumer decision evidence is part of the task.
---

# Consumer State Transition

Treat the consumer as a changing decision system, not a fixed persona.

## Core model

Represent analysis as:

`State(t+1) = f(State(t), Evidence, Event, Message, Offer, Context, Friction)`

Track four layers:

1. **Observed behavior** — clicks, searches, dwell, replies, consultations, objections, purchases, cancellations, referrals, repeated questions.
2. **Current state** — problem awareness, urgency, trust, perceived value, effort, risk, proof sufficiency, switching cost, commitment readiness.
3. **Decision policy** — the apparent rule governing the next action, inferred cautiously from repeated evidence.
4. **Transition** — what changed, what likely caused it, and what next observable action would confirm the hypothesis.

Never treat an inferred motive as a fact. Separate observed evidence from hypotheses.

## Workflow

### 1. Establish the target transition

Identify the concrete business transition under analysis, for example:

- unaware -> problem-aware
- problem-aware -> solution-seeking
- interested -> consultation
- consultation -> purchase
- first use -> repeated use
- active -> retained
- dissatisfied -> recovered
- dormant -> reactivated

If the user has not stated the transition explicitly, infer the narrowest transition supported by the request.

### 2. Gather evidence before interpretation

Prefer real evidence in this order:

1. purchase/payment/renewal/churn events
2. consultation and sales conversation logs
3. observed product or landing behavior
4. customer messages, interviews, support conversations
5. campaign response data
6. explicit survey responses
7. demographic or persona assumptions

When connected data sources are available and the user asks for actual-business analysis, retrieve the relevant evidence rather than inventing consumer psychology.

### 3. Build the state vector

Estimate only dimensions supported by evidence. Typical dimensions:

- problem awareness
- urgency
- trust
- proof requirement
- perceived value
- price sensitivity
- effort/friction sensitivity
- switching cost
- perceived risk
- social proof dependence
- commitment readiness
- expected outcome confidence

Use qualitative levels such as low / medium / high unless actual data supports numeric estimation.

Do not manufacture pseudo-precision such as 0.83 unless a scoring method or dataset supports it.

### 4. Infer the decision policy

Express the apparent policy as a conditional rule, for example:

`If problem severity is high but proof is insufficient, delay purchase and seek comparable cases.`

`If effort to switch exceeds perceived upside, remain with the current solution despite dissatisfaction.`

Policies are hypotheses. Attach the evidence that supports each one and note counter-evidence.

### 5. Map the transition bottleneck

Find the single strongest reason the desired transition is not occurring.

Prefer bottlenecks supported by observed behavior over broad psychological explanations.

Distinguish:

- missing information
- missing proof
- insufficient urgency
- unclear value
- excessive friction
- price resistance
- trust deficit
- switching cost
- timing mismatch
- offer mismatch
- implementation risk

### 6. Choose the next-best evidence or action

Do not default to persuasion copy. Choose the smallest intervention that can test or advance the transition.

Examples:

- show an individualized diagnosis rather than a generic benefit claim
- expose a concrete before/after result rather than add more feature explanation
- remove a form field rather than add urgency language
- ask one diagnostic question rather than send a long nurture sequence
- provide a trial or reversible step when switching risk is the bottleneck

Optimize for truth-revealing actions that both help the consumer decide and improve the business model.

### 7. Define the measurement

Every recommendation must name an observable outcome, such as:

- consultation start rate
- reply rate
- checkout completion
- payment conversion
- activation within 24 hours
- return usage within 7 days
- cancellation reason shift
- renewal rate
- objection frequency
- time-to-decision

Avoid claiming progress from content creation alone.

## Default output

Use this compact structure unless the user requests another format:

### Target transition
`[current state] -> [desired next state]`

### Evidence
- Observed: ...
- Missing: ...

### Current consumer state
- problem awareness: ...
- urgency: ...
- trust: ...
- proof requirement: ...
- friction / switching cost: ...
- other relevant dimensions: ...

### Likely decision policy
`If ..., then ...`

Confidence: low / medium / high
Evidence supporting it: ...
Counter-evidence: ...

### Main transition bottleneck
`...`

### Next-best action
`...`

Why this action: ...

### Reality check
Measure: `...`
Success signal: `...`
Failure signal: `...`
What to update in the model afterward: `...`

## Guardrails

- Do not diagnose personality, mental illness, or hidden motives from sparse data.
- Do not use protected or sensitive personal traits to target or manipulate people.
- Do not recommend deception, fabricated proof, fake scarcity, or concealment of material facts.
- Prefer interventions that increase decision quality, reduce friction, surface true value, or test a hypothesis.
- Keep person-level analysis provisional and update it when behavior contradicts the model.
- When evidence is weak, say what is unknown and propose the cheapest observation that would reduce uncertainty.

## Advanced use

For datasets with repeated events, construct a transition log with:

`consumer_id | timestamp | prior_state | event | evidence | inferred_policy | next_state | outcome`

Then compare which evidence or actions are associated with successful transitions. Do not infer causality from correlation alone.

For detailed state dimensions and examples, read `references/consumer-model.md`.
