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
  
  <div class="m-5">
        <h1 class="text-2xl text-center mt-10">List of Users</h1>
        {#each getUsers() as user, i}
        <div class="flex items-center my-4 bg-white border 
                    p-2 rounded-lg shadow-md hover:shadow-lg cursor-pointer">
            <p class="mr-4 w-10">{i + 1}</p>
            <img class="rounded-full w-14 mr-5" src="{user.image}" alt="" srcset="">
            <p class="mr-4 w-40">{user.name}</p>
            <p class="w-20">{user.email}</p>
        </div>
        {:else}
            <h2 class="text-xl text-center mt-10">No Users Found</h2>
        {/each}  
  </div>