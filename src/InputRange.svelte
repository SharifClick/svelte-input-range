<script>
  export let min =  0;
  export let max =  100;
  export let value =  50;
  export let classes = '';
  let computedStyle = '';

  $: {
      let range = max - min;
      let position = ((value - min) / range) * 100;
      let positionOffset = Math.round(position * 0.40);
      computedStyle = `left:calc(${position}% - ${positionOffset}px`;
        
  }
  
</script>

<style>
  .range-control {
    position: relative;
  }

  .range-control > input[type="range"] {
    -webkit-appearance: none;
    height: 100%;
    width: 100%;
    box-shadow: none;
    padding: 0;
  }

  .range-control > input[type="range"]::-webkit-slider-runnable-track {
    background: lightgrey;
    height: 5px;
    border-radius: 10px;
  }

  .range-control > input[type="range"]::-moz-range-track {
    background: lightgrey;
    height: 5px;
  }

  .range-control > input[type="range"]::-webkit-slider-thumb {
    -webkit-appearance: none;
    width: 40px;
    height: 24px;
    background:transparent;
    margin-top: -10px;
    cursor: pointer;
  }

  .range-control > input[type="range"]::-moz-range-thumb {
    width: 2.857rem;
    height: 1.714rem;
    background:transparent;
    margin-top: -0.714rem;
    cursor: pointer;
  }
  .range-control > output {
    position: absolute;
    top: 2px;
    pointer-events: none;
    display: block;
    width: 2.857em;
    height: 1.714em;
    border: 1px solid #e2e2e2;
    background-color: teal;
    border-radius: 3px;
    color: white;
    font-size: 1rem;
    line-height: 1.571em;
    text-align: center;
  }
</style>
<div class="range-control">
  <input class="input {classes}" type="range" bind:value on:change {min} {max} />
  <output style="{computedStyle}">{value}</output>
</div>
