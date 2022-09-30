<script lang="ts">
  import SnackBar from './SnackBar.svelte'
</script>
<slot/>

<SnackBar 
durationms={5000}
maxSnack={3}
position="top-right"
/>

