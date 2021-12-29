<main class="container mx-auto px-6 lg:px-14 py-4">
	<h1
		class="text-center py-8 font-extrabold text-transparent text-5xl bg-clip-text bg-gradient-to-br from-blue-400 to-red-600"
	>
		About Noty
	</h1>
    <img src="static/noty.gif">
	<div
		class="bg-[#4c4f64] p-6 rounded-lg duration-300  transition ease-in-out delay-150 hover:-translate-y-1 hover:scale-110 text-white py-3  mr-auto ml-auto prose prose-2xl text-lg lg:text-2xl max-w-6xl"
	>
		<p>
			This is project is <span><a class="text-blue-500" href="https://boadzie1.netlify.app">my</a></span> way of show casing my web developement skills using the awesome
			SvelteKit framework and its companion Tailwindcss framework. These two together make building web applications fast and easy. <span
				>The application shows CRUD(Create, Read, Update, Delete) functionality for a note-taking app.  
		</p>
		<div class="text-2xl py-3">
			The application has the folowing features;
			<ul class="mr-2 list-disc px-4 text-cyan-100">
				<li>A note listing</li>
				<li>The ability to create a note</li>
				<li>The ability to edit/update a note</li>
                <li>The ability to delete a note</li>
			</ul>
		</div>
	</div>
</main>

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

Before creating a production version of your app, install an [adapter](https://kit.svelte.dev/docs#adapters) for your target environment. Then:

```bash
npm run build
```

> You can preview the built app with `npm run preview`, regardless of whether you installed an adapter. This should _not_ be used to serve your app in production.
