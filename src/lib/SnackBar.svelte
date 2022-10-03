<script lang="ts">
import CallTheSnack from './CallTheSnack.svelte';
import { getContext } from 'svelte';

import { Layouts } from './Layout.svelte';
import type { ContextType } from './Types.svelte';

// get the context
const context : ContextType = getContext('Snackbar');

let isOpen = context.isOpen;
let snackBarArray = context.snackBarArray;


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
<CallTheSnack></CallTheSnack>