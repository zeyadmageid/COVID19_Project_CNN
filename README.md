# COVID19_Project_CNN

The project is a CNN classifier which classifies patients from XRAY scans as one of four: [healthy, covid-19, lung opacity, penmounia]
The dataset used was found at (https://www.kaggle.com/datasets/tawsifurrahman/covid19-radiography-database) for this project. It consists of Chest X-Ray (CXR) images of 3616 COVID-19 positive patients, 10,192 normal people, 6012 lung opacity patients,

1345 viral pneumonia patients. All the images were in grey scale with a resolution of 299×299 pixels. Only 1000 CXR images for each class were selected, to prevent the class imbalance problem, faster model tuning, and training. Then, the selected images were split into train, validation, and test sets with the ratio of 0.7 : 0.15 : 0.15. During the data set analysis, discrepancies in CXR images such as manually printed labels on the images, distortions due to imperfect scans, and capture of irrelevant body parts (E.g chin, neck) were noticed. Therefore, only well scanned images were selected to ensure fair training, testing process.

In general, grid search method, and random search method are used for hyper-parameter tuning. In grid search method, all the combinations of all hyper parameters are considered and
tried out (similar to a brute force approach). In this approach, the number of trials depends on the total number of possible combinations of the hyper parameters. In random search, the total number of trials to be tried out are specified at the beginning of tuning process. In each trial, a unique combination of hyper parameters are considered (like a trial and error method), and the best hyper parameter combination which delivers the highest accuracy is proposed as the best model after the tuning. 

Grid search based tuning would require a minimum 4x5x7=140 trials for our system. Due to the limited computational resources , the maximum number of trials I was able to run was 93. Therefore, in our system, the most crucial hyper parameters for image processing listed as follows were tuned using random search method with 93 trials.

Number of filters : Decides the number of feature maps generated (32 to 256 , step size = 32)
Number of convolutional layers  : Learns the features detected (5 to 9, step size = 1)
Filter size : Reduces the image dimensionality of the image between CNN layers (3,3), (4,4), (5,5), (6,6)
Due to limited computational resources, the other hyper parameters such as number of dense layers, learning rate were not tuned in this project.

The project also involved using transfer learning where other pretrained, well known CNN models were used and compared against an untuned CNN and the tuned CNN. The performance of the pretrained model (MobileNetV2) yielded very similar accuracy compared to the tuned CNN at a fraction of the required training time due to the fact that the pretrained model did not require hyperparameter tuning. 
