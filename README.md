<H1 align="center">Deep Learning with PyTorch: Neural Style Transfer</H1>

- In this repository I have learned to implement neural style transfer using PyTorch. Neural Style transfer is an optimization technique used to take a content and a style image and blend them together so the output image looks like the content image but painted in the style of the style image. We will create artistic style image using content and given style image. We will compute the content and style loss function. We will minimize this loss function using optimization techniques to get an artistic style image that retains content features and style features.
- At the end of this implementation you will be able to generate images from this:

![content6](https://github.com/Shifu34/Deep-Learning-with-PyTorch-Neural-Style-Transfer/assets/140503589/e3b71436-be2a-4a3b-97b7-5cdbaf214cce)

- To this:
  
![output1](https://github.com/Shifu34/Deep-Learning-with-PyTorch-Neural-Style-Transfer/assets/140503589/373f963b-6d92-4cef-ac86-c094a154ebc4)

![output2](https://github.com/Shifu34/Deep-Learning-with-PyTorch-Neural-Style-Transfer/assets/140503589/60de41f4-e7b5-440f-a871-2f07bd18bbae)

- This is divided into seven steps:
  1. Setup the enviroment
  2. Loading VGG pretrained model
  3. Preprocessing the image
  4. Deprocessing the image
  5. Get content,style features and create gram matrix
  6. Creating Style and Content loss function
  7. Training loop

1. Setup the enviroment:
   - In this step we will be setting up the enviroment like installing related dependencies and cloning the repository for images.
   - First we will install torchvision using this command:
     ```
        !pip install torch torchvision
     ```
   - After this you have to clone the repository for content and style images. For this we can use this command
     ```
        !git clone https://github.com/Shifu34/Deep-Learning-with-PyTorch-Neural-Style-Transfer.git
     ```
2. Loading VGG Pretrained Model:
   - In this step, we will load the VGG pretrained model so that we can use it on our images.
   - We will also remove the classification part of this model as it is not used in this implementation.
   - We will also move it to the GPU as we will utilize GPU for this task.
3. Preprocessing The Image:
   - In this step, we will be preprocessing the image.
   - We will resize the image to same size for both content and style image.
   - We are also converting it to tensor by using transform.ToTensor().
   - We are also normalizing the image using the default mean and standard deviation.
   - We are also unsqueezing it using unsqueeze(0). It will add batch size to the tensor.
   - After preprocessing both style and content image, we are sending it to the GPU.
4. Deprocessing The Image:
   - First we get the image back to the CPU for deprocessing.
   - Then we convert it to numpy.
   - We then squeeze it using squeeze(0). It will remove that batch size which was added by using unsqueeze(0).
   - Then we transpose the image because T.ToTensor method take a transpose when converting it to the tensor.
   - We also multiply it with standard deviation and add mean value.
   - We also use image.clip(0,1) to set the tensor value in this range.
5. Get Content, Style Features And Create Gram Matrix:
   - First we create a function as get_feature which will give us features. Then we will get features for both style and content image.
   - We also create a function gram_matrix which will give us gram matrix of a tensor.
6. Creating Style and Content Loss Function:
   - We create two function; content function and style function.
   - Content function will calculate the loss between target and content features.
   - Style function will calculate the loss between target and style images.
7. Training Loop:
   - So first, we initilize optimizier in which we pass target because we want to update the pixel value of the target when loss get minimized.
   - We also initilize alpha, beta, epochs and show_every.
   - We create function to calculate the total loss.
   - We then loop through the epochs and train it.
   - After this we will plot the target image and the content image.

These are all the steps to do the style neural style transfer using pytorch.

# We can do any content image and any style image we want to do.

Happy Coding:)
