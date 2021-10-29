<Page name="applications">
  <Navbar title="Applications" backLink="Back" />

  <List>
    {#each identities as identity}
    <ListItem title={identity.name} on:click={() => changeIdentity(identity)}>
    </ListItem>
    {/each}
  </List>
</Page>

<script lang="ts">
  import { Page, Navbar, List, ListItem } from 'framework7-svelte';

  export let setXprv;
  export let identities;

  function changeIdentity(identity: any) {
    setXprv(identity.xprv);
  }

</script>