# Data

This folder holds all of the original data used in this project:

### `data/Portal_rodent.csv`

Main rodent observation table. Each row represents a capture or survey record from the Portal rodent dataset.

Key fields include:

- `recordID`: unique record identifier
- `month`, `day`, `year`: date fields for the observation
- `period`: sampling period
- `plot`: plot number
- `species`: species code
- `sex`: recorded sex of the animal
- `age`: age category, where available
- `hfl`: hindfoot length
- `wgt`: body weight
- `note1` through `note5`: data notes and quality flags
- `id`: generated or combined identifier used in the local dataset

### `data/species.csv`

Species lookup table.

Fields:

- `species_id`: species code
- `genus`: genus name
- `species`: species name
- `taxa`: broad taxonomic group

### `data/plots.csv`

Plot lookup table.

Fields:

- `plot_id`: plot number
- `plot_type`: plot treatment or experimental category

### `data/Portal_rodent_datanotes.csv`

Data-note lookup table used to interpret the `note1` and related note fields in the rodent data.

Fields:

- `note1`: note code
- `meaning`: explanation of what the note code means
