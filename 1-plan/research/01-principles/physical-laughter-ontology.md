# Physical Laughter Ontology

## Purpose

Model observable physical manifestations associated with laughter without equating any single physical signal with the subjective experience of humor.

## Core principle

```text
Humor stimulus
  -> Cognitive / affective response
  -> Physical response
  -> Observable signal
  -> Measurement
```

Physical observation is evidence about a response, not proof of amusement.

## Root ontology

```text
PHYSICAL_LAUGHTER
├── RESPONSE
│   ├── Facial
│   ├── Vocal
│   ├── Respiratory
│   ├── Postural
│   ├── Gestural
│   └── Temporal
├── OBSERVATION
│   ├── Face_Landmarks
│   ├── Mouth_Movement
│   ├── Eye_Region
│   ├── Head_Movement
│   ├── Body_Movement
│   ├── Voice
│   └── Breathing
├── EVENT
│   ├── Onset
│   ├── Peak
│   ├── Offset
│   └── Episode
├── MEASUREMENT
│   ├── Amplitude
│   ├── Duration
│   ├── Frequency
│   ├── Velocity
│   ├── Symmetry
│   └── Temporal_Correlation
└── INTERPRETATION
    ├── Laughter_Candidate
    ├── Non_Laughter
    ├── Ambiguous
    └── Human_Confirmed
```

## Observation layers

### Facial

Potential observable features:

- mouth opening / closing
- mouth corner movement
- cheek movement
- eye-region movement
- head motion
- facial landmark trajectories

MediaPipe may be used as an observation layer for facial landmarks and temporal movement.

### Vocal

Potential features:

- voiced laughter
- unvoiced laughter
- rhythmic vocal bursts
- pitch variation
- intensity variation
- duration

### Respiratory

Potential features:

- rhythmic exhalation
- interrupted breathing
- breathing-rate change
- burst structure

### Postural / Gestural

Potential features:

- torso movement
- shoulder movement
- head movement
- hand gestures
- posture change

These should be treated as optional contextual signals, not universal markers.

## Temporal ontology

```text
stimulus_time
    ↓
response_onset
    ↓
laughter_episode
    ├── burst_1
    ├── burst_2
    └── burst_n
    ↓
response_peak
    ↓
response_offset
```

Temporal alignment is important because the research question concerns the relationship between a script event and a physical response.

## Event representation

```yaml
laughter_event:
  start: timestamp
  end: timestamp
  duration: value
  confidence: value
  facial_observation: value
  vocal_observation: value
  respiratory_observation: value
  postural_observation: value
  human_report: true|false|unknown
```

## Human ground truth

The physical layer must not replace human judgment.

Minimum human signal:

```text
laughed = true / false
```

Optional signals:

```text
intensity
felt_funny
reason
```

The experiment should distinguish:

```text
physical_laughter
subjective_amusement
humor_judgment
```

These are related but not identical variables.

## AI interpretation

```text
MediaPipe / sensors
        ↓
Observable features
        ↓
Laughter-event candidate
        ↓
AI interpretation
        ↓
Human confirmation
```

AI must not silently convert an observed facial movement into a claim that the person found the script funny.

## Humor research integration

```text
SCRIPT
  ↓
EXPECTED_ORDER
  ↓
DEVIATION
  ↓
HUMOR_CANDIDATE
  ↓
HUMAN_RESPONSE
  ├── subjective_laugh
  └── physical_observation
        ↓
      EVALUATION
        ↓
  HYPOTHESIS_REVISION
```

## Research questions

### RQ-P1
Which observable physical signals correlate with self-reported laughter?

### RQ-P2
Can temporal physical signals improve detection of laughter events?

### RQ-P3
Can physical observations distinguish amusement from other facial or vocal reactions?

### RQ-P4
Does physical-response evidence improve evaluation of AI-generated humor?

## Experimental caution

Do not assume:

```text
smile = laughter
laughter = humor
facial movement = amusement
```

The ontology is observational and probabilistic.

## Phase separation

Phase 1:

```text
Script + Human laughed/not-laughed
```

Phase 2:

```text
Script + Human judgment + MediaPipe / non-verbal observations
```

Phase 3:

```text
Multimodal evaluator
```

## Design principle

The physical layer should enrich the human response signal while preserving the distinction between what the body does, what the person reports, and what the AI infers.
