<Page name="account">
  <Navbar backLink="Back">
    <NavTitle sliding>{nonFungibleTokenVariation.name}</NavTitle>
    <NavRight>
      <Link popoverOpen=".popover-menu"><Icon f7="ellipsis_circle" color="black" /></Link>
    </NavRight>
  </Navbar>

  <!--
  <Popover class="popover-menu">
    <List>
      <ListItem link="#" popoverClose popupOpen=".popup-move" title="Move"><Icon slot="media" f7="arrow_right_arrow_left" /></ListItem>
      <ListItem link="#" popoverClose popupOpen=".popup-send" title="Send"><Icon slot="media" f7="arrowtriangle_up_fill" /></ListItem>
      <ListItem divider/>
      <ListItem link="#" popoverClose popupOpen=".popup-more" title="More informations"><Icon slot="media" f7="text_badge_plus" /></ListItem>
    </List>
  </Popover>

  <PopupMove/>
  <PopupSend/>
  -->
</Page>

<script lang="ts">
  import { Page, Navbar, NavTitle, NavRight, Link, Icon } from 'framework7-svelte';
  import type { Account, NonFungibleToken } from "@adoptbitcoincash/bch-orm";
//  import PopupMove from '../components/PopupMove.svelte';
//  import PopupSend from '../components/PopupSend.svelte';

  export let DB;
  export let account : Account;
  export let nonFungibleToken : NonFungibleToken;

  let nonFungibleTokenVariation = nonFungibleToken.variation;
</script>