# kinase

An open data project based on http://everkinetic.com created by Greg Priday. It
is a fitness dataset featuring descriptions and images for over 250 exercises.

## Usage

Dataset entries separated by directories named after the exercise's identifier,
which roughly corresponds to an index number (note some indices are omitted).

### Structure

The directories are structured like such:

```
data/
├── <ID>/              # exercise directory, named using its identifier
│  ├── data.json       # serialized data describing exercise
│  ├── relaxation.svg  # vector image of exercise in relaxation (optional)
┆  └── tension.svg     # vector image of exercise in tension (optional)
```

### Schema

Each data file adheres to the following schema, containing the following
entries:

- `"id"`: Unique string identifier.
- `"name"`: Unique internal exercise name, written in kebab-case.
- `"title"`: Human-readable title.
- `"primer"`: Quick primer or note.
- `"type"`: Array of exercise kinds in.
  - Must be from: {`"compound"`, `"isolation"`, `"isometric"`}
- `"part"`: Body part worked.
  - Must be in: {`"arms"`, `"back"`, `"chest"`, `"core"`, `"legs"`,
    `"shoulders"`}
- `"primary"`: Array of primary muscles used.
  - Must be from: {`"abdominals"`, `"back"`, `"biceps brachii"`, `"core"`,
    `"deltoid"`, `"erector spinae"`, `"forearm"`, `"gastrocnemius"`, `"glutaeus
    maximus"`, `"hip abductors"`, `"ischiocrural muscles"`, `"latissimus
    dorsi"`, `"obliques"`, `"pectoralis major"`, `"quadriceps"`, `"shoulders"`,
    `"soleus"`, `"trapezius"`, `"triceps brachii"`, `"upper back"`}
- `"secondary"`: Array of secondary muscles used.
  - Must be from same as `"primary"`.
- `"equipment"`: Array of equipment needed.
  - Must be from: {`"balance board"`, `"bar"`, `"barbell"`, `"bench press
    machine"`, `"bench"`, `"body"`, `"bosu ball"`, `"butterfly machine"`,
    `"cable machine"`, `"chest machine"`, `"decline bench"`, `"dumbbell"`,
    `"dumbbells"`, `"exercise band"`, `"flat bench"`, `"hyperextension bench"`,
    `"incline bench"`, `"machine"`, `"medicine ball"`, `"parallel bars"`,
    `"pull-up bar"`, `"smith machine"`, `"stability ball"`, `"t-bar machine"`,
    `"towel"`, `"v-bar"`, `"weight plate"`, `"wide bar"`}
- `"steps"`: Array of steps.
- `"tips"`: Array of tips.
- `"references"`: Array of references used.

## Contribution

Every (little) contribution is very welcomed!
