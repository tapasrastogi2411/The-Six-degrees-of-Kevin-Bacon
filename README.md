# The-Six-Degrees-of-Kevin-Bacon

### Description

This is the implementation of the backend for a service that computes the [Six degrees of
Kevin Bacon](https://en.wikipedia.org/wiki/Six_Degrees_of_Kevin_Bacon). This problem can be restated as finding the shortest path between Kevin Bacon
and a given actor (via shared movies). THis has been achieved using a specific dependency injection framework (Google Dagger2) and Neo4j as the database management system

### Objective 

- Explore NoSQL/Graph Databases(Neo4j)
- To create REST API endpoints that are supported by Neo4j Graph Databases
- To utilize Git, Gitflow, and Code Style correctly
- Using enterprise design patterns, specifically dependency injection using Google Dagger2
- Learning and applying CI/CD

### Technologies and Applications needed for this project

- You will need the following applications/technologies on your computer to run the project
    - Latest Version of Java 
        - JDK - Version 16.0.1
        - JRE - Version 16.0.1
    - Maven Version 3.6.3
    - Latest version of Neo4j Desktop
    - [Postman, which is a very helpful tool to use to test your endpoints for basic behaviour](https://www.postman.com/products/)

### Building and running the project

- The first step would be to clone the `master` branch of this repository and open the project in an IDE, either Intellij or Eclipse. Then you have the option of building and running your project from either your IDEs or the command line

    - From the command line: 
        - Install version of [Maven mentioned above](https://archive.apache.org/dist/maven/maven-3/3.6.3/binaries/)
        - To compile your code simply run `mvn compile` in the root directory (the folder that has pom.xml)
        - To run your code run `mvn: exec:java`

    - Intellij:
        - Import project
        - Navigate to the project location
        - Import the project from external model → Maven
        - Next → Next → Next → Finish
        - Add Configuration → (+) Button → Maven
        - Name the configurations and input `exec:java` in the Command Line box
        - Apply → Ok
        - You can now run the project by pressing the green play button.

    - Eclipse:
        - File → Import → Maven → Existing Maven Projects
        - Navigate to the project location
        - Right click the project → Maven Build…
        - Input compile `exec:java` in the Goals input box
        - You can now run the project by pressing the green play button
        
### Completed Features

- Server is up and running
- All GET and PUT requests work as expected (tested through POSTMAN)

### Caveats

- The format of the list of movies received by `getActor` request, and the bacon path generated by `computeBaconPath` request have an extra `/` in them 

Example input - Testing a `computeBaconPath` request

![sample_input](https://user-images.githubusercontent.com/56613320/124346055-a7bc7080-dbaa-11eb-84be-3424720cdd71.PNG)



Actual output received for `computeBaconPath` (as of now)

```json
{
    "baconPath": [
        "\"na0000101\"",
        "\"nm003\"",
        "\"na0000103\"",
        "\"nm002\"",
        "\"na0000104\"",
        "\"nm001\"",
        "\"nm0000102\""
    ]
}

```

Expected output for `computeBaconPath`(Notice how only the formatting of the baconPath is off)

```json

{
    "baconPath": [
        "na0000101",
        "nm003",
        "na0000103",
        "nm002",
        "na0000104",
        "nm001",
        "nm0000102"
    ]
}
```


### TODO
- Complete `AppTest.java` under `src/test/java/ca/utoronto/utm/mcs`
- Fix the format in the which bacon path is displayed.
