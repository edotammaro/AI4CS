# Password Strength Classification with Machine Learning

Classifies passwords into 5 strength levels (0 Very Weak → 4 Very Strong).
Exam project for *AI for Cyber Security* (M.Sc. Applied Computer Science, Parthenope).

## Approach
- Dataset: [PWLDS](https://github.com/Infinitode/PWLDS), 1,000,000 sampled passwords, 70/30 stratified split, fixed seed
- 13 hand-crafted features: length, upper/digit/special counts and ratios,
  unique characters, Shannon entropy, charset size, common-pattern count
- Why not TF-IDF: strong passwords share no tokens, and manual features keep the model interpretable
- Models: Logistic Regression, Gaussian Naive Bayes, Decision Tree, Random Forest (500 trees)
- Evaluation: accuracy, weighted precision, weighted F1, confusion matrices, learning curves (20%–100% of data)

## Results
Random Forest performs best (weighted F1 ≈ 0.945). Errors occur almost only between adjacent classes.

## Limitations
Labels come from the PWLDS dataset and may reflect a heuristic rule rather than real-world strength.

## Stack
Python · scikit-learn · pandas · NumPy · Google Colab

## Link dataset
https://github.com/Infinitode/PWLDS
