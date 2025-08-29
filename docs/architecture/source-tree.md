# Source Tree (Directory Structure)

This project is a Monorepo managed with pnpm workspaces. The structure is organized into `apps` for runnable applications and `packages` for shared code.

## Root Level Structure

```
/
|
├─── apps/
│    ├─── web-client/
│    └─── api-server/
|
├─── packages/
│    ├─── ui-components/
│    ├─── shared-utils/
│    ├─── eslint-config/
│    └─── tsconfig/
|
├─── docs/
├─── .gitignore
├─── package.json
├─── pnpm-workspace.yaml
└─── tsconfig.json
```

## Directory Explanations

### `apps/`

This directory contains the independent, runnable applications of the project.

-   **`apps/web-client/`**: The frontend application, built with React and Vite. This is the user-facing part of the service.
-   **`apps/api-server/`**: The backend API server, built with Node.js and Express. It handles business logic, data processing, and database interactions.

### `packages/`

This directory contains shared code and configurations, designed to be consumed by the applications in the `apps` directory.

-   **`packages/ui-components/`**: A shared library of React UI components (e.g., Buttons, Modals, Layouts) that can be used by `web-client` or any other future frontend applications to maintain a consistent look and feel.
-   **`packages/shared-utils/`**: A library for utility functions that can be used across the entire monorepo (both frontend and backend). Examples include validation functions, formatters, or constants.
-   **`packages/eslint-config/`**: A centralized ESLint configuration package to enforce consistent coding standards across all apps and packages.
-   **`packages/tsconfig/`**: Contains base TypeScript `tsconfig.json` files that can be extended by other packages, ensuring consistent compiler options.
