<script>
    import { User, ArrowLeftEndOnRectangle } from "@steeze-ui/heroicons"
    import { Icon } from "@steeze-ui/svelte-icon"
    import Homeslice from "homeslice";
    // import Solana from "homeslice/lib/solana"
    import { onMount } from "svelte";
    import Menu from "./Menu.svelte";

    let wallets = []

    let h // homeslice
    let s // solana
    let w // wallet

    onMount(() => {
        h = new Homeslice()
        // s = new Solana()
        wallets = h.wallets
    })

    async function auth(wallet) {
        w = await h?.connect(wallet)
        let nfts = await s?.nftsOwnedBy(w.address)
        console.log(nfts)
    }

    async function deauth() {
        w = undefined
    }
</script>

<Menu label="{ w ? w.name : "Connect" } Wallet" icon={ w ? w.icon : "" }>
    {#if w}
        <button class="menubtn">
            <img class="icon" src={w.icon} alt="">
            {w.name} Wallet
        </button>
        <button class="menubtn">
            <Icon src={User} size="1rem" />
            Profile
        </button>
        <button class="menubtn danger" on:click={deauth}>
            <Icon src={ArrowLeftEndOnRectangle} size="1rem" />
            Log Out
        </button>
    {:else}
        {#each wallets as wallet}
            <button class="menubtn" on:click={() => { auth(wallet) }}>
                <img class="icon" src={wallet.icon} alt="">
                {wallet.name}
            </button>
        {/each}
    {/if}
</Menu>

<style lang="postcss">
    .icon {
        @apply h-4 aspect-square;
    }

    .btn {
        @apply bg-white hover:bg-blue-50 active:bg-blue-100
            border-gray-300 border rounded hover:border-blue-300 active:border-blue-400
            flex gap-2 items-center
            py-2 px-6
            hover:cursor-pointer;
    }

    .menubtn {
        @apply btn border-none rounded-none text-left hover:bg-gray-50;
    }

    .menubtn.danger {
        @apply text-red-600
    }
</style>