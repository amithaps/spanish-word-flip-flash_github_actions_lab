# Spanish Word Flip Flash

A small React and Vite app for learning Spanish vocabulary with flip cards. This repository includes unit tests with Vitest and end-to-end tests with Playwright, making it a useful project for practicing GitHub Actions.

## Tech stack

- React, TypeScript, and Vite
- Tailwind CSS and shadcn/ui components
- Vitest for unit tests
- Playwright for end-to-end tests

## Requirements

- Node.js 20 or later is recommended.
- npm (included with Node.js)

The project does not currently specify an exact Node.js or npm version in `package.json`.

## Getting started

Install dependencies:

```bash
npm ci
```

Start the development server:

```bash
npm run dev
```

Vite serves the app at [http://localhost:8080](http://localhost:8080).

## Available scripts

| Command | Description |
| --- | --- |
| `npm run dev` | Start the development server |
| `npm run build` | Create a production build in `dist/` |
| `npm run preview` | Preview the production build locally |
| `npm run lint` | Run ESLint |
| `npm run test:unit` | Run unit tests with Vitest |
| `npm run test:e2e` | Run Playwright end-to-end tests |
| `npm run test:e2e:ui` | Open Playwright's interactive UI |
| `npm run test:e2e:update` | Update Playwright snapshots |
| `npm run test:e2e:report` | Open the most recent Playwright HTML report |

## Tests

### Unit tests

Run the unit tests:

```bash
npm run test:unit
```

Vitest is configured in `vitest.config.ts`. The current example test is `src/lib/utils.test.ts`.

### End-to-end tests

Install the Playwright browsers before running the end-to-end tests:

```bash
npx playwright install
```

Run the tests:

```bash
npm run test:e2e
```

Playwright is configured in `playwright.config.ts` to run Chromium, Firefox, and WebKit projects. By default, it starts the Vite development server at `http://localhost:8080` for the tests. You can override the test target with `E2E_BASE_URL`.

For example, to run only the Chromium tests in headed mode:

```bash
E2E_BASE_URL=http://localhost:8080 \
  npm run test:e2e -- --project=chromium --headed
```

To slow the browser down for debugging:

```bash
SLOW_MO=400 E2E_BASE_URL=http://localhost:8080 \
  npm run test:e2e -- --project=chromium --headed
```

Playwright writes its JUnit report to `reports-e2e/junit.xml` and its HTML report to `reports-e2e/html`. Traces, screenshots, and videos are configured to be retained on failure.

## GitHub Actions learning

This repository is suitable for practicing CI workflows. A good first workflow could run on pushes and pull requests and:

1. Set up Node.js.
2. Install dependencies with `npm ci`.
3. Run `npm run lint`.
4. Run `npm run test:unit`.
5. Run `npm run build`.

You can extend it later to install Playwright browsers and run `npm run test:e2e`.

## License

No license file is currently included in this repository. Add a `LICENSE` file if you want to specify the terms for using or distributing the project.
