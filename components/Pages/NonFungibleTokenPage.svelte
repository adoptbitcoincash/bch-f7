<Page name="account">
  <Navbar backLink="Back">
    <NavTitle sliding>{nonFungibleTokenVariation.name}</NavTitle>
    <NavRight>
      <Link popoverOpen=".popover-menu"><Icon f7="ellipsis_circle" color="black" /></Link>
    </NavRight>
  </Navbar>

  <div style="margin:15px;">
    <Row  style="height: 150px">
      <Col width="33">
        <img src={BCH.cdn.getImage(nonFungibleTokenVariation.image)} alt="" class="visual"/>
      </Col>
      <Col width="66">
        <div class="section">
          <div class="header">
            <div class="title">{nonFungibleTokenVariation.name}</div>
          </div>
          <div class="main">
            <div class="footer">
              <div class="buy">
                <div class="buttons-list">
                </div>
              </div>
            </div>
            <div class="mint">Mint 56/100</div>
          </div>
        </div>
      </Col>
    </Row>
  </div>

  <div>Show signatures</div>
  <div>Show additional datafeeds</div>
  <div>Show identified owners</div>
  <div>Add to wish list</div>
  <div>Add to watch list</div>
</Page>

<style>
  .visual {max-height: 150px;}

  .section { display: flex; flex-flow: column; height: 150px; }
  .header { }
  .main { flex: 2; overflow: auto; }
  .footer { float:right; height:120px; right:20px; display:flex; position:absolute; align-items:flex-end;}

  .title {font-size: 120%; font-weight:bold;}
  .highlight {margin-top: 10px; font-size: 110%;}
  .subhighlight {font-size: 100%;}
  .buy {display: flex; justify-content: flex-end;}
</style>

<script lang="ts">
  import { Page, Navbar, NavTitle, NavRight, Link, Icon, Row, Col, Button } from 'framework7-svelte';
  import type { Accounts, NonFungibleToken } from "@adoptbitcoincash/bch-orm";

  export let BCH;
  export let accounts : Accounts;
  export let nonFungibleToken : NonFungibleToken;

  let nonFungibleTokenVariation = nonFungibleToken.variation;
</script>