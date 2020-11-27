<script lang='ts'>
  import Pad from '../Pad/Pad.svelte';

  interface Sound {
    trigger: string,
    name: string,
    source: string
  }

  const soundList: Sound[] = [ 
                      { trigger: 'Q', name: 'Clap', source: 'Clap1.wav' },
                      { trigger: 'W', name: 'Hi-Hat 1', source: 'Hats2.wav' },
                      { trigger: 'E', name: 'Hi-Hat 2', source: 'HH2.wav' },
                      { trigger: 'A', name: 'Kick', source: 'Kik12.wav' },
                      { trigger: 'S', name: 'Open-Hat', source: 'OH21.wav' },
                      { trigger: 'D', name: 'Snare', source: 'Snare12.wav' }
                    ];
</script>

<style>
  .container {
    display: grid;
    grid-template-columns: 33% 33% 33%;
    grid-template-rows: 50% 50%; 
    column-gap: 10px;
    row-gap: 15px;
    justify-items: center;
  }
</style>

<div class="container">
  { #each soundList as sound }
    <Pad soundName={sound.name} soundSrc={`samples/kit-1/${sound.source}`} triggerKey={sound.trigger} />
  { /each }
</div>