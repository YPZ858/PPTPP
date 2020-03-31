# PPTPP
Codes of A novel therapeutic peptide prediction method using physicochemical property encoding and feature representation learning

Before you start
=========

Make sure JAVA, C++ complier have been properly installed on your machine to avoid the disappointment of getting dependences installation error.

Your javac need to support the version 6 therefore we recommend to use JDK 11 rather than 13

This work is based on Anaconda3, and therefore, we recommend users to choose Anaconda for running relevant Python codes.
The enviroment where PPTPP was built was exported as the file named PPTPPenvironment.yaml in the Zip file, please make sure you have the same environment to make everything works.

You could open the .yaml file with notepad to check if all the required dependencies have been installed properly.

How to use
==========

First, place your raw data, which should be in FASTA format with class lable (Please see the raw data already placed in the folder) and stored in TXT file, in the folder of RAW. The name of raw data should be the name of peptide for later prediction: AAP should be stored as AAP.txt

Then, 
-----
1.Open the Anaconda prompt and activate PPTPP environment using:

Activate PPTPP

2.switch to the path where you store the code using command: 

cd X:\XX\XXXX

2.Run the Training code:

When using class feature (PPTPP_cls):

python Training_cls.py -i XXP

When using probabilistic feature (PPTPP_prb):

python Training_prb.py -i XXP

When using class feature (PPTPP_fus):

python Training_fus.py -i XXP

where XXP is the name of your data. For example, if you stored your AAP data in the file of AAP.txt, please use the command  python Training_fus.py -i XXP when fusion feature mode was selected

During this process, all 531 meta-predictors would be established and the all the relevant ARFF, details produced by WEKA will be stored in the folder of PPTPP\Results\XXP\Bin. Metrics of all meta-predictors can be found in the folder PPTPP\Results\XXP\Metrics.

3.After Training.py finished its work, pleasr run Ranking.py by using:

python Ranking.py

MRMD2.0 will be started to perform the ranking task and the ranking result would be stored in the folder of PPTPP\Results\AAP\Metrics as a .log file.

4. Run the learning code:

When using class feature (PPTPP_cls):

python Learning_cls.py -i XXP

When using probabilistic feature (PPTPP_prb):

python Learning_prb.py -i XXP

When using class feature (PPTPP_fus):

python Learning_fus.py -i XXP

After this process, you may see the AUC on the screen and relevant data has been stored. All major metrics can be seen the Metrics folder.

5.If you want to do independent test, please place your raw testing data in the RAW folder and name it after the name of training data with a T attached to the end of name, for example, if you want to test AAP using the established predictor, please name your data as AAPT.txt and place in the RAW folder. 
Make sure you labled the data, even if its fake, as you can track the prediction of individual samples later. When everything is ready, run:

When using class feature (PPTPP_cls):

python Testing_cls.py -i XXP

When using probabilistic feature (PPTPP_prb):

python Testing_prb.py -i XXP

When using class feature (PPTPP_fus):

python Testing_fus.py -i XXP

All major metrics and individual prediction results can be found in the folder of Metrics.
