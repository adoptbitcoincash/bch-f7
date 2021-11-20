<Block>
  <BlockTitle>{$_('informations')}</BlockTitle>
  <List>
    <NftCollectionListItem nftCollectionId={nftCollection.id} BCH={BCH} />
    <ListItem header={$_('name')} title={nftVariation.name}></ListItem>

    {#each nftCollection.getEnumsIds() as enumId}
      {#if nftVariation.hasAnyTagsIds(nftCollection.getEnumTagsIds(enumId)) !== false}
      <ListItem header="{$_(enumId)}" title="{getEnumValueLocale(enumId)}"></ListItem>
      {/if}
    {/each}
  </List>
</Block>

<style></style>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { BlockTitle, List, ListItem, Block } from 'framework7-svelte';
  import type { NftVariation } from "@adoptbitcoincash/bch-orm";
  import NftCollectionListItem from './NftCollectionListItem.svelte';

  export let BCH;
  export let nftVariation : NftVariation;
  let nftCollection = nftVariation.collection;

  function getEnumValueLocale(enumId: string) {
      let tagId = nftVariation.hasAnyTagsIds(nftCollection.getEnumTagsIds(enumId));
      if(!tagId)
        return "";

      return $_(tagId);
  }
</script>