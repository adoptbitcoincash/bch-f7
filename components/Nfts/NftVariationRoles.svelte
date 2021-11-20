<Block>
  <BlockTitle>{$_('roles')}</BlockTitle>
  <List>
    <IdentityListItem identityId={collection.identityId} BCH={BCH} header={$_('role.author')} />

    {#if nftVariation.roles}
      {#each nftVariation.roles as role}
        <IdentityListItem identityId={role.identityId} BCH={BCH} header={$_(`role.${role.role}`)} />
      {/each}
    {/if}
  </List>
</Block>

<style></style>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { BlockTitle, List, Block } from 'framework7-svelte';
  import type { NftVariation } from "@adoptbitcoincash/bch-orm";
  import IdentityListItem from '../Identities/IdentityListItem.svelte';

  export let BCH;
  export let nftVariation : NftVariation;
  let collection = nftVariation.collection;
</script>