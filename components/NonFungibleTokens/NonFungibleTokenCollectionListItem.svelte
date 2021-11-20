{#if withMedia}
  <ListItem header={$_('collection')} title="{nonFungibleTokenCollection.name}" link="/nonFungibleTokenCollections/{nonFungibleTokenCollection.id}/details">
    <img slot="media" class="message-avatar" src={BCH.cdn.getImage(nonFungibleTokenCollection.imageAvatar)} width="40" alt="" />
  </ListItem>
{:else}
  <ListItem header={$_('collection')} title="{nonFungibleTokenCollection.name}" link="/nonFungibleTokenCollections/{nonFungibleTokenCollection.id}/details"/>
{/if}

<style></style>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { ListItem } from 'framework7-svelte';

  export let BCH;
  export let nonFungibleTokenCollectionId: string;
  export let withMedia: boolean = false;
  let nonFungibleTokenCollection = BCH.hub.nonFungibleTokenCollections.find(nonFungibleTokenCollectionId);
</script>