<script lang="ts">
    export let value: any;
    export let width: string = 'w-full';

    export let ref: HTMLInputElement | null = null;

    export let iconCount = 0;

    const calculatePaddingRight = () => {
        // Calculate padding based on icon count and icon size (assuming h-5)
        const iconSize = 1.25; // h-5 and w-5 are 1.25rem
        const padding = iconCount * iconSize;
        return `padding-right: ${padding + 0.5 /** px-2 */}rem;`;
    };
</script>

<div class="relative {width}">
    <input
        class="input w-full h-10 pl-2"
        style={calculatePaddingRight()}
        {...$$restProps}
        bind:value
        bind:this={ref}
        on:keydown
        on:keypress
        on:keyup
    />

    <div class="absolute inset-y-0 right-0 flex items-center px-2">
        <slot />
    </div>
</div>
