# vue-project

This template should help get you started developing with Vue 3 in Vite.

# Frontend Mentor Challenge with Next.js
![alt text](public/mulit-step-form-snapshot.png)
This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app). It incorporates a Frontend Mentor challenge, adhering to a specified front-end style guide.

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:5173](http://localhost:5173) with your browser to see the result.

## Features

-	Built with Vue 3 and Vite for fast development and optimized builds.
-	Toast notifications powered by vue3-toastify.
-	Responsive design adhering to a mobile-first approach.
-	Follows WCAG accessibility guidelines to ensure usability across screen sizes.

## Front-end Style Guide

#### Design Widths:
- Mobile: 375px
- Desktop: 1440px

### Colors

#### Primary
- Desaturated ```Red: hsl(0, 36%, 70%)```
- Soft Red: ```hsl(0, 93%, 68%)```

#### Neutral

- Dark Grayish Red: ```hsl(0, 6%, 24%)```

#### Typography
- Font size:  16px
- Font Family: Josefin Sans
- Font Weights: 300, 400, 600


### License
This project is licensed under the MIT License. See the LICENSE file for details.

### Run End-to-End Tests with [Playwright](https://playwright.dev)

```sh
# Install browsers for the first run
npx playwright install

# When testing on CI, must build the project first
pnpm build

# Runs the end-to-end tests
pnpm test:e2e
# Runs the tests only on Chromium
pnpm test:e2e --project=chromium
# Runs the tests of a specific file
pnpm test:e2e tests/example.spec.ts
# Runs the tests in debug mode
pnpm test:e2e --debug
```

### Lint with [ESLint](https://eslint.org/)

```sh
pnpm lint
```
