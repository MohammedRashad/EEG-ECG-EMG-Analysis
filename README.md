# eeg-ecg-pattern-recognition

- Visualization of signal in all channels
- Statistical reports (mean, std, variance, correlation..etc)
- Power spectrum and data filtering with high pass filter
- Detection of most notable frequencies in the signal
- Model in SVM and Random Forest to classify the signal

# Model and Signal Classification 

In this section, we just apply the the following algorithms on the data.
<br/> in order to classify the signal whether it belongs to rest or activity

### Common setup 
- test_size = 0.5

### SVM 
- C=10E3
- kernel = linear

#### confusion_matrix

|          | positive | negative |
|----------|----------|----------|
| positive | 4        | 0        |
| negative | 0        | 2        |

#### classification_report

|              | precision | recall | f1-score | support |
|--------------|-----------|--------|----------|---------|
| 0            | 1.00      | 1.00   | 1.00     | 4       |
| 1            | 1.00      | 1.00   | 1.00     | 2       |
| accuracy     | 1.00      | 6      |          |         |
| macro avg    | 1.00      | 1.00   | 1.00     | 6       |
| weighted avg | 1.00      | 1.00   | 1.00     | 6       | 

#### accuracy_score
1.0


### Random Forests 
- random_state = 0
- iterations = 100



#### confusion_matrix
|          | positive | negative |
|----------|----------|----------|
| positive | 3        | 1        |
| negative | 0        | 2        |


#### classification_report
|              | precision | recall | f1-score | support |
|--------------|-----------|--------|----------|---------|
| 0            | 1.00      | 0.75   | 0.86     | 4       |
| 1            | 0.67      | 1.00   | 0.80     | 2       |
| accuracy     | 0.83      | 6      |          |         |
| macro avg    | 0.83      | 0.88   | 0.83     | 6       |
| weighted avg | 0.89      | 0.83   | 0.84     | 6       |


#### accuracy_score

0.8333333333333334



## Rest Data 

### Data Loading
The data is first transformed into suitable format using a converter code, <br/>to be in csv format and remove redunant columns

### Data Visualization

We Visualize the time series in time domain. to make a visual check that we are loading the correct data,
<br/> and we can use it to the next steps

### Data Statistical Reporting 

Here we generate a full report for each sample, 
<br/>to see the correlation between signals and also the see the Statistical features of the data itself


### Transformation of the dataset to frequency domain and generation of power specturm

We do this, because EEG is only useful in frequency, and it's not having useful features in time domain alone,
also to apply a HPF to choose the relevant features

### Building the final dataset for classifcation 

We combine the data from all the samples, and add relevant features, to build a small dataset for the model itself


## Step Data 

### Data Loading
The data is first transformed into suitable format using a converter code, <br/>to be in csv format and remove redunant columns

### Data Visualization

We Visualize the time series in time domain. to make a visual check that we are loading the correct data,
<br/> and we can use it to the next steps

### Data Statistical Reporting 

Here we generate a full report for each sample, 
<br/>to see the correlation between signals and also the see the Statistical features of the data itself


### Transformation of the dataset to frequency domain and generation of power specturm

We do this, because EEG is only useful in frequency, and it's not having useful features in time domain alone,
also to apply a HPF to choose the relevant features

### Building the final dataset for classifcation 

We combine the data from all the samples, and add relevant features, to build a small dataset for the model itself
