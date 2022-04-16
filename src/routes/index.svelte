<script>
  import Split from "svelte-split";
</script>

<template lang='pug'>
  Split.f.s-full(storageKey='project-editor', defaultSizes='{[30, 40, 30]}')
    div.bg-red.f.fh
      div.text-white.fs32.bold red
    div.bg-green.f.fh
      div.text-white.fs32.bold green
    div.bg-blue.f.fh
      div.text-white.fs32.bold blue
</template>
