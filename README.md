# predictions

---

## Weight Lifting Exercise Prediction

### Project Overview
This project uses data from accelerometers placed on the belt, forearm, arm, and dumbbell of participants performing barbell lifts. The aim is to predict the manner (or "classe") in which the exercises were performed, using a dataset of recorded movements.

The dataset is part of the [Quantified Self movement](http://groupware.les.inf.puc-rio.br/har), which collects personal activity data to find patterns and improve health. Our primary objective is to build a machine learning model that can classify the exercise movements.

### Dataset Information
- **Training data**: [pml-training.csv](https://d396qusza40orc.cloudfront.net/predmachlearn/pml-training.csv)
- **Testing data**: [pml-testing.csv](https://d396qusza40orc.cloudfront.net/predmachlearn/pml-testing.csv)
  
The data come from accelerometers on different parts of the body during weightlifting exercises.

### Project Files
- `analysis_summary.pdf`: Summary of the analysis steps and methods.
- `analysis.Rmd`: R Markdown file detailing data preparation, model building, and evaluation.
- `predictions.csv`: The predicted "classe" values for the test dataset.
- `final_report.html`: Compiled HTML document of the analysis, including code and explanations.

### Getting Started

#### Requirements
- **R** (version >= 3.6)
- **R Libraries**:
  - `caret`: For data splitting, model training, and evaluation
  - `dplyr`: For data manipulation
  - `ggplot2`: For visualization
  - `randomForest`: For random forest model
  - `rpart` and `rpart.plot`: For decision tree visualization

#### Setup
1. Clone this repository to your local machine.
2. Install the necessary R packages:

   ```r
   install.packages(c("caret", "dplyr", "ggplot2", "randomForest", "rpart", "rpart.plot"))
   ```

3. Open the `analysis.Rmd` file in RStudio.
4. Click `Knit` to generate the HTML report or run the chunks sequentially for interactive analysis.

### Analysis Summary
1. **Data Preprocessing**:
   - Removed columns with excessive missing values.
   - Converted non-numeric columns to numeric where necessary.
   - Partitioned the data into training and validation sets.

2. **Exploratory Data Analysis (EDA)**:
   - Visualized class distribution.
   - Computed correlations among variables to understand feature relationships.

3. **Model Training**:
   - Trained a `randomForest` model on the training data, tuning parameters with cross-validation.
   - Evaluated model accuracy on the validation set.

4. **Model Evaluation**:
   - Calculated confusion matrix and out-of-sample error.
   - Fine-tuned the model with 5-fold cross-validation.

5. **Prediction**:
   - Generated predictions for the test dataset and saved the results in `predictions.csv`.

### Decision Tree Visualization
To interpret the model’s decisions, a single decision tree was visualized using the `rpart` package. This visualization helps in understanding feature splits for predicting "classe".

### Reproducibility
All code and results are provided in the R Markdown file (`predictions.Rmd`). Compiled results are available in the `analysis_summary.html` file.

### References
If you use this analysis, please cite the original dataset from the [Human Activity Recognition](http://groupware.les.inf.puc-rio.br/har) project.

---

This README template should cover all necessary aspects of your project. Let me know if you need further customization!
