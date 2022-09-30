<script>
    import { getContext, setContext } from 'svelte'
    import ChildComponent from './ChildComponent.svelte';
    const userDetails = getContext('user-details')

    const userDetails2 = { username: 'Andreas@childComponent.com', islogin: 'yes' };
    setContext('user-details2', userDetails2 )

</script>

<div>
    <div>
        <strong>User Name:</strong> { userDetails.username }
    </div>

    <div>
        <strong>User Login Status:</strong> { userDetails.islogin }
    </div>
    <div>
      <hr>
        <ChildComponent />
    </div>

</div>