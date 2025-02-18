<script lang="ts">
    import "../../app.css";
    import Footer from "$lib/components/layout/GlobalFooter.svelte";
    import Header from "$lib/components/layout/HomeHeader.svelte";
    let { children } = $props();
</script>

<div class="min-h-screen flex flex-col">
    <main class="flex-grow">
        <Header />
        {@render children()}
        <Footer />
    </main>
</div>
