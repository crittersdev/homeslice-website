<script>
    let cdnUrl = "https://homeslicedeliver.cdn/v1.0.1"
</script>

<div class="bg-zinc-950 text-white justify-center items-center flex flex-col h-screen w-screen">
    <img src="/homeslice.png" alt="">
    <h1>Homeslice</h1>
    <input type="text" class="mb-3 text-center w-96" value={cdnUrl} readonly>
    <div class="flex gap-1">
        {#each [
            [ "Source", "https://github.com/" ],
            [ "Download", "/download" ],
            [ "Demo", "/demo" ]
        ] as [ name, href ]}
            <a class="btn secondary" {href}>{name}</a>
        {/each}
    </div>
</div>

<!-- <style lang="scss">
    #banner {
        background-color: #050505;
        justify-content: center;
        flex-direction: column;
        align-items: center;
        color: white;
        display: flex;
        height: 100%;
        width: 100%;

        input {
            margin-bottom: 0.75rem;
            text-align: center;
            width: 350px;
        }

        div {
            display: flex;
            gap: 0.25rem;
        }
    }
</style> -->