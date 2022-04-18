# Bias-and-Explainability

Dataset: Download the cifar10 dataset from this link

Algorithm: Train a VGG16 model from scratch. Your testing accuracy must cross 60%. Hint: You may
modify the architecture.

Training: Train the model on coloured images.

Testing: Test the model on gray-scaled images. You can concatenate the gray scale images to make number of
channels as 3.

Evaluation: Perform a 10-class classification and report the performance as follows:

1. Perform 10 class classification using the above neural network, with the final node being a sigmoid
activation. Keep the loss function as the mean square error. Use the testing set to report accuracy.

Results - Accuracy and Other Bias metrics

In coloured CIFAR images, the loss was 0.7219253182411194 with accuracy
76.57999992370605 %, however, in gray-scale images, the loss increased to
0.8316113352775574 with accuracy 72.9200005531311 %.
The class-wise accuracy of the gray-test images is shown in Figure 14.

![Aspose Words 50618ed9-b1b2-4630-9df0-4f841fa4401b 014](https://user-images.githubusercontent.com/59523992/163760193-60501711-c803-4831-932a-b6b066399f45.png)


Figure 14: Class wise accuracy on gray test images

We can observe that the accuracy is very low in case of bias, cat and dog.

The bias metrics are shown below:

a) Confusion Matrix

![Aspose Words 50618ed9-b1b2-4630-9df0-4f841fa4401b 015](https://user-images.githubusercontent.com/59523992/163760228-26a34a27-791f-4fb4-aede-a51420222291.png)

Figure 15: Confusion matrix of gray test images

2.1.2 Degree of Bias
The degree of bias is 0.1453470329934533.

2.1.3 Disparate Impact
The disparate impact is 1.0544391431459281.

2.1.4 New evaluation metric
A new evaluation metric can be Accuracy × Degreeof Bias. Just like tf-idf.
High accuracy but low DOB means accurate and unbiased model where as high
accuracy but high DOB means accurate but biased model. The range of this
metric would be from 0-1, the perfect score would be somewhere around 0.5 and
extremes would be worst. The metric ssore is 0.1059870572627858.

b) DATA method (Pre-Processing)

We have converted 50 % images in the training set to gray-scale so as to remove
color bias and model to correctly predict the gray scale images which was downfall in the previously calculated accuracy where the model was solely trained on
RGB images but tested on gray-scale images. We have further performed data-augmentation techniques to increase the training set. These changes improves
the performance of the model than the previous model. Accuracy is increased
and is 75.31999945640564 %. The class-wise accuracy is shown in Figure 16.

![Aspose Words 50618ed9-b1b2-4630-9df0-4f841fa4401b 016](https://user-images.githubusercontent.com/59523992/163760390-6d4c17f1-f6de-40e2-9091-0dd18e47c345.png)

Figure 16: Class-wise accuracy with data method

Figure 17 shows confusion matrix with data method In this we observe the
earlier bird’s, cat’s and dog’s accuracy is increased significantly.

![Aspose Words 50618ed9-b1b2-4630-9df0-4f841fa4401b 017](https://user-images.githubusercontent.com/59523992/163760476-e3edf075-2916-4aab-abb5-113d5f41503e.png)


Figure 17: Confusion matrix with data method

The degree of bias is 0.13653043616717847. The disparate impact is
1.0614388262621224. The new evaluation metric score is 0.10283472377894708.

2. Test the above model on the testing set of gray-scaled images. [10 Marks]
3. Report class-wise accuracy. [10 Marks]
4. Do you think there is any kind of bias in the system? Evaluate the system using 3 different evaluation
metrics to see if there is any bias or not. [10 Marks]
5. (Bonus) Come up with a new evaluation metric to detect if there is a bias in the system. [10 Marks]
6. If you observed any bias in the system, mitigate the bias by:
• DATA method (Pre-Processing): You may use any of the pre-processing technique to achieve your
aim. [10 Marks]
• ALGORITHMIC method: You can alter loss function or use a multi tasking approach to achieve the
goal. [10 Marks]
7. Select 2 samples from each class which were correctly classified by the trained model. Apply GradCam
and GradCam++ on it and visualise most salient regions being used for prediction. [10 Marks]
8. Select 2 samples from each class which were incorrectly classified by the trained model. Apply GradCam
and GradCam++ on it and visualise most salient regions being used for prediction. [10 Marks]
