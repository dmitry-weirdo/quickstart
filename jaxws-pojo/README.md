# jaxws-pojo: An POJO JAX-WS Web Service

Author: R Searls  
Level: Beginner  
Technologies: JAX-WS  
Summary: The `jaxws-pojo` quickstart is a working example of the web service endpoint created from a POJO.  
Target Product: ${product.name}  
Source: <${github.repo.url}>  

## What is it?

The `jaxws-pojo` quickstart demonstrates the use of *JAX-WS* in ${product.name.full} as a simple POJO web service application.

## System Requirements

The application this project produces is designed to be run on ${product.name.full} ${product.version} or later.

All you need to build this project is ${build.requirements}. See [Configure Maven for ${product.name} ${product.version}](https://github.com/jboss-developer/jboss-developer-shared-resources/blob/master/guides/CONFIGURE_MAVEN_JBOSS_EAP7.md#configure-maven-to-build-and-deploy-the-quickstarts) to make sure you are configured correctly for testing the quickstarts.


## Use of ${jboss.home.name}

In the following instructions, replace `${jboss.home.name}` with the actual path to your ${product.name} installation. The installation path is described in detail here: [Use of ${jboss.home.name} and JBOSS_HOME Variables](https://github.com/jboss-developer/jboss-developer-shared-resources/blob/master/guides/USE_OF_${jboss.home.name}.md#use-of-eap_home-and-jboss_home-variables).


## Start the Server

1. Open a command prompt and navigate to the root of the ${product.name} directory.
2. The following shows the command line to start the server:

        For Linux:   ${jboss.home.name}/bin/standalone.sh
        For Windows: ${jboss.home.name}\bin\standalone.bat


## Build and Deploy the Quickstart

1. Make sure you have started the ${product.name} server as described above.
2. Open a command prompt and navigate to the root directory of this quickstart.
3. Type this command to build and deploy the archive:

        mvn clean install wildfly:deploy

4. This will deploy `service/target/${project.artifactId}-service.war` to the running instance of the server.

## Access the Application

You can check that the Web Service is running and deployed correctly by accessing the following URL: <http://localhost:8080/${project.artifactId}/JSEBean?wsdl>. This URL will display the deployed WSDL endpoint for the Web Service.

## Run the Client
1. Make sure the service deployed properly.
2. Open a command prompt and navigate into the client directory of this quickstart.

        cd client/

3. Type this command to run the client.

        mvn exec:java        
    __Note__: This quickstart requires `quickstart-parent` artifact to be installed in your local Maven repository.
    To install it, navigate to quickstarts project root directory and run the following command:

        mvn clean install


4. You should see the following response.

        JSEBean pojo: pojoClient calling


## Undeploy the Archive

1. Make sure you have started the ${product.name} server as described above.
2. Open a command prompt and navigate to the root directory of this quickstart.
3. When you are finished testing, type this command to undeploy the archive:

        mvn wildfly:undeploy


## Run the Quickstart in Red Hat JBoss Developer Studio or Eclipse

You can also start the server and deploy the quickstarts or run the Arquillian tests from Eclipse using JBoss tools. For general information about how to import a quickstart, add a ${product.name} server, and build and deploy a quickstart, see [Use JBoss Developer Studio or Eclipse to Run the Quickstarts](${use.eclipse.url}).

For this quickstart, follow the special instructions to build [Quickstarts Containing an EAR](https://github.com/jboss-developer/jboss-developer-shared-resources/blob/master/guides/USE_JBDS.md#deploy-and-undeploy-a-quickstart-containing-server-and-java-client-projects)

1. Right-click on the `${project.artifactId}-service` subproject, and choose `Run As` --> `Run on Server`.
2. Choose the server and click `Finish`.
3. This starts the server, deploys the application, and opens a browser window that accesses the running application.
4. To undeploy the project, right-click on the `${project.artifactId}-ear` project and choose `Run As` --> `Maven build`. Enter `wildfly:undeploy` for the `Goals` and click `Run`.


## Debug the Application

If you want to debug the source code of any library in the project, run the following command to pull the source into your local repository. The IDE should then detect it.

    mvn dependency:sources
