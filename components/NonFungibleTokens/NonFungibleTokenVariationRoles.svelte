<Block>
  <BlockTitle>{$_('roles')}</BlockTitle>
  <List>
    <IdentityListItem identityId={collection.identityId} DB={DB} header={$_('role.author')} />

    {#if variation.roles}
      {#each variation.roles as role}
        <IdentityListItem identityId={role.identityId} DB={DB} header={$_(`role.${role.role}`)} />
      {/each}
    {/if}
  </List>
</Block>

<style></style>

<script lang="ts">
  import { _ } from 'svelte-i18n';
  import { BlockTitle, List, Block } from 'framework7-svelte';
  import type { NonFungibleTokenVariation } from "@adoptbitcoincash/bch-orm";
  import IdentityListItem from '../Identities/IdentityListItem.svelte';

  export let DB;
  export let variation : NonFungibleTokenVariation;
  let collection = variation.collection;
</script>