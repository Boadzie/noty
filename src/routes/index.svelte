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
	let isEdit = false;
	let editNote = (note) => {
		isEdit = true;
		data = note;
	};

	let updateNote = () => {
		isEdit = !isEdit;
		let noteDB = {
			title: data.title,
			category: data.category,
			content: data.content,
			id: data.id
		};
		let objIndex = notes.findIndex((obj) => obj.id == noteDB.id);
		console.log('Before update: ', notes[objIndex]);
		notes[objIndex] = noteDB;

		data = {
			id: null,
			title: '',
			category: '',
			content: ''
		};
	};
</script>

<section class="container mx-auto px-4 lg:px-8 py-6">
	<div class="flex lg:flex-row flex-col  space-y-4 lg:space-x-4">
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
						<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
					</div>
				</div>
				<div class="relative mb-4">
					<label for="content" class="leading-7 text-sm text-gray-600">Content</label>
					<textarea
						bind:value={data.content}
						id="content"
						name="content"
						class="w-full bg-white rounded border border-gray-300 focus:border-indigo-500 focus:ring-2 focus:ring-indigo-200 h-32 text-base outline-none text-gray-700 py-1 px-3 resize-none leading-6 transition-colors duration-200 ease-in-out"
					/>
				</div>
				{#if isEdit === false}
					<button
						on:click|preventDefault={addNote}
						class="inline-flex text-white bg-green-500 border-0 py-1 px-4 focus:outline-none hover:bg-green-600 rounded"
						>Add Note</button
					>
				{:else}
					<button
						on:click|preventDefault={updateNote}
						class="inline-flex text-white bg-green-500 border-0 py-1 px-4 focus:outline-none hover:bg-green-600 rounded"
						>Update
					</button>
				{/if}
			</form>
		</div>

		<div class="w-full p-4 lg:w-1/2">
			{#each notes as note}
				<div class="flex flex-col shadow-md w-full p-4">
					<h2 class="py-3 text-4xl text-md border-b-2">{note.category}</h2>
					<div class="py-2">
						<h2 class="text-2xl">{note.title}</h2>
						<p class="py-2">{note.content}</p>
					</div>
					<div class="py-2  flex space-x-2">
						<button
							on:click={editNote(note)}
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
