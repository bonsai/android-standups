# Expression Engine Ontology

## Purpose

Extend the research and generation engine from comedy-only output to general expressive production.

The engine should treat `type` as the form of the generated work, while intent, style, platform, audience, and evaluation remain separate dimensions.

## Type

```text
TYPE
├── comedy
│   ├── standup
│   ├── conte
│   ├── manzai
│   ├── sketch
│   ├── satire
│   └── parody
├── theater
│   ├── play
│   ├── monologue
│   ├── dialogue
│   └── screenplay
├── literature
│   ├── novel
│   ├── short_story
│   ├── flash_fiction
│   └── poetry
├── video
│   ├── youtube_short
│   ├── youtube
│   ├── commercial
│   └── web_video
├── performance
│   ├── improv
│   ├── storytelling
│   └── performance_art
└── other
    ├── advertisement
    ├── game
    ├── dialogue
    ├── speech
    └── custom
```

## Independent dimensions

### Intent

```text
humor
drama
emotion
education
persuasion
entertainment
```

### Style

```text
absurd
realistic
surreal
dark
warm
experimental
```

### Platform

```text
youtube_short
youtube
stage
theater
book
web
custom
```

### Audience

```text
general
children
adult
professional
niche
custom
```

### Evaluation

```text
human
ai
physical
audience
```

## Example

```yaml
type: conte
intent: humor
style: absurd
platform: youtube_short
audience: general
```

The same underlying premise may be transformed into `conte`, `theater`, `novel`, or another type without changing its core research representation.

## Engine model

```text
EXPRESSION_ENGINE
    -> TYPE
    -> INTENT
    -> STYLE
    -> PLATFORM
    -> AUDIENCE
    -> GENERATE
    -> EVALUATE
    -> REVISE
```

## Research implication

The humor research remains an important first domain, but the general research question becomes whether an AI system can model expectations, deviations, emotion, context, and audience response well enough to generate and evaluate different forms of human expression.
