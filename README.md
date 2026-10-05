# Hurricane Risk Prediction

I worked on this project with the Data Science and Machine Learning Club at Baruch College in November and December 2025. We looked at recorded hurricane damage in Miami-Dade County, Florida. My part included cleaning the data, analyzing ZIP codes, and working with a Random Forest model.

## What we did

We used OpenFEMA housing-assistance records and kept the ZIP code, disaster number, and damage amount. After removing missing values, we grouped the records by ZIP code. I looked at the 10 ZIP codes with the highest total recorded damage and made a bar chart.

For the model, ZIP codes in the top 25% of recorded damage were labeled high risk. We used average damage, record count, and a mock exposure feature as inputs. The data was split into 153 training ZIP codes and 39 test ZIP codes. The repo has one model: Random Forest, built with scikit-learn.

## Results and what they mean

The saved notebook reports 89.7% accuracy. A rerun using the saved CSV files also got 35 of the 39 test ZIP codes right.

That score needs context. The exposure feature is made from random numbers, not real exposure measurements. The high-risk label is also based on the same damage records used for the inputs. Average damage multiplied by record count gives the total damage used to create the label, so the model already has much of the answer in its inputs.

This was a learning project, not a reliable forecast of future hurricane damage. The test set is small. The top-10 chart shows past recorded damage, not a prediction of which areas will be hit next. The data request also does not collect every page of FEMA results, so this file is not a complete damage history. I would not use it for emergency planning or insurance decisions.

## Running the notebooks

The original notebooks and CSV files are kept here. They were written in Google Colab and use manual file uploads. 

Before rerunning, change Y_test to y_test in the evaluation cell, use the same variable name for importance in the feature chart, and remove the extra dot at the end of the top-10 chart's ticklabel_format line. The chart labels dollars as millions without dividing the values, so that axis also needs correcting. Set a NumPy random seed if you regenerate the mock exposure feature.

I used Python, pandas, NumPy, scikit-learn, and matplotlib.

This is a copy of the project from my old account: https://github.com/Swi-kc/Hurricane-Risk-Prediction
