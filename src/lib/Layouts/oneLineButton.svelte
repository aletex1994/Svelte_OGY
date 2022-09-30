<script lang="ts">
    export let message: string;
    export let action: any;
    export let actionText: string;
</script>
<div class="snackbar">
    <div class="container">
      <div class="textBox">
        <p>
          {message}
        </p>
      </div>
      <div>
        <button
          on:click={() => {
            action();
          }}
        >
          {actionText}
        </button>
      </div>
    </div>
  </div>