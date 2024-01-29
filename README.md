<H1 align="center">Deep Learning with PyTorch: Neural Style Transfer</H1>

- In this repository I have learned to implement neural style transfer using PyTorch. Neural Style transfer is an optimization technique used to take a content and a style image and blend them together so the output image looks like the content image but painted in the style of the style image. We will create artistic style image using content and given style image. We will compute the content and style loss function. We will minimize this loss function using optimization techniques to get an artistic style image that retains content features and style features.
- At the end of this implementation you will be able to generate images from this:

![content6](https://github.com/Shifu34/Deep-Learning-with-PyTorch-Neural-Style-Transfer/assets/140503589/e3b71436-be2a-4a3b-97b7-5cdbaf214cce)

- To this:
  
![output1](https://github.com/Shifu34/Deep-Learning-with-PyTorch-Neural-Style-Transfer/assets/140503589/373f963b-6d92-4cef-ac86-c094a154ebc4)

![output2](https://github.com/Shifu34/Deep-Learning-with-PyTorch-Neural-Style-Transfer/assets/140503589/60de41f4-e7b5-440f-a871-2f07bd18bbae)

- This is divided into seven steps:
  1. Setup the enviroment
  2. Loading VGG pertrained model
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
