# Automated determination of transport and depositional environments in sand and sandstones

## Description
This repository includes all code related to the manuscript "Automated determination of transport and depositional environments in sand and sandstones" by Michael Hasson, M. Colin Marvin, and Mathieu Lapôtre (PNAS, 2024). Using the files in this repository, anyone can use the model documented in our manuscript to identify the transport or depositional environment of scanning electron microscope (SEM) images of individual grains of quartz sand (as long as the meet the requirements for model input). The only configuration required is for a user to set the path to their folder of images and path where they would like the results to be saved.

The model has been validated on modern and ancient quartz grains, so it can be used on modern sediment and lithified rocks. 

Included are: 
- Tutorials for use with example outputs
- All code related to training and evaluating the model used in this study

If you use this for research, please cite our publication: Hasson, M., Marvin, M.C., and Lapôtre, M.G.A., 2024, Automated determination of transport and depositional environments in sand and sandstones: Proceedings of the National Academy of Sciences, v. 121, p. e2407655121, doi:10.1073/pnas.2407655121.

## Using the tool:

Using the tool is very simple. Click this button to open the inference software in Google Colab: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/michaelhasson/SandAI/blob/main/Inference_notebook_Colab.ipynb) 

Google Colab is a free service that will let you quickly infer the classes of your images. No coding, downloading, or configuration is required. Simply click the button and follow the instructions inside.

From the Colab notebook, simply hit shift-enter or click the play buttons on each cell. This will run a demonstration of the expected outputs. 

To classify your own images, upload them to Google Colab and change the path and name of the sample. A new CSV file of model predictions will be saved in the "Predictions" folder that you can then download to your local computer. 

Be sure to look through the checklist (below and in the inference notebook) to make sure that your images meet the requirements for classification!

## Submitting images:

If you are willing to share your images (for future model improvements), please do so at [this link](https://docs.google.com/forms/d/e/1FAIpQLSfds06XC0Tg1Km7ei_WAqNm0a-K0pYoxayOnjfhQJgqOlD5rA/viewform). If you provide your name, we will acknowledge you in any future work! 

## Checklist

Before using the model, it is critical to make that images are suitable for model inference. Failure to do so will lead to inaccurate results. The requirements are:
1. Sand must be from terrestrial environments (eolian, glacial, beach, or fluvial).
2. No scale bars.
3. Individual grains only -- there can only be one sand grain per image.
4. The original grain shapes and textures must be present. If they have been obscured by diagenesis (e.g., silica cementation) or the sample preparation procedure, they will not produce valid results.

### Visual checklist examples:
Make sure that your images *do not* look like these before using the classifier!

1. Do your images contain scale bars?

<table>
  <tr>
    <td><img src="./Checklist_images/Scale_bars/scale_bar.png" width="375" height="300"></td>
  </tr>
</table>

2. Is there only one grain per image?

<table>
  <tr>
    <td><img src="./Checklist_images/Multiple_grains/FF01i_0074_annotated.png" width="375" height="300"></td>
    <td><img src="./Checklist_images/Multiple_grains/a16-64455-thin_0037_annotated.png" width="375" height="300"></td>
  </tr>
</table>

3. Are the grain surfaces obscured by diagenesis?

<table>
  <tr>
    <td><img src="./Checklist_images/Overgrowth/Dino_cyn_5_postHCl_10_13_23_0003_annotated.png" width="375" height="300"></td>
    <td><img src="./Checklist_images/Overgrowth/Dino_cyn_5_postHCl_10_13_23_0004_annotated.png" width="375" height="300"></td>
  </tr>
</table>

4. Are the grain surfaces obscured by the sample preparation procedure?

<table>
  <tr>
    <td><img src="./Checklist_images/Coatings/4_annotated.png" width="375" height="300"></td>
    <td><img src="./Checklist_images/Coatings/91_annotated.png" width="375" height="300"></td>
  </tr>
</table>

## Calibration and Precision-Recall Curves

One vs. rest calibration and precision-recall curves are shown here to gauge model performance on each class. We constructed calibration curves for each class using in-sample test predictions.

<table>
  <tr>
    <td><img src="./cal_pr_curves/Calibration_curves.png" width="375" height="300"></td>
  </tr>
</table>

Above: One-versus-rest calibration curves for SandAI classes.  Results demonstrate agreement between prediction scores and actual likelihood of correct prediction. Points represent centers of probability bins.

<table>
  <tr>
    <td><img src="./cal_pr_curves/PR_curves.png" width="562" height="450"></td>
  </tr>
</table>

Above: One-versus-rest precision-recall curves for SandAI classes.
    


