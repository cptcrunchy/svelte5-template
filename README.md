# SvelteKit Template

_Almost_ everything you need to build a SvelteKit project.
Has many of the packages that I have used over the years for various projects.

## Installed Packages

 - [Bits-UI](https://github.com/huntabyte/bits-ui#readme)
 - [Chart.js](https://www.chartjs.org)
 - [Http-status-codes](https://github.com/prettymuchbryce/http-status-codes#readme)
 - [Iconify](https://github.com/iconify/iconify)
 - [KitRoutes](https://www.kitql.dev/docs/tools/06_vite-plugin-kit-routes#installation)
 - [Lucia-Auth](https://github.com/lucia-auth/lucia)
 - [Lucide](https://lucide.dev)
 - [Mode-watcher](https://github.com/svecosystem/mode-watcher#readme)
 - [Postcss](https://postcss.org/)
 - [Prisma](https://www.prisma.io)
 - [Shadcn-svelte](https://www.shadcn-svelte.com/)
 - [Superforms](https://superforms.rocks)
 - [Svelte-french-toast](https://github.com/kbrgl/svelte-french-toast#readme)
 - [Tailwind](https://tailwindcss.com)
 - [Vite](https://vitejs.dev)
 - [Zod](https://zod.dev)


## Developing
```bash
# Created a convenient helper script to add new shadcn-svelte components
npm shadd <component>
# OR
pnpm shadd <component>
# OR
bun shadd <component>

```

### Aliases
 I added some helpful aliases after learning / failing in past projects.

`svelte.config.js`
 ```js
 /** @type {import('@sveltejs/kit').Config} */
const config = {
	// Consult https://kit.svelte.dev/docs/integrations#preprocessors
	// for more information about preprocessors
	preprocess: [vitePreprocess({})],

	kit: {
		// adapter-auto only supports some environments, see https://kit.svelte.dev/docs/adapter-auto for a list.
		// If your environment is not supported, or you settled on a specific environment, switch out the adapter.
		// See https://kit.svelte.dev/docs/adapters for more information about adapters.
		adapter: adapter(),
    alias: {
      $assets: 'src/lib/assets',
      $base: 'src/*',
      $components: 'src/lib/components',
      $client: 'src/lib/client',
      $schemas: 'src/lib/schemas',
      $server: 'src/lib/server',
    }
	}
};
 ```
  - `$base` - I mainly use this as a convenience for the app.css file. It really helps with deeply nested layouts. So having:
  ```js
  // Replaces:
  import "../app.css" || "../../../app.css"
  // With:
  import "$base/app.css"
  ```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://kit.svelte.dev/docs/adapters) for your target environment.
