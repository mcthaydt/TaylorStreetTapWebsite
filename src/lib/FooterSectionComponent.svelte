<script lang="ts">
  export let cocktailOfTheWeek : string 
</script>

<div class="container"> 
  <a href="https://www.facebook.com/taylorstreettap" class="links-section-item">FACEBOOK</a>
  <a href="https://www.yelp.com/biz/taylor-street-tap-chicago" class="links-section-item">YELP</a>
  <p><b>COCKTAIL OF THE WEEK: </b>{cocktailOfTheWeek}</p>
</div>

<style>
  .container {
    display: flex;
    align-items: center;
  }
  a {
    font-size: 0.8rem;
    font-weight: bold;
    color: rgba(248, 248, 248, 0.85);
    padding-right: 2rem;
  }
  p {
    text-align: right;
    margin-left: auto;
  }
</style>
