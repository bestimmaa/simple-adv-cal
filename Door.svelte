<script>
  let open = false;
  export let suprise;
  let doorImage =
    `url(${suprise})`;
  let backDoorColor = "#FF5555";
  $: cssVarStyles = `--door-image:${doorImage};--back-door-color:${backDoorColor}`;
</script>

<style>
  .backDoor {
    background-color: var(--back-door-color, lightgray);
    position: relative;
    width: 200px;
    height: 300px;

    margin: 0 auto;
    margin-top: 0px;

    background-image: var(--door-image, lightgray);
    background-repeat: no-repeat;
    background-size: cover;
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



<div style="{cssVarStyles}" class="backDoor">
	<div class="{open === true ? 'door doorOpen' : 'door'}" on:click="{() => open = !open}"><span class="number"><slot></slot></span></div>
</div>