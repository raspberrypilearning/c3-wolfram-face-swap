## Basic face swap

The `ImageCompose` function layers different images. Here, you can use the original image as the background and place the faces on top, in their new positions.

`ImageCompose` takes three arguments:
1. The background image
1. A list of images to place on top of the background
1. A list of position coordinates that determine where each new image goes

If you put the background image, `i`, and the images of the faces, `faceImages`, into `ImageCompose`, the function places the two images right in the middle of the background.

![ImageCompose](images/imagecompose2.png)

You need to use the `"Position"` data to tell `ImageCompose` where to place the images. The first face should be placed at the location of the second face, and the second face should be pplaced  at the location of the first face.

So `ImageCompose` can do this, you need to fill in this information:

```
ImageCompose[i, {first face, second face}, {new position for first face, new position for second face}]
```

+ The new position of the first face is the original position of the second face
+ The new position of the second face is the original position of the first face.

To get this information from the lists `faceImages` and `facePositions`, you need to access specific items in the lists.

You access a specific item in a list by using `[[]]`. For example, to access the first item in a list, you use `list[[1]]`:

![Parts of Lists](images/listpart.png)

---task---

Use `ImageCompose`, `faceImages`, and `facePositions` to swap the positions of the faces in the image `i`.

--- hints ---
--- hint ---
Remember that `ImageCompose` needs the images as well the positions at which to place the images.

```
ImageCompose[i, {first face, second face}, {new position for first face, new position for second face}]
```
--- /hint ---
--- hint ---
You need to reverse the positions of the images.:
+ Take the first image and place it in the position of the second image
+ Take the second image and place it in the position of the first image

--- /hint ---
--- hint ---
This is the code you need:

```
ImageCompose[i, {faceImages[[1]], faceImages[[2]]}, {facePositions[[2]], facePositions[[1]]}]
```
--- /hint ---
--- /hints ---

![basic swap](images/basicswap2.png)
---/task---
