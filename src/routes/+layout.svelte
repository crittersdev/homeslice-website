<script>
    import Navbar from "$lib/Navbar.svelte";
    import "../app.scss";
</script>

<svelte:head>
    <title>Homeslice</title>

    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&amp;display=swap" rel="stylesheet" />
</svelte:head>

<Navbar />

<slot></slot>