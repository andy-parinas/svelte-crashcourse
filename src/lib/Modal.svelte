<script>
    import { createEventDispatcher } from "svelte";

    export let title = "Modal Title"


    const dispatch = createEventDispatcher()

    const close = () => {
        dispatch("close")
    }

    const submit = () => {
        dispatch('submit')
    }
</script>


<!-- svelte-ignore a11y-click-events-have-key-events -->
<div
    class="relative z-10"
    aria-labelledby="modal-title"
    role="dialog"
    aria-modal="true"
>
<div class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity" />

<div class="fixed z-10 inset-0 overflow-y-auto">
  <div
    class="flex items-center sm:items-center justify-center min-h-full p-4 text-center sm:p-0"
  >
    <div
      class="relative bg-white rounded-lg px-4 pb-4 text-left overflow-hidden 
        shadow-xl transform transition-all sm:my-8 sm:max-w-sm sm:w-full sm:p-6"
    >
    <h1 class="text-lg text-bold text-center">{title}</h1>
    <form class="mt-5" on:submit|preventDefault={submit}>
        <slot></slot>

        <div class="mt-10 flex justify-between items-center">
            <button on:click={close}
                class="px-2 py-1 border rounded bg-white hover:bg-gray-200">
             Close
            </button>
           <slot name="action-button" />
        </div>
  
    </form>
      


    </div>
  </div>
</div>
</div>