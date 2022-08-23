<script lang="ts">
  import { slide } from "svelte/transition";

  export let cocktailMenu;
  export let beerMenu;
  export let catagories;
</script>

<div class="MenuContainer">
  <div>
    <h2 class="CatagoryTitleText"><b><u>{catagories[1]}</b></h2>
    <div class="CatagoryContainer">
      {#each cocktailMenu as cocktailItem}
        <div class="CocktailItemContainer" transition:slide>
          <h3 class="ItemName"><b>{cocktailItem.cocktailName.toUpperCase()}</b></h3>
          <h3 class="ItemPrice">{cocktailItem.cocktailPrice}</h3>
        </div>
        <p class="ItemDescripion">{cocktailItem.cocktailDescription}</p>
      {/each}
    </div>
  </div>

  <div>
    <h2 class="CatagoryTitleText"><b><u>{catagories[0]}<u></b></h2>
    <div class="CatagoryContainer">
        {#each beerMenu as beerItem}
          <div class="BeerItemContainer" transition:slide>
            <h3 class="ItemName"><b>{beerItem.beerName.toUpperCase()}</b></h3>
            <h3 class="ItemPrice">{beerItem.beerPrice}</h3>
          </div>
          <div class="ItemTypeContainer">
            <p class="ItemType">{beerItem.beerType}</p>
          </div>
        {/each}
    </div>
  </div>
</div>

<style>
  .MenuContainer {
    max-height: 32rem;
    overflow-x: hidden;
  } 
  .CatagoryTitleText {
    text-align: left;
  }
  .CatagoryContainer {
    display: flex;
    flex-direction: column;
  }
  .CocktailItemContainer {
    display: flex;
    float: right;
  }
  .BeerItemContainer {
    display: flex;
    float: right;
    margin-top: -1rem;
  }
  .ItemName {
    float: left;
    text-align: left;
  }
  .ItemPrice {
    float: right;
    text-align: right;
  }
  .ItemDescripion {
    margin-top: -1rem;
  }
  .ItemTypeContainer {
    display: flex;
    align-items: center;
  }
  .ItemType {
    float: left;
    text-align: left;
    margin-top: -1rem;
    padding-right: 1rem;
    letter-spacing: 1.3px
  }
</style>
