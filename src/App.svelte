<script lang="ts">
  import {writable} from 'svelte/store';
  import { setContext } from 'svelte';
	import SnackProvider from './lib/SnackProvider.svelte';
  import type { SnackBarProps } from './lib/Types.svelte';

	// write a writable store
  let isOpen = writable(false);
  // write a writable array of snackbars with type SnackBarProps
  let snackBarArray = writable<SnackBarProps[]>([]);
  // set the context
  setContext('isOpen', isOpen);

  setContext('snackBarArray', snackBarArray);
  const addSnackBar = (snackbar: SnackBarProps) => {
    isOpen.set(true);
    // add the snackbar to snackBarArray
    snackBarArray.update((arr) => [...arr, snackbar]);
  };
  function consoleLog() {
    console.log('hello');
  }
</script>

<main>
  <SnackProvider>
  <div>
      <button on:click={() => addSnackBar({layout:"oneLine",message:"This is a One Line Snack"})}>Stack One Line Snack</button>
      <button on:click={() => addSnackBar({layout:"oneLineButton",message:"This is a One Line Snack Button",actionText:"Click for action", action:consoleLog})}>Stack One Line Button Snack</button>
      <button on:click={() => addSnackBar({layout:"twoLine",message:"This is a Two Lines Snack, This is a Two Lines Snack, This is a Two Lines Snack"})}>Stack Two Line Snack</button>
  </div>
  <p class="read-the-docs">
    Click on the Vite and Svelte logos to learn more
  </p>
  </SnackProvider>
</main>
