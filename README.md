# Data_cleaning_cheatsheet
**Handling missing data: Missing data points can introduce bias and affect the accuracy of analyses. Various approaches can be used to handle missing data, such as imputation techniques where missing values are replaced with estimated values based on the available data, or removing rows or columns with excessive missing data if appropriate.

Removing duplicates: Duplicated entries in a dataset can distort analysis results. Identifying and removing duplicate rows or records helps ensure that each observation is unique. This can be done by comparing values across columns or using unique identifiers.

Correcting inconsistent data: Inconsistent data occurs when the same attribute is represented differently. For example, different spellings or abbreviations of the same category. Standardizing data formats, correcting spelling errors, and mapping variations to a common format can help ensure consistency.

Handling outliers: Outliers are extreme values that deviate significantly from the rest of the data. As discussed earlier, outliers can be treated by removing them, transforming them, or applying specific analysis techniques that are robust to their influence.

Handling formatting issues: Data cleaning also involves addressing formatting issues such as removing leading or trailing spaces, converting data types, ensuring consistent date formats, and addressing any other formatting inconsistencies.

Validating data integrity: Checking the integrity of the data involves verifying that the values fall within reasonable ranges and conform to specific constraints. For example, ensuring that numeric values are within a certain range, or verifying that categorical variables have expected values.

Dealing with inconsistent or erroneous entries: Data cleaning also involves identifying and addressing data entries that are clearly erroneous or contradict other information in the dataset. This may involve manual inspection or the use of automated algorithms to detect inconsistencies.
**
Documentation: Throughout the data cleaning process, it is essential to maintain clear documentation of the steps taken, the decisions made, and the changes applied. This documentation helps ensure transparency, reproducibility, and effective collaboration

Finding outliers in a dataset involves identifying data points that deviate significantly from the majority of the observations. Outliers can be caused by various factors such as measurement errors, data corruption, or rare events. Here are a few common methods to detect outliers:

1. Visual inspection: Plotting the data using graphs or charts can help identify outliers. Box plots, scatter plots, or histograms can reveal data points that are located far away from the bulk of the data.

2. Descriptive statistics: Basic statistical measures like the mean, median, and standard deviation can provide insight into the distribution of the data. Observations that lie several standard deviations away from the mean might be considered outliers.

3. Z-score method: The z-score measures how many standard deviations a particular data point is away from the mean. Observations with a z-score greater than a predefined threshold, typically 2 or 3, are flagged as outliers.

4. Modified z-score method: The modified z-score, such as the Median Absolute Deviation (MAD), is less sensitive to extreme values and works well with skewed data. Data points with modified z-scores above a certain threshold (e.g., 2.5 or 3.5) are considered outliers.

5. Box plots: Box plots visualize the distribution of the data and highlight potential outliers as individual data points outside the whiskers (usually defined as 1.5 times the interquartile range).

6. Density-based methods: Density-based clustering algorithms like DBSCAN (Density-Based Spatial Clustering of Applications with Noise) can identify outliers as data points that do not belong to any cluster or are assigned to a cluster with very few members.

7. Machine learning models: Anomaly detection algorithms, such as Isolation Forest or One-Class SVM (Support Vector Machines), can be trained to identify outliers based on the deviation from the normal pattern observed in the training data.

It is important to note that the choice of method depends on the nature of the data and the specific context in which outliers are being investigated. Different techniques may yield different results, so it is often necessary to use multiple methods and exercise domain knowledge to determine which observations should be considered outliers.

The Interquartile Range (IQR) is a statistical measure used to measure the dispersion or spread of a dataset. It is particularly useful for identifying outliers and understanding the variability within the middle 50% of the data. The IQR is calculated by finding the difference between the upper quartile (Q3) and the lower quartile (Q1) of a dataset.

Here's how to calculate the IQR:

1. Arrange the dataset in ascending order.
2. Find the median, which is the middle value of the dataset. If the dataset has an odd number of observations, the median is the value at the exact center. If the dataset has an even number of observations, the median is the average of the two middle values.
3. Split the dataset into two halves: the lower half and the upper half. If the median is included in both halves, it is common to exclude it from both halves as well.
4. Find the lower quartile (Q1) by calculating the median of the lower half of the dataset.
5. Find the upper quartile (Q3) by calculating the median of the upper half of the dataset.
6. Calculate the IQR by subtracting Q1 from Q3: IQR = Q3 - Q1.

The IQR represents the range of the middle 50% of the data. It provides a robust measure of dispersion because it is not affected by extreme values or outliers in the dataset. By considering the IQR, you can gain insight into the variability of the data without being overly influenced by extreme values.

The IQR is commonly used in conjunction with the concept of the fences to detect outliers. The lower fence is calculated as Q1 - (1.5 * IQR), and the upper fence is calculated as Q3 + (1.5 * IQR). Observations outside these fences are often considered outliers and may warrant further investigation.

The IQR is a valuable tool in exploratory data analysis and is particularly useful when dealing with skewed or non-normal distributions where other measures like the mean and standard deviation might be affected by extreme values. It allows you to identify potential outliers and understand the spread of the data in a robust and reliable manner.

Treating outliers in a dataset depends on the specific context and goals of your analysis. Here are a few commonly used approaches to handle outliers:

1. Data removal: In some cases, if outliers are due to data entry errors or measurement mistakes, it may be appropriate to remove them from the dataset. However, this approach should be used with caution and only if there is a clear justification for removing the outliers.

2. Data transformation: Transforming the data using mathematical operations such as log transformations, square roots, or reciprocals can sometimes reduce the impact of outliers. This approach can help make the data distribution more symmetric and reduce the influence of extreme values.

3. Winsorization: Winsorization is a technique where outliers are replaced with values that are closer to the rest of the data. The upper outliers are replaced with the highest non-outlier value (e.g., the 95th percentile), and the lower outliers are replaced with the lowest non-outlier value (e.g., the 5th percentile).

4. Capping and flooring: Similar to Winsorization, capping and flooring involves replacing outliers with predetermined values. Outliers above a certain threshold are replaced with the maximum value allowed, and outliers below a certain threshold are replaced with the minimum value allowed.

5. Imputation: Instead of removing outliers, you can choose to impute missing or extreme values with estimates based on the rest of the data. Imputation methods such as mean, median, or regression-based imputation can be used to replace outliers with more typical values.

6. Robust statistical techniques: Instead of treating outliers directly, you can utilize statistical techniques that are less affected by outliers. For example, using median instead of mean, or employing robust regression techniques that downweight the influence of outliers.

7. Separate analysis: In some cases, outliers represent unique or significant observations that require separate analysis. You may choose to analyze the data both with and without outliers to understand their impact on your results and draw conclusions accordingly.

It's important to note that the choice of outlier treatment depends on the specific circumstances and the goals of your analysis. It is always recommended to carefully consider the reasons behind the outliers and consult domain experts if necessary. Additionally, documenting any outlier treatment methods and justifications is crucial for transparency in your analysis.
