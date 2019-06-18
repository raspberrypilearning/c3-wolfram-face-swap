## Make the face swap look better

There are three things you can do to make the face swap look better:
+ Swap the sizes of the `faceImage`s so they fit better
+ Reflect the `faceImage`s so they're looking in the same direction as the original face
+ Fade the edges of the `faceImage`s so they blend into the background image

First, swap the sizes of the images.

To do this, you need two new functions:
1. `ImageDimensions`, which gives you the size of the image
1. `ImageResize`, which resizes the image to specific dimensions

--- task ---
Find the size of each image in the list `faceImages`.

```
faceImages[[1]]
ImageDimensions[faceImages[[1]]]
```

```
faceImages[[2]]
ImageDimensions[faceImages[[2]]]
```
---/task ---

Now use `ImageResize` to change the size of each image.

`ImageResize` takes two arguments:
1. The image to resize
1. The dimensions you want the image to be

---task---
Use `ImageResize` to change the size of each image to the size of the other image.

--- hints ---
--- hint ---
Your images are stored in `faceImages`, and your image dimensions are stored inthe new `ImageDimensions` list.
--- /hint ---
--- hint ---
You need to use the `ImageResize` function twice.
--- /hint ---
--- hint ---
Here's the code to resize the images:
```
ImageResize[faceImages[[1]], ImageDimensions[faceImages[[2]]]]
ImageResize[faceImages[[2]], ImageDimensions[faceImages[[1]]]]
```
--- /hint ---
--- /hints ---
---/task---

Now you know how to swap the sizes of the images. Next, use `ImageReflect` to change the direction that the face is turned. Reflect both of the images to the left, so that they're facing the opposite direction.

`ImageReflect` takes two arguments:
1. The image you want to reflect
1. The direction you want to reflect it in

--- task---
Change the direction that the face is turned using `ImageReflect`.

Within the code for `ImageReflect`, include your code for changing the image size. This makes the code change the image's size and reflect the image at the same time.

```
ImageReflect[ImageResize[faceImages[[1]], ImageDimensions[faceImages[[2]]], Left]
```
```
ImageReflect[ImageResize[faceImages[[2]], ImageDimensions[faceImages[[1]]], Left]

```
---/task ---

Finally, blur the edges of the face images to remove the borders between the images and the background.

You do this by using the function `ImageEffect` with the specification `"FadedFrame"`. You need to blur the outer 1/4 of the image so it blends enough, so specify`"FadedFrame"` to be `Scaled[1/4]`.

`ImageEffect` takes two arguments:
1. Ihe image you want to change
1. The way in which you want to change the image

Use a list, `{}`, to specify exactly what you want `ImageEffect` to do.

--- task ---
Blur the outer 1/4 of the image using `ImageEffect` with the specification `"FadedFrame"`.

+ Within the code for `ImageEffect`, include your code for `ImageReflect` and `ImageResize`. This makes the program blur the image, change its size, and reflect it, all at the same time.
+ Assign the edited versions of the faces to the variable names `newFace1`, and `newFace2`.

You can use this code:

```
newFace1 = ImageEffect[ImageReflect[ImageResize[faceImages[[1]], ImageDimensions[faceImages[[2]]], Left], {"FadedFrame", Scaled[1/4]}]
```
```
newFace2 = ImageEffect[ImageReflect[ImageResize[faceImages[[2]], ImageDimensions[faceImages[[1]]], Left], {"FadedFrame", Scaled[1/4]}]

```

Check the output of this code to make sure it does what you expect.

Then put a `;` at the end of the line of code to suppress the output.
---/task ---