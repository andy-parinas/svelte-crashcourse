<script>
    import { createEventDispatcher } from "svelte";
    
    import Modal from "./Modal.svelte";
    import user1 from '../assets/images/user1.png'

    let showModal = false

    const newUser = {
        image: user1,
        name: "",
        email: "",
        active: true
    }

    const dispatch = createEventDispatcher()

    const createUser = () => {
       dispatch('createUser', newUser)
       showModal = false
    }

    const handleTextField = (e) => {
        newUser[e.target.name] = e.target.value
    }

    const handleEmailField = (e) => {
        newUser.email = e.target.value
    }

    const handleRadioField = (e) => {
        newUser.active = e.target.value === 'true' ? true : false
    }

</script>

<div>
    <button on:click={() => (showModal = true)}
     class="px-2 py-1 text-sm bg-blue-600 text-white rounded-lg shadow-sm
        hover:bg-blue-800 hover:shadow-lg">
        New User
    </button>

    {#if showModal}
        <Modal on:submit={createUser}
            on:close={() => (showModal = false)} title="Create New User" >
            <div class="py-1 px-2 my-4">
                <label class="w-2/12 mr-1"
                    for="name">Name</label>
                <input on:change={handleTextField}
                    class="px-2 py-1 rounded border w-full"
                    type="text" name="name" >
            </div>
            <div class="py-1 px-2 my-4">
                <label class="w-2/12 mr-1"
                    for="name">Email</label>
                <input on:change={handleEmailField}
                    class="px-2 py-1 rounded border w-full"
                    type="text" name="email" >
            </div>
            <div class="px-2 py-1 my-4 flex justify-between">
                <p>Active: </p>
                <div class="flex items-center"> 
                    <label for="yes">Yes</label>
                    <input on:change={handleRadioField}
                        class="px-2 py-1 mx-5"
                        type="radio" name="active" id="yes" value="true">
                    <label for="no">No</label>
                    <input on:change={handleRadioField}
                        class="px-2 py-1 mx-5"
                        type="radio" name="active" id="no" value="false">
                </div>
            </div>
            <pre>{newUser.name }</pre>
            <button slot="action-button"  type="submit"
                class="px-2 py-1 bg-blue-700 text-white rounded-lg">Create</button>
        </Modal>    
    {/if}
</div>