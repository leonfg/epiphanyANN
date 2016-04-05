# epiphanyANN

This project is based on nickoppen's nnP project(https://github.com/nickoppen/nnP). I changed the nnP.cpp and nn.hpp code for the following purposes:
1. Prediction process run faster when there are multiple samples in the *.dat file. By make the JIT compile once instead of everytime.
2. Output a prediction log file named "testlog.csv" to record all the prediction result when there are more than one sample in the *.dat file.

Other Work:
1. Because I did not make the training feature run correctly, I wrote some Matlab codes to train a MLP in Matlab and import the weights and biases in *.nn format, and import the test samples in *.dat format. So I can test the prediction feature of the epiphany ann. The Matlab codes will upload in another repository later.
2. UCI IRIS test case integrated.

FILE DESCRIPTION:
testData/4-10-3-IRIS: 
This folder contains the IRIS test cases. you can run the test with a "4/10/3" topology ann. There are 3 different cases, for example, folder 75-75 means the weights and biases were trained by 75 samples and tested by 75 other samples. And the 100-50-100 means the weights and biases were trained by 100 samples and tested by 50 other samples and the accuracy rate is 100%(in Matlab). The accuracy rate in Matlab are also recorded in every rr.txt. There are other important files. "matlabtestresult.csv" recorded the Matlab prediction results with the same test samples in tt.dat, you can check the consistency of prediction result between Epiphany and Matlab by compare the "matlabtestresult.csv" and "testlog.csv". "input_train.csv", "output_train.csv" are the samples for training in Matlab. "input_test.csv", "output_test.csv" are the samples for test in Matlab, and the data in input_test.csv is same with the tt.dat. 

BUILD:
./buld.sh

RUN:
reference the t*.sh in the testData folder.

Note:
The prediction results of Epiphany are not always same as the MLP in Matlab, in some case the results of Epiphany are totally wrong. But in some other test case for example the 100-50-100, they are exactly same. I'm still figuring out the reason.
 
Leon
