<Block>
  {@html text}

  {#if !more}
    <Link onClick={() => setDescriptionVisible()}>{$_('more')}</Link>
  {/if}
</Block>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { Block, Link } from 'framework7-svelte';

  export let description: string;
  let more = false;
  let text = getDescription();

  function setDescriptionVisible() {
    more = true;
    text = getDescription();
  }

  function getDescription() {
    return more ? description : `${description.substring(0, 115)}...`;
  }
</script>