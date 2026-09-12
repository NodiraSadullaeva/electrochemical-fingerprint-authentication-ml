# Machine Learning for Electrochemical Fingerprint Authentication

A BSc final year project applying machine learning to distinguish genuine from counterfeit spirits using electrochemical fingerprinting data (cyclic voltammetry), developed in partnership with an industrial technology SME.

## What this project does
Each sample is represented by a 1400-dimensional feature vector (current response across a voltage sweep), with only around 100 labelled training samples available (a classic high-dimensional, small-sample-size classification problem where naive approaches overfit badly).
- Preprocessing pipeline: long-to-wide feature engineering, z-score standardisation, PCA-based outlier detection
- 6 classification algorithms benchmarked end-to-end: logistic regression, linear SVM, SVM RBF, random forest, a neural network and a from-scratch SIMCA implementation
- Generalisation testing: repeated stratified train/test splits, train-test gap analysis and cross-validation variance, specifically to catch the overfitting this kind of feature-to-sample ratio invites
- Confidence-based deployment framework: inter-model agreement on unlabelled field samples, used to decide which predictions can be trusted automatically and which need a human in the loop

## Results
The two strongest models generalised cleanly across repeated cross-validation with no meaningful train–test gap, exceeding the project's pre-defined accuracy and stability criteria (with the original data given from the industry). Applied to unlabelled field samples, the models showed strong inter-model agreement, supporting a tiered auto-classify / flag-for-review deployment strategy. Full methodology, metrics, and critical discussion of the results (including honest scepticism about the very high accuracy) are in the written report (for confidentiality reasons).

**This work is currently contributing to a peer-reviewed publication in preparation with the collaborating company and academic partners.**

### A note on confidentiality
This was an industry-sponsored project, and the dataset was collected and is owned by the partner company. This means:
- The original dataset is not included
- Original cell outputs have been replaced with the outputs of the fake generated data to show what kind of visuals and outputs we would get if there was an input (obviously it is slightly different than if we would put the real data)
- The generated dataset is included here as all_data.csv

## Repository structure
[whisky_authentication_pipeline.ipynb](https://github.com/NodiraSadullaeva/electrochemical-fingerprint-authentication-ml/edit/main/whisky_authentication_pipeline.ipynb) - full pipeline
[all_data.csv]() - generated data
[requirements.txt](https://github.com/NodiraSadullaeva/electrochemical-fingerprint-authentication-ml/edit/main/requirements.txt)
[.gitignore](https://github.com/NodiraSadullaeva/electrochemical-fingerprint-authentication-ml/edit/main/.gitignore)
[README.md](https://github.com/NodiraSadullaeva/electrochemical-fingerprint-authentication-ml/edit/main/README.md)

## Tech stack
Python, pandas, scikit-learn, SciPy, NumPy, matplotlib, seaborn

## Acknowledgements
Supervised by Richard Bingham at the University of York. Developed in collaboration with an industrial technology partner, whose electrochemical sensing hardware generated the underlying data.

## License
Code in this repository is shared under the MIT License. This licence convers the code only, it does not extend to any data, as none is included.
