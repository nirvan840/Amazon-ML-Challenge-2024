# ML Challenge Problem Statement

## Feature Extraction from Images
> In this hackathon, the goal is to create a machine-learning model that extracts entity values from images. This capability is crucial in healthcare, e-commerce, and content moderation, where precise product information is vital. As digital marketplaces expand, many products lack detailed textual descriptions, making it essential to obtain key details directly from images. These images provide important information such as weight, volume, voltage, wattage, dimensions, and many more, which are critical for digital stores.

## Note
The original files are present in `Tensor Titans - Amazon ML - Submission/Original Data.zip`.

## Data Description:
The dataset consists of the following columns:

**index**: An unique identifier (ID) for the data sample
**image_link**: Public URL where the product image is available for download. Example link - [https://m.media-amazon.com/images/I/71XfHPR36-L.jpg](https://m.media-amazon.com/images/I/71XfHPR36-L.jpg)
To download images, use the `download_images` function from `src/utils.py`. See sample code in `src/test.ipynb`.
**group_id**: Category code of the product
**entity_name**: Product entity name. For eg, “item_weight”
**entity_value**: Product entity value. For eg, “34 gram”
Note: For test.csv, you will not see the column entity_value as it is the target variable.
Output Format: The output file should be a CSV with 2 columns:

**index**: The unique identifier (ID) of the data sample. Note the index should match the test record index.
prediction: A string should have the following format: “x unit”, where x is a float number in standard formatting and the unit is one of the allowed units (allowed units are mentioned in the Appendix). The two values should be concatenated and have a space between them. For eg: “2 gram”, “12.5 centimetre”, “2.56 ounce” are valid. Few invalid cases: “2 gms”, “60 ounce/1.7 kilogram”, “2.2e2 kilogram” etc.
Note: Make sure to output a prediction for all indices. If no value is found in the image for any test sample, return an empty string, i.e., “”. If you have less/more number of output samples in the output file as compared to test.csv, your output won’t be evaluated.
File Descriptions:
source files

`src/sanity.py`: Sanity checker to ensure that the final output file passes all formatting checks. Note: the script will not check if fewer/more number predictions are present compared to the test file. Please take a look at sample code in src/test.ipynb
`src/utils.py`: Contains helper functions for downloading images from the image_link.
`src/constants.py`: Contains the allowed units for each entity type.
`sample_code.py`: We also provided a sample dummy code to generate an output file in the given format. Usage of this file is optional.

## Dataset files

`dataset/train.csv`: Training file with labels (entity_value).
`dataset/test.csv`: Test file without output labels (entity_value). Generate predictions using your model/solution on this file's data and format the output file to match sample_test_out.csv (Refer the above section "Output Format")
`dataset/sample_test.csv`: Sample test input file.
`dataset/sample_test_out.csv`: Sample outputs for sample_test.csv. The output for test.csv must be formatted in the same way. Note: The predictions in the file might not be correct

## Constraints
You will receive a sample output file and a sanity checker file. Format your output to match the sample output file exactly and pass it through the sanity checker to ensure its validity. Note: If the file does not pass through the sanity checker, it will not be evaluated. You should recieve a message like Parsing successfull for file: ...csv if the output file is correctly formatted.
You are given the list of allowed units in constants.py and the Appendix. Your outputs must be in these units. Predictions using any other units will be considered invalid during validation.

## Evaluation Criteria
Submissions will be evaluated based on the F1 score and standard measures of prediction accuracy for classification and extraction problems.

Let GT = Ground truth value for a sample and OUT be the output prediction from the model for a sample. Then, we classify the predictions into one of the 4 classes with the following logic:
True Positives - If OUT != "" and GT != "" and OUT == GT
False Positives - If OUT != "" and GT != "" and OUT != GT
False Positives - If OUT != "" and GT == ""
False Negatives - If OUT == "" and GT != ""
True Negatives - If OUT == "" and GT == ""
Then, F1 score = 2*PrecisionRecall/(Precision + Recall) where:

Precision = True Positives/(True Positives + False Positives)
Recall = True Positives/(True Positives + False Negatives)
Submission File
Upload a test_out.csv file in the Portal with the same formatting as sample_test_out.csv

## Appendix

```
entity_unit_map = {
  "width": {
    "centimetre",
    "foot",
    "millimetre",
    "metre",
    "inch",
    "yard"
  },
  "depth": {
    "centimetre",
    "foot",
    "millimetre",
    "metre",
    "inch",
    "yard"
  },
  "height": {
    "centimetre",
    "foot",
    "millimetre",
    "metre",
    "inch",
    "yard"
  },
  "item_weight": {
    "milligram",
    "kilogram",
    "microgram",
    "gram",
    "ounce",
    "ton",
    "pound"
  },
  "maximum_weight_recommendation": {
    "milligram",
    "kilogram",
    "microgram",
    "gram",
    "ounce",
    "ton",
    "pound"
  },
  "voltage": {
    "millivolt",
    "kilovolt",
    "volt"
  },
  "wattage": {
    "kilowatt",
    "watt"
  },
  "item_volume": {
    "cubic foot",
    "microlitre",
    "cup",
    "fluid ounce",
    "centilitre",
    "imperial gallon",
    "pint",
    "decilitre",
    "litre",
    "millilitre",
    "quart",
    "cubic inch",
    "gallon"
  }
}
```
