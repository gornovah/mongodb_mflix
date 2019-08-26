# Welcome to M220J  
  
In this course we will be exploring how to use MongoDB in the Java environment.  
We will be looking into:  
  
- Different versions and flavors of the MongoDB Java driver  
- How to express CRUD operations in Java code  
- Using the Aggregation Framework to express analytical queries  
- Building an application backend in Java that interacts with MongoDB  
  
  
#### Get Started  
  
For this course we will be setting up an application, ``MFlix``, that will  
allow users to list and interact with a movies catalog (any similarity with  
other popular video streaming services is pure coincidence!).  
  
In the finished version of the MFlix application, users will be able to:  
  
- Perform movie searches with the following criteria:  
  
  - cast members  
  - genre types  
  - text matches in title or description  
  - country of origin  
  
- Create faceted filters on movie searches  
- Create an account and manage their preferences  
- Leave comments on their favorite (or least favorite) movies  
  
... among other features, typical of any movie streaming service.  
  
Your job, as new team member of the team that builds MFlix, and soon-to-be  
MongoDB Java developer expert, is to implement the backend component, in  
specific the Database Access Object (DAO) layer. No worries, your team has  
already built all the integration and unit tests, you just need to get them all  
to pass!  
  
  
#### Project Structure  
  
MFlix is composed of two main components:  
  
- *Frontend*: All the UI functionality is already implemented for you, which  
  includes the built-in React application that you do not need to worry about.  
  
- *Backend*: *Java Spring Boot* project that provides the necessary service to  
  the application. The code is managed by a Maven project definition file that  
  you will have to load into your Java IDE.  
  
Most of what you will implement is located in the   
`src/main/java/mflix/api/daos` directory, which contains all database  
interfacing methods.  
  
The unit tests in `src/tests/java/mflix/api/daos` will test these database  
access methods directly, without going through the API.  
  
The UI will run these methods as part of the integration tests, and therefore  
they are required for the full application to be running.  
  
The API layer is fully implemented, as is the UI. By default the application  
will run on port 5000, but if you need it to run on a port other than 5000, you  
can edit the `index.html` file in the `build` directory to modify the value of  
**window.host**. You can find ``index.html`` in the  `src/main/resources/build` directory.  
  
We're using *Spring Boot* for the API. Maven will download this library for you.  
More on that below.  
  
  
#### Database Layer  
  
We will be using *MongoDB Atlas*, MongoDB's official Database as a Service (DBaaS),  
so you will not need to manage the database component yourself. However, you will  
still need to install MongoDB locally to access the command line tools that interact  
with Atlas, to load data into MongoDB and potentially do some exploration of  
your database with the shell.  
  
The following set of steps are here to get you setup for this course.  
  
  
#### Local Environment Dependencies  
  
There are two main system dependencies in this course:  
  
1. Java 1.8  
  
 * The java version this course is built against is Java 1.8. You can download  
    the appropriate version for your operating system by clicking  [here](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)  
  
2. Maven  
  
 * We use Maven to manage dependencies for the MFlix project. Click here to  
    download [Maven](https://maven.apache.org/install.html)
  
  
#### Java Project (MFlix) Installation  
  
The `mflix` project is supported by a `Maven` POM file that deals with all the  
dependencies required, as well as providing the `test` and `run` commands  
to control our project. This means that you can run all the tests and deploy  
the `mflix` backend from the command line with `Maven`.  
  
However, we recommend you use a Java IDE to follow along with the lessons and  
to accomplish the **Tickets** assigned to you in the course.  
  
You can use any IDE that you like, as you do not need to have a specific  
product to complete the course.  
It would be better if your IDE supports `Maven POM` files, so it can set the  
dependencies correctly, otherwise you will need to download and install  
manually the different libraries and drivers used by the project.  
  
That said, all the lectures and examples of this course have been produced using  
IntelliJ IDEA CE edition. You will find a lesson dedicated to setting up and  
exploring this IDE for the course.  
  
Once you downloaded and unzipped the `mflix-java.zip` file, you will find the  
project folder. The project folder contains the application code, the  
`pom.xml` file that you would import into your IDE, and the dataset  
required that you will have to import to Atlas. 

    $ ls
    mflix README.rst
    $ cd mflix
    $ ls
    src pom.xml data
  
#### MongoDB Installation  
  
It is recommended to connect *MFlix* with *MongoDB Atlas*, so you do not need to  
have a MongoDB server running on your host machine. The lectures and labs in  
this course will assume that you are using an *Atlas* cluster instead of a local  
instance.  
  
That said, you are still required to have the MongoDB server installed, in order  
to be able to use two server tool dependencies:  
  
- `mongorestore`
  
  - A utility for importing binary data into MongoDB.  
  
- `mongo`
  
  - The shell for exploring data in MongoDB.  
  
To download these command line tools, please visit the  [MongoDB download center](https://www.mongodb.com/download-center#enterprise) and choose the appropriate platform.  
  
  
#### MongoDB Atlas Cluster  
  
*MFlix* uses *MongoDB* to persist all its data.  
  
One of the easiest ways to get up and running with MongoDB is to use *MongoDB Atlas*,  
a hosted and fully-managed database solution.  
  
If you have taken other MongoDB University courses like M001 or M121, you may  
already have an account - feel free to reuse that cluster for this course.  
  
Make sure to use a **free tier cluster** for the application and course.  
  
*Note: Be advised that some of the UI aspects of Atlas may have changed since  
the redaction of this README, therefore some of the screenshots in this file may  
be different from the actual Atlas UI interface.*