<script lang="ts">
import { setContext } from 'svelte';
import { writable } from 'svelte/store';

import type { SnackBarType } from './Types.svelte';

import SnackBar from './SnackBar.svelte';

export let durationms : number;
export let maxSnack : number;
export let position : string;

//Default Values
durationms = durationms || 2000;
maxSnack = maxSnack || 3;
position = position || "top-right";

//Context
setContext("SnackbarProvider", {
  durationms,
  maxSnack,
  position
});

// write a writable store
let isOpen = writable(false);
// write a writable array of snackbars with type SnackBarProps
let snackBarArray = writable<SnackBarType[]>([]);
const addSnackBar = (snackbar: SnackBarType) => {
  isOpen.set(true);
  // add the snackbar to snackBarArray
  snackBarArray.update((arr) => [...arr, snackbar]);
  // remove the first item from snackBarArray after durationms
  setTimeout(() => {
    snackBarArray.update((arr) => arr.slice(1));
  }, durationms);
 
};


// set the context
setContext("Snackbar", {
  isOpen,
  snackBarArray,
  addSnackBar
});

</script>

<slot />
<SnackBar></SnackBar>
<div>HELLO</div>