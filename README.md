<h1 align="center">
DeepFake Image Recognition
</h1>
The project entails two main objectives: to understand the entire architecture of the underlying neural network, and to implement web application for distinguish Deepfake images.

## INTRODUCTION 
Deep fake technology has gained significant attention in recent years due to its potential to generate highly realistic counterfeit images and videos, raising concerns about the integrity of visual media. Addressing the challenge of detecting deep fake images is crucial to ensure trustworthiness in various domains, including journalism, forensics, and social media platforms. This project aims to explore the effectiveness of frequency analysis techniques and deep learning for deep fake image recognition, offering a comprehensive study to enhance the reliability of detection methods.

The project utilizes a  frequency analysis technique DCT, to extract spectral features that capture unique characteristics of deep fake images. These features are then used to train deep learning models, enhancing their ability to accurately classify deep fake images. We also aim to build a frontend web app which identifies a deep fake image and if possible where one can upload an image and it will classify the image as deep fake or real. We use Gradio for the frontend display of the web-app.By empowering users to detect deep fake images and promoting transparency, the project contributes to combating the harmful effects of deepfakes and fostering a more trustworthy digital media environment.


## TECHNOLOGIES USED
[![Tech_Used](https://skills.thijs.gg/icons?i=py,tensorflow&theme=dark)](https://skills.thijs.gg)

## ARCHITECTURE
<img width="500" alt="stylegan_architecture" src="https://github.com/shahcharu/DeepFake_Image_Recognition/assets/147295457/5ccdfb90-148a-40ce-a8e0-74ad590f0d34">

The AdaIN layer is normalizing the statistics of inputs and outputs to the convolution layer, and feeding the statistics of the style input. This way we can keep the information of x while transforming the distribution of the output of AdaIN to be similar to the style input.
The synthesis network uses progressive gan structure as its backbone, where the network grows from low resolution to high resolution as training continues.


# Dataset
FFHQ-dataset has been used for real images. Fake images have been generated via the use of StyleGAN

# Performance and Results

# References
1. [Reference](https://arxiv.org/pdf/2003.08685.pdf)
2. https://github.com/RUB-SysSec/GANDCTAnalysis

# Project Mentors:
1. [K V Srinanda](https://github.com/srinandakv)
2. [Charu Shah](https://github.com/shahcharu)
3. [Vishal Marwade](https://github.com/vishalMarwade)
   
# Project Mentees:
1. [Aniket Kulkarni](https://github.com/Aniketk047)
2. [Aryan N. Herur](https://github.com/Aryan-Herur)
3. [Jobin Jacob](https://github.com/Jokergif)
4. [Vaibhav Santhosh](https://github.com/pi-0)
