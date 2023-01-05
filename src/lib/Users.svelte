<script>
    import User from "./User.svelte";
    import user1 from '../assets/images/user1.png'


    const users = [
        {
            image: user1,
            name: "John Doe",
            email: "john@email.com"
        },
        {
            image: user1,
            name: "Steve McQueen",
            email: "steve@email.com"
        },
        {
            image: user1,
            name: "Bill Gates",
            email: "bill@email.com"
        }
    ]


    const getUsers = () => {
        return users
    }

  </script>
  
  <div class="m-5">
        <h1 class="text-2xl text-center mt-10">List of Users</h1>
        {#each getUsers() as user, i}
        <User user={user} index={i} />
       
        {:else}
            <h2 class="text-xl text-center mt-10">No Users Found</h2>
        {/each}  
  </div>