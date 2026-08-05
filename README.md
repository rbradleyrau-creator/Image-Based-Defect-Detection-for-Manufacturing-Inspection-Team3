# Automated Visual Inspection System for Industry Defect Detection

This project implements an automated visual inspection pipeline in MATLAB to detect manufacturing defects in industrial components using classical computer vision techniques. The system identifies both color and shape anomalies in metal tubes.

The inspection pipeline was developed using images from the MPDD (Magnetic Particle Defect Detection) dataset and uses image preprocessing, segmentation, morphological operations, and geometric feature extraction to classify normal and defective parts.

## Setup

To begin, download the following files into the same directory:
- data folder
- The Tube classifier model (tubeClassifierNet.mat)
- testImages folder (located inside the model folder)
- Main program (tubeClassifierTrainAndTest.mlx)
- ALL Matlab scripts inside the functions folder (located inside the programFiles folder)

Also, Download and install the following toolboxes:
- [Computer Vision Toolbox](url)
- [Deep Learning Toolbox](https://www.mathworks.com/products/deep-learning/overview.html?adobe_mc_sdid=SDID%3D5D456B546B5AE5CB-09E2BBF1C9033B6F%7CMCORGID%3DB1441C8B533095C00A490D4D%40AdobeOrg%7CTS%3D1785963895&adobe_mc_ref=https%3A%2F%2Fwww.bing.com%2F)
- [Deep Learning Toolbox Model for Resnet18 Network](https://www.mathworks.com/matlabcentral/fileexchange/68261-deep-learning-toolbox-model-for-resnet-18-network)
- [Image Processing Toolbox](https://www.mathworks.com/products/image-processing/overview.html?adobe_mc_sdid=SDID%3D0D575A0B887F2903-31B3D4BAD3A66A88%7CMCORGID%3DB1441C8B533095C00A490D4D%40AdobeOrg%7CTS%3D1785964501&adobe_mc_ref=https%3A%2F%2Fwww.bing.com%2F)
- [Statistics and Machine Learning Toolbox](https://www.mathworks.com/products/statistics.html)

Then open up the main program and follow the instructions (or refer to the instructions below):

## How to run

The main files provides access to 3 features; training new models, performing batch testing, and performing tests on single images. If you downloaded the files in the models folder, there is no need to perform the testing function. To run a feature, press 'run' in its corresponding section. In addition, inputs to each feature can be adjusted in the section just below the run section. Image variations can be tested in the section located at the bottom of the live script.

To test that your setup is functioning correctly, scroll to the 'Single Image Inspection' section. Select 'Metal Defects', select image '1', turn off compareMasks, and click run. The output should match the following:

<div align="center">
  <div style="overflow-x: auto; gap: 10px; padding-bottom: 10px; white-space: nowrap; display: inline-block; margin-right: 10px;">
    <img src="https://github.com/rbradleyrau-creator/Image-Based-Defect-Detection-for-Manufacturing-Inspection-Team7/blob/main/images/InspectionResultsMetalDefect1.png" width="800" height="450" />
  </div>
</div>

Note: By pressing the arrow in the top right of output figure, the data can be expanded into its own pop-out window, allowing easier readability of the data. If the text does not appear, try changing your MATLAB instance to dark mode.

<div align="center">
  <div style="overflow-x: auto; gap: 10px; padding-bottom: 10px; white-space: nowrap; display: inline-block; margin-right: 10px;">
    <img src="https://github.com/rbradleyrau-creator/Image-Based-Defect-Detection-for-Manufacturing-Inspection-Team7/blob/main/images/tooltip1.png" width="500" height="250" />
  </div>
</div>

## Results

The below shows Batch Testing output for each of the four recommended settings:

- Normal | Actual Yield: 68.9% | Predicted Yield 68.9% | Defect Rate: 31.1% | Escaped Defect Rate 0.0% <br>
<div align="center">
  <div style="overflow-x: auto; gap: 10px; padding-bottom: 10px; white-space: nowrap; display: inline-block; margin-right: 10px;">
    <img src="https://github.com/rbradleyrau-creator/Image-Based-Defect-Detection-for-Manufacturing-Inspection-Team7/blob/main/images/NormalBatchTestFull.png" width="400" height="320" />
    <img src="https://github.com/rbradleyrau-creator/Image-Based-Defect-Detection-for-Manufacturing-Inspection-Team7/blob/main/images/NormalBatchTestPF.png" width="385" height="400" />
  </div>
</div>

- Bright | Actual Yield: 68.9% | Predicted Yield 66.7% | Defect Rate: 31.1% | Escaped Defect Rate 0.0% <br>
<div align="center">
  <div style="overflow-x: auto; gap: 10px; padding-bottom: 10px; white-space: nowrap; display: inline-block; margin-right: 10px;">
    <img src="https://github.com/rbradleyrau-creator/Image-Based-Defect-Detection-for-Manufacturing-Inspection-Team7/blob/main/images/BrightBatchTestFull.png" width="400" height="320" />
    <img src="https://github.com/rbradleyrau-creator/Image-Based-Defect-Detection-for-Manufacturing-Inspection-Team7/blob/main/images/BrightBatchTestPF.png" width="385" height="400" />
  </div>
</div>

- Blurry | Actual Yield: 68.9% | Predicted Yield 84.4% | Defect Rate: 31.1% | Escaped Defect Rate 7.0% <br>
<div align="center">
  <div style="overflow-x: auto; gap: 10px; padding-bottom: 10px; white-space: nowrap; display: inline-block; margin-right: 10px;">
    <img src="https://github.com/rbradleyrau-creator/Image-Based-Defect-Detection-for-Manufacturing-Inspection-Team7/blob/main/images/BlurryBatchTestFull.png" width="400" height="320" />
    <img src="https://github.com/rbradleyrau-creator/Image-Based-Defect-Detection-for-Manufacturing-Inspection-Team7/blob/main/images/BlurryBatchTestPF.png" width="385" height="400" />
  </div>
</div>

- Noisy | Actual Yield: 68.9% | Predicted Yield 75.6% | Defect Rate: 31.1% | Escaped Defect Rate 3.0% <br>
<div align="center">
  <div style="overflow-x: auto; gap: 10px; padding-bottom: 10px; white-space: nowrap; display: inline-block; margin-right: 10px;">
    <img src="https://github.com/rbradleyrau-creator/Image-Based-Defect-Detection-for-Manufacturing-Inspection-Team7/blob/main/images/NoisyBatchTestFull.png" width="400" height="320" />
    <img src="https://github.com/rbradleyrau-creator/Image-Based-Defect-Detection-for-Manufacturing-Inspection-Team7/blob/main/images/NoisyBatchTestPF.png" width="385" height="400" />
  </div>
</div>

## References

[Resnet 18 documentation](https://www.mathworks.com/help/deeplearning/ref/resnet18.html)
