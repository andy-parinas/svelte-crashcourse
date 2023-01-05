<script>
    export let user;
    export let index;
</script>

 <div class="flex items-center my-4 bg-white border 
        p-2 rounded-lg shadow-md hover:shadow-lg cursor-pointer">
    <p class="mr-4 w-10">{index + 1}</p>
    <img class="rounded-full w-14 mr-5" src="{user.image}" alt="" srcset="">
    <p class="mr-4 w-40">{user.name}</p>
    <p class="w-20">{user.email}</p>
</div>