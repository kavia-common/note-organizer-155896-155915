<script lang="ts">
  import NoteEditor from '$lib/components/NoteEditor.svelte';
</script>

<svelte:head>
  <title>Notes</title>
  <meta name="description" content="Create, edit, search, and organize your notes." />
</svelte:head>

<div class="page">
  <div class="page__content">
    <slot />
    <section class="content">
      <!-- Note editor -->
      <div class="editor-wrap">
        <div class="tip">Tip: Use the sidebar to switch notes or search.</div>
        <div class="editor-area">
          <NoteEditor />
        </div>
      </div>
    </section>
  </div>
</div>

<style>
  .page {
    display: flex;
    min-height: 100%;
  }
  .page__content {
    flex: 1;
    display: flex;
    flex-direction: column;
  }
  .content {
    min-height: 100%;
  }
  .editor-wrap {
    max-width: 960px;
    margin: 0 auto;
    padding: 16px;
  }
  .tip {
    font-size: 0.85rem;
    color: var(--color-text-tertiary);
    margin-bottom: 8px;
  }
  .editor-area {
    background: var(--color-background);
    border-radius: 12px;
  }
</style>
