<script lang="ts">
    import { onMount } from 'svelte';
    import { Visibility, VisibilityOff } from '@steeze-ui/material-design-icons';
    import { Icon } from '@steeze-ui/svelte-icon';

    import { ActionableInput, ActionableInputIcon } from '$lib';

    export let value: any;
    export let width: string = 'w-full';

    let ref: HTMLInputElement;
    let visibility = false;

    onMount(() => {
        ref.type = 'password';
    });

    function toogleVisibility() {
        visibility = !visibility;

        ref.type = visibility ? 'text' : 'password';
    }
</script>

<ActionableInput iconCount={1} {width} {...$$restProps} bind:value bind:ref on:keydown on:keypress on:keyup>
    <ActionableInputIcon>
        <button on:click={toogleVisibility}>
            {#if visibility}
                <Icon src={VisibilityOff} />
            {:else}
                <Icon src={Visibility} />
            {/if}
        </button>
    </ActionableInputIcon>
</ActionableInput>
