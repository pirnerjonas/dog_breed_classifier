# Dog breed classification
Image classification project with the aim to classify dog breeds. It also predicts the most resembling dog breed for humans.

![obama](/images/obama.png)

### Installation

The necessary data for this project contains a [dog dataset](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/dogImages.zip) and a [human dataset](http://vis-www.cs.umass.edu/lfw/lfw.tgz). Be sure to set the path in `dog_app.ipynb` to the datasets.

Also if you want to run the *Additional analysis* section in Step 5 of the notebook you have to make sure to download the pre-trained models [VGG-19](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/DogVGG19Data.npz), [ResNet-50](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/DogResnet50Data.npz) and[Inception](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/DogInceptionV3Data.npz) and store them in the folder `bottleneck_features`.

### Training process

In the notebook `dog_app.ipynb` various CNN architectures are trained. To speed up training I recommend running the code on a GPU. One - of many ways - is using [Google Colab](https://colab.research.google.com/).

### Results

The results of this project are discussed in an external [blog post](https://pirnerjonas.github.io/2020/04/17/dog-breed.html).

### Improvements

To underline that the presented algorithm is far from being perfect I will highlight three aspects that could be improved (there are certainly more than three):

- **human & dog detectors:** I chose not to implement own human and dog detectors because I wanted to focus on the CNN part. Nevertheless I think that there is room for improvement here. It would be very cool (and I think promising) to train another CNN which has the job to classify the data into human vs non-human.  
- **parameter tuning:** Even though I compared the different bottleneck features I spend little time on actually improving the architecture or the training parameters. Here different learning rates, number of layers, number of neurons, etc. could be tested to see if they impact the accuracy.
- **fine tuning:** rather then choosing either training from scratch or incorporating pretrained models (and just training the last layers) it could be tested if a more sophisticated fine tuning step could improve the performance metrics. This means "unfreezing" some of the top layers of the pretrained model to let the model adapt to the data it currently sees. There is a nice tensorflow tutorial that deals with this matter ([click here](https://www.tensorflow.org/tutorials/images/transfer_learning))
