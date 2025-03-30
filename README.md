# Node.js Boilerplate with TypeScript, Docker, and HMR

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

This is a **Node.js boilerplate** project designed to help you quickly set up a TypeScript-based backend application. It includes support for **Hot Module Replacement (HMR)**, **Docker**, **linting**, and other modern development tools.

---

## Features

- **TypeScript**: Write type-safe JavaScript with modern features.
- **Docker Integration**: Easily containerize your application using Docker and Docker Compose.
- **Hot Module Replacement (HMR)**: Automatically reload changes during development with `nodemon`.
- **Linting and Formatting**: Enforce consistent coding standards with ESLint and Prettier.
- **Environment Variables**: Use `.env` files for configuration.
- **Multi-stage Docker Build**: Optimize production builds with a lightweight container.
- **Path Aliases**: Use `@/*` path aliases for cleaner imports.

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [Prerequisites](#prerequisites)
3. [Installation](#installation)
4. [Development](#development)
5. [Building the Project](#building-the-project)
6. [Running in Production](#running-in-production)
7. [Docker Setup](#docker-setup)
8. [Linting and Formatting](#linting-and-formatting)
9. [Contributing](#contributing)
10. [License](#license)

---

## Getting Started

To get started with this boilerplate, follow the steps below.

### Prerequisites

Make sure you have the following installed on your machine:

- [Node.js](https://nodejs.org/) >= 22
- [npm](https://www.npmjs.com/) >= 10
- [Docker](https://www.docker.com/) (optional, for containerization)

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/muhin-g-s/node-hmr-ts-boilerplate.git
   cd node-hmr-ts-boilerplate
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the root directory and configure it:
   ```env
   PORT=3000
   NODE_ENV=development
   ```

---

## Development

Start the development server with Hot Module Replacement (HMR):

```bash
npm run dev
```

This will use `nodemon` to watch for changes in your TypeScript files and automatically restart the server. The `nodemon` configuration is set up in the `nodemon.json` file.

---

## Building the Project

To compile the TypeScript code into JavaScript:

```bash
npm run build
```

The compiled files will be placed in the `dist/` directory.

---

## Running in Production

After building the project, you can run the compiled JavaScript files:

```bash
npm run preview
```

This will start the server using the compiled code from the `dist/` directory.

---

## Docker Setup

This boilerplate includes Docker support for easy deployment. The `Dockerfile` uses a multi-stage build to optimize the production image.

1. Build the Docker image:
   ```bash
   docker-compose up --build
   ```

2. Access the app at `http://localhost:3000`.

3. To stop the container:
   ```bash
   docker-compose down
   ```

#### Dockerfile Details

- **Builder Stage**:
  - Installs dependencies using `npm ci` for deterministic builds.
  - Compiles TypeScript code into JavaScript.

- **Production Stage**:
  - Copies only the necessary files (`dist/`, `node_modules/`, and `package*.json`) to keep the image lightweight.
  - Runs the application using `node dist/index.js`.

---

## Linting and Formatting

This project uses ESLint and Prettier for linting and formatting. You can run the following commands:

- **Lint TypeScript files**:
  ```bash
  npm run lint:ts
  ```

- **Lint JavaScript and TypeScript files with ESLint**:
  ```bash
  npm run lint:eslint
  ```

- **Format code with Prettier**:
  ```bash
  npx prettier --write "src/**/*.{ts,js,json}"
  ```

---

## Path Aliases

This project supports path aliases for cleaner imports. For example:

```typescript
import myModule from '@/utils/myModule';
```

This is configured in the `tsconfig.json` file under the `paths` option:
```json
"paths": {
  "@/*": ["src/*"]
}
```

When running the application, `tsconfig-paths/register` ensures that path aliases are resolved correctly.

---

## Contributing

Contributions are welcome! If you find any issues or want to add new features, feel free to open an issue or submit a pull request.

1. Fork the repository.
2. Create your feature branch (`git checkout -b feature/new-feature`).
3. Commit your changes (`git commit -m 'Add new feature'`).
4. Push to the branch (`git push origin feature/new-feature`).
5. Open a pull request.

---

## License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/muhin-g-s/node-hmr-ts-boilerplate#license) file for details.

---

## Bugs and Issues

If you encounter any bugs or issues, please report them in the [issue tracker](https://github.com/muhin-g-s/node-hmr-ts-boilerplate/issues).

---

## Author

Created and maintained by **Muhin G.S.**
Email: [muhin.g.s.00@gmail.com](mailto:muhin.g.s.00@gmail.com)
