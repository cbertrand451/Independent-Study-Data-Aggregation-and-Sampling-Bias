# Data Aggregation and Sampling Bias: How Does It Affect Analysis?

## Summary

This project is an independent-study data analysis project focused on how common data decisions can change the conclusions we draw from ecological datasets. Using Portal Project rodent data, the notebooks explore how aggregation level, sampling strategy, missing data, and data-quality filtering affect data analysis and modeling for machine learning. 

The folder is organized like a small workshop or project homepage. The goal is for a reader to understand what the project is about, what data it uses, where to start, and how each notebook contributes to the larger question.

## Requirements

This project is designed to be run locally with Python and Jupyter notebooks.

Recommended software:

- Python 3.x
- Jupyter Notebook or JupyterLab
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn, for the machine-learning preparation notebook

Suggested setup:

1. Create or activate a Python environment for the project.
2. Install the packages listed above.
3. Open the notebooks in JupyterLab, Jupyter Notebook, VS Code, or another notebook editor.
4. Run notebooks from the project root so relative paths such as **data/**, **images/**, and **output/** resolve correctly.

## Project Workflow

Start with *simplified_dataset.ipynb*, which prepares the working dataset used by the analysis notebooks. It would also be helpful to run the *plots.ipynb* notebook as well, so that the correct visualizations are displayed in the correlating notebooks. After that, the project is designed to move through the numbered notebooks in order, although several modules can also be read independently.

Recommended order:

1. `simplified_dataset.ipynb`  
   Builds the simplified working dataset from the raw Portal rodent, species, plots, and data-note files.

2. `analysis/aggregation_analysis/01_population_trends.ipynb`  
   Compares population trends at different taxonomic levels, especially species-level versus genus-level summaries.

3. `analysis/aggregation_analysis/02_monthly_vs_yearly.ipynb`  
   Examines how monthly and yearly aggregation can produce different patterns from the same observations.

4. `analysis/aggregation_analysis/03_mean_vs_median_weight.ipynb`  
   Compares mean and median body-weight summaries across grouping levels.

5. `analysis/sampling_bias/04_stratified_sampling.ipynb`  
   Compares random sampling and stratified sampling, with attention to species representation.

6. `analysis/sampling_bias/05_machine_learning_preparation.ipynb`  
   Prepares sampled datasets for model workflows and checks how sampling choices affect representation and prediction targets.

7. `analysis/missing_data_analysis/06_data_quality_filtering.ipynb`  
   Uses note fields as data-quality flags and compares results before and after filtering.

8. `analysis/missing_data_analysis/07_missingness_simulation_scenarios.ipynb`  
   Simulates different missing-data patterns to show how missingness can affect ecological conclusions.

`plots.ipynb` collects plot-generation work for the figures stored in `images/`.

## Based On

This project is inspired by the structure of the Data Carpentry Ecology Workshop:

https://datacarpentry.github.io/ecology-workshop/

That workshop presents a clear worfklow for learners to follow and explore how to use different data-focused programs, with the ecology dataset as the example data. This project aims to follow a similar structure, but instead explores how aggregation, sampling, and missingness shape results.

The data source is related to the Portal Project, a long-term ecological study of small mammal communities in the Chihuahuan Desert. 

Here are the sources that helped explain and provide the data necessary to comeplete this project:

- Portal Project Teaching Database: https://doi.org/10.6084/m9.figshare.1314459
- Data Carpentry Ecology Workshop data page: https://datacarpentry.github.io/ecology-workshop/instructor/data.html
- Portal Project information: https://www.weecology.org/data-projects/portal-teaching-db/

## Data Dictionary

The `data/` folder contains the source files used by the notebooks.

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

### Derived Files

- `output/merged_full.csv`: merged working dataset produced by the data-preparation workflow.
- `images/fig_*.png`: exported figures used across the analysis notebooks.

## Usage Rights

The Portal Project teaching data is commonly distributed for teaching and reuse, but the exact license depends on the source and version being used. The current data here is placed under the **CC0 1.0 Universal License**, meaning users are allowed to copy, modify, and distribute the data and work. 

This license was found from the following source:

https://github.com/weecology/portal-teachingdb/blob/master/LICENSE

## Project Purpose

This project was built as an independent study between Information Science + Data Science Senior Undergraduate Colin Bertrand and Library and Information Science Instructor Elizabeth Wickes from the iSchool at University of Illinois Urbana - Champaign.

The project asks a practical data-science question: *when analysts make reasonable decisions about grouping, sampling, filtering, and missing data, how much can those decisions change the results?*

By working through the notebooks, a reader should be able to:

- Describe how aggregation level can hide or reveal ecological patterns.
- Compare species-level, genus-level, monthly, and yearly summaries.
- Explain why random samples and stratified samples can tell different stories.
- Recognize how data-quality notes can be used as filtering rules.
- Understand how different missing-data patterns can bias conclusions.
- Connect exploratory analysis decisions to downstream modeling preparation.

## Repository Structure

```text
.
|-- data/                         Source data files
|-- analysis/
|   |-- aggregation_analysis/      Aggregation-level notebooks
|   |-- sampling_bias/             Sampling and model-preparation notebooks
|   `-- missing_data_analysis/     Data-quality and missingness notebooks
|-- images/                       Exported figures
|-- output/                       Derived datasets
|-- simplified_dataset.ipynb       Dataset preparation notebook
|-- plots.ipynb                    Figure generation notebook
`-- README.md                     Project homepage
```
