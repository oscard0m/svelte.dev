<script>
	let questions = [
		{ id: 1, text: `Where did you go to school?` },
		{ id: 2, text: `What is your mother's name?` },
		{ id: 3, text: `What is another personal fact that an attacker could easily find with Google?` }
	];

	let selected = $state();

	let answer = $state('');

	function handleSubmit(event) {
		event.preventDefault();
		alert(`answered question ${selected.id} (${selected.text}) with "${answer}"`);
	}
</script>

<h2>Insecurity questions</h2>

<form onsubmit={handleSubmit}>
	<select bind:value={selected} onchange={() => (answer = '')}>
		{#each questions as question}
			<option value={question}>
				{question.text}
			</option>
		{/each}
	</select>

	<input bind:value={answer} />

	<button disabled={!answer} type="submit"> Submit </button>
</form>

<p>selected question {selected ? selected.id : '[waiting...]'}</p>

<style>
	input {
		display: block;
		width: 500px;
		max-width: 100%;
	}
</style>
