---
name: vite
description: Configure, run, build, and troubleshoot a lightweight Vite front-end application with minimal project complexity.
---

# Vite

Apply these instructions whenever a task affects project scaffolding, development-server behavior, environment variables, static assets, plugins, or production builds.

## Principles

- Keep the Vite configuration minimal and add options only for a demonstrated need.
- Use the official framework plugin and preserve the project's module format.
- Prefer standard source imports for processed assets and the public directory only for files that must retain stable names.
- Use supported aliases sparingly and keep editor and type-checker resolution aligned.
- Verify both development behavior and the production build when configuration changes.
- Keep browser compatibility decisions explicit and based on project requirements.

## Environment Variables

- Read client environment variables through `import.meta.env`.
- Treat every variable exposed to client code as public.
- Never store secrets in client-prefixed environment variables or committed environment files.
- Document required variables in an example file using non-sensitive placeholder values.
- Validate required configuration at application startup and report missing values clearly.

## Development and Build

- Use the development server for local iteration, not as a production server.
- Keep plugins to the minimum required for the demo.
- Preserve predictable entry points and output paths.
- Configure SPA history fallback in the deployment platform when client-side routing is enabled.
- Investigate build warnings rather than suppressing them globally.
- Add dependency optimization or chunking configuration only after observing a real issue.

## Avoid

- Copying a large configuration from an unrelated project.
- Accessing client configuration through server-only environment APIs.
- Exposing credentials through the generated bundle.
- Adding plugins for behavior available through Vite or the browser.
- Depending on development-server behavior that is absent from the production host.
- Premature manual chunking or build micro-optimization.

## Verification

- Start the development server and confirm the application loads without console errors.
- Run the production build and preview its output.
- Verify direct navigation and refresh behavior for every client-side route.
- Check that environment-specific values are handled correctly and no secret appears in built assets.
