# DSA4212

## Objective
Build an algorithm that can automatically tell whether an image corresponds to a young person or not.
* You are only allowed to use a logistic regression model (possibly with regularization).
* You can only use the first 15,000 images to train you model. The accuracy of your model will be evaluated on the last 5,000 images.
* You are allowed to use whatever optimization algorithm you think is most efficient.
* You are allowed to do whatever pre-processing you deem appropriate.
* You will report the accuracy (i.e. th percentage of correctly classified) on the test dataset (i.e. the last 5,000 images).
* You will as well report the Area Under the Curve (AUC) of your classifier on the test dataset.

Some remarks:
* You can work with colored, or grayscale images.
* You can rescale the images to whatever resolution you think is best/efficient
* It is usually a good idea to rescale the pixel intensity in between 0 and 1
* If you fit a logistic regression in dimension D, with each coordinate roughly in between 0 and 1, it is usually a good idea to start with a random β with mean 0 (or 0.5), and standard deviation 1/sqrt(D) for each coordinate.
* It may be a good (or bad?) idea to increase/lower the contrast of the image.
* It may be a good (or bad?) idea to only consider a smaller parts of the image (eg. only the parts near the eye?) -- some parts of the image may be irrelevant.
* Sometimes it can be a good idea to randomly add noise, or randomly add some variations to the images. (keyword: data-augmentation)
It can be a good idea to quickly explore different approaches on a subset of the dataset, and maybe at a lower resolution (to make the algorithm converge faster)
* The dataset is imbalanced -- there are 78% of "Young" people in the dataset. It is sometimes a good idea to consider a balanced subset of the dataset to fit your algorithm.
* Make absolutely sure that you do not use the test dataset (i.e. the last 5,000 images) to train your algorithm.

D = 40 (predictors)
Initialise each beta as N(0, 1/sqrt(40))

## Workflow
1. Split into training [0:14999], test[15000:20001] data 
  - Work with a temporary dataset of 3000 picked randomly from final_training, no need to select balanced for now \\
  - Consider a balanced subset of the dataset if classifier turns out to be useless

2. Rescale images to fixed resolution
  - Try 100x100 first

3. Rescale pixel intensity between 0 and 1
4. On a subset of the data, test logistic regression under these scenarios (report % accurately classified and AUC)
  - Try regularised (LASSO/ Ridge)
  - Colored vs grayscale
  - Different contrast of image
  - Consider a smaller part of the image
  - Add random noise (data-augmentation)

5. Write report

### Optimisation algorithms we have covered
* Gradient descent
* Stochastic GD (For large n)
* SGD + momentum
* L-BFGS (For large p)
* BFGS (For large p)
* S subG D

### Things to consider
* Coloured or gray scaled images
* Image scale
* Contrast of images
* Which parts of image to consider (Feature selection??)
* Data augmentation?
* Which algorithm or regularization method to use?
