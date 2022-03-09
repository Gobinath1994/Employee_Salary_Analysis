# Employee_Salary_Analysis
This analysis done the on the basis active employee salary dataset. Analyse the salary details and see if we can find a good model capable of imputing/predicting the salaries.
Executive summary The purpose of this exercise was to

Analyse the salary details and see if we can find a good model capable of imputing/predicting the salaries in the missing rows. All the salaries were first classified into 7 different classes (742750.0, 1475000.0] 610 (1475000.0, 2200000.0] 256 (2200000.0, 2925000.0] 102 (2925000.0, 3650000.0] 35 (4375000.0, 5100000.0] 13 (3650000.0, 4375000.0] 12 (6550000.0, 7275000.0] 4 (7275000.0, 8000000.0] 3 (5825000.0, 6550000.0] 2 (5100000.0, 5825000.0] 1 Here the last 4 classes were combined to take care of the long tail of the salaries. Due to the severe class imbalance, the model was upscaled to ensure that all the classes have an adequate representation. After trying out multiple models, we finalized on an ensemble method of logistics and SVC (rbf) based model with soft voting criteria as it had a test accuracy of 76% with a standard deviation of 1.2%. We successfully imputed all the missing values to get the salaries for all the rows with missing salaries. The distribution of the final salaries is quite similar to that of the original salaries which acts as a sanity check for the predictions.
After the salary predictions the next step was to find out any trend in the titles and see if there was a way to predict the title based on the remaining parameters. After trying out multiple models including SVC, Decision tree, Random forest, Adaboost and ensemble, we reach the conclusion that the titles cannot be predicted in an accurate enough manner. So we decided to go with unsupervised classifications to see if we can extract meaning out of the data.
Unsupervised classification: After trying out multiple classes, we were able to find a good classification at 6 levels with KNN. The meaning of these classes and their associated cluster names were derived by performing the Tukey test.
Cluster 0:
Cluster name: Townie Identifiers:

These are the jobs located in all the small cities
Most of the titles in this cluster are related to Developers and Engineers
Low experience requirement of 3 to 7 years with very low salary expectations of less than INR 14,75,000 (AUD 29500) Skills: SQL, HTML and Java
Cluster 1:
Cluster name: Fresher Identifiers:

With very low experience requirement, they are most likely to be fresh college graduates.
Almost all the jobs in NCR are in this cluster with a high concentration in other major cities of Hyd, Pune, Mumbai, Bangalore and Chennai.
Most of the titles for this cluster are Developers and Engineers.
Lowest salary tier of less than INR 14,75,000 (AUD 29500) Skills: SQL and generic software skills
Cluster 2:
Cluster name: Leader Identifiers:

High job experience (with expectations of 6 to 10 years experience)
Most of the job in Bangalore are in this cluster.
They will almost never have the title of ’Analyst’
Most of the time the title is likely to have the keyword ‘Lead’, ‘Senior’ or ‘Engineer’
This cluster falls in the highest salary level typically in the range of upwards to INR 29,25,000 (60,000 AUD) Skills: SQL, Python, Algorithms, Java
Cluster 3:
Cluster name: Manager Identifiers: Extremely high experience (with expectations of 8 to 12 years experience) They are highly likely to have a managerial role Very high salaries typically in the range of upwards to INR 22,00,000 (AUD 44,000) Skills: SQL, Project Management, Six Sigma, Python and Oracle

Cluster 4:
Cluster name: Local Hotshot Identifiers: Similar to Townie Cluster with respect to small town location Likely to have much higher experience than Townies in the range of 5 to 10 years Most likely to have titles like Architect, Consultant or even Lead with similar salary range of Fresher Skills: SQL, HTML, Six Sigma, Python and Oracle

Cluster 5:
Cluster name: Hyder Identifiers: Limited to the city of Hyderabad Average Salary and experience requirements Most likely to not be in NCR Most likely salary to be in the similar range to fresher Skills: SQL, HTML, Java, Python, C and Oracle
