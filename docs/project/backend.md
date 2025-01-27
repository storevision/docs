# Backend Structure

Here is a overview about the backend folder structure:

## Root folder

    Webshop/
    ├── App/
    │   └── src/
    │       └── main/
    │           ├── Controllers # contains all the logic for handling incoming requests and returning appropriate responses. 
    │           ├── Data # contains the dbcontext configuration.
    │           ├── Models/
    │           │   ├── ApiHelper # base class for the controllers, handle responses.
    │           │   ├── DB-Models # all db-models for db-migration
    │           │   └── Responses # response classes, to generate json objects.
    │           └── Services/
    │               └── ... # services that handle incoming requests, and create responses
    ├── sql /
    │   └── ... # script to insert test datas into the database
    ├── Migrations/
    │   └── ... # migration file to update changes on the db.
    ├── .gitignore # list of files what should be ignored
    ├── appsettings.json # settings for the application
    ├── appsettings.Development.json # configure the LogLevel
    ├── backend.env # environments for the connectionstring
    ├── docker-compose.yml # defines and manages multi-container Docker applications and their configurations.
    └── Dockerfile # specifying the base image



