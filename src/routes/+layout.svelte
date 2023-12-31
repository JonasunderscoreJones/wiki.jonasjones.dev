<script>
    import Header from "$lib/components/Header.svelte";
    import Footer from "$lib/components/Footer.svelte";
    import Navbar from "$lib/components/Navbar.svelte";
</script>

<Header />
<div class="container">
    <div class="column box-shadow"><Navbar /></div>
    <div class="column box-shadow content flex_grow">
        <main>
            <slot />
        </main>
    </div>
</div>

<Footer />
