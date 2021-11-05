<div class={`block-title block-title-enhanced${ noHairline ? ' no-hairline' : '' }`} style="margin-top:0;">
  <span>{title}</span>
  <slot/>
</div>

<script lang="ts">
  import { } from 'framework7-svelte';
  import './BlockTitleEnhanced.less';

  export let title: string;
  export let noHairline = false;
</script>