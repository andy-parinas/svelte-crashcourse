<script>
    import { createEventDispatcher } from "svelte";


    export let user;
    export let index;

    const dispatch = createEventDispatcher()

    const remove = () => {
        dispatch('remove', user.id)
    }

</script>

 <div class="flex items-center my-4 bg-white border 
        p-2 rounded-lg shadow-md hover:shadow-lg cursor-pointer relative">
    
    <button on:click={remove}
        class="absolute right-0 top-0 -mt-3 
        rounded-full w-5 h-5 bg-red-300 text-white text-sm text-center hover:bg-red-700">X</button>

    <p class="mr-4 w-10">{index + 1}</p>
    <img class="rounded-full w-14 mr-5" src="{user.image}" alt="" srcset="">
    <p class="mr-4 w-40">{user.name}</p>
    <p class="w-20">{user.email}</p>
</div>