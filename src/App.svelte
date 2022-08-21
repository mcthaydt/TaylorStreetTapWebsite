<script lang="ts">
import { each } from "svelte/internal";

  let catagories: string[] = ["BEERS", "COCKTAILS"]
  let beerCatagories: string[] = ["TAP", "BOTTLE", "CAN"]
  let cocktailOfTheWeek : string = "Mojito Run"
  
  let beerMenu = [
    // Tap
    {"beerName": "Guinness", "beerPrice" : 8, "beerType": beerCatagories[0]},
    {"beerName": "Hamms", "beerPrice" : 4, "beerType": beerCatagories[0]},
    {"beerName": "Anti Hero", "beerPrice" : 7, "beerType": beerCatagories[0]},
    {"beerName": "Modelo Negra", "beerPrice" : 7,"beerType": beerCatagories[0]},
    {"beerName": "Sierra Nevada", "beerPrice" : 7,"beerType": beerCatagories[0]},
    // Can
    {"beerName": "Modelo", "beerPrice" : 6,"beerType": beerCatagories[2]},
    {"beerName": "Old Style", "beerPrice" : 4,"beerType": beerCatagories[2]},
    {"beerName": "Hazy IPA", "beerPrice" : 6,"beerType": beerCatagories[2]},
    {"beerName": "Topop Chico Strawberry Guava", "beerPrice" : 7,"beerType": beerCatagories[2]},
    {"beerName": "White Claw", "beerPrice" : 7,"beerType": beerCatagories[2]},
    {"beerName": "Hacker Pschour", "beerPrice" : 7,"beerType": beerCatagories[2]},
    {"beerName": "Pilsner Urquell", "beerPrice" : 7,"beerType": beerCatagories[2]},
    {"beerName": "Paulanur Grapefruit Radler", "beerPrice" : 7,"beerType": beerCatagories[2]},
    // Bottle
    {"beerName": "Victoria", "beerPrice" : 6,"beerType": beerCatagories[1]},
    {"beerName": "Peroni", "beerPrice" : 6,"beerType": beerCatagories[1]},
    {"beerName": "Red Stripe", "beerPrice" : 6,"beerType": beerCatagories[1]},
    {"beerName": "Bohemia", "beerPrice" : 6,"beerType": beerCatagories[1]},
    {"beerName": "Miller High", "beerPrice" : 5,"beerType": beerCatagories[1]},
    {"beerName": "Miller High Life", "beerPrice" : 4,"beerType": beerCatagories[1]},
  ]

  let cocktailMenu = [
    {"cocktailName": "OLD FASHIONED", "cocktailPrice" : 11, "cocktailDescription": "BOURBON, DEMERA SYRUP, BITTERS"},
    {"cocktailName": "MANHATTAN", "cocktailPrice" : 11, "cocktailDescription": "WHISKEY, SWEET VERMOUTH, BITTERS"},
    {"cocktailName": "TOM COLLINS", "cocktailPrice" : 11, "cocktailDescription": "GIN, LEMON, SIMPLE SODA"},
    {"cocktailName": "PATSY'S CLASSIC", "cocktailPrice" : 13, "cocktailDescription": "SAPPHIRE GIN, DRY VERMOUTH, BLUE CHEESE OLIVES"},
    {"cocktailName": "VESPER", "cocktailPrice" : 13, "cocktailDescription": "GIN, VODKA, LILLET BLANC"},
    {"cocktailName": "GIBSON", "cocktailPrice" : 11, "cocktailDescription": "GIN / VODKA MARTINI W/ A COCKTAIL ONION"},
    {"cocktailName": "COSMOPOLITAN", "cocktailPrice" : 11, "cocktailDescription": "VODKA, TRIPLE SEC, CRANBERRY, LIME"},
    {"cocktailName": "DAQUIRI", "cocktailPrice" : 11, "cocktailDescription": "RUM, DEMERA SYRUP, LIME"},
    {"cocktailName": "MARGARITA10", "cocktailPrice" : 11, "cocktailDescription": "TEQUILIA, TRIPLE SEC, SIMPLE, LIME, SALT"},
    {"cocktailName": "WHISKEY SOUR", "cocktailPrice" : 11, "cocktailDescription": "BOURBON, LEMON. SIMPLE"},
    {"cocktailName": "SIDECAR", "cocktailPrice" : 13, "cocktailDescription": "COGNAC, SIMPLE, LEMON, BITTERS"},
    {"cocktailName": "MOSCOW MULE", "cocktailPrice" : 11, "cocktailDescription": "VODKA, LIME, GINGER BEER"},
    {"cocktailName": "PALOMA", "cocktailPrice" : 11, "cocktailDescription": "TEQUILIA, GRAPEFRUIT, LIME, SALT"},
  ]

</script>

<main class="main-container">
    <div style="display: flex; align-content: center">
      
      <div style="float:left;">
        <img src="src/assets/TST2.jpeg" alt="taylor_street_taps" style="object-fit: cover; width: 80%; height: 250px;">
        
        <h1 style="letter-spacing: 1.1rem; font-weight: 100;">TAYLOR STREET TAP</h1>
        <div>
          <h3><b>LOCATION</b></h3>
          <p> 1358 W Taylor, Chicago, IL 60607</p>
        </div>
        <div>
          <h3><b>PHONE NUMBER</b></h3>
          <p>(312) 455-8255</p>
        </div>
        <div>
          <h3><b>HOURS</b></h3>
          <p>Open Everyday from 3pm to 2am</p>
        </div>
      </div>

      <div style="float: right; margin-left: auto;">
        <h1 style="text-align: right; margin: auto; padding-bottom: 15px;">MENU</h1>

        <div style="max-height: 32rem; overflow-x: hidden">
          <div>
            <h2 style="text-align: left;"><b><u>{catagories[1]}</b></h2>
            <div style="display: flex; flex-direction:column;">
              {#each cocktailMenu as cocktailItem}
                <div style="display: flex; float: right; ">
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
                  <div style="display: flex; float: right; margin-top: -5px;">
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
      </div>
    </div>

    <div style="display: flex; align-items: center;">
      <a style="padding-right: 2rem;" href="https://www.facebook.com/taylorstreettap" class="links-section-item">FACEBOOK</a>
      <a style="padding-right: 2rem;" href="https://www.yelp.com/biz/taylor-street-tap-chicago" class="links-section-item">YELP</a>
      <p style="text-align: right; margin-left: auto;"><b>COCKTAIL OF THE WEEK: </b>{cocktailOfTheWeek}</p>
    </div>
</main>

<style>
  .main-container {
    margin: 60px;
  }
  h1 {
    font-size: 3rem;
    line-height: 3rem;
  }
  h2 {
    font-size: 1.1rem;
    padding-right: 0.3em;
  }
  h3 {
    font-size: 0.90rem;
    padding-right: 0.85em;
    font-weight: 500;
  }
  p {
    font-size: 0.8rem;
  }
  a {
    font-size: 0.8rem;
    font-weight: bold;
    color: rgba(248, 248, 248, 0.85);
  }
</style>
