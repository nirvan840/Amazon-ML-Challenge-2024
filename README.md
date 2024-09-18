# Tensor Titans - Amazon ML [Challenge '24](https://unstop.com/hackathons/amazon-ml-challenge-amazon-1100713/coding-challenge/200089) | [Standings](https://unstop.com/hackathons/amazon-ml-challenge-amazon-1100713/coding-challenge/200089)
> ### BITS Pilani, K. K. Birla Goa Campus <br>
> #### Our Standings - [**22nd / 74,843 Teams**](https://unstop.com/hackathons/amazon-ml-challenge-amazon-1100713/coding-challenge/200089?d=eyJwYWdlIjo3LCJ0ZWFtSWQiOjIzMDU1Njc4LCJhc3NvY2lhdGlvbklkIjo4NDEzMzl9)
> Nirvan Patil  <br>
> Priyansh <br>
> Pranjay

.
## Problem Statement & Approach
<img src="https://github.com/user-attachments/assets/1e8d218e-6669-4cef-b6a0-992168af053c" alt="Description" width="750" height="400">

.
## Final Results 
> ### F1 Score - **0.6793** (on test_original.csv)
> **Predictions**: 83355/131187 | **Filled**: 38.852 %

<img src="https://github.com/user-attachments/assets/307af941-7d46-47c3-827e-1c07ea70e5b8" alt="Description" width="750" height="350">

* We achieved an F1 score of 0.679 despite having only 38.85% of entries filled. This indicates that most <br>
**most** of the **entires** filled **are True Positives**.

* Our algorithms and logic fill most rows for `entity_name`: `height`, `width`, demonstrating the strength of <br>
our Custom Line Detection Algorithm (_described in detail in the `Amazon ML - Review Document`_)

* Images with `entity_name` as `volume` show promising entries filled %. Owing to the strength of our optimized PaddleOCR.
  
* **Limitations** - Initial outputs for images with `entity_name` as `depth` were poor when checked manually. <br>
Keeping all predictions corresponding to `depth` as empty gave us the best result.


.
## GitHub Directory Details

### `Amazon ML - Review Document`
* PDF document providing an overview of our submission
* Problem Statement, Approach, Challenges Faced, Models Used, Code Explanation & Conclusion

### `Kaggle_Notebook 1_Amazon ML_Nirvan.ipynb`
* Jupyter notebook containing code for generating test.csv values on entity_name: height, width, depth
* OCR -> Custom Line Detection -> Basic Regex -> Write to `.csv` file

### `Kaggle_Notebook 2_Amazon ML_Priyansh.ipynb`
* Jupyter notebook containing code for generating test.csv values on entity_name: weight, wattage, voltage & volume
* OCR -> Custom Regex -> Write to `.csv` file

### `Tensor Titans - Amazon ML - Submission/Primary Code (ipynb)`
* Contains the same `Kaggle_Notebook 1_Amazon ML_Nirvan.ipynb` and `Kaggle_Notebook 2_Amazon ML_Priyansh.ipynb`. <br>
These contain the code for the primary logic (OCR + Regex + Line Detection).

### `Tensor Titans - Amazon ML - Submission/Primary Code (ipynb)`
* Contains `.csv` files representing different versions of our submission files on Unstop.
* `cleaned_test_FINAL.csv` is the file corresponding to our best F1 score.

### `Tensor Titans - Amazon ML - Submission/CSV Operations`
* Contains `.ipynb` files with code for different operations on .csv files using **pandas**.
* `combine.ipynb`: Code for preparing .csv in the required output format given .csv containing data <br>
for the first and second half.
* `combine_abscence.ipynb`: Code for **removing missing/incorrect units** from prepared .csv file.
* `combine_priyansh.ipynb`: Code for preparing .csv in the required output format given given multiple <br>
`.csv` files, each containing a part of the answer.

.
## Conclusion

To conclude, by utilizing PaddleOCR for text extraction and implementing **Custom Regex** and **Line Detection Algorithms**, we efficiently address resource limitations while extracting key dimensions and values. This streamlined approach, with minimal GPU dependency, reduced processing time to **~0.2 seconds per image**, enabling large-scale data generation in a practical and resource-efficient manner without relying on heavy vision models.
