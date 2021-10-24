<Block>
  <BlockTitle>{$_('informations')}</BlockTitle>
  <List>
    <NonFungibleTokenCollectionListItem nonFungibleTokenCollectionId={collection.id} DB={DB} />
    <ListItem header={$_('name')} title={variation.name}></ListItem>

    {#each collection.getEnumsIds() as enumId}
      {#if variation.hasAnyTagsIds(collection.getEnumTagsIds(enumId)) !== false}
      <ListItem header="{$_(enumId)}" title="{getEnumValueLocale(enumId)}"></ListItem>
      {/if}
    {/each}
  </List>
</Block>

<style></style>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { BlockTitle, List, ListItem, Block } from 'framework7-svelte';
  import type { NonFungibleTokenVariation } from "@adoptbitcoincash/bch-orm";
  import NonFungibleTokenCollectionListItem from './NonFungibleTokenCollectionListItem.svelte';

  export let DB;
  export let variation : NonFungibleTokenVariation;
  let collection = variation.collection;

  function getEnumValueLocale(enumId: string) {
      let tagId = variation.hasAnyTagsIds(collection.getEnumTagsIds(enumId));
      if(!tagId)
        return "";

      return $_(tagId);
  }
</script>