# Ex02-Outlier
You are given bhp.csv which contains property prices in the city of banglore, India. You need to examine price_per_sqft column and do following,

- (1) Remove outliers using IQR

- (2) After removing outliers in step 1, you get a new dataframe.

- (3) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result

- (4) for the data set height_weight.csv find the following

  - (i) Using IQR detect weight outliers and print them
   
  - (ii) Using IQR, detect height outliers and print them

# Explanation:
An Outlier is an observation in a given dataset that lies far from the rest of the observations. That means an outlier is vastly larger or smaller than the remaining values in the set. An outlier is an observation of a data point that lies an abnormal distance from other values in a given population. (odd man out). Outliers badly affect mean and standard deviation of the dataset. These may statistically give erroneous results.

# Algorithm:
- Step1: Read the given Data.
- Step2: Get the information about the data.
- Step3: Detect the Outliers using IQR method and Z score.
- Step4: Remove the outliers.
- Step5: Plot the datas using Box Plot.
