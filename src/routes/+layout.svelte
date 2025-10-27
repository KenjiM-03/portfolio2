<script lang="ts">
    import '../app.css';
    import Footer from "../components/Footer.svelte";
    import Header from "../components/Header.svelte";

    let y = $state(0);
    let innerHeight = $state(0);
    let innerWidth = $state(0);

    function goTop() {
        document.body.scrollIntoView({ behavior: "smooth" });
    }

    let { children } = $props();
</script>

<div class="relative flex-col max-w-[1400px] mx-auto w-full text-sm sm:text-base min-h-screen pointer-events-none">

    <div class="fixed bottom-0 right-0 duration-200 flex p-10 z-[10] pointer-events-auto">
        {#if y > 0}
            <button onclick={goTop} class="bg-purple-600 text-white p-3 rounded-full shadow-lg" aria-label="Scroll to top">
                <i class="fa-solid fa-arrow-up"></i>
            </button>
        {/if}
    </div>

    <div class="pointer-events-auto">
        <Header y={y}/>
        {@render children()}
        <Footer />
    </div>
</div>

<svelte:window bind:scrollY={y} bind:innerHeight bind:innerWidth />
