<script>
import { getContext } from 'svelte';
import Snack from './Snack.svelte';
let name = getContext('name');

</script>
<div>
		<slot/>
    {#if $name == 'Mike'}
      <Snack/>
    {/if}
</div>