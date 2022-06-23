<script lang="ts">
  let color = 'Ready'
  const availableHex = '0123456789ABCDEF'
  const hexLength = 6
  const getRandomHex = () => {
    let hex = ''
    for (let i = 0; i < hexLength; i++) {
      hex += availableHex[Math.floor(Math.random() * availableHex.length)]
    }
    color = hex
    const elements: HTMLCollectionOf<HTMLElement> = document.getElementsByClassName(
      'color'
    ) as HTMLCollectionOf<HTMLElement>
    for (let i = 0; i < elements.length; i++) {
      elements[i].style.backgroundColor = '#' + hex
      elements[i].style.borderColor = '#' + hex
      if (Math.abs(parseInt(hex, 16) - 0xffffff) < Math.abs(parseInt(hex, 16) - 0x000000)) {
        elements[i].style.color = 'white'
      } else {
        elements[i].style.color = 'black'
      }
    }
    // copy to clipboard
    // create textarea
    const textarea = document.createElement('textarea')
    textarea.value = hex
    document.body.appendChild(textarea)
    textarea.select()
    navigator.clipboard.writeText(textarea.value)
    document.body.removeChild(textarea)
  }
</script>

<button on:click={getRandomHex} class="color" id="copy">
  {color}
</button>

<style>
  button {
    font-family: inherit;
    font-size: inherit;
    padding: 1em 2em;
    background-color: rgba(255, 62, 0, 0.1);
    border-radius: 2em;
    border: 2px solid rgba(255, 62, 0, 0);
    outline: none;
    width: 200px;
    font-variant-numeric: tabular-nums;
    cursor: pointer;
  }
</style>
