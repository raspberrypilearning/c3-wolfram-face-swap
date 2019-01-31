## Making the Face Swap Look Better

There are three things we can do to make the face swap look better:
+ swap the sizes of the `faceImage`s, so that they fit into the other head more cleanly
+ reflect the face images, so that they're looking in the same direction as the original face
+ fade the edges of the face images, so that they blend into the background image

First, let's swap the sizes of the images.

To swap the sizes, we need to use two new functions: `ImageDimensions`, which gives us the size of the image, and `ImageResize`, which resizes the image to specific dimensions.

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

We can now use `ImageResize` to change the size of each image.
`ImageResize` takes two arguments: the image we want to resize, and the dimensions we want the image to be.

---task---

Use `ImageResize` to change the size of each image in the list `faceImages` to the size of the other image in the list.

```
ImageResize[faceImages[[1]], ImageDimensions[faceImages[[2]]]]
```
```
ImageResize[faceImages[[2]], ImageDimensions[faceImages[[1]]]]
```

---/task---

Now that we know how to swap the sizes of the images, we can use `ImageReflect` to change the direction that the face is turned. We can reflect both of the images to the left, so that they're facing opposite directions.

`ImageReflect` takes two arguments: the image that we want to reflect, and the direction we want to reflect it in.

--- task---
Change the direction that the face is turned using `ImageReflect`.

Within the code for `ImageReflect`, instead of reflecting the image directly from the list `faceImages`, include your code for changing size. This will make the code swap the size, and reflect the image, at the same time.

```
ImageReflect[ImageResize[faceImages[[1]], ImageDimensions[faceImages[[2]]]], Left]
```
```
ImageReflect[ImageResize[faceImages[[2]], ImageDimensions[faceImages[[1]]]], Left]

```
---/task ---

We also want to blur the edges of the face images, so that they don't have hard borders with the background image.

We can do this by using the function `ImageEffect`, and the specification `"FadedFrame"`. We want to blur out the outer 1/4 of the image, so that it blends nicely, so we specify that we want `"Faded Frame"` to be `Scaled[1/4]`.

`ImageEffect` takes two arguments, the image we want to change, and the way we want to change it. We can use a list, `{}`, to specify exactly what we want `ImageEffect` to do.

--- task ---
Blur the outer 1/4 of the image using `ImageEffect`, with the specification `"FadedFrame"`.

Within the code for `ImageEffect`, include your previous code for `ImageReflect` and `ImageResize` This will make the code blur the frame, swap the size, and reflect the image, all at the same time.

Assign the edited versions of the faces to the variable names `newFace1`, and `newFace2`.

```
newFace1 = ImageEffect[ImageReflect[ImageResize[faceImages[[1]], ImageDimensions[faceImages[[2]]]], Left], {"FadedFrame", Scaled[1/4]}]
```
```
newFace2 = ImageEffect[ImageReflect[ImageResize[faceImages[[2]], ImageDimensions[faceImages[[1]]]], Left], {"FadedFrame", Scaled[1/4]}]

```

Once you have looked at your output to check that it does what you are expecting, put a `;` after the line of code, to supress the output, so that you don't get a print out of the new images every time you run the code.
---/task ---