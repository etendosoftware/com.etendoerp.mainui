# Etendo Main UI

## Installation Steps

### 1. Clone the Repository
Clone the module into the `modules` directory of your Etendo Classic project:
```bash
cd modules
git clone <repository_url>
```

### 2. Install Required Modules  
Install the following modules in your Etendo Classic project:

- `com.etendoerp.openapi`  
- `com.etendoerp.etendorx`  
- `com.etendoerp.metadata`  
- `com.etendoerp.metadata.template`  

After installing `com.etendoerp.etendorx`, configure the authentication manager by adding the following line to your `Openbravo.properties` file:

```properties
authentication.class=com.etendoerp.etendorx.auth.SWSAuthenticationManager
```

### 3. Configure Services  
Add the following lines to your `gradle.properties` file:
```properties
docker_com.etendoerp.mainui=true
ETENDO_CLASSIC_URL=http://your.etendo.instance/etendo
```

#### If Running Etendo Classic via Docker
To enable Docker services for Etendo Classic, also add these lines:
```properties
docker_com.etendoerp.docker_db=true
docker_com.etendoerp.tomcat=true
```

### 4. Set Up the Module  
Run the following commands to set up the module and update resources:
```bash
./gradlew setup
./gradlew resources.up
```

### 5. (If Running in Docker) Set Up the Database  
If this is your first time running Etendo Classic via Docker, install the database:
```bash
./gradlew install
```

## Notes  
- The `install` task is only needed if running Etendo Classic via Docker for the first time.

## Troubleshooting  
- Ensure Docker and Java are properly installed.  
- Check the logs for detailed error messages if issues occur.
