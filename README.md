# Currency Converter

A currency converter web app built with **React** and **Vite**. It fetches exchange rates from an external API and converts amounts between currencies.

## Tech Stack

- [React 19](https://react.dev/) – UI library
- [Vite](https://vite.dev/) – build tool and dev server
- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react) – React support for Vite
- [Oxlint](https://oxc.rs/docs/guide/usage/linter) – fast linter (React and Oxc plugins enabled)

## Prerequisites

- [Node.js](https://nodejs.org/) (a recent LTS version is recommended)
- npm
- An API key from your exchange rate provider

## Getting Started

### 1. Clone the repository

```bash
git clone <your-repo-url>
cd currency-converter
```

### 2. Install dependencies

```bash
npm install
```

### 3. Configure environment variables

Create a `.env` file in the project root:

```env
VITE_API_KEY=your_api_key_here
```

| Variable       | Description                           |
| -------------- | ------------------------------------- |
| `VITE_API_KEY` | API key for the exchange rate service |

> **Security note:** Vite exposes every variable prefixed with `VITE_` in the browser bundle, so the key is visible to anyone using the app. Use a free-tier or restricted key, and never reuse a key that has access to sensitive resources. For a production app with a paid key, proxy the requests through a backend instead.
>
> Also make sure `.env` is listed in your `.gitignore` so it is never committed.

### 4. Run the development server

```bash
npm run dev
```

The app will be available at the URL printed in your terminal (by default `http://localhost:5173`).

## Available Scripts

| Command           | Description                                      |
| ----------------- | ------------------------------------------------ |
| `npm run dev`     | Starts the development server with HMR           |
| `npm run build`   | Creates an optimized production build in `dist/` |
| `npm run preview` | Serves the production build locally              |
| `npm run lint`    | Runs Oxlint on the project                       |

## Project Structure

```
.
├── public/            # Static assets (e.g. favicon.svg)
├── src/
│   └── main.jsx       # Application entry point
├── .env               # Environment variables (do not commit)
├── .oxlintrc.json     # Linter configuration
├── index.html         # HTML entry point
├── package.json
└── vite.config.js     # Vite configuration
```

## Linting

Oxlint is configured with the `react` and `oxc` plugins. Two React rules are set explicitly:

- `react/rules-of-hooks` – **error**
- `react/only-export-components` – **warn** (constant exports allowed)

```bash
npm run lint
```

## Building for Production

```bash
npm run build
npm run preview   # optional: test the build locally
```

The output is generated in the `dist/` folder and can be deployed to any static hosting service (Vercel, Netlify, GitHub Pages, etc.). Remember to set `VITE_API_KEY` in your hosting provider's environment settings before building.

## License

This project is open source and available under the [MIT License](LICENSE).
