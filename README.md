# Tensor Titans - Amazon ML [Challenge '24](https://unstop.com/hackathons/amazon-ml-challenge-amazon-1100713/coding-challenge/200089) | [Standings](https://unstop.com/hackathons/amazon-ml-challenge-amazon-1100713/coding-challenge/200089)
> ### BITS Pilani K K Birla Goa Campus <br>
> Nirvan Patil  <br>
> Priyansh <br>
> Pranjay

## Problem Statement & Approach
![image](https://github.com/user-attachments/assets/1e8d218e-6669-4cef-b6a0-992168af053c)


## Directory Information

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
* `combine_priyansh.ipynb`: Code for for preparing .csv in the required output format given given multiple <br>
`.csv` files each containing a part of the answer.
