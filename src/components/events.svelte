<script>
	let events = [];

	const getEventsFromAPI = async () => {
		const response = await fetch('https://api.opensourceatillinois.com/events');
		events = await response.json();
	};

	getEventsFromAPI();
</script>

<div class="flex flex-row flex-wrap mx-auto justify-center">
	{#each events as event}
		<div class="flex w-96 flex-col items-center bg-gray-300 p-5 m-5 rounded-lg justify-between">
			<div class="text-lg font-bold text-center">
				{event.name}
			</div>
			<div>
				{event.when}
			</div>
		</div>
	{/each}
</div>
