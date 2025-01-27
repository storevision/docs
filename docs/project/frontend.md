# Frontend Structure

Here is a overview about the frontend folder structure:

## Root folder

    webstore-frontend/
    ├── .github/
    │   └── ...    # GitHub Configuration.
    ├── mkdocs.yml  # The configuration file for documentation.
    ├── docs/
    │   └── ...    # Markdown pages, images and other files for documentation.
    ├── e2e-tests/
    │   └── ...    # End-to-end tests implemented using Playwright.
    ├── public/
    │   └── ...    # Public files like images and other assets.
    ├── src/
    │   └── ...    # Source files
    ├── .editorconfig          # Editor configuration file.
    ├── .env                   # Environment variables.
    ├── .eslintrc.js           # ESLint configuration file. (Code formatting, linting)
    ├── .gitattributes         # Git attributes file. (Proper handling of line endings, etc.)
    ├── .gitignore             # Git ignore file.
    ├── .nvmrc                 # Node version manager configuration file. Used to specify the Node.js version.
    ├── Frontend.Dockerfile    # Dockerfile for building the frontend.
    ├── jest.config.ts         # Jest configuration file. (Unit testing)
    ├── LICENSE                # License file.
    ├── next.config.js         # Next.js configuration file.
    ├── next-env.d.ts          # Next.js typescript definitions.
    ├── package.json           # Node.js package file.
    ├── playwrigth.config.ts   # Playwright configuration file.
    ├── Playwright.Dockerfile  # Dockerfile for building the Playwright image.
    ├── README.md              # Readme file.
    ├── tsconfig.json          # TypeScript configuration file.
    └── yarn.lock              # Yarn lock file.

## `.github/` folder

    .github/
    ├── workflows/
    │   ├── ci.yml    # GitHub Actions workflow file for CI.
    │   └── docs.yml  # Configuration file for the mkdocs action.
    └── dependabot.yml  # Dependabot configuration file.

The `.github/workflows` folder contains the **GitHub Actions** workflow files. Here, we have files describing the CI/CD pipeline for the project.
These files contain tests to see if everything still works, check the code quality, and build + deploy the project.

The `dependabot.yml` file contains the configuration for the **Dependabot** service.
**Dependabot** checks for outdated dependencies and creates pull requests to update them.

## `docs/` folder

    docs/
    ├── index.md  # The documentation homepage.
    └── ...       # Other markdown files for documentation.

Here you can find the documentation for the project. The documentation is written in markdown and can be viewed using the **mkdocs** tool.

You can find more information about **mkdocs** [here](https://www.mkdocs.org) and our developer documentation [here](../developer/index.md).

## `e2e-tests/` folder

    e2e-tests/
    └── ...    # End-to-end tests implemented using Playwright.

This folder contains the end-to-end tests for the project. The tests are implemented using the **Playwright** testing framework.

The tests define the behavior of the application from the user's perspective.
They simulate user interactions with the application and check if the application behaves as expected.

## `src/` folder

    src/
    ├── app/         # The Next.js app folder. Contains the pages and components.
    ├── components/  # Reusable components.
    ├── constants/   # Constants used in the app.
    ├── generated/   # Generated files by openapi-typescript codegen.
    ├── hooks/       # Custom hooks.
    ├── providers/   # Context providers.
    ├── stores/      # Zustand state management stores.
    ├── utils/       # Utility functions.
    ├── mui.ts       # @mui/material module augmentation.
    ├── theme.ts     # Material-UI theme.
    └── types.d.ts   # TypeScript global types.

This is where the code of the project is located. The `src` folder contains the source files for the project.

The `app` folder contains the Next.js app. It contains the pages and components that make up the application.
You can read more about the Next.js app structure <a href="https://nextjs.org/docs/app/getting-started" target="_blank">here</a>.

The `app` folder also contains a folder called `_api` which contains the API functions used to communicate with the backend.
The reason this is inside the `app` folder is that these functions are server actions.
Especially because of the <a href="https://nextjs.org/docs/app/api-reference/functions/cookies" target="_blank">`cookies()`</a> function, which is only available on the server.

## `src/utils/api.ts` file

For the API functions, we use a API client that is type-safe. The generation is provided by the `openapi-typescript` package.
The `openapi-fetch` package is used to take these generated types and create a fetch function that is type-safe.

There are also some typescript generics that we have to extract things like a `SuccessResponse` or `ErrorResponse` from the API response.
