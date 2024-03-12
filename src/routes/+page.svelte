<!-- <h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p> -->

<script lang="js">
    import Header from "$lib/components/pageComponents/header.svelte";
	import Main from "$lib/components/pageComponents/main.svelte";
</script>

<div class="flex items-start justify-center" >
    <Header/>
    <main class="mt-20 w-full h-full max-w-5xl " >
        <Main/>
    </main>
</div>