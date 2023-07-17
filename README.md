
# Covid 19 Mortality Prediction

COVID-19 is commonly mild and self-limiting, but in a considerable portion of patients the disease is severe and fatal. Determining which patients are at high risk of severe illness or mortality is essential for appropriate clinical decision-making. By early prediction of Severe covid-19 patients it can help overburdened hospitals to arrange the resources like Oxygen cylinders and ICU beds accordingly which can save the life of patient.

## Dataset Description

The data file contains information on demographics, comorbidities, admission laboratory values, admission medications, admission supplemental oxygen orders, discharge, and mortality. The data were derived from a healthcare surveillance software package (Clinical Looking Glass [CLG]; Streamline Health, Atlanta, Georgia) and review of the primary medical records.

It has a total of 85 features and 4711 rows. Some of the variables included in the dataset are: length of hospital stay (LOS), myocardial infraction (MI), peripheral vascular disease (PVD), congestive heart failure (CHF), cardiovascular disease (CVD), dementia (Dement), Chronic obstructive pulmonary disease (COPD), diabetes mellitus simple (DM simple), diabetes mellitus complicated (DM complicated), oxygen saturation (OsSats), mean arterial pressure, in mmHg (MAP), D-dimer, in mg/ml (Ddimer), platelets, in k per mm3 (Plts), international normalized ratio (INR), blood urea nitrogen, in mg/dL (BUN), alanine aminotransferase, in U/liter (AST), while blood cells, in per mm3 (WBC) and interleukin-6, in pg/ml (IL-6).
## Feature Selection

1. The following features were dropped due to similarity with other features:
'FerritinYes', 'O2SatsYes','O2 Sat < 94', 'AgeScore', 'Age','TempYes','Temp > 38','MapYes','MAP < 70', 'DDimerYes','D-Dimer > 3', 'PltsYes','PltsScore', 'INRYes', 'INR > 1.2', 'BUNYes', 'BUN > 30', 'CrtnYes','CrtnScore', 'SodimuYes','Sodium < 139 or > 154', 'GlucoseYese','Glucose <60 or > 500', 'ASTYes', 'AST > 40','ALT > 40',  'ALTYes', 'WBCYes', 'WBC <1.8 or > 4.8' 'LymphoYes','Lymphocytes < 1', 'IL6Yes','IL6 > 150', 'FerritinYes','Ferritin > 300','CrctProtYes','C-Reactive Prot > 10', 'ProCalCYes', 'Procalciton > 0.1', 'TropYes', 'Troponin > 0.1', 'LOS_Y'

2. With the help of ANOVA test, the features who impact on the prediction were chosen. 

This led to a final feature count of 23.


## Decision Tree

In general pruning is a process of removal of selected part of plant such as bud,branches and roots . In Decision Tree pruning does the same task it removes the branchesof decision tree to overcome the overfitting condition of decision tree.

There are two kinds of pruning: Pre-pruning and Post-pruning. Here, Post-Pruning was used.

#### Post-Pruning: 
This technique is used after construction of decision tree. It is used when decision tree will have very large depth and will show overfitting of model. Here we will control the branches of decision tree that is max_depth and min_samples_split using cost_complexity_pruning.

ccp_alphas gives minimum leaf value of decision tree and each ccp_aphas will create different - different classifier and choose best out of it.ccp_alphas will be added as a parameter in DecisionTreeClassifier() .
