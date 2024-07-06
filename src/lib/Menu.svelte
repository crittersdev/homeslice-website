<script>
    import { ChevronDown } from "@steeze-ui/heroicons"
    import { Icon } from "@steeze-ui/svelte-icon"

    export let label = "Menu"
    export let icon = ""

    let open = false
</script>

<button class="relative btn" on:click={() => { open = !open }}>
    {#if icon && icon !== ""}<img class="icon" src={icon} alt="">{/if}
    {label}
    <Icon src={ChevronDown} size="1rem" />
    {#if open}
        <div class="absolute left-0 top-[calc(100%+0.5rem)] w-[max-content]
                    bg-white
                    border-gray-300 border rounded
                    py-2
                    flex flex-col
                    open-menu">
            <slot />
        </div>
    {/if}
</button>