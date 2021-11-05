<BlockTitleEnhanced title={title}>
  <Link href={href}>{$_(label)} &gt;</Link>
</BlockTitleEnhanced>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { Link } from 'framework7-svelte';
  import BlockTitleEnhanced from './BlockTitleEnhanced.svelte';

  export let title: string;
  export let href: string;
  export let label: string = 'action.more';
</script>