<script>
    import Header from "$lib/components/Header.svelte";
    import Footer from "$lib/components/Footer.svelte";
    import Navbar from "$lib/components/Navbar.svelte";

</script>

<div style="height:2rem" />
<Header />
<div class="container">
    <div class="column"><Navbar /></div>
    <div class="column content flex_grow">
        <main>
            <slot />
        </main>
    </div>
</div>

<Footer />
<div style="height:2rem" />
