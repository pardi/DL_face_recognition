This project implements a Generative Aversarial Network (GAN) to generate faces based on the celebrity dataset, [CalebA] (https://www.kaggle.com/datasets/jessicali9530/celeba-dataset)


# Install

TODO

# Usage

# Results

# The dataset

The dataset has been pre-processed to obtain images with consistent size and the face in the centre of the image. The restriction on the type of images make the problem easier and suitable for the initial testing of the algorithm.

# The network

We implemented the two tipycal networks: the discriminator and the generator.
The latter **must** generate images that as much similar as possible to the real images give in the dataset, and the former must distinguish whether the presentend image is a **real** image or not.

The generator takes as input a randomly generated vector between [-1, 1]. Then, the network employs a sequence of transposed convolutional layers that double the size of the image at every step. Finally, an output layer reduce the feature channels to 3 and apply a <em>Tan()</em>, which constrains the output of the generator between [-1, 1].


The discriminator takes as input either a real image coming from the dataset or a fake image, generated by the generator. The size of the images **must** be (X, Y, 3) and the network uses CNNs to capture the most valuable information of the image and discriminate the probability that the presented image is actully real.

For both networks, we do not use <em>maxpooling</em> or <em>upsampling</em>. However, we achieve the enlarging or shrinking of the original image using a <em>stride = 2</em>.

# Hyperparameters
TODO

