*************
Architecture
*************
![unnamed](https://github.com/user-attachments/assets/aa178e76-9c54-4416-a374-41d654edec40)
*************
*************

Preprocessing 
=========
First of all preprocessing are programme with two multiple languages but not have connected together C++ and Python. C++ are work for preprocessing to create commad to execute and create pixels forders and in that given dataset have multiple folders for multiple objects so same to same in C++ And Python also C++ create commad with dataset path and python will create pixels folder in current directory and make .txt file of multiple objects in count of limit and stores the normalized pixels in that.
Now Let's How to create pixels folder that collection of given dataset multiple object images pixels to normalized and create txt files.
**************************
Selecting Dataset
![Screenshot 2025-06-08 021930](https://github.com/user-attachments/assets/3491308b-1e83-4c86-8adf-3ed6c9318e85)
**************************

After Press Ok The Programme Will show the message that created the folder.

**************************
**************************
How It's Look After Preprocessing
![Screenshot 2025-06-08 022604](https://github.com/user-attachments/assets/f8476abd-d34e-4c87-9b26-ebc3e6cd7c11)
**************************
Now as you can see we have created the pixels folder and cretes .txt file that have image normalized pixels.

**************************
**************************
Why 6 Line
![image](https://github.com/user-attachments/assets/3feba4f0-2cfb-4e53-bd65-f50a1ce77ccf)
**************************

As you can you seen the down side of my pixels folder image that are 6 line there means what? when i give path dataset in that two folders have 5 images in each. So my progamme will one poxels in one with heigth * widths  = one_line eg. 64 * 64 = 4096 without ",".

Preprocessing I have already developed separatly This Link 🔗 https://github.com/AlwaysDhruv/Image_Preprocessing
**************************
**************************
One Hot Encoding

![alt text](image.png)
**************************

The Given Image i have used member() of preprocess class by using pre objetc. I have give Two arguments first labels that in stores the one hot values in double dimentional vector. Labels are type of true output that are used optimiza loss and make the suitbale weigths and biases value to predict the output using gradients and decents method.

**************************
How it's look

![alt text](image-1.png)

Here you can see the 2x2 matrix are there and why it's 2x2 or how it's develop? When we are preprocessing you have watched the we have give the dataset folder to the model and in that dataset have two folders that defines two objects. so when the first folder will came out for one values with their folder name so programme will give one hot value like [1 0]. why 1 are first because there first folder are came output and when second folder will cam out so one value like that [0 1] and size one value 2 why bacause there are two objects.

[1 0] folder1
[0 1] folder2

**************************
**************************

Weights Biases
==============
Now will talk about weigths and biases whet is this? This one type value are suitable for predict the given input after training and so optimization using gradients decents method.

**************************
Convoluational Parameters

![image-3](https://github.com/user-attachments/assets/d41ec49a-b0da-429d-a1b3-72040980037f)

Here you can see i have used values member function of Kernal class using kenral objetc. In that methos i have six arguments first convo_weigths for weigths, convo_bias for bias, 5, 5 for filter dimention, 1 for input channel means image are grayscale there are only one layer pixels are there. for eg when it's come to the RGB stands for red, green and blue so in image there three layer of pixels are there. and last 2 means 5x5 filter will genrate 2 menas 5x5x2 = 25,2 = 50 value for weigths. For bias 2 value will genrated why becaue each filter have sum with one bias value so filter.size() == bias.size().

**************************
How It's Look

![image-4](https://github.com/user-attachments/assets/0a954d1b-9a2c-41d1-9830-9e134086fae2)

Here you can see 5x5 kenal are there 2. bias are 2. In That one image will make it two different value of two image using filter.

**************************

**************************
Source Code

![alt text](image-7.png)

**************************
**************************

Convoluationl Operation
==============

Now the topic are came out Convolluationl are working for extract the features from images using filters.

**************************

1.Convoluation Operation

Formula

![alt text](unnamed.png)

Source Code

![alt text](image-5.png)

flatten the values for fully conneted layer for eg. 64x64 image are their. so filter shape are 5x5x2 for convolution the output shape
are 64 - 5 + 1 = 60 for column and 64 - 5 + 1 = 60 so convoluation output will generate 60x60x2 there are 2 filter are their that's why.

1.1 Relu activation()

Formula

![alt text](Relu-activation-function.png)

Source Code

![alt text](image-8.png)

Relu Are used for raplace negative value to zero for not will generate infinity.

**************************

2. Max Pooling

Formula

![alt text](MaxpoolSample2.png)

Source Code

![alt text](image-6.png)

after maxpooling 2x2 maxpooling and stride are 2. In that what is the stride? stride are type value that define how many pixels value move 
after in convoluation output. 60x60x2 when we apply 2x2 max pooling and stride = 2 so output will generate 30x30x2.

**************************

3. Flatten

Style

![alt text](73_blog_image_1.png)

For Source Code i have apply single dimention vector for flattening.

**************************
Here Fully Explanation

[alt text](cnn-digit-2.jpg)

**************************
**************************
