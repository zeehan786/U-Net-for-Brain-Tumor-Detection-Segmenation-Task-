# U-Net-for-Brain-Tumor-Detection-Segmenation-Task-
Brain Tumor Auto-Segmentation for Magnetic Resonance Imaging (MRI) (A Multi-Label Image Classifier)

In this Coursera assignment, I have performed segmentation tasks of 3d images of the brain. The goal of the assignment is to predict whether a pixel of an image belongs to any tumor (Edema, Non-enhancing tumor and enhancing tumor).

Apart from the width and height, a 3D image also contains depth. Furthermore, there is also a 4th dimension which represents the four sequences. In simple terms, each sequence highlights different regions of the brain to detect different kinds of tumors. Before the image is fed into the model, it contains a whopping of 5 dimensions (the first one being the batch dimension).

As training a single image with 5 dimensions (even using Stochastic Gradient Descent) will consume a lot of memory (the training might lead to out-of memory error in local cpu), training the images with patches is recommended. Random patches are extracted from the 3d image and fed into the U-Net model for training. However, training with patches was considerably slow on the free version of Colab. Therefore, I used a pretrained model to perform the segmentation task.

Laslty, soft dice loss is the ideal loss function when it comes to segmentation task and imbalanced data. The lower the soft dice loss means, the better the predicted patch matches with the ground truth patch.  
