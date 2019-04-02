## Find faces

--- task ---
If you have never used the Wolfram Language before, follow [this guide to get started](https://projects.raspberrypi.org/en/projects/getting-started-with-mathematica) and learn to use the tool. Look at the sections **Starting Mathematica** and **Programming in Mathematica**.
--- /task ---

To start, you will use built-in functions of the Wolfram Language to:
+ Find faces in an image
+ Find information about these faces, e.g. their size and position

You can work with any image of two people facing the camera. Ideally, the faces should be about the same distance from the camera.

Here is an image you can use:

![original image](images/startingimage2.png)

--- task ---

Drag and drop the image into your notebook.

Assign it the variable name `i`. Put a `;` at the end of the line of code. Doing this suppresses the output, so you don't get a print-out of the image every time you run your code.

![assign image to variable i](images/iequals2.png)

--- /task ---

The function `FindFaces` detects faces in images.

You specify a property of the `FindFaces` function to determine what the output of `FindFaces` is.

`FindFaces` always returns a list of faces it finds in a photo.

--- task ---

Use `FindFaces` to find the `"Image"` of the faces in the photo.

Assign the `"Image"` list to the variable name `faceImages`.

```
faceImages = FindFaces[i, "Image"]
```

Check the output of this code to make sure it does what you expect.

Then put a `;` at the end of the line of code to suppress the output.

--- /task ---

You also need to know where exactly in the photo the faces are. Using `FindFaces` with the property `"Position"`returns a list of the coordinates of each face in the photo.

--- task ---

Use `FindFaces` to find the `"Position"` of the faces in the photo.

Assign the `"Position"` list to the variable name `facePositions`.

```
facePositions = FindFaces[i, "Position"]
```

Check the output of this code to make sure it does what you expect.

Then put a `;` at the end of the line of code to suppress the output.
---/task---




