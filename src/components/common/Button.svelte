<script lang="ts">
    import {createEventDispatcher} from 'svelte'
    import {ButtonSize} from "./buttonTypes"

    export let size: ButtonSize = ButtonSize.Medium

    export let label = 'Button'

    export let backgroundColor: string = 'bg-blue-300'

    export let loading: boolean = false

    export let classes: string = ''

    $: loadingStyling = loading ? 'loading' : ''

    const dispatch = createEventDispatcher()

    function onClick(event) {
        dispatch('click', event)
    }
</script>

    <button
            on:click={onClick}
            class={['p-2 rounded-xl text-white', size, backgroundColor, loadingStyling,
            classes].join(' ')}
    >
        {label}
    </button>
