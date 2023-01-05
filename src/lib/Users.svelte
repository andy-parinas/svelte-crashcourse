<script>
    import User from "./User.svelte";
    import user1 from '../assets/images/user1.png'
    import FilterUser from "./FilterUser.svelte";


    const users = [
        {
            image: user1,
            name: "John Doe",
            email: "john@email.com",
            active: true
        },
        {
            image: user1,
            name: "Steve McQueen",
            email: "steve@email.com",
            active: false
        },
        {
            image: user1,
            name: "Bill Gates",
            email: "bill@email.com",
            active: true
        }
    ]

    
    const getUsers = () => {
        return users
    }

    let filteredUsers = users
    const filter = (event) => {
        const filter = event.detail

        filteredUsers = users.filter((user) => {
            if(filter === 'all'){
                return true
            }else {
                const active = filter === 'active'
                return user.active === active
            }

        })
    }

  </script>
  
  <div class="m-5">
        <h1 class="text-2xl text-center mt-10">List of Users</h1>
        <FilterUser on:filter={filter} />
     
        {#each filteredUsers as user, i}
        <User user={user} index={i} />
       
        {:else}
            <h2 class="text-xl text-center mt-10">No Users Found</h2>
        {/each}  
  </div>