<script>
	let name = $state('');
</script>

<input bind:value={name} placeholder="enter your name" />
<p>Hello {name || 'stranger'}!</p>
