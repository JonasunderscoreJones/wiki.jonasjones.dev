<script>
	import Header from '$lib/components/Header.svelte';
    import Footer from '$lib/components/Footer.svelte';
    import Navbar from '$lib/components/Navbar.svelte';
    import { isDarkMode } from '$lib/stores/darkModeStore';
    import '$lib/styles/style.css';

    //change background color based on dark mode
    //$: document.body.style.backgroundColor = $isDarkMode ? '#fff' : '#16181c';

</script>
<body style="background-color: {$isDarkMode ? '#fff' : '#16181c'};padding:0">
    <div style="height:2rem"></div>
    <Header />
    <div class="container" class:invert={$isDarkMode}>
        <div class="column"><Navbar /></div>
        <div class="column content flex_grow" style="margin-left: 0;">
            <main>
                <slot />
                <!-- Please god forgive me -->
                <h1 style="color: #26292f;margin:0;padding:0" class="unselectable">YOU CANT SEE THIS YOU CANT SEE THIS YOU CANT SEE THIS YOU CANT SEE THIS</h1>
            </main>
        </div>
    </div>



    <div class:invert={$isDarkMode}>
        <Footer />
    </div>
    <div style="height:2rem"></div>
</body>

