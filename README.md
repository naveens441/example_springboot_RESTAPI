# example springboot RESTAPI
A very simple example project using Spring Boot to build a rest API. The example project is intended to showcase how you can build an application based upon the spring boot framework in combination with Maven. The example code is based upon the example from Spring which can be found at https://spring.io/guides/gs/rest-service/ . It is not the intention of the repository to provide you with a solution which can be used in a real-world solution. It is rather intended as an informational guideline on how to use Spring Boot and Maven to build a REST API. 

#### prerequisites
Even though compiling and running the example included in the example will work on a large set of configurations we have used a specific set of components which did work. To ensure the same experience you can use the below prerequisites as guidance on preparing your environment

##### Select the operating system
In our case we used Oracle Linux 6 as an operating system. To be more precise we used Oracle Linux 6.9 as it is provided as a docker container by Oracle. You can find the docker container at https://github.com/oracle/ol-container-images/tree/master/6.9 and it is also located at https://hub.docker.com/_/oraclelinux/ 

to get the docker container we used you can use the below command:
```shell
docker pull oraclelinux:6.9
```

#### Running the example
The below steps will take you through downlaoding, packaging and running the example project. Following the steps (after you ensured you have the prerequisites in place) should be straight forward. 

##### step 1 - getting the code
Getting the code on your machine can be done using the git command as shown in the example below. this will ensure you will get the source code including the pom.xml file which is needed by Maven to build the code into a package
```shell
git clone https://github.com/louwersj/example_springboot_RESTAPI
```

##### step 2 - compile and package the code
As soon as you have retrieved the code you will have to compile and package your code. The result of this will be a jar file which you can use to run the example project. Using maven you can package the appication with the command shown below:
```shell
mvn clean package
```

##### step 3 - running the code
In the previous step we packaged the code which resulted in a self sufficient .jar file able to run the application. You can use this .jar file to run the application on the machine you build the code or on a different machine. running it can be done by using the below java command to start it. This should start the embeded application server and run the code which makes it availabel on port 8080
```shell
java -jar gs-rest-service-0.1.0.jar
```

##### step 4 - testing the application
Now that we have the code running you can test if it serves you what is expected from it. The code is intended to provide you a JSON file as soon as you call /greeting on port 8080. This means that we can use curl on the commandline to do so. 

```shell
curl http://localhost:8080/greeting
```
The above example test should give you something like the below response(which can differ on id as it is raise by one every time you call  greeting 
```json
{"id":8,"content":"Hello, World!"}
```
