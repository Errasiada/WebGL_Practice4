# WebGL_Practice4

In this practice we will add a texture to our WebGL project. Before that, we have to modify some parameters in our project to make it work. First of all, deleting or commenting the Blazor.Expansion.Canvas, install Node.js and .Net v.6.0.

After following the tutorial and downloading the blazor canvas extension, we duplicate package.json with a new name. Inside we modify the code and we install different npm extensions because the dotnet build will generate many errors. If we followed the steps, the terminal should look like this after building.

![image](https://user-images.githubusercontent.com/114673717/215258419-ad4b88c3-1b82-4034-a230-0792b41222dd.png)

After that, check WebGLContext.cs line 407, and add some changes to those methods. Add an int border in TexImage2D. Then, dotnet build.

![image](https://user-images.githubusercontent.com/114673717/215259081-33f120da-d9a5-431c-aebe-485b46f5e8ce.png)

We can use it for our project, but first add the SixLabors.ImageSharp package.

![image](https://user-images.githubusercontent.com/114673717/215259440-3bdf0c39-5efa-4f2c-b74f-b9fd14bfa5fb.png)

Now in SimpleGame.cs reference the route for the blazor canvas correction. In my case, as seen below.

![image](https://user-images.githubusercontent.com/114673717/215259750-836a6800-b3fe-4a48-84a6-93f4520d8efd.png)

Now everything should work if you dotnet clean > dotnet build > dotnet run.

After finishing the tutorial we can start working on our base project. As we have to implement a shooting system, we have to add the controller's movement from the previous activities in the Controller.razor.cs. In my case looks like this:

![image](https://user-images.githubusercontent.com/114673717/215260785-374e7895-8125-445c-b5b6-8e500f32abcc.png)

![image](https://user-images.githubusercontent.com/114673717/215260815-3ade68cf-1c4a-4c52-9069-8ca427cee6ab.png)

To add the texture let's modify in assets folder the level.json adding the texture we want to use to the texture list.

![image](https://user-images.githubusercontent.com/114673717/215261888-47efc06a-bb25-4ff5-827e-f70d63188105.png)

To add the repeated texture to the floor, the prepareBuffers were modify between BindBufferAsync and BufferDataAsync

![image](https://user-images.githubusercontent.com/114673717/215262072-91b84bfa-0c8c-40fc-a11e-aa923590a2dd.png)

These are the modifications we apply in Game.razor.cs:

![image](https://user-images.githubusercontent.com/114673717/215265245-4a2f433b-5422-4ab5-afc8-7857be5097bf.png)

![image](https://user-images.githubusercontent.com/114673717/215265268-0fdeac30-e0da-4358-aec3-c90901d7e139.png)

![image](https://user-images.githubusercontent.com/114673717/215265272-66fdfc94-10e7-4f87-a136-5ce571f2f94f.png)

If we compile, we will get an error, that's because the library changed and we need to modify the method setTexture in Level.cs class. Here is how it looks:

![image](https://user-images.githubusercontent.com/114673717/215265344-c4875d9b-712b-4d1c-8d36-a172e883b79b.png)

Applying textures to the pawn, cubes and floor.

![image](https://user-images.githubusercontent.com/114673717/215266181-dd4a41a7-5afe-4178-a95c-f1198ff45acd.png)

![image](https://user-images.githubusercontent.com/114673717/215266186-8a377c03-0db5-4b00-bc4a-72b0cd14ad24.png)

![image](https://user-images.githubusercontent.com/114673717/215266189-1db8cf40-7455-4129-af83-b9ed94eec5ee.png)














