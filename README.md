# Image_processing
Image processing with OpenCV using python

this is about how to detect faces and i am 

using OpenCV with Python to detect one or more faces from an image.

So basically how does face detection works anyway? Well the idea is that

someone has created some Cascades which are basically some XML files such as

this one(which i used) for more you can check this link 

https://github.com/opencv/opencv/tree/master/data/haarcascades

and this XML file contains the information about the features that an

image of a face contains, so we're talking about a ratio of the shadows

of the eyes, and nose, and lips, and all these features, these pixel intensity

numbers are stored are recorded in this XML file which has been created by using

some images with faces as training samples. So basically you tell your

computer's ok these are, all these are faces and then you use software like

open CV to create such XML files. So these are called haarcascades and this

is the haarcascade for a frontal face object, and if you want other objects you

can find them in this link here so you've got full body and left eye

and lower body and so on. Alternatively you can use the resource file here in this repository

we'll be using this cascade to detect faces. The way it works now is that

we'll load the image in Python and then we will tell Python that this is a model

that you want to look for in the image and you want to find this model, so the

xml model in the image and what Python will do with it with the help of OpenCV,

it will start to search all the image using a window and then it will resize the image,

so it will decrease the image size and using the same window to detect for

for smaller faces and so on.  we have a

method called Cascade Classifier, so this will create a face cascade object

in Python and all we have to pass here is the path or the haarcascade.

And that will create a cascade classifier object, and now you can use

this cascade classifier object of the face feature to search for a face in your

image  we will load the image using imread method. a good idea is to use grayscale images

when searching for a face so I loaded the image here, but I'll be using the

grayscale version of the image when searching for a face in that image. That is

thought to produce high accuracy when were searching for faces because you know you

may notice that when you have very busy images with lots of features

OpenCV will not be 100 percent accurate so you may get faces that

OpenCV will miss out or you may get features that will be classified as faces.

Using the greyscale image though increases accuracy.

And now we will use a method called detect multiscale and what this method

will do it will search for the cascade classifier so it will search for this

frontal face XML file in our image and it will return the coordinates of the

face in the image so for instance this is the image and what this method will

return is it will find the face and it'll say, so it will give you the number

of the row and the column of the upper left point of the face, so it will start

here and it will also give you the height of the face and the width of the face,

so we'd get a rectangle and then we would draw that rectangle in the image so

that's basically it.

What Python will do is that it will start from the original size of the

image and it will search it will create a window that will search for faces in

the image, so searching this area in this area in this area, and so once it does

that, then by giving a scale factor of one point zero five you're telling

Python to decrease the scale by five percent for the next face search.

So what Python will do is it will down scale the image by five percent and it

will search for bigger faces in the image so search again, search again and

then decrease it by five percent again the image and search for bigger faces

and so on until it goes to a final size. So that means a smaller value means

higher accuracy. If you give for example point five Python would decrease the

scale by 50 percent, so it will start from the original size and then it will

go 50 percent higher, and so you don't get much accuracy with that. The profit

with this number is the script will run quicker, so you'll have less passes to

the image for searching for a face. Zero point five is good, okay, and then you

have another parameter called minimum neighbors and that is usually set to

five and what this basically is, is that this tells Python how many neighbors to

search around the window, so you may want to experiment with these numbers

a little bit and see which gets the better result, but these two

are well accepted numbers. So let's do something now. Let's print

out faces and see what this is about, so what kinds of what kind of object this is.

And I could also print the type for faces, just like that. So I'll run the script

now and what the script will do is it will it will read this XML file and it will

load the image it will make the grayscale version of the of image and

then it will detect the coordinates of upper left corner of the face in the

image and the width and the height of the rectangle defining the face in the image.

And then it will print out the type of the faces and it would print the faces,

the actual faces object. So okay, press any key to exit this and so faces

is a Numpy array, a N dimensional array object and it is an array with four

values, so we have detected our face and these are the values basically defining

the face in in the image, so basically what we have here is, so this is 155

which would be the 155th column so this is the X, so the rectangle

should start somewhere here in the forehead and this should be 83, so row 83,

column 155, and then we have the width which is 382 and the height which is the same.

And so we have a rectangle in face. Now let's go ahead and draw that

rectangle in face, in the image, so we create the faces array and then what you

want to do is access all these values of this array. To do that we can use a

for loop, so for X Y width and height in faces.
