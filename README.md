# Etendo Main UI

## Overview
This README provides the necessary steps to install and set up the Etendo Main UI. Follow these instructions to get the module running in your Etendo Classic environment.

## Prerequisites
- Etendo Classic project set up.
- Docker installed and running.
- Java and Gradle installed.

## Installation Steps

### 1. Clone the Repository
Clone the module into the `modules` directory of your Etendo Classic project:
```bash
cd modules
git clone <repository_url>
```

### 2. Configure Services
Add the following lines to your `gradle.properties` file to set up the required services:
```properties
docker_com.etendoerp.docker_db=true
docker_com.etendoerp.tomcat=true
docker_com.etendoerp.mainui=true
```

### 3. Run Setup and Resources
Execute the following commands to set up the module and update resources:
```bash
./gradlew setup
./gradlew resources.up
```

### 4. (Optional) Database Setup
If the database has not been set up yet, run the following command:
```bash
./gradlew install
```

## Notes
- Ensure Docker services are up and running before executing the Gradle commands.
- The `install` task is only necessary when setting up the database for the first time.

## Troubleshooting
- If you encounter issues during the setup, verify your Docker and Java installations.
- Check the logs for detailed error messages.


