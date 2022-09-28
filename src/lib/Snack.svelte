<script>
	import { getContext } from 'svelte';
	let isOpen= getContext('isOpen');
</script>
	
<div>
	<p>SNACKBAR {$isOpen}</p>
</div>