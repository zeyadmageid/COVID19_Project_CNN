# COVID19_Project_CNN

The goal of the project is to use a CNN classifier which classifies patients from XRAY scans as one of four: [healthy, covid-19, lung opacity, penmounia]
The dataset used was found at (https://www.kaggle.com/datasets/tawsifurrahman/covid19-radiography-database) for this project. It consists of Chest X-Ray (CXR) images of 3616 COVID-19 positive patients, 10,192 normal people, 6012 lung opacity patients,

1345 viral pneumonia patients. All the images were in grey scale with a resolution of 299×299 pixels. Only 1000 CXR images for each class were selected, to prevent the class imbalance problem, faster model tuning, and training. Then, the selected images were split into train, validation, and test sets with the ratio of 0.7 : 0.15 : 0.15. During the data set analysis, discrepancies in CXR images such as manually printed labels on the images, distortions due to imperfect scans, and capture of irrelevant body parts (E.g chin, neck) were noticed. Therefore, only well scanned images were selected to ensure fair training, testing process.

In this project,hyperparameter tuning and transfer learning were used and compared in order to find the CNN with the highest testing accuracy. Random search was used when tuning the CNNs and various other pre-trained CNNs were used as well. In order to show case the benefit of hyperparameter tuning, an untuned CNN was used and compared to all the previously mentioned CNN,

The performance of the pretrained model (MobileNetV2) yielded very similar accuracy compared to the tuned CNN at a fraction of the required training time due to the fact that the pretrained model did not require hyperparameter tuning. 

For more detaisl about the project, please read the attached PDF file which shows the overall project report findings.
