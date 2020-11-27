<script lang="ts">
  export let soundSrc: string;
  export let soundName: string;
  export let triggerKey: string;
  let audio: HTMLAudioElement;

  function playSound() {
    if(!audio.paused) {
      audio.currentTime = 0;
    }
    audio.play();
  }
  
  function handleKeydown(e) {
    console.log(e.key);
    if(e.key.toLowerCase() === triggerKey ) {
      playSound();
    }
  }
</script>

<style>
    .pad {
      width: 200px;
      height: 200px;
      background: rgba(0,0,0,0.5);
      display: inline-block;
      margin: 7.5px 5px;
      box-shadow: 0 4px 0 #1e1e1e, 0px 0px 10px 1px rgba(0,0,0,0.5);
      border: 1px solid #1e1e1e;
      border-radius: 3px;
    }
</style>

<svelte:window on:keydown={handleKeydown} />
<button class="pad" on:click={playSound}>{ soundName }</button>
<audio bind:this={audio} src={soundSrc}>
  <track kind="captions" />
</audio>