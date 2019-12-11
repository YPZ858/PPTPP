# PPTPP
Codes of A novel therapeutic peptide prediction method using physicochemical property encoding and feature representation learning

Before you start
=========

Make sure JAVA, C++ complier have been properly installed on your machine to avoid the disappointment of getting dependences installation error.

This work is based on Anaconda 5.3.1, and therefore, we recommend users to choose Anaconda for running relevant Python codes.
The enviroment where PPTPP was built was exported as the file named PPTPPenvironment.yaml in the Zip file, please make sure you have the same environment to make everything works.

How to use
==========

First, place your raw data, which should be in FASTA format with class lable (Please see the raw data already placed in the folder) and stored in TXT file, in the folder of RAW.

Then, 
-----
1.switch to the path where you store the code using command: 
cd X:\XX\XXXX

2.Run the code using command:

%run Training -i XXP

where XXP is the name of your data. For example, if you stored your AAP data in the file of AAP.txt, please use the command  %run Training.py -i AAP

During this process, all 531 meta-predictors would be established and the all the relevant ARFF, details produced by WEKA will be stored in the folder of PPTPP\Results\XXP\Data\Level1. Metrics of all meta-predictors can be found in the folder PPTPP\Results\AAP\Metrics\531 Metrics.

3.After Training.py finished its work, pleasr run Ranking.py by using:

%run Ranking.py

MRMD2.0 will be started to perform the ranking task and the ranking result would be stored in the folder of PPTPP\Results\AAP\Metrics\Learning as a .log file.

4.When Ranking.py done its job, PLEASE RESTART THE KERNEL AND CLEAR THE CONSOLE, to avoid the error of starting jvm.

5.Now switch to the path, as did in the step1, run the learning.py by using: run Learning.py . The optimal result will be shown when the programme ends and relevant data during learning process can be found in the folder of PPTPP\Results\AAP\Metrics\Learning Metrics.

6.If you want to do independent test, please place your raw testing data in the RAW folder and name it after the name of training data with a T attached to the name, for example, if you want to test AAP using the established predictor, please name your data as AAPT.txt and place in the RAW folder. Make sure you labled the data, even if its fake, as you can track the prediction of individual samples later. To sure the correct tracking, please put all the samples with the same class lable together, for sample, the first half of the sample should be 0 and the second half be 1, as the test data stored in the fold of RAW suggests. Then the ID of the samples in the final file can be exactly the same as what we initially input.

7.Then repeat step 4, switch to the current path and run: %run Testing.py -i AAPT 
Results will be stored in \PPTPP\Results\AAPT\Data\Level2\Data. You can find the prediction results of individual samples in the buffer.txt 
