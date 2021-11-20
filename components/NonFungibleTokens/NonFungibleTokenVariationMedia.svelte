<div style="text-align:center; margin-top:15px; margin-bottom:10px;">
  <img src={BCH.cdn.getImage(nonFungibleTokenVariation.image)} alt="" class="visual lazy" on:click={standaloneDark.open()}/>
</div>

<PhotoBrowser theme="dark" photos={photos} bind:this={standaloneDark} />

<style>
  .visual {max-height:300px;}
</style>

<script lang="ts">
  import { PhotoBrowser } from 'framework7-svelte';
  import type { NonFungibleTokenVariation } from "@adoptbitcoincash/bch-orm";

  export let BCH;
  export let nonFungibleTokenVariation : NonFungibleTokenVariation;

  let standaloneDark;
  console.log(nonFungibleTokenVariation)
  const photos = [BCH.cdn.getImage(nonFungibleTokenVariation.image)];
</script>