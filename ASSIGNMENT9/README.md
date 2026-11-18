# UCS420 Cognitive Computing - Lab Assignment 9

**Landing AI: Vision-Based Cognitive Systems**  
**Student:** Mehakdeep Kaur  
**Roll Number:** 1024170364

This folder contains the Jupyter solution, report, Landing AI evaluation exports, confusion matrices, and training charts for both projects.

## Files in this folder

| File | Description | Latest commit |
|---|---|---|
| [UCS420_Assignment9_LandingAI_Solution.ipynb](UCS420_Assignment9_LandingAI_Solution.ipynb) | Complete Jupyter Notebook: workflows, code, evaluation, plots, and interpretation | Add Assignment 9 |
| [UCS420_Assignment9_LandingAI_Solution.pdf](UCS420_Assignment9_LandingAI_Solution.pdf) | Complete assignment report | Add Assignment 9 |
| [Q1CSV.csv](Q1CSV.csv) | Medicine-label model evaluation export (87 image records) | Add Assignment 9 |
| [Q1 CONFUSION MATRIX.png](Q1%20CONFUSION%20MATRIX.png) | Medicine-label evaluation confusion matrix | Add Assignment 9 |
| [Q1 CHARTS.png](Q1%20CHARTS.png) | Medicine-label training and validation charts | Add Assignment 9 |
| [Q2 CSV.csv](Q2%20CSV.csv) | Emotion-classification export (400 train + 100 dev records) | Add Assignment 9 |
| [Q2 CONFUSION MATRIX.png](Q2%20CONFUSION%20MATRIX.png) | Emotion-classification confusion matrix supplied with the results | Add Assignment 9 |
| [Q2 TRAIN CONFUSION MATRIX.png](Q2%20TRAIN%20CONFUSION%20MATRIX.png) | Confusion matrix calculated from the 400 training records | Add Assignment 9 |
| [Q2 TRAIN DEV ACCURACY.png](Q2%20TRAIN%20DEV%20ACCURACY.png) | Training/development accuracy comparison calculated from the CSV | Add Assignment 9 |
| [requirements.txt](requirements.txt) | Python package dependencies | Add Assignment 9 |
| [UPLOAD_TO_GITHUB.md](UPLOAD_TO_GITHUB.md) | Steps for uploading this folder to GitHub | Add Assignment 9 |

> GitHub's normal folder view automatically displays file names, the latest commit message, and the update time. The `Latest commit` column above is a preview; GitHub will generate the actual commit information after these files are uploaded.

## Project 1 - Medicine Bottle Label Reading Assistant

An object-detection model locates the medicine label. The detected crop can then be passed to OCR to read the medicine name, strength, batch number, manufacturing date, expiry date, and MRP. Extracted values must be verified against the physical packaging; OCR is not a substitute for pharmacist or clinician verification.

**Supplied export:** 87 records; all 87 rows show the predicted class matching the ground-truth class. Mean prediction confidence from the JSON export is **97.66%**. Mean bounding-box IoU calculated from the exported boxes is **0.9442**. These figures describe the supplied export and should not be called independent test performance unless the split is confirmed as held out.

## Project 2 - Emotion-Aware Cognitive Assistant

The classifier predicts `neutral`, `happy`, `angry`, `surprise`, or `sad`. The notebook evaluates training and development records separately.

| Split | Images | Correct | Accuracy |
|---|---:|---:|---:|
| Train | 400 | 234 | 58.5% |
| Dev | 100 | 41 | 41.0% |
| Combined | 500 | 275 | 55.0% |

The 17.5 percentage-point train/dev accuracy gap suggests weak generalization and/or overfitting. The `sad` class is especially difficult in the training confusion matrix, with many examples predicted as `angry`.

Facial-expression predictions are uncertain signals and must not be treated as reliable measurements of someone's internal emotional state. Use cautious wording, allow correction, and do not use the prediction for high-stakes decisions.

## Run the notebook

1. Download or clone the repository.
2. Open the notebook in Jupyter or Google Colab.
3. Keep the two CSV files in the same folder as the notebook.
4. Run cells from top to bottom. Export analysis does not require an API key.
5. Live Landing AI inference is optional and requires your own deployed endpoint ID and API key. Never commit credentials to GitHub.

**Note:** CSV exports contain evaluation metadata, not original image pixels; they cannot independently retrain the image models.
