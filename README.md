# SVC-Cataract (pending)
## Support Vector Classifier for cataract detection.

For this binary classification problem, the Cataract dataset from Kaggle was used. The algorithm implements a SVC (Support Vector Classifier) for 
detecting cataract based on retina images. The 2 classes that were created are:

### • Normal 

### • Cataract

Since each individual image is of size 2464x1632x3 and due to the size of the dataset, only 160 images were used. Then, each one of them is resized to 50x50x3,
passing the data to a 'DataFrame'. 
After that it splits the data (60% for training, 40% for testing). 
Then is up to us to optimise the algorithm, so we tune the parameters: kernel, C and gamma. 
For the specific dataset, taking into consideration the amount of images and their respectful sizes, the linear kernel with the parameter C = 1 was the best one.

First, we decide the kernel that will be used. Notice that by using the grid search technique, the linear kernel seems to have the same results as the rbf one, 
so based on the Occam's razor principle, we will be choosing the linear kernel. For the multi class classification problem the algorithm implements the One-Vs-One 
strategy. Since we talk about a medical problem, great precision is required for errors not to be resulted. This justifies the reason why the value of C should not 
be greater than 1. By further reducing the value did not seem to have any other effect, rather than decreasing the accuracy.
Lastly, the algorithm prints a detailed classification report. Scores regarding the precision, recall and f1 metrics are printed. 

The accuracy as well as the other metrics were satisfactory, even though a small number of images was used. For the specific dataset, resizing the images was 
crucial. At first, 50 images from each class was used. After increasing the size of the dataset, there was a significant increase of the accuracy· from almost 70% 
to almost 90%, as shown above. So, testing the model with this image:

![alttext](https://github.com/raf-init/SVC-Cataract/blob/main/cataract_img.png)

We get the following result on the command line:

![alttext](https://github.com/raf-init/SVC-Cataract/blob/main/cataract_res.png)
