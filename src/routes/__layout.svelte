<script>
	import '../app.css';
</script>
<nav class="p-6 w-full border-b-2 shadow-md bg-[#4c4f64]">
	<ul class="flex text-white text-2xl lg:mx-4 font-bold flex-wrap lg:justify-between justify-center items-center space-x-4 -m-2">
		<li class="font-extrabold uppercase tracking-widest text-transparent bg-clip-text bg-gradient-to-br from-blue-400 to-red-600"><a href="/">Noty</a></li>
		<div class="flex space-x-4">
			<li><a href="/">Home</a></li>
		<li><a href="/about">About</a></li>
		</div>
	</ul>
</nav>
<main>
	<slot />
</main>

<style>
	:global(html) {
		font-family: 'Indie Flower', cursive;
		font-size: 20px;
		background-color: #edf3f3;
		background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 80 80' width='80' height='80'%3E%3Cpath fill='%23c6c6c6' fill-opacity='0.9' d='M14 16H9v-2h5V9.87a4 4 0 1 1 2 0V14h5v2h-5v15.95A10 10 0 0 0 23.66 27l-3.46-2 8.2-2.2-2.9 5a12 12 0 0 1-21 0l-2.89-5 8.2 2.2-3.47 2A10 10 0 0 0 14 31.95V16zm40 40h-5v-2h5v-4.13a4 4 0 1 1 2 0V54h5v2h-5v15.95A10 10 0 0 0 63.66 67l-3.47-2 8.2-2.2-2.88 5a12 12 0 0 1-21.02 0l-2.88-5 8.2 2.2-3.47 2A10 10 0 0 0 54 71.95V56zm-39 6a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm40-40a2 2 0 1 1 0-4 2 2 0 0 1 0 4zM15 8a2 2 0 1 0 0-4 2 2 0 0 0 0 4zm40 40a2 2 0 1 0 0-4 2 2 0 0 0 0 4z'%3E%3C/path%3E%3C/svg%3E");
	}
</style>
