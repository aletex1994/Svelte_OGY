<script lang="ts">
  import svelteLogo from "./assets/svelte.svg";
  import { writable } from "svelte/store";
  import { setContext } from "svelte";
  import SnackProvider from "./lib/SnackProvider.svelte";
  import type { SnackBarProps } from "./lib/Types.svelte";
  // write a writable store
  let isOpen = writable(false);
  // write a writable array of snackbars with type SnackBarProps
  let snackBarArray = writable<SnackBarProps[]>([]);
  // set the context
  setContext("isOpen", isOpen);

  setContext("snackBarArray", snackBarArray);
  const addSnackBar = (snackbar: SnackBarProps) => {
    isOpen.set(true);
    // add the snackbar to snackBarArray
    snackBarArray.update((arr) => [...arr, snackbar]);
  };
</script>
<main>
  <SnackProvider>
    <div>
      <button
        on:click={() =>
          addSnackBar({
            layout: "oneLine",
            message: "This is a One Line Snack",
          })}>Stack One Line Snack</button
      >
      <button
        on:click={() =>
          addSnackBar({
            layout: "oneLineIcon",
            message: "This is a One Line Snack with an Icon",
            icon : svelteLogo
          })}>Stack One Line Icon </button
      >
    </div>
  </SnackProvider>
</main>
