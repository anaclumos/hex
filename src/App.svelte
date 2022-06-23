<script>
  import HexPicker from './lib/hex.svelte'
</script>

<main>
  <h1>Random Hex Generator</h1>
  <HexPicker />
</main>

<style>
  @import url('https://cdn.jsdelivr.net/gh/orioncactus/pretendard/dist/web/static/pretendard.css');
  :root {
    font-family: ui-sans-serif, -apple-system, BlinkMacSystemFont, 'Apple SD Gothic Neo', Pretendard, system-ui,
      -system-ui, sans-serif, 'Apple Color Emoji';
  }
  main {
    text-align: center;
    padding: 1em;
    margin: 5rem auto;
  }
  :global(body) {
    background-color: #000;
    color: #bfc2c7;
  }

  h1 {
    font-size: 4rem;
    font-weight: 400;
    line-height: 1.1;
    margin: 2rem auto;
    max-width: 14rem;
  }

  @media (min-width: 480px) {
    h1 {
      max-width: none;
    }

    p {
      max-width: none;
    }
  }
</style>
