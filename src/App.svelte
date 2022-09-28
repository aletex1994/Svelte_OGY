<script lang="ts">
  import {writable} from 'svelte/store';
  import { setContext } from 'svelte';
	import SnackProvider from './lib/SnackProvider.svelte';
	
	let name = writable('John');
	setContext('name',name);
	
	function changeName(){
		$name = 'Mike';
	}
</script>

<main>
  <SnackProvider>
  <div>
      <h1>My name is: {$name}</h1>
      <button on:click={changeName}>Change Name</button>
  </div>

  <p class="read-the-docs">
    Click on the Vite and Svelte logos to learn more
  </p>
  </SnackProvider>
</main>
