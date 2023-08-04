# SvelteKit App | Chromium Extension

[github.com/SvelteKitApp/sveltekitapp-chromium-extension-tpl-sveltekit](https://github.com/SvelteKitApp/sveltekitapp-chromium-extension-tpl-sveltekit)

- генерация проекта [`create-svelte v5`](https://github.com/sveltejs/kit/tree/master/packages/create-svelte).

```bash
$node --version
18.15.0
$npm create  svelte@latest sveltekitapp-chromium-extension-tpl-sveltekit
Need to install the following packages:
  create-svelte@5.0.4
Ok to proceed? (y) y

create-svelte version 5.0.4

┌  Welcome to SvelteKit!
│
◇  Which Svelte app template?
│  Skeleton project
│
◇  Add type checking with TypeScript?
│  Yes, using TypeScript syntax
│
◇  Select additional options (use arrow keys/space bar)
│  Add ESLint for code linting, Add Prettier for code formatting, Add Vitest for unit testing
│
└  Your project is ready!
$cd sveltekitapp-chromium-extension-tpl-sveltekit
$git init && git add -A && git commit -m ":star: Start project"
```

- установка [svelte adapter static](https://github.com/sveltejs/kit/tree/master/packages/adapter-static) в соотвествии с [инсктрукцией](https://kit.svelte.dev/docs/single-page-apps#usage)

```bash
$npm uninstall -D @sveltejs/adapter-auto
$npm i -D @sveltejs/adapter-static
```

```diff
# svelte.config.js
-import adapter from '@sveltejs/adapter-auto';
+import adapter from '@sveltejs/adapter-static';
 import { vitePreprocess } from '@sveltejs/kit/vite';
# ...
-		adapter: adapter()
+		adapter: adapter({
+			fallback: 'index.html'
+		}),
+    appDir: 'ext'
 	}
 };
```

### Добавление TailwindCSS

```bash
$npx svelte-add@latest tailwindcss
➕ Svelte Add (Version 2023.06.280.00)
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://kit.svelte.dev/docs/adapters) for your target environment.
