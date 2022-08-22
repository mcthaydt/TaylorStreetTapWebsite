<script lang="ts">
  import { slide } from "svelte/transition";
  export let cocktailMenu;
  export let beerMenu;
  export let catagories;
</script>

        <div style="max-height: 32rem; overflow-x: hidden">
          <div>
            <h2 style="text-align: left;"><b><u>{catagories[1]}</b></h2>
            <div style="display: flex; flex-direction:column;">
              {#each cocktailMenu as cocktailItem}
                <div style="display: flex; float: right;" transition:slide>
                  <h3 style="float: left;"><b>{cocktailItem.cocktailName.toUpperCase()}</b></h3>
                  <h3 style="float: right">{cocktailItem.cocktailPrice}</h3>
                </div>
                <p style="margin-top: -5px;">{cocktailItem.cocktailDescription}</p>
                {#if cocktailItem.Seasonal == true}
                  <p style="float: right; text-align: left; margin-top: -5px; letter-spacing: 1.3px; color: orange">SEASONAL</p>
                {/if}
              {/each}
            </div>
          </div>

          <div>
            <h2 style="text-align: left;"><b><u>{catagories[0]}<u></b></h2>
            <div style="display: flex; flex-direction:column;">
                {#each beerMenu as beerItem}
                  <div style="display: flex; float: right; margin-top: -5px;" transition:slide>
                    <h3 style="float: left; text-align: left;"><b>{beerItem.beerName.toUpperCase()}</b></h3>
                    <h3 style="float: right; text-align: right;">{beerItem.beerPrice}</h3>
                  </div>
                  <div style="display: flex; align-items: center;">
                    <p style="float: left; text-align: left; margin-top: -5px; padding-right: 1rem; letter-spacing: 1.3px">{beerItem.beerType}</p>
                  </div>
                {/each}
            </div>
          </div>
        </div>
