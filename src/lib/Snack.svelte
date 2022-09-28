<script>
	import { getContext } from 'svelte';

	let name = getContext('name');

</script>
<div>
	<p>SNACKBAR {$name}</p>
</div>