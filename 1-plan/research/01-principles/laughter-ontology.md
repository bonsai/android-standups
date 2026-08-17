# Laughter Ontology

## Scope

Define laughter and humor response as a multidimensional phenomenon rather than a single binary variable.

## Root

```text
LAUGHTER_HUMOR_RESPONSE
├── COGNITIVE
├── AFFECTIVE
├── PHYSICAL
├── LINGUISTIC
├── SOCIAL
├── BEHAVIORAL
├── TEMPORAL
├── CONTEXTUAL
├── SEMANTIC
├── SOCIO_CULTURAL
├── AUDIENCE
└── MEASUREMENT
```

## Cognitive

```text
expectation
incongruity
surprise
recognition
reinterpretation
resolution
absurdity
```

## Affective

```text
amusement
pleasure
relief
tension_release
embarrassment
schadenfreude
mixed_emotion
```

## Physical

```text
FACIAL
  mouth
  eyes
  cheeks

VOCAL
  laugh
  chuckle
  snort
  silence

RESPIRATORY
POSTURAL
GESTURAL
MOVEMENT
```

Physical observations must not automatically be treated as proof of amusement or humor.

## Linguistic

```text
wordplay
ambiguity
pun
irony
metaphor
understatement
exaggeration
timing
```

## Social

```text
affiliation
bonding
status
dominance
ridicule
embarrassment
politeness
group_norm
```

## Behavioral

```text
smile
laugh
speech_interruption
hesitation
repetition
imitation
avoidance
```

## Temporal

```text
setup
anticipation
punchline
pause
reaction
aftershock
recovery
delayed_laughter
```

## Contextual

```text
situation
relationship
culture
shared_knowledge
environment
audience
```

## Semantic

```text
literal
conventional
implied
violated
reframed
```

## Socio-cultural

```text
taboo
norm_violation
convention
stereotype
identity
cultural_difference
```

## Audience response

```text
laugh
smile
silence
groan
confusion
rejection
delayed_laughter
```

## Measurement

```text
SUBJECTIVE
  humorousness
  amusement
  self_reported_laughter

BEHAVIORAL
  laughter_event
  smile
  movement

FACIAL
  landmarks
  mouth_motion
  eye_motion

VOCAL
  laugh_signal
  prosody
  pause

PHYSIOLOGICAL
  respiration
  other_observable_signals

LINGUISTIC
  utterance
  timing
  semantic_features

MULTIMODAL
  aligned_observations
```

## Critical distinctions

```text
humorousness != amusement
amusement != laughter
laughter != smile
laughter != comprehension
physical_laughter_signal != confirmed_humor
```

Possible cases include:

```text
funny_but_no_laughter
laughter_without_humor
confusion_with_laughter
social_laughter
nervous_laughter
understood_but_not_funny
funny_after_delayed_interpretation
```

## Laughter event

```text
LAUGHTER_EVENT
{
  trigger,
  expectation,
  deviation,
  interpretation,
  emotion,
  physical_response,
  social_context,
  timing,
  audience_response,
  subjective_judgment
}
```

## Research principle

The ontology should preserve the distinction between what a person experiences, what a person reports, and what an observer or sensor measures.

## MediaPipe role

MediaPipe belongs primarily to the physical observation layer. It should provide observable facial/body features and temporal changes; it should not be treated as a ground-truth humor classifier.

## Research objective

Use the ontology to connect:

```text
language
→ context
→ world knowledge
→ expectation
→ deviation
→ interpretation
→ affect
→ physical response
→ social response
```

and investigate which relationships explain human humor judgments.
