<script>
  import { getContext } from 'svelte'

  const userDetails2 = getContext('user-details2')

  

</script>

<div>
  <div>
      <strong>User Name From Child:</strong> { userDetails2.username }
  </div>

  <div>
      <strong>User Login Status From Child:</strong> { userDetails2.islogin }
  </div>

</div>