# svelte-breakpoint-badge

A lightweight Svelte component that displays the current Tailwind CSS breakpoint during development. Perfect for responsive design debugging!

![Demo](svelte-breakpoint-badge-2.gif)

## Installation
```bash
npm install svelte-breakpoint-badge
```

## Usage

### SvelteKit
```svelte
<script>
  import { SvelteBreakpointBadge } from 'svelte-breakpoint-badge';
  import { dev } from '$app/environment';
</script>

<SvelteBreakpointBadge {dev} />
```

### Other Svelte Projects
```svelte
<script>
  import { SvelteBreakpointBadge } from 'svelte-breakpoint-badge';
</script>

<SvelteBreakpointBadge dev={import.meta.env.DEV} />
```

### Manual Control

You can also manually control when the badge is shown:
```svelte
<SvelteBreakpointBadge dev={true} />
```

## Features

- 🎯 Shows current Tailwind breakpoint (default, sm, md, lg, xl, 2xl, 3xl, 4xl)
- 🎨 Color-coded badges for easy identification
- 📱 Automatically hides/shows based on screen size
- 🚀 Zero runtime overhead in production (when `dev={false}`)
- 🪶 Lightweight with no dependencies

## Props

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `dev` | `boolean` | `false` | Whether to display the badge |

## Tailwind Configuration

This component uses standard Tailwind utility classes. Make sure your Tailwind configuration includes the breakpoints you want to use.

## How It Works

The component displays different colored badges at different breakpoints:
- **Red** (default): < 640px
- **Blue** (sm): 640px - 767px
- **Purple** (md): 768px - 1023px
- **Green** (lg): 1024px - 1279px
- **Orange** (xl): 1280px - 1535px
- **Yellow** (2xl): 1536px - 1919px
- **Blue** (3xl): 1920px - 2559px
- **Red** (4xl): ≥ 2560px

## Placement Recommendation

Add it to your root layout so it appears on every page, or a specific page that you are currently working on:
```svelte
<!-- +layout.svelte -->
<script>
  import { SvelteBreakpointBadge } from 'svelte-breakpoint-badge';
  import { dev } from '$app/environment';
</script>

<SvelteBreakpointBadge {dev} />

<slot />
```

## License

MIT

## Author

firdausai

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
