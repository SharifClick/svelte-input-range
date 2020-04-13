<script>
  import { InputRange } from "../src/index.js"

  let binded_value = 0;

</script>

<style>
  .container{
    display: flex;
    flex-grow: 1;
    height: 100%;
    width: 100%;
    padding: 2rem;
  }

  .column {
    display: block;
    flex-basis: 0;
    flex-grow: 1;
    flex-shrink: 1;
    padding: 0.75rem;
  }

  .is-pmless{
    padding: 0;
    margin:0;
  }

  
</style>
<div class="container">
 <div class="column">
    <InputRange bind:value={binded_value}/>
 </div>
 <div class="column">
   <h1 class="is-pmless">{binded_value}</h1>
 </div>
</div>


