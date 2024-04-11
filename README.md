## Happy ALMANA...
...is the collaborative group formed by  <ins>Al</ins>iya S., <ins>Ma</ins>rita S., and <ins>Na</ins>talie M. within the scope of the capstone project for the  Data Practitioner Course at the [Neue Fische School](https://www.neuefische.de/en).   The project was [presented](../Capstone_Happy_Almana/slides/Happy_Capstone.pdf) at the graduation event on April 11, 2024.

[The World Happiness Report](https://worldhappiness.report/data/) with its associated data and some additional related data from Numbeo, Kaggle and the United Nations are the focus of this project. For more details about the datasets, features and sources visit the [Features](../Capstone_Happy_Almana/Features.md) document in this repository.

## Assignment
In this capstone project, we  set out to analyze the  data, highlight trends and relationships  between the target, "life_ladder", and  other features. Additionally, we sought to create a predictive model for the life_ladder, starting initially with a baseline model of just one feature and then methodically adding and removing features, testing the results to optimize the  model(s). 

## Requirements:

- pyenv with Python: 3.11.3

### Setup

Use the requirements file in this repo to create a new environment.

```BASH
make setup

#or

pyenv local 3.11.3
python -m venv .venv
source .venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
```

The `requirements.txt` file contains the libraries needed for deployment.. of model or dashboard .. thus no jupyter or other libs used during development.


