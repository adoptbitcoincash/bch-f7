<Block>
  <BlockTitle>{$_('informations')}</BlockTitle>
  <List>
    <NonFungibleTokenCollectionListItem nonFungibleTokenCollectionId={nonFungibleTokenCollection.id} DB={DB} />
    <ListItem header={$_('name')} title={nonFungibleTokenVariation.name}></ListItem>

    {#each nonFungibleTokenCollection.getEnumsIds() as enumId}
      {#if nonFungibleTokenVariation.hasAnyTagsIds(nonFungibleTokenCollection.getEnumTagsIds(enumId)) !== false}
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
  export let nonFungibleTokenVariation : NonFungibleTokenVariation;
  let nonFungibleTokenCollection = nonFungibleTokenVariation.collection;

  function getEnumValueLocale(enumId: string) {
      let tagId = nonFungibleTokenVariation.hasAnyTagsIds(nonFungibleTokenCollection.getEnumTagsIds(enumId));
      if(!tagId)
        return "";

      return $_(tagId);
  }
</script>