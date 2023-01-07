<script>
    import {createEventDispatcher} from 'svelte'
    const dispatch = createEventDispatcher()

    const filter = (e) => {
        dispatch('filter', e.target.value)
    }
</script>


<div class="flex items-center">
    <h3 class="mr-4">Select User Type</h3>
    <select on:change={filter}
        name="user-filter" 
        class="border rounded-lg px-5 py-1">
        <option value="all">All</option>
        <option value="active">Active</option>
        <option value="inactive">Inactive</option>
    </select>
</div>