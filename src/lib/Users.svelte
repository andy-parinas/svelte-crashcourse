<script>
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
  
  <div>
        <h1 class="text-2xl text-center mt-10">List of Users</h1>
        {#each getUsers() as user}
        <div class="flex items-center my-4">
            <img class="rounded-full w-20 mr-5" src="{user.image}" alt="" srcset="">
            <p>{user.name}</p>
        </div>
        {:else}
            <h2>No Users Found</h2>
        {/each}  
  </div>