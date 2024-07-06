<script>
	import { page } from '$app/stores';

    let customMessages = {
        "404": "Looks like we couldn't find that for you!"
    }
</script>

<div class="flex flex-col justify-center items-center h-screen w-screen">
    <h1>{$page.status}</h1>
    <h2>{customMessages[$page.status] || $page.error.message}</h2>
    <a href="/">Go Home</a>
</div>