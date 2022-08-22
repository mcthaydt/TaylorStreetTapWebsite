<script lang="ts">
export let cocktailOfTheWeek : string 
</script>

<div style="display: flex; align-items: center;">
  <a style="padding-right: 2rem;" href="https://www.facebook.com/taylorstreettap" class="links-section-item">FACEBOOK</a>
  <a style="padding-right: 2rem;" href="https://www.yelp.com/biz/taylor-street-tap-chicago" class="links-section-item">YELP</a>
  <p style="text-align: right; margin-left: auto;"><b>COCKTAIL OF THE WEEK: </b>{cocktailOfTheWeek}</p>
</div>

<style>
  a {
    font-size: 0.8rem;
    font-weight: bold;
    color: rgba(248, 248, 248, 0.85);
  }
</style>
