<script>
	let notes = [
		{
			id: 1,
			title: 'Sweetest framework ever',
			category: 'School',
			content: 'This is the content of this note'
		},
		{
			id: 2,
			title: 'Awesome framework ever',
			category: 'Web',
			content: 'This is the best framework ever'
		}
	];
	let data = {
		title: '',
		category: '',
		content: '',
		id: null
	};

	let addNote = () => {
		const newNote = {
			id: notes.length + 1,
			title: data.title,
			category: data.category,
			content: data.content
		};
		notes = notes.concat(newNote);
		data = {
			id: null,
			title: '',
			category: '',
			content: ''
		};
	};
	let deleteNote = (id) => {
		console.log(id);
		notes = notes.filter((note) => note.id !== id);
	};
</script>

<section class="container mx-auto px-8 py-6">
	<div class="flex lg:flex-row flex-col space-y-4 space-x-4">
		<div class="flex flex-col h-5/6 lg:w-1/2 p-4  shadow-md">
			<h2 class="text-4xl ">Add Note</h2>
			<form class="py-3 w-full" action="">
				<div class="relative mb-4">
					<label for="title" class="leading-7 text-sm text-gray-600">Title</label>
					<input
						bind:value={data.title}
						type="text"
						name="title"
						class="w-full bg-white rounded border border-gray-300  focus:ring-2 focus:ring-indigo-200 text-base outline-none text-gray-700 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out"
					/>
				</div>
				<div class="relative inline-block w-full text-gray-600">
					<select
						class="w-full h-10 pl-3 pr-6 text-base placeholder-gray-600 border rounded-sm appearance-none focus:ring-2 focus:ring-indigo-200"
						placeholder="Regular input"
						bind:value={data.category}
					>
						<option selected disaabled>Selecet a category</option>
						<option value="School">School</option>
						<option value="Church">Church</option>
						<option value="Home">Web</option>
					</select>
					<div class="absolute inset-y-0 right-0 flex items-center px-2 pointer-events-none">
						<svg class="w-4 h-4 fill-current" viewBox="0 0 20 20"
							><path
								d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
								clip-rule="evenodd"
								fill-rule="evenodd"
							/></svg
						>
					</div>
				</div>
				<div class="relative mb-4">
					<label for="message" class="leading-7 text-sm text-gray-600">Message</label>
					<textarea
						bind:value={data.content}
						id="message"
						name="message"
						class="w-full bg-white rounded border border-gray-300 focus:border-indigo-500 focus:ring-2 focus:ring-indigo-200 h-32 text-base outline-none text-gray-700 py-1 px-3 resize-none leading-6 transition-colors duration-200 ease-in-out"
					/>
				</div>
				<button
					on:click|preventDefault={addNote}
					class="inline-flex text-white bg-green-500 border-0 py-1 px-4 focus:outline-none hover:bg-green-600 rounded"
					>Submit</button
				>
			</form>
		</div>

		<div class=" p-4 lg:w-1/2">
			{#each notes as note}
				<div class="flex flex-col shadow-md p-4">
					<h2 class="py-3 text-4xl text-md border-b-2">{note.category}</h2>
					<div class="py-2">
						<h2 class="text-2xl">{note.title}</h2>
						<p class="py-2">{note.content}</p>
					</div>
					<div class="py-2  flex space-x-2">
						<button
							class="inline-flex text-white bg-yellow-500 border-0 py-1 px-4 focus:outline-none hover:bg-yellow-600 rounded"
							>Edit</button
						>
						<button
							on:click={deleteNote(note.id)}
							class="inline-flex text-white bg-red-500 border-0 py-1 px-4 focus:outline-none hover:bg-red-600 rounded"
							>Delete</button
						>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>
