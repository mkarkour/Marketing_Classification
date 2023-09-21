# MediaZone Customer Loyalty and Cross-Selling Project

## Business Objective
MediaZone aims to increase customer loyalty and improve the net margin of its web shop through cross-selling. To achieve this, the Chief Marketing Officer (CMO) proposes a project to develop an automated system that identifies and suggests relevant promotions to customers in real-time. The Data Science department is tasked with creating a proof-of-concept and making recommendations for potential industrialization.

## Data
Data for this project has been extracted based on the following design:
- **Target Period:** 1 week to measure if a client purchases a product in a specific category.
- **Observation Period:** 6 months before the target period.
- **No Latency Period:** Real-time identification of visitors using cookies.
- During the observation period, 392 variables describing customer purchases have been computed.

Promotions have been aggregated into a set of 10 categories:
- C1_A_Chanson Francaise_La Nouvelle scene
- C2_A_Polars / SF_Polars
- C3_A_Pop-Rock_Rock independant
- C4_A_Films_Action et Policier
- C5_A_Films_Cinephiles
- C6_A_BD_BD Mangas
- C7_A_Maison / Loisirs_Tourisme
- C8_A_Romans_Bestsellers
- C9_A_Pop-Rock_Pop-Rock FM
- C10_A_Films_Drames

Each client (Client_ID) has a flag = 1 (Target) for one of the above variables if he/she took the proposed promotion during the week of the test (Target period).

## Assignment
- Tasked with proposing the best promotion category, "BD Mangas" or "Pop-Rock_Rock independant," for each visiting client.
- The chosen category should maximize the expected margin, which partially depends on the chance to convert the proposed promotion into a sale.

## Data Sets
Two data sets are provided:
- `2021_WebShop_train.csv.gz`: Compressed CSV file containing 15,000 records.
- `2021_WebShop_test.csv.gz`: Compressed CSV file containing 20,000 records with the same variables, excluding category target variables except "C3_A_Pop-Rock_Rock independant" and "C6_A_BD_BD Mangas," which contain missing values to be filled.

## Project Tasks
1. Implement the promotion assignment process in Python.
2. Create a PowerPoint document named "2021_GroupXX_Webshop_report" to explain the process:
   - Describe any new derived variables.
   - Explain the model in business terms.
   - Discuss model quality, including Sensitivity, Precision, Accuracy, and AUC.
   - Address model variance and overfitting.
   - Explain how the promotion choice is made to maximize net margin.
3. Assign a single promotion to each client in `2021_WebShop_test.csv.gz` by filling "1" for the proposed category and "0" for the other one.
   - Save the results in a CSV file named `2021_GroupXX_Webshop_test.csv.gz` with fields "Client_ID," "C6_A_BD_BD Mangas," and "C3_A_Pop-Rock_Rock independant."

Be cautious not to assign "1" for both promotions to ensure proper revenue calculation.
