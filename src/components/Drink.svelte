<script>
  export let drink;
  export let strDrinkThumb;
  export let strDrink;
  export let strAlcoholic;
  export let strInstructions;



</script>


<div class="flex w-1/4 flex-col items-center bg-slate-300 p-7 border border-indigo-200 border-2 rounded-xl hover:bg-slate-600 hover:text-white">

  <img src={strDrinkThumb} class="w-1/4 " alt="">
  <p class="p-3 font-bold text-2xl"> {strDrink}</p>
  <div class="flex flex-col items-center">
    {#if strAlcoholic==="Alcoholic"}
      <p class="p-2 font-sans font-semibold">With alcohol</p>
    {:else}
      <p class="p-2 font-sans font-semibold">Virgin Cocktail</p>
    {/if}
    <p class="w-1/2 p-2 font-light">{strInstructions}</p>
  </div>
</div>