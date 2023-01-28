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









