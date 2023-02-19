## svelte-masonry-jothsa

This is a copy of Janzheng's project. I removed everything except the svelte masonry component, fixed a deprecated function call that broke the polyfill, and set typescript to ignore the component's script. The original project had a bunch of unneeded and deprecated stuff in the package, but if you want to use the masonry component, all you need is the Masonry.svelte file. A lot of this readme is copy pasted from the original.

## Usage

1. Copy Masonry.svelte into the directory of your choice. Please note that this file is not the same one found in the npm package. You can not use npm or yarn to install this file right now.

1. Add this to the script tags of the file where you want to use the component.

```
import Masonry from 'path/to/Masonry.svelte'
```

1. wrap the elements you want displayed in the masonry layout with \<Maysonry\> and \<\\Maysonry\> tags. You will probably most often be wrapping an entire each loop.

## Options

There are a few props you can pass to the Svelte component as options.

- `stretchFirst` (default: `false`): Setting `stretchFirst={true}` will stretch the first item across all items
- `gridGap` (default: `".5em;"`): This is a CSS value that sets the grid gap and padding for each element
- `colWidth` (default: `"minmax(Min(20em, 100%), 1fr);"`): This is a CSS value that sets the width of each column. The default allows for some leeway before the grids collapse.
- `items` (default: `[]`): Set this to your array of data if you have dynamic items and want masonry to recalculate when you add new items

## Development + Feedback

This project is pretty complete, and shouldn't need any major changes. If you see a problem or area for improvement please feel free to create an issue, feature request, or a pull request and I'll check it out. Additionally, check out [the CSS tricks article.](https://css-tricks.com/a-lightweight-masonry-solution/)

The original readme is below. Please note some information may be out of date.

# svelte-masonry

This is an implementation of Masonry based on this excellent article by Ana Tudor (@anatudor) on CSS Tricks: https://css-tricks.com/a-lightweight-masonry-solution. It's really great. It requires no external dependencies, is super light-weight, etc.

Basically I just wrapped Svelte around the Masonry code as a reusable component.

Here's a REPL demo: https://svelte.dev/repl/d5ff70834832498882d1570b9355561e?version=3.24.1

## Usage

Add svelte-masonry to your package:

```
npm install svelte-masonry
```

or use yarn

```
yarn add svelte-masonry
```

Then import the masonry component in your project. Honestly I'm not sure if this is the correct way, but this method works on my projects:

```
import Masonry from 'svelte-masonry/Masonry.svelte'
```

Now you can use it as component and wrap around your repeating `{#each}` blocks.

```

<Masonry>
  {#each data as o}
    <div>
    	Content: {o.content}
    </div>
  {/each}
</Masonry>

```

If you have any implementation questions, please hit me up on twitter @yawnxyz or create an issue.

## Manually Refreshing

Sometimes you might need to dynamically refresh the grid calculations. You can do this by binding `refreshLayout` like so: `bind:refreshLayout={refreshLayout}` and then calling that function when everything's finished loading. Here's an example: https://svelte.dev/repl/2c5a8e5ae579471ea22b3f5561268d11?version=3.24.1

## Options

There are a few props you can pass to the Svelte component as options.

- `stretchFirst` (default: `false`): Setting `stretchFirst={true}` will stretch the first item across all items
- `gridGap` (default: `".5em;"`): This is a CSS value that sets the grid gap and padding for each element
- `colWidth` (default: `"minmax(Min(20em, 100%), 1fr);"`): This is a CSS value that sets the width of each column. The default allows for some leeway before the grids collapse.
- `items` (default: `[]`): Set this to your array of data if you have dynamic items and want masonry to recalculate when you add new items

## Development + Feedback

You're welcome to create an issue, feature request, or a pull request and I'll take a look, but this won't be a very managed repo. Instead, please read the the CSS tricks articlecheck out the source code, or ask the author (@anatudor) directly.

## License

The code was lifted from Ana Tudor (@anatudor) from CSS tricks. They have a funny license page, so you should take a look (https://css-tricks.com/license/). Do whatever you'd like with this example!
