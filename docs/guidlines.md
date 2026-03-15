B31MV Assignment 2 - 15%
Image Classification
Due Date: 16.03.2026
Objective
The objective of this assignment is to implement and compare a traditional Bag of VisualWords (BoVW)
image classification pipeline with a deep learning convolutional neural network (CNN) for cat and dog
breed recognition using the Oxford-IIIT Pet dataset. The assignment also investigates the impact of
domain-specific data augmentation techniques on classification performance.
Dataset
This project uses the Oxford-IIIT Pet dataset, which contains labelled images spanning 37 pet breeds
(including both cats and dogs). Each image is annotated with its corresponding breed label.
Data Acquisition
Obtain the dataset using one of the following methods:
Kaggle
https://www.kaggle.com/competitions/oxford-iiit-pet-dataset/
Official Visual Geometry Group (VGG) - (Contains direct image and annotation downloads)
https://www.robots.ox.ac.uk/~vgg/data/pets/
PyTorch API
import torchvision . datasets as datasets
dataset = datasets . OxfordIIITPet ( root = DATA_ROOT , download = True )
Task 1: Data Exploration and Preprocessing (10 marks)
1. Visualize representative sample images from each class.
2. Convert images to grayscale for the traditional BoVW pipeline.
3. Normalize image tensors for deep learning models.
4. Split the dataset into training, validation, and test sets.
Task 2: Feature Extraction using ORB (12 marks)
1. Detect keypoints using the ORB feature detector.
2. Extract descriptors from grayscale images.
3. Store descriptors for all training images for codebook generation.
1
Task 3: Codebook Generation and Representation (12 marks)
Construct visual vocabularies using Mini-Batch K-Means clustering with codebook sizes: [ K = 100, 300,
500 ]
For each value of K:
1. Train the codebook using descriptors from the training set only.
2. Represent every image as a normalized histogram of visual words.
3. Prepare histogram features for training, validation, and test sets.
Task 4: Classification using Traditional Machine Learning (22
marks)
For each codebook size:
1. Train a Gradient Boosting classifier on the training histogram features.
2. Evaluate the classifier on the validation set using:
• Accuracy
• Precision
• Recall
• F1-score
3. Compare results for K = 100, K = 300, and K = 500.
4. Select the best-performing vocabulary size.
5. Retrain the classifier using training and validation data.
6. Report final performance on the test set and include a confusion matrix.
Task 5: Deep Learning Classification (22 marks)
1. Load a pre-trained DenseNet-121 model.
2. Replace the final classification layer for 10 classes.
3. Train (fine-tune) the network using the training dataset.
4. Evaluate performance on the validation and test sets using accuracy, precision, recall, and F1-score.
Task 6: Data Augmentation (12 marks)
Apply aerial-image appropriate augmentation:
• Rotation (90°, 180°, 270°)
• Horizontal flipping
• Vertical flipping
• Slight scaling
1. Retrain the DenseNet-121 model using the augmented dataset.
2. Compare performance with the non-augmented CNN model.
2
Submission Format (MANDATORY)
STUDENTS MUST SUBMIT ONE SINGLE PDF FILE ON CANVAS. They must also
include a link to their code (either in Google Colab or as a Python notebook) within the
submitted PDF.
Instructions for the Report
• Submit one report covering the entire assignment, including all exercises and sub-questions. Use
consistent numbering and retain the original question structure in your answers (e.g. Part A, Q1.1).
• The report should be written as a technical report. It must be clear enough that a reader unfamiliar
with the assignment can understand what was done and why.
• Code (screenshots only): All code must be shown as screenshots embedded in the PDF (no raw
code files). Screenshots should focus on key parts only. Each code snippet must be explicitly
referenced in the text (e.g. “see Code Snippet 1, line 5”) and its purpose clearly explained.
• Results & figures: All results must be presented as figures or tables with proper captions. Every
figure/table must be referenced in the main text (e.g. “Figure 2 shows. . . ”) and explained, not
just displayed. Focus on presenting your results in a clear and understandable manner - length of
the report is not important.
• Analysis & discussion: Discuss the results obtained, including limitations, failure cases, and sensitivity
to parameters, where relevant.
• Short conclusion: Provide a short concluding section summarising the main findings.
MARKING PROFILE FOR ALL ASSIGNMENTS
• [90%] – Technical content
Marks are awarded based on:
o Correct and appropriate methodology
o Correctness and coherence of the implementation (coding)
o Quality and correctness of results (screenshots/plots etc)
Incomplete, incorrect, or poorly justified answers will receive reduced marks
• [10%] – Presentation clarity
Assessed based on:
o Clear structure and logical flow
o Proper in-text referencing of figures, tables, and code snippets
o Figures and tables correctly captioned and discussed
o Concise, technical, and professional academic writing
3