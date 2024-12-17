# API Definition

Our API is defined using the OpenAPI Specification (OAS) version 3.0.0. The API definition is in another repository and can be found [here](https://github.com/storevision/openapi-schema).

The API definition is used to generate TypeScript types for the API. These types are used in the frontend to ensure type safety when interacting with the API.

You can find a hosted version of the API documentation [here](https://storevision.github.io/openapi-schema/). (Swagger UI)

## Backends

There are two backends:
    - [C# Backend](https://github.com/storevision/webstore-backend)
    - [Node.js Backend](https://github.com/storevision/webstore-backend-js)

The C# backend is the main backend for the project. The Node.js backend is a backup backend that can be used if the C# backend is not available or outdated.
