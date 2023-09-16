<!-- DarkModeSwitcher.svelte -->
<script>
  import { isDarkMode } from '$lib/stores/darkModeStore.js';

  function toggleDarkMode() {
    $isDarkMode = !$isDarkMode;
    document.body.classList.toggle("dark-mode", $isDarkMode);
  }
</script>

<button on:click={toggleDarkMode}>
  <img src={$isDarkMode ? "/dark.svg" : "/light.svg"} alt="Dark Mode">
</button>

<div class:invert={$isDarkMode} class="content">
  <!-- Your content here -->
</div>

<style>
  body {
    transition: background-color 0.5s, color 0.5s;
  }

  button {
    background-color: transparent;
    border: none;
    cursor: pointer;
  }

  button.dark {
    color: #fff; /* Dark mode text color */
    background-color: #333; /* Dark mode background color */
  }

  .content {
    /* Your default content styles here */
  }

  .invert {
    filter: invert(1); /* Apply the invert filter for dark mode */
  }
</style>
