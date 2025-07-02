# Gemini Project Overview: Personal Website

This document is maintained by Gemini to provide a comprehensive overview of your personal website project. It helps Gemini retain context about the project's structure, technologies, and goals across conversations.

## Project Description

This project is your personal website, built as a monorepo containing a [Next.js](https://nextjs.org/) frontend and a [Sanity](https://www.sanity.io/) Studio backend. The website will feature a project portfolio, a blog, and a photo gallery. The project is set up with a focus on real-time visual editing, customizable pages, and a great developer experience.

The project is structured as a monorepo with two main workspaces:

- `frontend`: A Next.js 15 application that serves as the public-facing website.
- `studio`: A Sanity Studio application for content management.

## Key Technologies

- **Next.js 15:** A React framework for building server-rendered and statically generated web applications.
- **Sanity:** A headless CMS for structured content.
- **TypeScript:** A typed superset of JavaScript that compiles to plain JavaScript.
- **Tailwind CSS:** A utility-first CSS framework for rapid UI development.
- **React:** A JavaScript library for building user interfaces.
- **Vercel:** A cloud platform for static sites and Serverless Functions.

## Project Structure

### Root

- `package.json`: Defines the project's dependencies and scripts. It uses npm workspaces to manage the `frontend` and `studio` packages.
- `README.md`: Provides instructions on how to set up and run the project.
- `.gitignore`: Specifies which files and directories to ignore in Git.

### `frontend`

The `frontend` directory contains the Next.js application.

- **`app/`**: The main application directory for the Next.js app, using the App Router.
    - **`app/page.tsx`**: The homepage of the website.
    - **`app/[slug]/page.tsx`**: A dynamic route that renders individual pages based on a slug.
    - **`app/components/`**: Contains reusable React components used throughout the application.
        - **`PageBuilder.tsx`**: A key component that dynamically renders pages based on the content from Sanity's `pageBuilder` field.
- **`sanity/`**: Contains the Sanity client, queries, and other utility functions for interacting with the Sanity API.
- **`public/`**: Contains static assets like images and fonts.
- **`package.json`**: Defines the dependencies and scripts for the frontend application.
- **`next.config.ts`**: The configuration file for Next.js.
- **`tailwind.config.ts`**: The configuration file for Tailwind CSS.

### `studio`

The `studio` directory contains the Sanity Studio application.

- **`src/`**: The main source code directory for the Sanity Studio.
    - **`schemaTypes/`**: Defines the content models (schemas) for the Sanity database.
        - **`documents/`**: Contains the schema definitions for document types like `page` and `post`.
        - **`objects/`**: Contains the schema definitions for reusable object types.
        - **`singletons/`**: Contains the schema definitions for singleton document types like `settings`.
- **`sanity.config.ts`**: The main configuration file for the Sanity Studio.
- **`sanity.cli.ts`**: The configuration file for the Sanity CLI.
- **`package.json`**: Defines the dependencies and scripts for the Sanity Studio.

## Content Model

The Sanity Studio is configured with the following main content types:

- **Page:** Represents a page on the website. It has a `pageBuilder` field that allows content editors to build pages by adding and arranging different content blocks.
- **Post:** Represents a blog post.
- **Person:** Represents an author or a person.
- **Settings:** A singleton document for global site settings.

## How to Run the Project

1.  **Install dependencies:**
    ```bash
    npm install
    ```
2.  **Run the development servers:**
    ```bash
    npm run dev
    ```
    This will start both the Next.js frontend (on `http://localhost:3000`) and the Sanity Studio (on `http://localhost:3333`).

## Next Steps

This `GEMINI.md` file provides a starting point for understanding the project. As the project evolves, this file can be updated to reflect the latest changes and additions.
