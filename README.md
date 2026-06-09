# OpenMuscle Dataset

Labeled and raw sensor capture sessions from [OpenMuscle](https://openmuscle.org)
wearable devices, published for machine learning research on hand and forearm
biomechanics. Free to use under CC BY 4.0 (see [License](#license)).

This is the first public drop of the corpus the
[OpenMuscle roadmap](https://github.com/Open-Muscle/OpenMuscle-Hub/blob/main/ROADMAP.md)
commits to: a hosted, downloadable set of hand-biomechanics sessions anyone can
train against. It will grow as new capture sessions land.

## Layout

```
flexgrid/   FlexGrid V3 capture sessions (CSV, 60-sensor pressure matrix)
merged/     Merged multi-session training CSVs produced by the PC pipeline
curated/    Hand-picked good sessions from early capture runs (Nov 29-30 era)
legacy/     Early prototype captures (txt) from pre-FlexGrid devices
```

Sessions were recorded with the tooling in
[OpenMuscle-Software](https://github.com/Open-Muscle/OpenMuscle-Software), which
also reads these formats (`openmuscle convert`, `openmuscle train`). A formal
schema document is on the roadmap; until then the loader code in
`pc/src/openmuscle/data/` is the format reference.

Empty (zero-byte) capture files from aborted sessions were excluded from this
repository.

## Devices

| Folder | Device | Sensors |
|--------|--------|---------|
| flexgrid, merged | FlexGrid V3 (15x4 Velostat pressure matrix, ESP32-S3) | 60 |
| curated, legacy | Earlier OpenMuscle prototypes (Band / FlexGrid V1 era) | varies |

Ground-truth labels, where present, come from the
[LASK5](https://github.com/Open-Muscle/OpenMuscle-LASK5) labeling wand or other
input devices recorded alongside the sensor stream.

## Using the data

```bash
git clone https://github.com/Open-Muscle/OpenMuscle-Dataset.git
```

The capture files are plain text/CSV; the clone transfers compressed (well under
the on-disk size). For training examples, see the
[OpenMuscle-Software](https://github.com/Open-Muscle/OpenMuscle-Software) README.

## Contributing data

Recorded sessions with an OpenMuscle device? Open an issue here or on the
[Hub](https://github.com/Open-Muscle/OpenMuscle-Hub/issues) to discuss adding
them. Contributions are credited per the
[org contributing guide](https://github.com/Open-Muscle/.github/blob/main/CONTRIBUTING.md).

## License

This dataset is licensed under
[Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
You may use, share, and adapt it for any purpose, including commercially, with
attribution to the OpenMuscle project.
