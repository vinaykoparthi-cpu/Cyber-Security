# Cyber-Security
UNSW-NB15 INTRUSION DETECTION AND LABEL-POISONING STUDY
Module: MOD006570 – Cyber Security and AI Case Studies

PROJECT OVERVIEW

This project investigates whether a neural network can distinguish malicious
network traffic from normal traffic. It also examines how the detector is
affected when an insider deliberately changes training labels.

The project contains three parts:

Part A – Explore the dataset, compare machine-learning models and evaluate the
selected intrusion detector.

Part B – Test random and targeted label-poisoning attacks at different
poisoning levels.

Part C – Propose a secure autonomous-agent system for preparing data, checking
integrity, training, validating, deploying and monitoring the model.


DATASET

The project uses the official UNSW-NB15 cybersecurity dataset.

Dataset source:
https://research.unsw.edu.au/projects/unsw-nb15-dataset

The official training and testing split is retained. Testing labels are never
changed because the testing data must provide an honest evaluation of every
trained model.


REQUIRED SOFTWARE

- Python 3
- Jupyter Notebook or JupyterLab
- pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- joblib

The required packages can be installed using:

pip install pandas numpy matplotlib seaborn scikit-learn joblib jupyter


HOW TO RUN THE PROJECT

1. Download the official training and testing CSV datasets.
2. Place both datasets inside the folder expected by the notebook.
3. Open the project notebook in Jupyter Notebook or JupyterLab.
4. Select “Restart Kernel and Run All Cells”.
5. Wait until all model-training and poisoning experiments finish.
6. Check that the tables, figures and final results appear correctly.
7. Keep the executed outputs visible before submission.

The complete run may take time because the neural network is retrained at
several poisoning levels.


DATASET CHECK

Training records: 175,341
Testing records: 82,332
Columns: 45
Missing cells: 0
Duplicate rows: 0
Target classes: 2

Label 0 represents normal traffic.
Label 1 represents malicious traffic.


PROJECT WORKFLOW

1. Import and inspect the dataset.
2. Check missing values, duplicates and target labels.
3. Explore class balance and network-traffic behaviour.
4. Prepare numeric and categorical variables.
5. Compare a linear baseline with neural-network models.
6. Select the model using validation attack F1.
7. Evaluate the clean model on the untouched testing set.
8. Apply random and targeted label poisoning.
9. Measure recall, precision, F1, miss rate and false alarms.
10. Compare the effect on individual attack families.
11. Design a secure autonomous deployment architecture.
12. Save the generated figures, results and trained model.


MAIN RESULTS

The Wide MLP containing hidden layers of 64 and 32 neurons was selected.

Validation attack F1: 0.9619
Clean test attack precision: 0.8229
Clean test attack recall: 0.9781
Clean test attack F1: 0.8938
Clean test ROC AUC: 0.9783

Random label flipping did not seriously reduce attack recall, although it
increased false alarms.

Targeted attack-to-normal poisoning caused much greater damage. At 25%
poisoning, attack recall fell from 0.9781 to 0.6484. The poisoned model missed
approximately 15,939 genuine attacks.

Shellcode, Reconnaissance, Worms and Fuzzers were among the attack families most
seriously affected by targeted poisoning.


SECURITY RECOMMENDATIONS

- Protect training data using hashes and immutable versions.
- Restrict who can modify labels.
- Keep validation separate from model training.
- Check recall for individual attack families.
- Sign approved models before deployment.
- Monitor changes in recall, alert volume and false alarms.
- Quarantine suspicious datasets.
- Roll back to the last trusted model when unsafe behaviour is detected.
