<script lang='ts'>
  import Pad from '../Pad/Pad.svelte';

  interface Sound {
    trigger: string,
    source: string
  }

  const soundList: Sound[] = [ 
                      { trigger: 'q', source: 'Clap1.wav' },
                      { trigger: 'w', source: 'Hats2.wav' },
                      { trigger: 'e', source: 'HH2.wav' },
                      { trigger: 'r', source: 'Kik12.wav' },
                      { trigger: 't', source: 'OH21.wav' },
                      { trigger: 'y', source: 'Snare12.wav' }
                    ];
</script>

<style>
  .container {
    display: grid;
    grid-template-columns: 33% 33% 33%;
    grid-template-rows: 50% 50%; 
    column-gap: 10px;
    row-gap: 15px;
  }
</style>

<div class="container">
  { #each soundList as sound }
    <Pad soundName={sound.source} soundSrc={`samples/kit-1/${sound.source}`} triggerKey={sound.trigger} />
  { /each }
</div>