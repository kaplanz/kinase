# kinase

An open dataset of nearly 300 fitness exercises, each with written instructions
and most with illustrations, adapted from [everkinetic] by Greg Priday.

[everkinetic]: http://everkinetic.com

## Structure

Each exercise lives in its own directory under `data/`, named after its
four-digit identifier. Identifiers are index numbers, and some numbers in the
sequence are unused.

```text
data/
└── <ID>/               # one exercise, named after its identifier
   ├── data.json        # exercise data
   ├── relaxation.svg   # illustration of the relaxed position (optional)
   └── tension.svg      # illustration of the tensed position (optional)
```

Most exercises have both illustrations, and the rest have one or none.

## Schema

Every `data.json` holds one object with all of the fields below. A field holding
an array may hold an empty one.

| Field        | Type             | Contents                                   |
| ------------ | ---------------- | ------------------------------------------ |
| `id`         | string           | identifier, the same as the directory name |
| `name`       | string           | unique name, in kebab-case                 |
| `title`      | string           | human-readable title                       |
| `primer`     | string           | short summary of the exercise              |
| `type`       | array of strings | kinds of movement                          |
| `part`       | string           | body part worked                           |
| `primary`    | array of strings | muscles the exercise mainly works          |
| `secondary`  | array of strings | muscles the exercise also works            |
| `equipment`  | array of strings | equipment needed                           |
| `steps`      | array of strings | instructions, in order                     |
| `tips`       | array of strings | advice on form and safety                  |
| `references` | array of strings | links to sources                           |

### Values

Five fields take their values from a fixed vocabulary:

- `type`: `compound`, `isolation`, `isometric`.
- `part`: `arms`, `back`, `chest`, `core`, `legs`, `shoulders`.
- `primary` and `secondary`: `abdominals`, `biceps brachii`, `deltoid`,
  `erector spinae`, `forearm`, `gastrocnemius`, `gluteus maximus`, `hamstrings`,
  `hip abductors`, `hip adductors`, `latissimus dorsi`, `obliques`,
  `pectoralis major`, `quadriceps`, `soleus`, `tibialis anterior`, `trapezius`,
  `triceps brachii`.
- `equipment`: `balance board`, `bar`, `barbell`, `bench`, `body`, `bosu ball`,
  `butterfly machine`, `cable machine`, `chest machine`, `decline bench`,
  `dumbbell`, `exercise band`, `flat bench`, `hyperextension bench`,
  `incline bench`, `machine`, `medicine ball`, `parallel bars`,
  `preacher bench`, `pull-up bar`, `smith machine`, `stability ball`,
  `t-bar machine`, `towel`, `v-bar`, `weight plate`, `wide bar`.

The equipment value `body` marks an exercise that needs no equipment, so it
never appears beside another value.

## Credits

The exercise descriptions and illustrations are adapted from [everkinetic],
created by Greg Priday.

## Contributing

Contributions of any size are welcome.

## License

This dataset is licensed under the [Creative Commons Attribution-ShareAlike 4.0
International](./LICENSE) license.
