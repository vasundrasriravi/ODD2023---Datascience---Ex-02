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

212222230168

VASUNDRA SRI R

# Code:
# bhp.csv:
import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
from google.colab import files
uploaded=files.upload()

df=pd.read_csv('bhp.csv')

df.info()
print(df.describe())

df.head()

## BEFORE REMOVING OUTLIER

sns.boxplot(y='price_per_sqft',data=df)

q1=df['price_per_sqft'].quantile(0.25)

q3=df['price_per_sqft'].quantile(0.75)

IQR=q3-q1

low=q1-1.5*IQR

high=q3+1.5*IQR

new=df[((df['price_per_sqft']>=low)&(df['price_per_sqft']<=high))]

## AFTER REMOVING OUTLIER using IQR method

sns.boxplot(y='price_per_sqft',data=new)

z=np.abs(stats.zscore(df['price_per_sqft']))

new2=df[(z<3)]

new2.head()

## AFTER REMOVING OUTLIER using Zscore method

sns.boxplot(y="price_per_sqft",data=new2)

# height_weight.csv:
import pandas as pd
import seaborn as sns
from google.colab import files
uploaded=files.upload()

df=pd.read_csv('height_weight.csv')

df.info()
print(df.describe())

df.head()

## BEFORE REMOVING OUTLIER in HEIGHT

sns.boxplot(y='height',data=df)

height_q1 = df['height'].quantile(0.25)

height_q3 = df['height'].quantile(0.75)

height_IQR = height_q3 - height_q1

height_low = height_q1 - 1.5 * height_IQR

height_high = height_q3 + 1.5 * height_IQR

height_new=df[((df['height']>=height_low)&(df['height']<=height_high))]

## AFTER REMOVING OUTLIER in HEIGHT

sns.boxplot(y='height',data=height_new)

## BEFORE REMOVING OUTLIER in WEIGHT

sns.boxplot(y='weight',data=df)

weight_q1 = df['weight'].quantile(0.25)

weight_q3 = df['weight'].quantile(0.75)

weight_IQR = weight_q3 - weight_q1

weight_low = weight_q1 - 1.5 * weight_IQR

weight_high = weight_q3 + 1.5 * weight_IQR

weight_new=df[((df['weight']>=weight_low)&(df['weight']<=weight_high))]

## AFTER REMOVING OUTLIER in WEIGHT

sns.boxplot(y='weight',data=weight_new)

# OUTPUT:
# bhp.csv
![Screenshot 2023-09-04 122735](https://github.com/vasundrasriravi/ODD2023---Datascience---Ex-02/assets/119393983/ca9c7412-62db-4c71-ac8c-d03ce50d0c8a)

![Screenshot 2023-09-04 122759](https://github.com/vasundrasriravi/ODD2023---Datascience---Ex-02/assets/119393983/02a9f5b6-b547-4d1c-9095-e1eafe3999cb)

![Screenshot 2023-09-04 122822](https://github.com/vasundrasriravi/ODD2023---Datascience---Ex-02/assets/119393983/662eb6ca-3246-40b0-ae0f-9ac19c5f7d15)

![Screenshot 2023-09-04 122859](https://github.com/vasundrasriravi/ODD2023---Datascience---Ex-02/assets/119393983/ef8618dc-b186-4438-a5a1-86be1054c8ec)

![Screenshot 2023-09-04 122951](https://github.com/vasundrasriravi/ODD2023---Datascience---Ex-02/assets/119393983/5531056e-2899-4e63-8781-3af8f4e8ab1a)

![Screenshot 2023-09-04 123015](https://github.com/vasundrasriravi/ODD2023---Datascience---Ex-02/assets/119393983/dcc38701-67e9-4db9-abef-8949926409d7)

# height_weight.csv
![Screenshot 2023-09-04 123418](https://github.com/vasundrasriravi/ODD2023---Datascience---Ex-02/assets/119393983/18f06a4a-d814-4005-ad8b-057c1cf60233)

![Screenshot 2023-09-04 123511](https://github.com/vasundrasriravi/ODD2023---Datascience---Ex-02/assets/119393983/eb0ef83a-871e-4a39-96ff-cd00502ea2a1)

![Screenshot 2023-09-04 123559](https://github.com/vasundrasriravi/ODD2023---Datascience---Ex-02/assets/119393983/6ad55b2d-3682-4ebd-9d11-16f8ca30b363)

![Screenshot 2023-09-04 123651](https://github.com/vasundrasriravi/ODD2023---Datascience---Ex-02/assets/119393983/ed4f43d3-4a8a-4365-a5bc-eaa28ed36de2)

![Screenshot 2023-09-04 123737](https://github.com/vasundrasriravi/ODD2023---Datascience---Ex-02/assets/119393983/6c1c0521-db54-4c98-9095-4aabbbed856e)

![Screenshot 2023-09-04 123828](https://github.com/vasundrasriravi/ODD2023---Datascience---Ex-02/assets/119393983/b2cf1cee-c6d7-4be7-9d54-694e58c19a5f)

