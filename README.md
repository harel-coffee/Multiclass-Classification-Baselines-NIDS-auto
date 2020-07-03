![Neural Network Architecture](https://github.com/ajay340/Multiclass-Classification-Baselines-NIDS/blob/master/images/model_architecture.png)
Multiclass Classification Baselines for Anomaly-based Network Intrusion Detection Systems
=========================================================================================

This repository contains jupyter notebooks for applying machine learning classification algorithms for enhancements in Network Intrusion Detection Systems.

Table of contents
=================

<!--ts-->
   * [Technology Stack](#technology-stack)
   * [Notebooks](#Notebooks)
      * [ASNM-TUN.ipynb](#ASNM-TUNipynb)
      * [EDA.ipynb](#EDAipynb)
      * [FFS.ipynb](#FFSipynb)
   * [Dataset Source](#dataset-source) 
   * [Dataset Statistics](#dataset-statistics)    
   * [Features selected from ASNM TUN Dataset](#features-selected-from-asnm-tun-dataset)
   * [Results](#results)    
<!--te-->   

Technology Stack
================
- Python 3.6
- Keras, Tensorflow, sklearn, and numpy dependencies
- Microsoft Azure Machine Learning Virtual Machine
  - 14 GiB RAM
  - 4 vCPU

Notebooks
===========
ASNM-TUN.ipynb
--------------
This notebook contains the Malware NIDS baselines using neural networks, decision trees, random forests, and support vector classifiers.

EDA.ipynb
----------
This notebook contains the compilation of the profile of the attributes in the dataset.

FFS.ipynb
---------
This notebook contains the select features used for the baselines using Forward Feature Selection with cross validation.

Dataset Source
==============
[ASNM Datasets](http://www.fit.vutbr.cz/~ihomoliak/asnm/index.html)

[ASNM Datasets: A Collection of Network Traffic Data for Testing of Adversarial Classifiers and Network Intrusion Detectors](https://ieee-dataport.org/open-access/asnm-datasets-collection-network-traffic-data-testing-adversarial-classifiers-and)

Dataset Statistics
==================
Attribute | Measured
------------ | -------------
Number of variables | 895
Number of observations | 394
Missing cells | 100
Missing cells  (%) | < 0.1%
Duplicate rows | 2
Duplicate rows (%) | 0.5%
Total size in memory | 2.7 MiB
Average record size in memory | 7.0 KiB


Features selected from ASNM TUN Dataset
=======================================
Attribute | Description
--------- | -----------
PolyInd10ordOut[3] | Outbound packet length of 10th polynomial of a packet occurrences, representing the 4th coefficient of the polynomial.
OutPktLen64s10i[8] | Outbound packets occurred in the first 64 seconds of a connection which are distributed into 10 intervals, representing totaled outbound packet lengths of 9th interval.
OutPkt4s10i[7] | Outbound packets in the first 4 seconds of a connection which are distributed into 10 intervals, representing total output packet of 8th interval.
ConTcpFinCntIn | The number of TCP FIN flags captured in inbound network traffic.
GaussProds4In[1] | Normalized sums of products of inbound packet sizes with 4 Gaussian curves for the second interval.
FourGonAngleAllN[2] | Fast Fourier Transformation of all packet sizes, while inbound packets are represented by angle coefficients.
MedTCPHdrLen | The median of TCP header lengths in all traffic.
GaussProds8In[5] | Normalized sums of products of inbound packet sizes with 8 Gaussian curves for the 5th interval.
SumTTLOut | Sum of TTL value for outbound traffic.
PolyTime10ordOut[2] | Inbound communication by 10th polynomial of packet occurrences, representing the 2nd coefficient of the polynomial.
InPkt64s20iTr2KB[14] | Number of inbound packets occurred in the first 64 seconds of a connection distributed into 20 intervals, each after accumulation of 2KB of data in the 15th interval.
OutPktLen64s10i[5] | Outbound packets occurred in the first 64 seconds of a connection which are distributed into 10 intervals in the 6th index
PolyInd13ordIn[7] | Inbound communication by polynomial of 13rd order in the 8th index domain of packet occurrences.
InPkt1s10i[8] | Inbound packets occurred at initial connection which are distributed into 10 intervals, representing totaled inbound packet lengths of the 9th interval.
OutPkt32s20iTr4KB[11] | Outbound packets occurred in initial connection distributed into 32 intervals, each after accumulation of 4KB of data on the 12th index. 
PolyTime10ordOut[8] | Approximation of outbound communication by polynomial of 10th order in the 9th time domain of packet occurrences.
OutPktLen4s10i[3] | Outbound packets occurred in the first 4 seconds of a connection which are distributed into 10 intervals, representing totaled outbound packet lengths of the 4th interval.
PolyInd13ordOut[13] | Outbound communication by polynomial of 13th order in the 14th index domain of packet occurrences.
PolyInd13ordIn[12] | Inbound communication by polynomial of 13th order in the 13th index domain of packet occurrences.
InPkt64s20iTr2KB[7] | Inbound packets occurred in the first 64 seconds of a connection distributed into 20 intervals, each after accumulation of 2KB of data on the 8th interval.

Results
=======
Comparison of 5 Neural Networks using Adam optimizer's measured accuracy over 1200 epochs.
![NN Adam Optimizer Accuracy](https://github.com/ajay340/Multiclass-Classification-Baselines-NIDS/blob/master/images/adam_accuracy.png)


Comparison of 5 Neural Networks using SGD optimizer's measured accuracy over 1200 epochs.
![NN SGD Optimizer Accuracy](https://github.com/ajay340/Multiclass-Classification-Baselines-NIDS/blob/master/images/sgd_accuracy.png)


Average scores for Baselines
Baseline | Averages
-------- | --------
Neural Network with Adam optimizer | 79.18%
Neural Network with SGD optimizer | 69.30%
Decision Tree | 87.57%
K Nearest Neighbors | 82.24%
Random Forest | 85.78%
Linear Support Vector Classifier | 14.99%

