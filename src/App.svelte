<script lang="ts">

  import { each } from "svelte/internal";

  import Info from './lib/InfoSectionComponent.svelte';
  import Hero from './lib/HeroSectionComponent.svelte';
  import Title from './lib/TitleComponent.svelte';
  import DrinkMenuTitle from './lib/DrinkMenuTitleComponent.svelte';
  import DrinkMenu from './lib/DrinkMenuComponent.svelte';
  import Footer from './lib/FooterSectionComponent.svelte';

  let catagories: string[] = ["BEERS", "COCKTAILS"]
  let beerCatagories: string[] = ["TAP", "BOTTLE", "CAN"]

  let beerMenu = [
    // Tap
    {"beerName": "Guinness", "beerPrice" : 8, "beerType": beerCatagories[0]},
    {"beerName": "Hamms", "beerPrice" : 4, "beerType": beerCatagories[0]},
    {"beerName": "Anti Hero", "beerPrice" : 7, "beerType": beerCatagories[0]},
    {"beerName": "Modelo Negra", "beerPrice" : 7, "beerType": beerCatagories[0]},
    {"beerName": "Sierra Nevada", "beerPrice" : 7, "beerType": beerCatagories[0]},
    // Can
    {"beerName": "Modelo", "beerPrice" : 6, "beerType": beerCatagories[2]},
    {"beerName": "Old Style", "beerPrice" : 4, "beerType": beerCatagories[2]},
    {"beerName": "Hazy IPA", "beerPrice" : 6, "beerType": beerCatagories[2]},
    {"beerName": "Topop Chico Strawberry Guava", "beerPrice" : 7, "beerType": beerCatagories[2]},
    {"beerName": "White Claw", "beerPrice" : 7, "beerType": beerCatagories[2]},
    {"beerName": "Hacker Pschour", "beerPrice" : 7, "beerType": beerCatagories[2]},
    {"beerName": "Pilsner Urquell", "beerPrice" : 7, "beerType": beerCatagories[2]},
    {"beerName": "Paulanur Grapefruit Radler", "beerPrice" : 7, "beerType": beerCatagories[2]},
    // Bottle
    {"beerName": "Victoria", "beerPrice" : 6, "beerType": beerCatagories[1]},
    {"beerName": "Peroni", "beerPrice" : 6, "beerType": beerCatagories[1]},
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

  let cocktailOfTheWeek : string = "Mojito Run"; 

</script>

<main class="main-container">
    <div style="display: flex; align-content: center">
      
      <div class="left-side">
        <Hero />
        <Title /> 
        <Info />
      </div>

      <div class="right-side"> 
        <DrinkMenuTitle />
        <DrinkMenu cocktailMenu={cocktailMenu} beerMenu={beerMenu} catagories={catagories} />
      </div>

    </div>
    <Footer cocktailOfTheWeek={cocktailOfTheWeek} /> 
</main>

<style>
  .main-container {
    margin: 60px;
  }
  .left-side {
    float:left;
  }
  .right-side {
    float: right;
    margin-left: auto;
  }
</style>
