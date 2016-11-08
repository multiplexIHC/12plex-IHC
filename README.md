# cppipe
Image coregistration tool for multiplex immunohistochemistry
Overview
Since the whole slide digital image scanner produces raw images containing minor misalignments between
images taken with different markers, a set of 12 images need to be precisely co-registered in a single pixel
resolution.
Download and Install
We have tested our modules on Windows and Mac OS X, but they should also run on and Linux.
• Install CellProfiler version 2.1.1.
• Download "Alighment_Batch.cppipe".
We use the following materials for our step-by-step protocol shown below.
• Alignment_Default.xlsx
• SVS image viewer (e.g. ImageScope by Leica Biosystems)
Step-by-Step Tutorial
1. Change file names of svs images by adding “One” “Two” “Three”…”Twelve” (Case sensitive).
e.g. XXX_Nuclei_One.svs
YYY_PD-1_Two.svs
ZZZ_CD3_Three.svs
2. Open a svs image file. Identify a target cell or structure that can be utilized for alignment. Targets should
be in stable tissues throughout iterative staining cycles, and make sure that selected target exists in both the
first and the last cycle-image.
3. Crop svs image into small-size TIF or JPG images including the target identified in Step 2 (Typically, 200
x 200 pixel-size is sufficient). Record the values of X and Y coordinates of the left-top corner of the
cropped image, and paste the values of X and Y coordinates to column C and D (blue arrow) in the Excel
spread sheet, "Alignment_Default.xlsx".
4. Repeat Steps 2 & 3 for all 12 images. Save the excel file with a new name. If the number of images is less
than 12, create dummy files and prepare a total of 12 files including “One” to “Twelve”. All of 12 image
files should have a same canvas size. If you have less than 12 images, you need to prepare same-size
dummy files including missing number file names such as "Eleven", "Twelve", etc.
5. Run CellProfiler with "Alighment_Batch.cppipe" pipeline.
(1) Select favorite folders for input/output (#1).
(2) Drop files to the space shown as #2 below.
(3) Press “Analyze images” (#3).
Please make sure that all of 12 images are prepared with numbering from “One” to "Twelve" (Case
sensitive). A missing number and misspelling cause an alert message.
6. Press “F” and draw the outline of the target (red arrow). Press "Done". You can undo the selection by
clicking “Undo” (blue arrow). Repeat this step for all images. You will see 11 csv files and a folder
“Pictures” in your output folder. Image2, Image3,,,Image12 indicate delta X and Y between Image1 vs
Image2, Image3,,,Image12, respectively.
7. Open a csv file named Image2. Copy the values of “Align_Xsh” and “Align_Ysh” (blue arrow), and paste
them to yellow cells (red arrow) in the “Alignment_Default” excel file. Repeat this for the rest of files.
8. Select an area of your interest in ImageOne. Input the values of “Left: and “Top” to “a”. X-Y coordinates
of the rest of 11 images will be calculated and shown in the corresponding cells in "b".
(c) 2016, Takahiro Tsujikawa, Rohan N. Borkar and Vahid Azimi. Released under the GPLv2 - see LICENCE
for details.
