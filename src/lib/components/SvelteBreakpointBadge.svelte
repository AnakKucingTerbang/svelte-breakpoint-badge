<script lang="ts">
    import type { SvelteBreakpointBadgeProps } from "$lib/types.ts";

    const { dev = true }: SvelteBreakpointBadgeProps = $props();

    const breakpoints = [
        {
            name: "default",
            color: "red",
            hideClass: "sm:hidden",
            rounded: "rounded-md",
        },
        {
            name: "sm",
            color: "blue",
            hideClass: "hidden sm:block md:hidden",
            rounded: "rounded-md",
        },
        {
            name: "md",
            color: "purple",
            hideClass: "hidden md:block lg:hidden",
            rounded: "rounded-md",
        },
        {
            name: "lg",
            color: "green",
            hideClass: "hidden lg:block xl:hidden",
            rounded: "rounded-md",
        },
        {
            name: "xl",
            color: "orange",
            hideClass: "hidden xl:block 2xl:hidden",
            rounded: "rounded-md",
        },
        {
            name: "2xl",
            color: "yellow",
            hideClass: "hidden 2xl:block 3xl:hidden",
            rounded: "rounded-md",
        },
        {
            name: "3xl",
            color: "blue",
            hideClass: "hidden 3xl:block 4xl:hidden",
            rounded: "rounded-md",
        },
        {
            name: "4xl",
            color: "red",
            hideClass: "hidden 4xl:block 5xl:hidden",
            rounded: "rounded-md",
        },
    ];
</script>

{#if dev}
    <div class="w-fit">
        {#each breakpoints as bp}
            <div
                class="{bp.rounded} bg-{bp.color}-100 {bp.hideClass} border border-{bp.color}-300 px-2 text-xs text-{bp.color}-600"
            >
                {bp.name}
            </div>
        {/each}
    </div>
{/if}
