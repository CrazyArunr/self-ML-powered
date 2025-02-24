# Project Title
**MLPoweredSeleniumJavaPOC**

This project demonstrates the integration of Healenium, a machine-learning-powered library, with Selenium for efficient regression testing by addressing issues caused by minor web locator changes.

# Project Description
This proof of concept project showcases the integration of Healenium into a Maven Java Selenium project. It highlights how machine learning capabilities can be integrated into Selenium, addressing the problem of test failures due to small changes in web locators. The project is designed to make regression testing more robust and less prone to false negatives.

## Key Points
- **Healenium**: Healenium is an open-source library that enhances Selenium-based UI tests by providing self-healing capabilities. It identifies elements that were not found during test execution and attempts to locate them using alternative locators.
- **Benefits**: Healenium reduces maintenance efforts required for Selenium UI tests and minimizes false-negative results due to outdated locators.
- **Setup**: The project combines a Selenium project, an Angular project to test, and Healenium as a Maven dependency.

# Table of Contents
- [Project Description](#Project-Description)
- [Key Points](#Key-Points)
- [How to Install and Run the Project](#how-to-install-and-run-the-project)
- [How to Use the Project](#how-to-use-the-project-demo)
- [DEMO](#DEMO)
- [Summary](#Summary)

# How to Install and Run the Project
To install and run the project, follow these steps:

Clone down the solution to your local machine. Note the solution contains two projects. Angular application and Selenium test project. Healenium is already installed as a Maven dependency. You will need to spin up containers that contain Healenium backend. See instructions below on how to do that. 

Healenium consists of a Maven Healenium dependency and docker backend. More information on these components can be found below:

Maven dependency <br>
https://github.com/healenium/healenium-web <br>
https://mvnrepository.com/artifact/com.epam.healenium/healenium-web

Docker backend <br>
https://github.com/healenium/healenium-backend <br>
https://hub.docker.com/search?q=healenium

## Build and run Angular app

Navigate to my-angular.app folder and run the following command in the terminal to start Angular dev server on localhost http://localhost:4200

```shell
ng serve --open
The command "ng serve --open" is used in Angular development to start a local development server and automatically open a web browser to preview your Angular application. Here's a brief explanation:

1. **ng serve:** This part of the command is used to start the Angular CLI's development server. It compiles your Angular application's code, bundles it, and makes it available for testing and development.

2. **--open:** This flag is an optional parameter that instructs the Angular CLI to automatically open a web browser. When you run "ng serve --open," it launches a default web browser, which then loads your Angular app.
```

Upon successfull build of the Angular application, you should see the following page on http://localhost:4200/


## Download docker images and spin up docker containers required for Healenium

Navigate to infra folder in the JavaHealeniumPOC in the terminal and run the following command to download images and spin up containers

infra folder is found here where docker compose file is located


docker command to run 
```shell
docker-compose up -d

The Docker command "docker-compose up -d" is used to start containers defined in a Docker Compose configuration file in detached mode. Here's a brief explanation:

1. **docker-compose:** This command is part of Docker Compose, a tool for defining and running multi-container Docker applications. It reads the configuration from a "docker-compose.yml" file in your project directory.

2. **up:** The "up" command tells Docker Compose to create and start containers defined in the Compose file. It ensures that your defined services, networks, and volumes are launched and configured as specified in the Compose configuration.

3. **-d:** The "-d" flag stands for "detached" mode. When you use this flag, Docker Compose starts the containers in the background, and the command prompt is returned to you immediately. This means you can continue using the terminal for other tasks without being attached to the container's logs.
```


# How to Use the Project
The POC demonstrates how Healenium can handle changes in web locators to prevent test failures.

1. Ensure that you have a baseline snapshot of the elements. To do this, run the test once to save a snapshot of the elements used during the test.

2. In the Angular project, change the ID of an element, simulating a locator change.

3. Run the test with the changed locator to observe how the self-healing capability works. With Healenium enabled, the test should pass by healing the web element locator.

4. You can verify the self-healing by visiting [http://localhost:7878/healenium/report/](http://localhost:7878/healenium/report/), where you'll find a report and a screenshot of the healed web element.










# Summary
Healenium offers a valuable solution for Selenium automation projects, significantly reducing maintenance work and addressing the common issue of failing regression tests due to minor web locator changes. It's a powerful tool for making your test automation more robust and efficient, allowing you to focus on creating tests for new features rather than constantly fixing failing regression tests. Explore Healenium further to harness its full capabilities and enhance your test automation processes.
