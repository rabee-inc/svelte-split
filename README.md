# svelte-split

[![npm version](https://badge.fury.io/js/svelte-split.svg)](https://badge.fury.io/js/svelte-split)

svelte-split is ...

## Demo

- Live Demo: https://svelte-split.onrender.com
- REPL: https://svelte.dev/repl/cc5bb5705d07470993183e58ff62f508?version=3.47.0

## Install

```bash
npm install svelte-split --save
```

## Usage

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/phi-jp/meltline@v0.1.13/meltline.css">

<script>
  import Split from "svelte-split";
</script>

<Split class='f s-full' storageKey='demo' defaultSizes='{[30, 40, 30]}'>
	<div class='bg-red text-white f fh'>
		<div class='fs32 bold'>
			red
		</div>
	</div>
	<div class='bg-green text-white f fh'>
		<div class='fs32 bold'>
			green
		</div>
	</div>
	<div class='bg-blue text-white f fh'>
		<div class='fs32 bold'>
			blue
		</div>
	</div>
</Split>
```

## Development

```
$ npm run dev
```

## Release

```
$ npm run release
```

## License

MIT
