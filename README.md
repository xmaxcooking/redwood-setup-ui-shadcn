# Shadcn-UI Example Repository

This repository serves as an example of how to integrate Shadcn-UI into a RedwoodJS project. Shadcn-UI is a powerful UI library that offers a wide range of customization options. To get started, follow these installations steps or check the [Shadcn-UI documentation](https://ui.shadcn.com/docs/installation/manual).

## Installation Steps
1. Setup RedwoodJS
    ```bash
    yarn create redwood-app my-redwood-project --typescript
    cd my-redwood-project
    yarn install
    ```

2. Setup Tailwind CSS using the following command:

   ```bash
   yarn redwood setup ui tailwindcss
   ```

3. Initialize Shadcn-UI in your Redwood project's web workspace:

   ```bash
   npx shadcn-ui@0.7.0 init -c web
   ```

4. Install the shacdn dependencies in your Redwood project's web workspace:

   ```bash
   yarn workspace web add tailwindcss-animate class-variance-authority clsx tailwind-merge
   ```

5. During the init process, follow these configuration steps:

   - Choose TypeScript if you created your Redwood project with TypeScript.
   - Select a style theme from the available options. You can compare the default and New York styles [here](https://ui.shadcn.com/themes).
   - Pick any base color.
   - Set the path to your `index.css` as `src/index.css`.
   - It's recommended to choose CSS variables if you intend to use more theming options than just light and dark.
   - Set the path to your Tailwind CSS configuration file as `config/tailwind.config.js`.
   - Set the path to your components directory as `src/components`.
   - Set the path for utils as `src/lib/utils`.
   - Disable React Server Components (NOTE: this feature may become available in the future).
   - Save the `components.json` configuration.

    The created `web/components.json` file should mostly look like this:
    ```json
    {
      "$schema": "https://ui.shadcn.com/schema.json",
      "style": "default",
      "rsc": false,
      "tsx": true,
      "tailwind": {
        "config": "config/tailwind.config.js",
        "css": "src/index.css",
        "baseColor": "slate",
        "cssVariables": true
      },
      "aliases": {
        "components": "src/components",
        "utils": "src/lib/utils"
      }
    }
    ```

6. After completing the initialization, you can start adding components using the following command:

   ```bash
   npx shadcn-ui@latest add -c web
   ```

   For Redwood projects, this command would ideally create a folder for each component. Inside each component folder, you could add a `.test.tsx` file for tests and a `.stories.tsx` file for stories.

   However, keep in mind that if you update the predefined components structure that `npx shadcn-ui@latest diff -c web` uses, you may lose the option to update the components automatically with . If you want to include test and story files, add them inside the `ui` folder next to your components and update your components with:

   ```bash
   npx shadcn-ui@latest diff -c web
   ```

## Get Started

With Shadcn-UI successfully integrated into your RedwoodJS project, you can now leverage its powerful components and styling options to build your web application. Explore the documentation and start creating beautiful user interfaces.

For more details, refer to the [Shadcn-UI documentation](https://ui.shadcn.com/docs).

Happy coding!
