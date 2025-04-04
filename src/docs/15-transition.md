---
title: Transition
description: Transition CSS Classes for Svelte
openGraph:
  type: website
  url: https://captaincodeman.github.io/svelte-headlessui/transition
  title: Tabs
  images:
    - url: /svelte-headlessui/transition.png
      width: 1332
      height: 756
twitter:
  card: summary_large_image
  site: captaincodeman
  title: Transition 🚀 Svelte-HeadlessUI
  description: Headless Transition for Svelte
  image: /svelte-headlessui/transition.png
---

# Transition

The Transition component lets you add enter/leave transitions to conditionally rendered elements, using CSS classes to control the actual transition styles in the different stages of the transition.

<iframe class="w-full h-[378px] rounded-xl border-none" src="./example/transition"></iframe>
<a href="./example/transition" target="_blank">
	Open in separate tab
</a>

NOTE: the transition element is published as a separate package `svelte-transition`

## Example

```svelte
<script lang="ts">
	import Transition from 'svelte-transition'

	interface Props {
		show?: boolean
	}

	let { show = $bindable(true) }: Props = $props()

	function resetIsShowing() {
		show = false
		setTimeout(() => (show = true), 500)
	}
</script>

<div class="h-32 w-32">
	<Transition
		{show}
		appear
		enter="duration-[400ms]"
		enterFrom="opacity-0 rotate-[-120deg] scale-50"
		enterTo="opacity-100 rotate-0 scale-100"
		leave="duration-200 transition ease-in-out"
		leaveFrom="opacity-100 rotate-0 scale-100"
		leaveTo="opacity-0 scale-95"
	>
		<div class="h-full w-full rounded-md bg-white shadow-lg"></div>
	</Transition>
</div>
<button
	onclick={resetIsShowing}
	disabled={!show}
	class="mt-8 flex transform items-center rounded-full bg-black/20 px-3 py-2 text-sm font-medium text-white transition hover:scale-105 hover:bg-black/30 focus:outline-hidden active:bg-black/40"
>
	<svg viewBox="0 0 20 20" fill="none" class="h-5 w-5 opacity-70">
		<path
			d="M14.9497 14.9498C12.2161 17.6835 7.78392 17.6835 5.05025 14.9498C2.31658 12.2162 2.31658 7.784 5.05025 5.05033C7.78392 2.31666 12.2161 2.31666 14.9497 5.05033C15.5333 5.63385 15.9922 6.29475 16.3266 7M16.9497 2L17 7H16.3266M12 7L16.3266 7"
			stroke="currentColor"
			stroke-width="1.5"
		/>
	</svg>

	<span class="ml-3">Click to transition</span>
</button>
```

## TailwindUI

If you're using TailwindUI the suggested transition classes are defined as HTML comments. Use the [conversion tool](https://captaincodeman.github.io/svelte-transition/) to convert the comments into the equivalent `<Transition />` element syntax.
