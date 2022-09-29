<script>
  import Door from "./Door.svelte";
  let doors = Array.from({ length: 24 }, (_, i) => {
    return {
      number: i + 1,
      content: "https://static.wikia.nocookie.net/lego/images/8/8d/MS8_Santa.jpg"
    };
  });
</script>

<style>
  main {
    font-family: sans-serif;
    text-align: center;
  }
  .container {
    display: grid;
    grid-template-columns: 200px 200px 200px 200px 200px 200px;
    grid-template-rows: auto;
    column-gap: 10pt;
    row-gap: 10pt;
    justify-content: center;
  }

  @media only screen and (max-width: 1090px) {
    .container {
      grid-template-columns: 200px 200px 200px 200px 200px;
    }
  }

  @media only screen and (max-width: 880px) {
    .container {
      grid-template-columns: 200px 200px 200px 200px;
    }
  }
  @media only screen and (max-width: 670px) {
    .container {
      grid-template-columns: 200px 200px 200px;
    }
  }
  @media only screen and (max-width: 460px) {
    .container {
      grid-template-columns: 200px 200px;
    }
  }
  @media only screen and (max-width: 250px) {
    .container {
      grid-template-columns: 200px;
    }
  }
</style>

<main>
	<h1>Simple AdvCal</h1>
  <div class='container'>
    {#each doors as door}
    <Door suprise={door.content}>{door.number}</Door>
    {/each}
  </div>
</main>