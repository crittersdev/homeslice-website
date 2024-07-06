<div class="bg-white flex justify-between items-center fixed px-20 h-12 right-0 left-0 top-0">
    <div>
        <img src="/homeslice.png" height="25px" alt="">
        <a href="/">Homeslice</a>
    </div>

    <div>
        {#each [
            [ "GitHub", "https://github.com/" ],
            [ "Demo", "/demo" ],
            [ "Documentation", "/docs" ]
        ] as [ name, href ]}
            <a class="btn" {href}>{name}</a>
        {/each}
    </div>
</div>

<style lang="scss">


    :global(body) {
        margin-top: 3rem;
    }
</style>