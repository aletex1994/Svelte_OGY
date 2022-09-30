<script lang="ts">
  import { getContext, setContext, onMount } from "svelte";
  import { Layouts } from "./Layout.svelte";
  import type { ContextType, SnackProviderProps } from "./Types.svelte";

  let context : ContextType  = getContext("snackContext");
  let snackBarArray = context.snackBarArray;
  let isOpen = context.isOpen;

  export let durationms: number;
  export let maxSnack: number;
  export let position: string;

  let SnackProvider = {
    durationms: durationms || 3000,
    maxSnack: maxSnack || 3,
    position: position || "bottom-right",
  } as SnackProviderProps;

</script>

<div>
  <slot />
  {#if $isOpen === true && $snackBarArray.length > 0}
    {#each $snackBarArray as snackbar}
      <div class="snackContainer">
        {#if snackbar.layout === "oneLine"}
          <Layouts.oneLine message={snackbar.message} />
        {/if}
        {#if snackbar.layout === "twoLines"}
          <Layouts.twoLines message={snackbar.message} />
        {/if}
        {#if snackbar.layout === "oneLineIcon"}
          <Layouts.oneLineIcon message={snackbar.message} icon={snackbar.icon} />
        {/if}
        {#if snackbar.layout === "oneLineButton"}
          <Layouts.oneLineButton
            message={snackbar.message}
            actionText={snackbar.actionText}
            action={snackbar.action} />
        {/if}
        {#if snackbar.layout === "twoLinesButton"}
          <Layouts.twoLinesButton
            message={snackbar.message}
            actionText={snackbar.actionText}
            action={snackbar.action} />
        {/if}
      </div>
    {/each}
  {/if}
</div>
