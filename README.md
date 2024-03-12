Gideion Prabhudas

March 22, 2023

<br>

# <strong>Lab 4 - .NET Core MVC</strong>

<br>

# Executive Summary
I learned how to use .NET Core MVC to create and organize models, views, and controllers, as well as how to handle user input and send responses back to the user. I learned the importance of securing my application and protecting against cross-site scripting attacks. I used various tools such as Entity Framework Core and MongoDb to store data efficiently. I also learned how to use google authentication during login process.

<br>

# Design Overview

### UML of Crud Operation using .NET Core MVC
![UML Diagram](UML%204.jpg)


### Controller Folder
## `_TaskController.cs`
Contanins all the components of Crud Function to interacts with the model and view 

## `HomeController.cs`
Contains action to send back to a user when a user makes a browser request

#### Data Folder
## `TaskDao.cs`
Contains Functions to connect and store Data of the CRUD to the database 

## `AtlasSettings.cs`
Contains getter and setters of the collections, Database,ConnectionString

## `MongoDbContext.cs`
Contains functions to connect to the Atlas DB

### Models
## `_Task.cs`
Contains Getters and setters to set Id, UserId, Text, Done, Date 

### Views
## `Create.cshtml`
Shows the user how the tasks in created from inputting text, date and so on
## `Delete.cshtml`
Shows the user how the delete function is displayed

## `Details.cshtml`
Show all the details of the page

## `Edit.cshtml`
Shows the user when an Update is made

## `Index.cshtml`
Contains the users view of the todo-page

## `_Layout.cshtml`
shows the user the layout of the page

 
## `appsettings.jscon`
Contains the default connection query and the Atlas Db and collection name

## `Startup.cs`
contains the functions of google authentication and connection to the Atlas Db


## `Screenshots`
### Login Page to register, login and use google as a login method
![Login page](Screenshot-Login%20and%20Google%20sigin%20option.png)

### Welcome Page after Logged in
![Logged in page](Screenshot-Welcome%20page.png)

### Todo list of task
![task view](Screenshot-Todo%20list%20view.png)


<br>

# Questions

### 4a Question 1: In the context of MongoDB compared to SQL databases, what's a Document? What's a Collection?
>* In the context of MongoDB, a document is a basic unit of data storage that contains all the information and attributes of an entity in a JSON-like format. It can be compared to a row in a SQL database table. A document is essentially a set of key-value pairs where each key represents an attribute of the entity, and the value can be of various types including strings, numbers, Booleans, arrays, or other embedded documents.
One of the main benefits of using documents in MongoDB is that they are schema-less, meaning that they do not require a predefined structure or schema like a SQL database. This allows for more flexibility and dynamic data modeling.

>* A collection, on the other hand, is a group of related documents that are stored together in MongoDB, similar to a table in a SQL database. Collections can be thought of as containers for documents, and they allow for easy management and organization of related data. Each document in a collection can have its own unique structure and fields, making collections a powerful tool for storing and querying dynamic and evolving data.

It's important to note that MongoDB is a NoSQL database, which means it doesn't rely on the traditional tabular structure used by SQL databases. Instead, MongoDB uses collections of documents to store data in a more flexible and scalable way.

### 4a Question 2: When you log in with Google, where is the hash of your password stored? Your app, Google, or both??
> When you log in with Google, your password is not stored in the traditional sense. Instead of using a password, Google uses a system called OAuth, which allows users to authenticate themselves to third-party applications without sharing their passwords. When you log in with Google, you are redirected to the Google login page, where you enter your Google email address and password. Once you have successfully authenticated yourself to Google, the Google server generates a unique access token, which is then passed back to the third-party application. This access token is what the third-party application uses to access your Google account on your behalf. The access token is stored securely by the third-party application, typically in a database or server-side session, to allow you to stay logged in and access authorized resources on the application. The access token is not the hash of your password, and it cannot be used to gain access to your Google account directly. Instead, it is a secure token that allows the third-party application to access your Google account on your behalf.
In summary, when you log in with Google, your password is not stored in your app or by Google. Instead, a secure access token is generated and stored by your app, allowing you to stay logged in and access authorized resources on the application without sharing your password.

### 4a Question 3: What's the difference between using Cloud services to store data (like Atlas) and storing data locally with something like MySQL? List 2 benefits of each approach.
>* The main difference between using cloud services like MongoDB Atlas and storing data locally with something like MySQL is the location of the data storage. Cloud services store data on remote servers, while local databases store data on the machine where the database software is installed. 
>* Cloud services offer advantages such as scalability, flexibility, and accessibility from anywhere with an internet connection. Local databases offer advantages such as increased control and security over data, lower cost, and faster response times for certain types of applications.

## Benefits of using cloud services:
>* Scalability: Cloud services like MongoDB Atlas are typically more scalable than local databases like MySQL. With cloud services, you can easily add or remove resources as needed to accommodate changes in data volume or application usage. On the other hand, scaling a local database can be more challenging, as it often requires purchasing additional hardware and configuring it to work with the existing database.
>* Accessibility: Cloud services like Atlas are accessible from anywhere with an internet connection, making it easy to access your data and manage your application from anywhere in the world

## Benefits of using local databases:
>* Data control: Storing data locally with something like MySQL gives you more control over your data. You have full control over where your data is stored, how it is managed, and how it is backed up.
>* Performance: Local databases can offer faster performance than cloud services, as they are not subject to network latency or other factors that can impact data access speeds in a cloud environment.

### 4a Question 4: List 3 core features of fully-fledged IDE's like Visual Studio that give them an advantage over text-editors like Sublime or VSCode.
>* Integrated Debugging: One of the key features of an IDE is the ability to debug code directly within the editor. This includes features such as setting breakpoints, examining variable values, and stepping through code. Fully-fledged IDEs like Visual Studio have powerful debugging tools that make it easier to identify and fix issues in code.
>* Code Generation: IDEs can generate code automatically, such as creating class templates, methods, and constructors. This can save developers time and effort by reducing the amount of boilerplate code they need to write. Additionally, some IDEs have code completion features that can suggest code based on the context in which it's being used, which can help reduce errors and improve code quality.
>* Built-in Refactoring: IDEs offer built-in refactoring tools that can help developers quickly and easily modify their code to improve its structure, readability, and maintainability. These tools can automate tasks like renaming variables, methods, and classes, extracting methods, and changing the signature of a method.

### 4b Question 1: What is the role of a Model?
> In the context of .NET Core MVC, the Model is responsible for representing the data and business logic of the application. The Model is the layer that interacts with the database or any other data source to retrieve, manipulate, and persist data. The primary role of a Model in .NET Core MVC is to define the structure and behavior of the data that an application will work with. This includes defining the properties and methods of the data, as well as any validation or data manipulation logic that is needed. In .NET Core MVC, Models are typically defined as classes that encapsulate the data and business logic of an application. These classes are then used by Controllers to interact with the data and pass it to Views for display to the user.

### 4b Question 2: What is the role of a View?
> A View is responsible for rendering the user interface and displaying the data to the user.In MVC architecture, the View is the component that interacts with the end-user, and it presents the data in a format that is easily understandable by the user. It receives the data from the Controller, processes it and then presents it in a user-friendly way.The View is typically an HTML template that uses a templating language, such as Razor, to dynamically generate HTML content based on the data received from the Controller. The View can also include client-side scripting, such as JavaScript, to add interactivity to the user interface.
In summary, the View plays an important role in separating the presentation logic from the business logic in an application, and it is responsible for rendering the data to the end-user.

### 4b Question 3: What is the role of a Controller?
> A Controller is responsible for receiving requests from the View, processing them, and returning a response to the View. The Controller is the component that sits between the View and the Model, and it is responsible for handling user input, managing the flow of data between the View and the Model, and performing any necessary operations, such as data validation, authentication, and authorization. When a user interacts with the View, for example by clicking a button or submitting a form, the View sends a request to the Controller, which then retrieves the necessary data from the Model and returns it to the View for rendering. The Controller typically contains a set of actions, or methods, that correspond to different requests from the View. These actions are responsible for performing the necessary processing and returning a response to the View.

### 4b Question 4: List 3 pros and 3 cons of hosting your website on the cloud.

## Pros:
>* Scalability: Cloud hosting allows you to easily scale up or down the resources required by your website. You can add more server capacity or storage space as your traffic grows, or scale down when traffic decreases. This flexibility ensures that your website can handle fluctuations in traffic and demand.
>* Reliability: Cloud hosting providers typically offer high levels of uptime and availability, as they have redundant systems in place to ensure that your website stays online even if one server fails. This is important for businesses that rely on their website to generate revenue or serve customers.
>* Cost-effective: Cloud hosting can be more cost-effective than traditional hosting methods, as you only pay for the resources you use. This means that you can avoid the high upfront costs of purchasing and maintaining your own hardware and infrastructure.

## Cons
>* Security: Cloud hosting can be vulnerable to security threats, such as hacking or data breaches, especially if you don't take the necessary precautions. It's important to ensure that your website and data are properly secured, and that you follow best practices for security.
>* Dependency on Internet Connectivity: Hosting your website on the cloud means that your website and its data will be stored on remote servers, which are accessed through the internet. This makes your website's availability dependent on a stable and reliable internet connection. If your internet connection goes down or experiences interruptions, your website may become inaccessible to users, which can lead to a loss of business or damage to your online reputation.
>* Loss of control: When problems arise, companies are powerless to control the outcome and are compelled to transfer this risk and the capacity to fix problems to the cloud provider. Similar to on-site servers, unrestored cloud services or data unavailability can have a detrimental impact on a company's essential operations and customer services.

<br>

# Lessons Learned
## Lesson 1: `connectionString` parameter is null.
The error message "ArgumentNullException: Invalid connection string. (Parameter 'settings')" is thrown when the connection string passed as a parameter to the constructor of MongoDbContext is null or invalid. To fix this issue, ensure that the IAtlasSettings object passed to the TaskDao constructor contains a valid connection string. Check the implementation of the IAtlasSettings interface to ensure that the connection string is properly set.

## Lesson 2: Processing unhandled Exceptions C#
In C#, unhandled exceptions can cause your application to crash or behave unexpectedly. It's important to handle exceptions to make your code more robust and predictable. One way to handle exceptions is to use a try-catch block. This allows you to catch exceptions and handle them gracefully without crashing your application. For example, using `Try` and `Catch` method can help catch unhandled Exceptions and help you Debug your code efficiently. It's important to be specific in the types of exceptions you catch. Catching a general Exception can be convenient, but it can also catch `exceptions` that you're not prepared to handle. For example, catching a `NullReferenceException` might require different handling than catching an `InvalidOperationException`.  

## Lesson 3: Model binding errors (Missing or incorrect parameters) :
In C#, model binding errors occur when there are issues with binding data to a model. Model binding is the process of taking data from an HTTP request and converting it to a C# object that can be used in your application. Model binding requires that the names and types of the properties in the model match the names and types of the form fields or query string parameters in the HTTP request. To troubleshoot this error, check the names and types of the properties in the model and the form fields or query string parameters in the HTTP request. To catch and handle model binding errors in C#, you can use the `ModelState` property of the controller. This property contains a dictionary of validation errors and other information about the model binding process.


<br>

# Conclusions

## Skills Acquired
* I can connect to the MongoDb and store data 
* I can code with C# by creating various functions, classes and implement Crud Operations
* I can use the Debugging tool to identify and fix issues efficiently
* I can use the Google authentication to login users using there google credentials 

<br>

# References
* https://learn.microsoft.com/en-us/aspnet/mvc/overview/security/create-an-aspnet-mvc-5-app-with-facebook-and-google-oauth2-and-openid-sign-on
* https://learn.microsoft.com/en-us/aspnet/core/tutorials/first-mongo-app?view=aspnetcore-7.0&tabs=visual-studio&viewFallbackFrom=aspnetcore-2.2
* https://www.w3schools.com/cs/cs_exceptions.php
* https://learn.microsoft.com/en-us/aspnet/core/tutorials/first-mvc-app/controller-methods-views?view=aspnetcore-3.1