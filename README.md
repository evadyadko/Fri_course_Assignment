# Fri_course_Assignment
This is the GitHub repository of group 4 for the 'Digital Technology as a Medical Device (2025-2026-400-HDT4006)' course, for Assignment 2.
This is a prediction model based on clinical and radiomic features to identify pathological lymph nodes at risk of failure after radiotherapy.
DOI 10.1016/j.radonc.2020.02.005



## What this model does

We made the model interoperable by using standardized FHIR data and medical codes like SNOMED and LOINC. It calculates a risk score based on five specific features:

* Gender: Coded via SNOMED (Male/Female).
* T-Stage: Clinical stage T3 or T4.
* WHO PS: Patient performance status (grades 0-4).
* LALLN: The length of the largest lymph node.
* Corr_GLCM: A specific texture feature from imaging.


## How the risk is categorized

The model gives a percentage score that shows how likely the node is to fail. Based on the original paper, we group these into three levels:

* **High Risk**: Score $\ge 60\%$.
* **Medium Risk**: Score between $10\%$ and $60\%$.
* **Low Risk**: Score $\le 10\%$.

## Files in this repository

* **`myModel.py`**: The main code that processes the patient data, reads the patient in JSON format.
* **`opdracht.ipynb`**: The notebook where we built and defined the model parameters.
* **`testing_locally.ipynb`**: A test file with sample patients to make sure everything works.
* **`requirements.txt`**: The libraries you need to run this code.

## How to use it

pip install -r requirements.txt

Then you can use it in your own Python script like this:
Python

from myModel import Zhai_predictLymph
model = Zhai_predictLymph()
result = model.predict(patient_data)
print(result)

## Project Info

    Model URI: https://v3.fairmodels.org/instance/8da56fed-5f87-4699-9b69-38b255b08268.

    Reference: Zhai et al. (2020).

    Authors: Group 4 (Lisa van de Beek, Daan Dieteren, Casper Dijkstra, Eva Dyadko, Maggie Janisch).



