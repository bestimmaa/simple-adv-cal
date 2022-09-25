<style>
  .backDoor {
    background-color: #333;
    position: relative;
    width: 200px;
    height: 300px;

    margin: 0 auto;
    margin-top: 0px;
  }

  .door {
    background-color: green;
    position: absolute;
    top: 0px;
    left: 0px;
    width: 200px;
    height: 300px;

    transform-origin: left;
    /*Speed of the Door animation*/
    transition: all 0.5s ease-in-out;
  }

  .doorOpen {
    /*prespectiv creates the door open effect*/
    transform: perspective(1200px) translateZ(0px) translateX(0px) translateY(0px)
      rotateY(-105deg);
  }

  .number {
    font-size: 50pt;
  }
</style>

<script>
	let open = false;
	export let suprise;
</script>

<div class="backDoor">
  {suprise}
	<div class="{open === true ? 'door doorOpen' : 'door'}" on:click="{() => open = !open}"><span class="number"><slot></slot></span></div>
</div>