<script lang="ts">
  import { getContext } from "svelte";
  import type { SnackBarProps } from "./Types.svelte";
  import { Layouts } from "./Layouts.svelte";
  let isOpen: any = getContext("isOpen");
  let snackBarArray: any = getContext("snackBarArray");
</script>

<div>
  <slot />
  {#if $isOpen === true && $snackBarArray.length > 0}
    {#each $snackBarArray as snackbar}
      <div class = "snackContainer">
        {@html Layouts[snackbar.layout](snackbar)}
      </div>
    {/each}
  {/if}
</div>