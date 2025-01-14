webstore-backend/
    .github/
        ...    # GitHub Configuration
    docs/
        ...    # Markdown pages, images, and other files for documentation
    src/
        Controllers/
            ...    # Controller files for handling API requests
        Models/
            ...    # Model files for database entities
        Services/
            ...    # Service files containing business logic
        Data/
            ...    # Database related files, e.g., migrations
        Middleware/
            ...    # Middleware files for logging, authentication, etc.
        Helpers/
            ...    # Utility classes or functions
        appsettings.json    # Application configuration file
        Program.cs          # Entry point of the application (starting the API)
        Startup.cs          # Configure services and middleware
        appsettings.Development.json    # Development environment config
        appsettings.Production.json     # Production environment config
    .editorconfig          # Editor configuration file
    .env                   # Environment variables
    .gitignore             # Git ignore file
    .gitattributes         # Git attributes file
    Dockerfile             # Dockerfile for building the backend image
    LICENSE                # License file
    README.md              # Readme file with project overview
    appsettings.json       # Default application settings
    package.json           # Node.js package file (if using Node for some backend tasks)
    Playwright.Dockerfile  # Dockerfile for building Playwright tests image
    Playwright.config.ts   # Playwright configuration file for tests
    tsconfig.json          # TypeScript configuration file (if using TypeScript for backend code)
    yarn.lock              # Yarn lock file (if using Yarn for package management)
