<script lang="ts">
  import { writable } from "svelte/store";
  import { setContext, onMount } from "svelte";
  import type { SnackBarProps, ContextType } from "../lib/Types.svelte";

  // write a writable store
  let isOpen = writable(false);
  // write a writable array of snackbars with type SnackBarProps
  let snackBarArray = writable<SnackBarProps[]>([]);
  const addSnackBar = (snackbar: SnackBarProps) => {
    isOpen.set(true);
    // add the snackbar to snackBarArray
    snackBarArray.update((arr) => [...arr, snackbar]);
  };

  // set the context
  onMount(() => {
    setContext<ContextType>("SnackContext", {
      isOpen,
      snackBarArray,
      addSnackBar,
      providerPosition: "bottom-right",
    });
  });
</script>
<div>
  <slot />
</div>