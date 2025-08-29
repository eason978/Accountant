# Technology Stack & Tooling

This document outlines the primary technologies, frameworks, and tools chosen for this project. The goal is to build a modern, scalable, and maintainable application with a great developer experience.

| Category | Tool/Technology | Purpose & Rationale |
| :--- | :--- | :--- |
| **Runtime Environment** | **Node.js** | The fundamental JavaScript runtime for both the backend and the development toolchain. |
| **Package Management** | **pnpm** | A fast and disk-space-efficient package manager. Its superior support for monorepos makes it the ideal choice for this project structure. |
| **Monorepo Management** | **Turborepo** | A high-performance build system for JavaScript/TypeScript monorepos. It speeds up development by caching task outputs and running tasks in parallel. |
| **Language** | **TypeScript** | Provides static typing for JavaScript, which helps catch errors early, improves code quality, and makes the codebase easier to refactor and maintain. |
| **Backend Framework** | **Express.js** | A minimal and flexible Node.js web application framework that provides a robust set of features for building the `api-server`. |
| **Frontend Framework** | **React** | A declarative, component-based library for building user interfaces, providing a rich ecosystem and strong community support. |
| **Frontend Build Tool** | **Vite** | A next-generation frontend tooling that offers an extremely fast development server and optimized build process for the `web-client`. |
| **Testing Framework** | **Vitest** | A Vite-native testing framework that is fast, simple, and provides a modern testing experience for all applications and packages. |
| **Code Style & Formatting**| **ESLint & Prettier** | ESLint statically analyzes the code to find problems, while Prettier automatically formats it to ensure a consistent style. They work together to maintain high code quality. |
