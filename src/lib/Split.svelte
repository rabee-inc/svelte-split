
   
<script context="module">
  const STORAGE_KEY = '_svelte-split-data';
  import { browser } from '$app/env';
  // svelte-ignore unused-export-let
  export let _data;
  // svelte-ignore unused-export-let
  export let _save = (sizes) => {
    let data_str = JSON.stringify(_data);
    localStorage.setItem(STORAGE_KEY, data_str);
  };
  let _load = () => {
    let data = localStorage.getItem(STORAGE_KEY);
    _data = data ? JSON.parse(data) : {};
  };
  if (browser) {
    _load();
  }
</script>

<script>
  import Split from 'split.js';
  import { onMount } from 'svelte';
  // root 用のクラス
  let className;
  export { className as class };
  // 保存, 復元するための値
  export let storageKey = '';
  // デフォルトのサイズ
  export let defaultSizes = null;
  // 方向
  export let direction = 'horizontal'; // or 'vertical'
  let root;
  onMount(() => {
    let sizes = _data[storageKey] || defaultSizes;
    Split(root.children, {
      sizes,
      gutterSize: 6,
      direction,
      onDragEnd: (sizes) => {
        // storageKey が指定されている場合は sizes を保存しておく
        if (storageKey) {
          _data[storageKey] = sizes;
          _save();
        }
      },
    });
  });
</script>

<template lang="pug">
  div.root(bind:this='{root}', class='{className}')
    slot
</template>