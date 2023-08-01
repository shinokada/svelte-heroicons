# Svelte Heros

<div class="flex gap-2 my-8">
<a href="https://github.com/sponsors/shinokada" target="_blank"><img src="https://img.shields.io/static/v1?label=Sponsor&message=%E2%9D%A4&logo=GitHub&color=%23fe8e86" alt="sponsor" height="25" style="height: 25px !important;"></a>
<a href="https://www.npmjs.com/package/svelte-heros" rel="nofollow" target="_blank"><img src="https://img.shields.io/npm/v/svelte-heros" alt="npm" height="25" style="height: 25px !important;"></a>
<a href="https://twitter.com/shinokada" rel="nofollow" target="_blank"><img src="https://img.shields.io/badge/created%20by-@shinokada-4BBAAB.svg" alt="Created by Shin Okada" height="25" style="height: 25px !important;"></a>
<a href="http://www.apache.org/licenses/" rel="nofollow" target="_blank"><img src="https://img.shields.io/github/license/shinokada/svelte-heros" alt="License" height="25" style="height: 25px !important;"></a>
<a href="https://www.npmjs.com/package/svelte-heros" rel="nofollow" target="_blank"><img src="https://img.shields.io/npm/dw/svelte-heros.svg" alt="npm" height="25" style="height: 25px !important;"></a>
</div>

New version, [Svelte-Heros-v2](https://svelte-heros-v2.vercel.app) is out.

Hero Icons v1 for Svelte. You can select outline and solid icons using the variation props. Svlete-Heros support major CSS framework. You can add additional CSS using the `class` props.

Thank you for considering my open-source package. If you use it in a commercial project, please support me by sponsoring me on GitHub: https://github.com/sponsors/shinokada. Your support helps me maintain and improve this package for the benefit of the community.

## Repo

[GitHub Repo](https://github.com/shinokada/svelte-heros)

## Original source

[tailwindlabs/heroicons](https://github.com/tailwindlabs/heroicons)

## License

[Svelte-Heros License](https://github.com/shinokada/svelte-heros/blob/main/LICENSE)

[tailwindlabs/heroicons LICENSE](https://github.com/tailwindlabs/heroicons/blob/main/LICENSE)


## Installation

```sh
pnpm i svelte-heros@latest
```

## Usage

```html
<script>
  import { IconSolid, IconOutline } from 'svelte-heros';
</script>

<IconSolid name="academic-cap-solid" />
<IconOutline name="academic-cap-outline" />
```

## Props

- @prop name;
- @prop width = "24";
- @prop height = "24";
- @prop role = 'img';
- @prop color = 'currentColor'
- @prop ariaLabel='icon name'
- @prop strokeWidth = "1.5";

## IDE support

If you are using an LSP-compatible editor, such as VSCode, Atom, Sublime Text, or Neovim, hovering over a component name will display a documentation link, features, props, events, and an example.

## Size

Use the `width` and `height` props to change the size of icons.

```html
<IconOutline name="academic-cap-outline" width="100" height="100" />
```

If you are using Tailwind CSS, you can add a custom size using Tailwind CSS by including the desired classes in the class prop. For example:

```html
<IconOutline name="academic-cap-outline" class="shrink-0 h-20 w-20" />
```

## CSS HEX Colors

Use the `color` prop to change colors with HEX color code.

```html
<IconOutline name="academic-cap-outline" color="#c61515" />
```

## CSS frameworks suport

You can apply CSS framework color and other attributes directly to the icon component or its parent tag using the `class` prop.

Tailwind CSS example:

```html
<IconOutline name="academic-cap-outline" class="text-red-700 inline m-1" />
```

Bootstrap examples:

```html
<IconOutline name="academic-cap-outline" class="position-absolute top-0 px-1" />
```

## Dark mode

If you are using the dark mode on your website with Tailwind CSS, add your dark mode class to the `class` prop.

Let's use `dark` for the dark mode class as an example.

```html
<IconOutline name="academic-cap-outline"  class="text-blue-700 dark:text-red-500" />
```

## aria-label

All icons have aria-label. For example `academic-cap-outline` has `aria-label="academic cap outline"`.
Use `ariaLabel` prop to modify the `aria-label` value.

```html
<IconOutline name="academic-cap-outline" ariaLabel="red academic cap outline" color="#c61515"/>
```

## Unfocusable icon

If you want to make an icon unfocusable, add `tabindex="-1"`.

```html
<IconOutline name="academic-cap-outline"  tabindex="-1" />
```

## Events

All icons have the following events:

- on:click
- on:keydown
- on:keyup
- on:focus
- on:blur
- on:mouseenter
- on:mouseleave
- on:mouseover
- on:mouseout

## Passing down other attributes

You can pass other attibutes as well.

```html
<IconOutline name="academic-cap-outline"  tabindex="0" />
```

## Using svelte:component

```html
<svelte:component this="{Icon}" name="academic-cap-outline" />
```

## Using onMount

```html
<script>
  import { IconOutline } from 'svelte-heros';
  import { onMount } from 'svelte';
  const props = {
    name: 'academic-cap-outline',
    size: '50',
    color: '#ff0000'
  };
  onMount(() => {
    const icon = new Icon({ target: document.body, props });
  });
</script>
```


## Import all

Use `import { IconOutline, icons } from 'svelte-heros';`.

```html
<script>
  import { IconOutline, icons } from 'svelte-heros-v2';
  function filterIconsByKeyword(icons, keyword) {
    const filteredIcons = {};
    for (const key in icons) {
      if (key.includes(keyword)) {
        filteredIcons[key] = icons[key];
      }
    }
    return filteredIcons;
  }
  const outlineIcons = filterIconsByKeyword(icons, '-outline');
</script>

{#each Object.keys(outlineIcons) as name}
<div class="flex gap-4 items-center text-lg">
  <IconOutline name={name} class="shrink-0"/>
  {name}
</div>
{/each}
```

## Other icons

[Svelte-Icon-Sets](https://svelte-svg-icons.vercel.app/)