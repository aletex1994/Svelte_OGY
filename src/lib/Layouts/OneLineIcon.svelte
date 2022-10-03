<script lang="ts">
    export let message: string;
    export let icon: string; 
</script>
<div class="snackbar">
    <div class="container">
      <div class="svgBox">
        <img src={icon} alt="icon" />
      </div>
      <div>
        <p>
        {message}
        </p>
      </div>
    </div>
  </div>