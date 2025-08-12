<script lang="ts">
  import '../app.css';
  import Sidebar from '$lib/components/Sidebar.svelte';
  import { loadNotes } from '$lib/stores/notes';
  import { onMount } from 'svelte';

  let { children } = $props();

  onMount(() => {
    // Initialize notes when app starts
    loadNotes().catch((e) => console.error('Failed to load notes', e));
  });
</script>

<div class="container-app">
  <Sidebar />
  <div class="container-main">
    {@render children()}
  </div>
</div>
