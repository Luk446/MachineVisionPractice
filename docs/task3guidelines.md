B31MV Assignment 3
3D Reconstruction and Motion Estimation
Weight: 15%
Due Date: 07.04.2026
Introduction and Data Access
This assignment involves the development of a high-performance Python pipeline for 3D
reconstruction. You will estimate camera geometry via sparse matching and generate
a dense depth map using advanced disparity estimation algorithms. All algorithmic
implementation must be performed in Python using NumPy and OpenCV.
Dataset Download
The required dataset for this assignment must be downloaded from the following repository:
https://drive.google.com/drive/folders/1-F8gd-kjQ2a-x2EXJYOaLwHhTt4apNBJ
Reference Image Verification
Confirm that the stereo pair has been successfully loaded from your project directory.
The images displayed below must be accessible via your local images/ sub-folder for the
implementation to proceed.

Dataset and Directory Constraints
All camera parameters, intrinsic values, and point correspondences are stored in Pythonnative
compressed NumPy archives (.npz). The specific directory containing all necessary
files is:
B31MV Assignment3 data (2026)/
1
B31MV: Machine Vision Assignment 3 – 2026
Required Data Inputs:
• intrinsics.npz: Contains 3 × 3 intrinsic matrices (K1, K2), rotation matrices
(R1, R2), and translation vectors (t1, t2).
• some corresp.npz: A curated set of validated point correspondences (pts1, pts2)
used for initial Fundamental Matrix estimation.
Section 1: Sparse Reconstruction
Part 1.1: Eight-Point Algorithm (10 marks)
The Task:
Implement the Eight-Point algorithm to estimate the Fundamental Matrix F that relates
the two views.
Technical Details:
Scale pixel coordinates by 1/M. Solve using Singular Value Decomposition (SVD)
and enforce the rank-2 constraint by zeroing the smallest singular value before unnormalizing:
F = T TFnormT .
Required Outputs:
• The computed 3 × 3 Fundamental Matrix F.
• A visualization displaying selected points in Image 1 and their corresponding epipolar
lines in Image 2.
Part 1.2: Epipolar Correspondences (20 marks)
The Task:
Find matching coordinates in the target image by searching along epipolar lines defined
by F.
Technical Details:
Use the Sum of Squared Differences (SSD) over a 15×15 window to find the match
that minimizes the error along the sampled epipolar line l = Fx.
Required Outputs:
• A list or table displaying the coordinates of five reference points in Image 1 and
their corresponding estimated matches in Image 2.
Part 1.3: Essential Matrix (10 marks)
The Task:
Convert the Fundamental Matrix to the Essential Matrix using camera calibration data.
Technical Details:
Calculate the matrix using the calibrated geometry equation: E = KT
2 FK1.
Required Outputs:
The numerical values of the 3 × 3 Essential Matrix E.
2
B31MV: Machine Vision Assignment 3 – 2026
Part 1.4: Triangulation (10 marks)
The Task:
Reconstruct 3D points from 2D correspondences using the linear triangulation method.
Technical Details:
Utilize Singular Value Decomposition (SVD) to solve the homogeneous system for
3D coordinates.
Required Outputs:
• The calculated Mean Re-projection Error (must be less than 2 pixels).
• Verification that triangulated points satisfy the chirality constraint (Z > 0).
Part 1.5: Full 3D Sparse Model (10 marks)
The Task:
Integrate all previous parts to create a complete sparse 3D model using the provided
correspondences.
Technical Details:
Project validated correspondences into 3D space and visualize the resulting point cloud
using standard coordinate orientations.
Required Outputs:
A 3D scatter plot of the reconstructed scene.
Section 2: Dense Reconstruction
Part 2.1: Image Rectification (10 marks)
The Task:
Warp the stereo images so that all epipolar lines become horizontal and collinear.
Technical Details:
Compute rectification matrices M1,M2 using the provided camera extrinsics to reduce
the correspondence search to a 1D horizontal operation.
Required Outputs:
A side-by-side visualization of the rectified left and right images.
Part 2.2: Dense Disparity Map (10 marks)
The Task:
Generate a high-resolution disparity map using a Semi-Global Block Matching (SGBM)
approach.
Technical Details:
Implement the disparity estimation using global smoothness constraints and a multi-way
matching mode to optimize depth accuracy across the search range.
Required Outputs:
A color-mapped visualization of the Dense Disparity Map (dispM) using a color bar to
indicate pixel shift.
3
B31MV: Machine Vision Assignment 3 – 2026
Part 2.3: Depth Map Generation (10 marks)
The Task:
Convert the pixel-based disparity map into a physical depth map.
Technical Details:
Use the formula Z(x, y) = b·f
dispM(x,y) .
Required Outputs:
• A visualization of the Dense Depth Map (depthM) using a perceptually uniform
colormap.
• The baseline (b) and scaled focal length (f) values used in the calculation.
Submission Format (MANDATORY)
STUDENTS MUST SUBMIT ONE SINGLE PDF FILE ON CANVAS.
They must also include a link to their code (either in Google Colab or as a
Python notebook) within the submitted PDF.
Instructions for the Report
• Submit one report covering the entire assignment, including all exercises and subquestions.
Use consistent numbering and retain the original question structure in
your answers (e.g. Part A, Q1.1).
• The report should be written as a technical report. It must be clear enough that a
reader unfamiliar with the assignment can understand what was done and why.
• Code (screenshots only): All code must be shown as screenshots embedded in the
PDF (no raw code files). Screenshots should focus on key parts only. Each code
snippet must be explicitly referenced in the text (e.g. “see Code Snippet 1, line 5”)
and its purpose clearly explained.
• Results & figures: All results must be presented as figures or tables with proper
captions. Every figure/table must be referenced in the main text (e.g. “Figure 2
shows. . . ”) and explained, not just displayed. Focus on presenting your results in
a clear and understandable manner - length of the report is not important.
• Analysis & discussion: Discuss the results obtained, including limitations, failure
cases, and sensitivity to parameters, where relevant.
• Short conclusion: Provide a short concluding section summarising the main findings.
4
B31MV: Machine Vision Assignment 3 – 2026
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
5