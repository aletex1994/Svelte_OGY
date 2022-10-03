<script lang="ts">
import { getContext } from 'svelte';
import svelteLogo from '../assets/svelte.svg'

import type { ContextType } from './Types.svelte';

let context :  ContextType = getContext('Snackbar');
let varArr = context.snackBarArray;
</script>
<div>
  <button on:click={() => context.addSnackBar({message: "Hello this is oneLine", layout: "oneLineIcon", icon:svelteLogo})}>Add Snack</button>
  <button on:click={() => console.log($varArr)}>LOGGG</button>
</div>