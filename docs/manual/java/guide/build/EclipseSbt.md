# Importing an sbt project into Eclipse

<<<<<<< HEAD
If you worked through the command line example for [[sbt|GettingStartedSbt]], you have an sbt build. The sbt tool provides an [sbt-eclipse](https://github.com/typesafehub/sbteclipse) plugin that generates Eclipse project artifacts, which you can then import into Eclipse.

Follow these steps to integrate your project with Eclipse:

1. Configure sbt to include the Eclipse plugin:
    
    1. In the `project` folder of your sbt build, create an `eclipse.sbt` file. For example, with a project named `hello`, create a `hello/project/eclipse.sbt` file. 
    
    1. Add the following line to the file:
    ```
    addSbtPlugin("com.typesafe.sbteclipse" % "sbteclipse-plugin" % "5.1.0")
    ```
    1. Save the file. 
    
1. In a console, `cd` to the top-level folder, and enter `sbt` to start the build tool.

    Continuing with the example of a `hello` project: 

    ```
    cd hello
    sbt
    ... (booting up)
    >
    ```
    The `>` prompt tells you that sbt is running.

1. Enter `eclipse` to generate the Eclipse project files for all projects in your build:

    ```
    > eclipse
=======
If you used the Giter8 template to create a build as described in the [[Getting Started|GettingStartedSbt]] section, you will have an sbt build project. To make it possible to import the project into Eclipse, sbt provides an [sbt-eclipse](https://github.com/typesafehub/sbteclipse) plugin that generates Eclipse project artifacts for each of the subprojects.

Follow these steps to integrate your project with Eclipse:

1. [Import the project](#Import-the-project)
1. [Create an External Tool Configuration](#Create-an-External-Tool-Configuration)

# Import the project

1. In a console, `cd` to the top-level folder of your existing sbt project, and enter `sbt eclipse` to generate the Eclipse project files for all projects in your build.
    The sbt plugin creates `.project` and `.classpath` files for the subprojects. The last few lines of output confirm success:

    ```
>>>>>>> a1474a71477d58cf6892b18c9947faadb5d81b21
    ...
    [info] Successfully created Eclipse project files for project(s):
    [info] hello-impl
    [info] hello-api
    [info] hello-stream-impl
    [info] hello-stream-api
    [info] lagom-internal-meta-project-service-locator
    [info] lagom-internal-meta-project-cassandra
<<<<<<< HEAD
    >
=======

>>>>>>> a1474a71477d58cf6892b18c9947faadb5d81b21
    ```

1. Start Eclipse and switch to the Workspace you want to use for your Lagom project.

1. From the **File** menu, select **Import**.
<<<<<<< HEAD
   The **Select** screen opens. 

1. Expand **General**, select **Existing Projects into Workspace** and click **Next**.
   The **Import Projects** page opens.
   
1. Click **Browse**, select the top-level project folder, and click **OK**.
    The sub-projects display in the dialog. For example:
    [[EclBrowseToSbt.png]]
1. Click **Finish**.

Your project should be imported and ready to work with.
=======
   The **Select** screen opens.

1. Expand **General**, select **Existing Projects into Workspace** and click **Next**.
   The **Import Projects** page opens.

1. Click **Browse**, select the top-level sbt project folder, and click **OK**.
    The sub-projects display in the dialog. For example:
    [[EclBrowseToSbt.png]]
1. Optionally, select **Copy projects into workspace**.
1. Click **Finish**.

# Create an External Tool Configuration

1. From the Eclipse toolbar, click **External Tools** and select **External Tools Configurations**.
    [[EclExternalConfig.png]]
1. In the left pane, select **Program** and click **New Launch Configuration**.
    [[EclNewLaunch.png]]
1. Create your configuration as follows:
    1. Enter a name.
    1. On the **Main** tab in the **Location** field, enter the location of your sbt installation.
    For Windows, browse to the location where you installed sbt and select `sbt.bat`. On Linux, you can find the location of sbt by opening a terminal and entering `which sbt`.
    1. For **Working Directory** browse to the top-level sbt project folder. (This is the folder containing the `build.sbt` file.)
    1. In the **Arguments** field, enter `runAll`.
    1. Click **Apply**. Your screen should look similar to the following:
    [[EclSbtConfig.png]]
1. Click **Run**.

On success, the console shows that the services are running.
[[EclSbtSuccess.png]]

Verify that the services are indeed up and running by invoking the `hello` service endpoint from any HTTP client, such as a browser:

```
http://localhost:9000/api/hello/World
```

The request returns the message `Hello, World!`.
>>>>>>> a1474a71477d58cf6892b18c9947faadb5d81b21
