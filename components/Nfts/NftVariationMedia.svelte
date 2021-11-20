<div style="text-align:center; margin-top:15px; margin-bottom:10px;">
  <img src={BCH.cdn.getImage(nftVariation.image)} alt="" class="visual lazy" on:click={standaloneDark.open()}/>
</div>

<PhotoBrowser theme="dark" photos={photos} bind:this={standaloneDark} />

<style>
  .visual {max-height:300px;}
</style>

<script lang="ts">
  import { PhotoBrowser } from 'framework7-svelte';
  import type { NftVariation } from "@adoptbitcoincash/bch-orm";

  export let BCH;
  export let nftVariation : NftVariation;

  let standaloneDark;
  console.log(nftVariation)
  const photos = [BCH.cdn.getImage(nftVariation.image)];
</script>