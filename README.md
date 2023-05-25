# <h1 align="center">**Mildew Detection in Cherry Leaves**</h1>

## Introduction

Mildew detection in cherry leaves is a dashboard app that uses Machine Learning to enable the user to upload images of cherry leaves to determine if the tree is healthy or infected with powedery mildew, and download a report of the findings.

[View the live project here](https://cherry-leaf-mildew-detection.herokuapp.com/)

## Table of Contents

- [Business Requirements](#business-requirements)
- [Hypothesis and how to Validate](#hypothesis-and-how-to-validate)
- [Rationale to map business requirements](#the-rationale-to-map-the-business-requirements-to-the-data-visualisations-and-ml-tasks)
- [ML Business Case](#ml-business-case)
- [Dashboard Design](#dashboard-design---streamlit-app-user-interface)
- [Methodology](#methodology)
- [Project Features](#project-features)
- [Project Outcomes](#project-outcomes)

.....

- [Hypothesis Outcomes](#hypothesis-outcomes)
- [Testing](#testing)
- [Bugs](#bugs)
- [Deployment](#deployment)
 

## Business Requirements

The cherry plantation crop from Farmy & Foods is facing a challenge where their cherry plantations have been presenting powdery mildew, a fungal disease that affects many plant species. The cherry plantation crop is one of the finest products in their portfolio, and the company is concerned about supplying the market with a compromised quality product.

Currently, the process is manual verification to determine if a given cherry tree is infected with powdery mildew. An employee spends around 30 minutes in each tree, taking a few samples of tree leaves and verifying visually if the tree is healthy or has powdery mildew. If there is powdery mildew, the employee applies a specific compound to kill the fungus. The time spent applying this compound is 1 minute. The company has thousands of cherry trees, located on multiple farms across the country. As a result, this manual process is not scalable due to the time spent in the manual inspection process.

To save time in this process, the IT team suggested an ML system that detects instantly, using a leaf tree image, if it is healthy or has powdery mildew. A similar manual process is in place for other crops for detecting pests, and if this initiative is successful, there is a realistic chance to replicate this project for all other crops.

The business case assessment interview can be found [here](readme_files/business_interview.md).

Summary:

- The client is interested in conducting a study to visually differentiate a healthy cherry leaf from one with powdery mildew.
- The client is interested in a dashboard that predicts if a cherry leaf is healthy or contains powdery mildew.
- The client would like the dashboard to predict if a cherry leaf is healthy or contains powdery mildew with a 97% accuracy.

[Table Of Contents](#table-of-contents)

## Hypothesis and how to Validate

1. Cherry leaves with powdery mildew can de differentiated from healthy leaves by their appearance.
   - An average image study will help to determine differences in the appearance of healthy leaves and leaves affected with powdery mildew.
2. Cherry leaves can be determined to be healthy or contain powdery mildew with a degree of 97% accuracy.
   - A model can be trained and validated to achieve a degree of 97% accuracy. The accuracy will be tested using the test set which should also achieve 97% accuracy.

[Table Of Contents](#table-of-contents)

## The rationale to map the business requirements to the Data Visualisations and ML tasks

- Business Requirement 1: Data Visualization

  - The 'mean' and 'standard deviation' images for healthy and powdery mildew infected leaves will be displayed.
  - The difference between an average healthy leaf and an average powdery mildew infected leaf will be displayed.
  - An image montage for both healthy leaves and powdery mildew infected leaves will be displayed.

- Business Requirement 2: Classification

  - To predict if a given leaf is healthy or infected with powdery mildew.
  - The predictions should have a 97% accuracy level.

- Business Requirement 3: Report
  - A report is available and downloadable with the predicted status of all uploaded images.

[Table Of Contents](#table-of-contents)

## ML Business Case

- Create a machine Learning model to predict if a leaf is healthy or infected with powdery mildew, based on an image dataset of historical data containing both healthy and powdery mildew infected leaves. It is a supervised, 2-class, single-label, classification model.
- The model outcome will ideally provide the client with a reliable and faster way to diagnose if a tree is infected with powdery mildew or not.
- The model will be succesfull if an accuracy of at least 97% is obtained on the test set.
- The model output is defined as a flag, indicating if the leaf is infected with powdery mildew or not and the associated probability of being infected or not. The farmers will take a picture of a leaves and upload them to the App.
- Heuristics: The current detection process is manual verification, where an employee spends around 30 minutes in each tree, taking a few samples of tree leaves and verifying visually if the leaf tree is healthy or has powdery mildew. With thousands of trees there is the possibility to produce inaccurate diagnostics due to human errors.
- The dataset contains 4208 images taken from the client's crop fields. The images show healthy cherry leaves and cherry leaves that have powdery mildew.
- The dataset is located on [Kaggle](https://www.kaggle.com/codeinstitute/cherry-leaves).

[Table Of Contents](#table-of-contents)

## Dashboard Design - Streamlit App User Interface

### Page 1: Introduction

- General Information about powdery mildew.
- Details of the project dataset.
- Business requirements.
- Link to this Readme file

### Page 2: Leaf Visualizer

- This page will fulfil business requirement 1.
- Show the difference between the average and variability image.
- Show the difference between average healthy leaves and leaves infected with powdery mildew.
- Show an image montage of healthy leaves and leaves infected with powdery mildew.

### Page 3: Powdery Mildew Detector

- This page will fulfill business requirements 2 and 3 by predicting if a leaf is infected with powdery mildew or not.
- Link to download a set of images showing healthy leaves and leaves infected with powdery mildew for live prediction.
- User Interface with a file uploader widget to allow the user to upload multiple leaf images. It will display the image and a prediction statement, indicating if the leaf is infected with powdery mildew or not and the probability associated with this prediction.
- Report with image name and prediction result.
- Download button to download the report.

### Page 4: Project Hypothesis and Validation

- Detail each [hypothesis](#hypothesis-and-how-to-validate), how it was validated and the conclusion.

### Page 5: ML Performance Metrics

- Details of the model performance including:
  - Label frequencies for train, validation and test sets
  - Model history - accuracy and losses
  - Model evaluation result

[Table Of Contents](#table-of-contents)

## Methodology

### CRISP-DM

CRISP-DM (Cross Industry Standard Process for Data Mining) methodology was used for the data mining project. There are six stages to the process and have the following relationship:

![CRISP_DM](readme_files/crisp-dm.png)

### Agile

An agile approach was implemented for the project using GitHub projects with the aid of Milestones and Issues. Each Issue detailed the relevant tasks to be completed.

The project board can be viewed [here](https://github.com/users/Porsil/projects/7)

[Table Of Contents](#table-of-contents)

## Project Features

<details>

<summary>Navigation</summary>

The navigation bar is visible on all dashboard pages and provides easy links to other pages.

![Menu](readme_files/menu.png)

</details>

<details>

<summary>Page 1: Introduction</summary>

The introducion page provides the user with information about powdery mildew, the project summary, the dataset and the business requirements. There is also a link to this ReadMe file.

![Introduction](readme_files/introduction.png)

</details>

<details>

<summary>Page 2: Leaf Visualizer</summary>

The leaf visualizer page provides the user with the results of the study to visually differentiate a healthy cherry leaf from one with powdery mildew. It was determined that healthy leaves and infected leaves could be distinguished by their appearance.

The page gives the user the options to view the difference between average and variability images, the differences between average infected and average uninfected leaves and an image montage of healthy or infected leaves.

![Visualizer](readme_files/visualizer.png)

</details>

<details>

<summary>Page 3: Powdery Mildew Detector</summary>

The detector page allows the user to upload images of cherry leaves to determine if the leaf is healthy or infected with powdery mildew. Each image is presented with a prediction and a graph depicting the probability of the predictions accuracy. There is then a report detailing the image name, proability accuracy and result. This report is available to download into an Excel file.

![Detector](readme_files/detector.png)

</details>

<details>

<summary>Page 4: Project Hypothesis</summary>

The hypothesis page provides the user with details of the project hypotheses and their outcomes.

![Hypothesis](readme_files/hypothesis.png)

</details>

<details>

<summary>Page 5: Performance Metrics</summary>

The performance metrics page provides the user with the Machine Learning model dataset distribution, performance plots and performance on the test dataset.

![Performance](readme_files/performance.png)

</details>

[Table Of Contents](#table-of-contents)

## Project Outcomes

## Hypothesis Outcomes

### Hypothesis 1

-	Cherry leaves with powdery mildew can de differentiated from healthy leaves by their appearance.

An image montage shows that leaves infected with powdery mildew are easily identified due to the present of white deposits on the leaves.
The average and variability images showed a pattern within the center of the leaf related to colour pigmentation. This is most notable in the variability images where the center of the healthy leaves looks black and the center for the infected leaves is not.
The difference between averages study did not show patterns where we could intuitively differentiate one from another.
The image montage, average and variability images and the difference between averages study can be viewed by selecting the 'Leaf Visualiser' option on the sidebar menu.

### Hypothesis 2

-	Cherry leaves can be determined to be healthy or contain powdery mildew with a degree of 97% accuracy.

The model was successfully trained using a Convolutional Neural Network to classify if an image of a cherry leaf is healthy or infected with powdery mildew with a degree of accuracy of above 99%.

[Table Of Contents](#table-of-contents)

## Testing

<details>

<summary>ML Model Testing</summary>

The model testing can be viewed [here](readme_files/model_testing.pdf).

</details>

<details>

<summary>Dashboard Testing</summary>

| Page         | Feature                   | Pass / Fail |
|--------------|:-------------------------:|:-----------:|
| Introduction | Content                   | Pass        |
| Introduction | Nav link                  | Pass        |
| Introduction | ReadMe link               | Pass        |
| Visualizer   | Content                   | Pass        |
| Visualizer   | 1st checkbox ticked       | Pass        |
| Visualizer   | 1st checkbox unticked     | Pass        |
| Visualizer   | 2nd checkboz ticked       | Pass        |
| Visualizer   | 2nd checkbox unticked     | Pass        |
| Visualizer   | 3rd checkbox ticked       | Pass        |
| Visualizer   | 3rd checkbox unticked     | Pass        |
| Visualizer   | Healthy montage           | Pass        |
| Visualiser   | Infected montage          | Pass        |
| Detector     | Content                   | Pass        |
| Detector     | Kaggle link               | Pass        |
| Detector     | Drag add drop file upload | Pass        |
| Detector     | Browse file upload        | Pass        |
| Detector     | Show uploaded images      | Pass        |
| Detector     | Show predictions          | Pass        |
| Detector     | Show probability graph    | Pass        |
| Detector     | Analysis report           | Pass        |
| Detector     | Downloadable report       | Pass        |
| Hypothesis   | Content                   | Pass        |
| Performance  | Content                   | Pass        |

</details>

[Table Of Contents](#table-of-contents)

## Bugs

### Fixed Bugs

<details>

<summary>CodeAnywhere</summary>

Several issues were encountered with the CodeAnywhere IDE.

Firstly, the IDE would often go offline for 2 to 3 seconds. For the most part this was not an issue but if this occurred whilst executing a cell in a Jupyter notebook the IDE would crash and require restarting. This meant it was particularly difficult to fit the model as successfully executing this process often took up to an hour. As such not as many models were trained as I would have hoped. I decided to stop after v5 and ensure my dashboard and ReadMe report were complete to ensure my project was submitted on time. 

Secondly, during the model training impacted by the first issue, often the code that was saved and committed did not match the code what was in the workspace. Autosave was enabled and all code double checked to be saved by selecting File>Save All before the ‘git add’ and ‘git commit’ commands. This is shown in the commit for v4 where the code in Jupyter notebook 03_modelling_and_evaluation shows an error message for fitting the model, if this was true the outputs for the model would not have been generated.

Thirdly, when trying to commit the code for v3, the workspace would crash. Once re-opened the ‘git add’ command would produce the following error:

![IDE_error](readme_files/ide_error.png)

This was fixed by running the command ‘rm -f .git/index.lock’ as per this [Stack Overflow post](https://stackoverflow.com/questions/38004148/another-git-process-seems-to-be-running-in-this-repository). The issue kept occurring so instead of using ‘git add .’ each file was added individually. This determined that the source of the error was the ‘mildew_detector_model.h5’. To fix the error this file was added to the .gitignore file. The same was done for v2-5, and only v5 was removed to complete the dashboard.

</details>

### Unfixed Bugs

There are no known unfixed bugs.

[Table Of Contents](#table-of-contents)

## Deployment

### Heroku

- The App live link is: https://YOUR_APP_NAME.herokuapp.com/
- Set the runtime.txt Python version to a [Heroku-20](https://devcenter.heroku.com/articles/python-support#supported-runtimes) stack currently supported version.
- The project was deployed to Heroku using the following steps.

1. Log in to Heroku and create an App
2. At the Deploy tab, select GitHub as the deployment method.
3. Select your repository name and click Search. Once it is found, click Connect.
4. Select the branch you want to deploy, then click Deploy Branch.
5. The deployment process should happen smoothly if all deployment files are fully functional. Click now the button Open App on the top of the page to access your App.
6. If the slug size is too large then add large files not required for the app to the .slugignore file.

## Main Data Analysis and Machine Learning Libraries

- Here you should list the libraries used in the project and provide an example(s) of how you used these libraries.

## Credits

- In this section, you need to reference where you got your content, media and from where you got extra help. It is common practice to use code from other repositories and tutorials. However, it is necessary to be very specific about these sources to avoid plagiarism.
- You can break the credits section up into Content and Media, depending on what you have included in your project.

### Content

- The text for the Home page was taken from Wikipedia Article A.
- Instructions on how to implement form validation on the Sign-Up page were taken from [Specific YouTube Tutorial](https://www.youtube.com/).
- The icons in the footer were taken from [Font Awesome](https://fontawesome.com/).

### Media

- The photos used on the home and sign-up page are from This Open-Source site.
- The images used for the gallery page were taken from this other open-source site.

## Acknowledgements (optional)

- Thank the people that provided support throughout this project.
