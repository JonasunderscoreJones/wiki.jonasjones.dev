<script>
    import Header from "$lib/components/Header.svelte";
    import Footer from "$lib/components/Footer.svelte";
    import Navbar from "$lib/components/Navbar.svelte";
</script>

<div style="height:2rem" />
<Header />
<div class="container">
    <div class="column"><Navbar /></div>
    <div class="column content flex_grow" style="margin-left: 0;">
        <main>
            <slot />
            <!-- Please god forgive me -->
            <h1
                style="color: var(--container-background-color);margin:0;padding:0"
                class="unselectable"
            >
                YOU CANT SEE THIS YOU CANT SEE THIS YOU CANT SEE THIS YOU CANT
                SEE THIS
            </h1>
        </main>
    </div>
</div>

<Footer />
<div style="height:2rem" />
