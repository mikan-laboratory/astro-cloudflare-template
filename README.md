# Astro Cloudflare Template

This repository provides a ready-to-use template for building web projects using Astro, tailored for deployment on Cloudflare with Tailwind CSS for styling. It includes a robust setup with tools like Husky for pre-commit linting, ESLint, Prettier, and TypeScript configurations to ensure code quality and consistency.

Read [this article](https://devdesigndaily.com/astro-and-cloudflare) to learn why we love Astro and Cloudflare.

## Features

- **Astro Configuration**: Pre-configured to optimize your development experience.
- **Tailwind CSS**: Integrated for rapid UI development.
- **Cloudflare Ready**: Ready for deployment to Cloudflare with necessary configurations.
- **Code Quality Tools**:
  - **ESLint**: Helps in identifying and reporting on patterns found in ECMAScript/JavaScript code.
  - **Prettier**: An opinionated code formatter to maintain code style consistency.
  - **Husky**: Manages pre-commit hooks to lint your code before commits.
  - **GitHub Dependency Checks**: Ensures your dependencies are secure and up-to-date.

## Image Handling

The template uses a passthrough image service by default in the Astro configuration. This is essentially a no-op configuration — it does not alter or process images but simply serves them as is. If you require different image handling, such as integration with Cloudflare Images or another service, modify the `astro.config.mjs`:

```javascript
image: {
  service: yourImageService(),
},
```

## Environment Variables

To use environment variables within your Astro project, configure them in the `astro.config.mjs` under the `vite` section as shown below:

```javascript
vite: {
  define: {
    'process.env.SOME_API_KEY': JSON.stringify(process.env.SOME_API_KEY),
  },
},
```

You can then access these variables in your code:

```javascript
if (!import.meta.env.SOME_API_KEY) {
  throw new Error('SOME_API_KEY not set');
}
```

Make sure to replace `SOME_API_KEY` with your actual environment variable keys.

## Getting Started

To use this repository as a template, follow these steps:

1. **Create Your Repository**:
   Visit the template repository and click on **Use this template**. Follow the instructions to set up your new repository.

   Alternatively, you can use the GitHub CLI:

   ```bash
   gh repo create your-new-repo --template mikan-laboratory/astro-cloudflare-template --private
   cd your-new-repo
   git push --set-upstream origin main
   ```

2. **Clone Your Repository**:

   ```bash
   git clone https://github.com/your-username/your-new-repository.git
   cd your-new-repository
   ```

3. **Install Dependencies**:

   ```bash
   npm install
   ```

4. **Local Development**:
   Start the development server:

   ```bash
   npm run dev
   ```

5. **Build**:
   Build your project:

   ```bash
   npm run build
   ```

6. **Linting and Formatting**:
   Run ESLint to identify issues:
   ```bash
   npm run lint
   ```
   Lint and fix:
   ```bash
   npm run fix
   ```

## Deployment on Cloudflare

To deploy your Astro project on Cloudflare:

1. **Connect Your GitHub Project**:

   - Go to the Cloudflare Dashboard and connect your GitHub repository containing your project.

2. **Set Environment Variables**:

   - Define any necessary environment variables in the Cloudflare settings to match those expected by your Astro configuration.

3. **Deploy**:
   - Use the default settings provided by Cloudflare for a straightforward deployment, or customize as needed based on your project's requirements.
