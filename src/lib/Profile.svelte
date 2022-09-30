<script>

  import { setContext } from 'svelte'
  import ContextComponent from "./ContextComponent.svelte";

  const userDetails = { username: 'Alessandro@example.com', islogin: 'yes' };

  setContext('user-details', userDetails )


</script>

  <p> Context Example. </p>
  <hr/>

  <div>
      <br />
      <ContextComponent />
  </div>
