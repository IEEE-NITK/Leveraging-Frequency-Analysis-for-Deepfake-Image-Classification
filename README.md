<h1 align="center">
DeepFake Image Recognition
</h1>
The project entails two main objectives: to understand the entire architecture of the underlying neural network, and to implement web application for distinguish Deepfake images.

## INTRODUCTION 
Deep fake technology has gained significant attention in recent years due to its potential to generate highly realistic counterfeit images and videos, raising concerns about the integrity of visual media. Addressing the challenge of detecting deep fake images is crucial to ensure trustworthiness in various domains, including journalism, forensics, and social media platforms. This project aims to explore the effectiveness of frequency analysis techniques and deep learning for deep fake image recognition, offering a comprehensive study to enhance the reliability of detection methods.

The project utilizes a  frequency analysis technique DCT, to extract spectral features that capture unique characteristics of deep fake images. These features are then used to train deep learning models, enhancing their ability to accurately classify deep fake images. We also aim to build a frontend web app which identifies a deep fake image and if possible where one can upload an image and it will classify the image as deep fake or real. We use Gradio for the frontend display of the web-app. By empowering users to detect deep fake images and promoting transparency, the project contributes to combating the harmful effects of deepfakes and fostering a more trustworthy digital media environment.


## TECHNOLOGIES USED
[![Tech_Used](https://skills.thijs.gg/icons?i=py,tensorflow&theme=dark)](https://skills.thijs.gg)

## ARCHITECTURE
<img width="500" alt="stylegan_architecture" src="https://github.com/shahcharu/DeepFake_Image_Recognition/assets/147295457/5ccdfb90-148a-40ce-a8e0-74ad590f0d34">

<br><br>
The AdaIN layer is normalizing the statistics of inputs and outputs to the convolution layer, and feeding the statistics of the style input. This way we can keep the information of x while transforming the distribution of the output of AdaIN to be similar to the style input.
<br><br>
![images_chrishongzzang_post_dcae114b-cde5-4763-9406-f8f14ac2193b_stylegan2](https://github.com/shahcharu/DeepFake_Image_Recognition/assets/147295457/442b38eb-8817-442b-936b-ff25b6686938)
<br><br>

The synthesis network uses a progressive GAN structure as its backbone, where the network grows from low resolution to high resolution as training continues.
Noise is given as an input to each synthesis block in order to capture variational details and thus rendering the image to be seen more realistic. The input latent vector  characterizes important features such as gender, ethnicity and hairstyle. This leads to more controllability of the input style vector.
Style mixing in StyleGAN involves interpolating the latent code vectors (Z vectors) of two input images at specific layers in the network. By blending the style vectors (W vectors) of these images, it allows for the synthesis of new images that exhibit a combination of visual attributes from both source images, effectively influencing the appearance of generated outputs at different hierarchical levels within the network.
<br><br>

We transform images into the frequency domain using the discrete cosine transform (DCT). The DCT expresses, much like the discrete Fourier transform (DFT), a finite sequence of data points as a sum of cosine functions oscillating at different frequencies. In practice, we compute the 2D-DCT as a product of two 1D-DCTs, i.e. for images we first compute a DCT along the columns and then a DCT along the rows. When we plot the DCT spectrum, we depict the DCT coefficients as a heatmap. To classify the images based on their frequency domain counterparts, we use a simple linear classifier. To demonstrate this, we perform a ridge regression on real and generated images, after applying a DCT. We also perform a ridge regression on the original images without any transformations for comparative analysis. We use a ridge classifier for the classification which is a modification of linear regression where regularization, specifically L2 regularization, is applied to the coefficients. 
<br><br>


![image_999](https://github.com/shahcharu/DeepFake_Image_Recognition/assets/53830790/b379fc36-59c9-41d7-ae37-5f4924a4232b)
![image_998](https://github.com/shahcharu/DeepFake_Image_Recognition/assets/53830790/abb18fc7-9d33-4629-8e4c-7fe152f1030e)
![image_995](https://github.com/shahcharu/DeepFake_Image_Recognition/assets/53830790/67de681a-a86e-49f0-908b-c5986d287598)
![image_994](https://github.com/shahcharu/DeepFake_Image_Recognition/assets/53830790/d9d43235-eadb-4604-be3a-1b5441c69b72)
![image_993](https://github.com/shahcharu/DeepFake_Image_Recognition/assets/53830790/123924e0-d4a8-49ca-a205-2346fe9fa66f)


# Dataset
FFHQ-dataset has been used for real images. Fake images have been generated via the use of StyleGAN

# Performance and Results
## DCT Performance
<img src="https://github.com/shahcharu/DeepFake_Image_Recognition/assets/147295457/19b81c66-40f8-49ae-9f67-89186508abfd" alt="DCT" height="300">

## Standard Performance
<img src="https://github.com/shahcharu/DeepFake_Image_Recognition/assets/147295457/e399220f-6624-4c1c-a8fe-78df8da20823" alt ="PIXEL" height="300">
<br><br>

Accuracy of DCT of Image: 1.0

Accuracy of Standard Image: 0.547


A large improvement in detection of deepfake images is noticed when taking the DCT of images compared to normal images as input to a ridge classifier. DCT is able to pickup on artifacts present in deepfake images generated by the STYLEGAN.
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
